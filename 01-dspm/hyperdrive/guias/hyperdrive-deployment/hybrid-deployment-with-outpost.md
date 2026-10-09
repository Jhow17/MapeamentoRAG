---
title: "Hybrid deployment with Outpost - AWS"
slug: "hybrid-deployment-with-outpost"
status: "new"
updated: 2026-10-05T19:38:07Z
published: 2026-10-05T19:38:07Z
canonical: "helpcenter.securiti.ai/hybrid-deployment-with-outpost"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hybrid deployment with Outpost - AWS

> [!WARNING]
> Important
> 
> Hybrid deployment with Outpost involves creating and managing cloud resources in your AWS environment automatically through a template. Missing prerequisites or insufficient permissions can cause deployment failures or prevent Outposts from functioning as expected.

This page provides the complete deployment guide for Hybrid deployment with Outpost in your AWS cloud environment.

For the architecture Hybrid Outpost deploys in your AWS cloud, see the Securiti **Outpost AWS Architecture** diagram below.

![Diagram illustrating the architecture of Securiti Outpost on AWS with various components.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Securiti Outpost AWS Architecture.jpg)

## Prerequisites

Before deploying Hybrid Outpost, ensure that your environment meets the required infrastructure, permissions, and configuration prerequisites. Outpost runs within your cloud account and relies on specific AWS services and resources to operate correctly.

Review and complete all the prerequisites listed below before initiating the Outpost deployment to ensure a smooth installation and reliable scanning performance.

### AWS account and environment requirements

The table below describes the AWS environment requirements for the Hybrid Outpost deployment.

| **AWS requirement** | **Description** |
| --- | --- |
| Cloud account | You must provide a separate cloud account with complete permissions so that the deployment can scale the scanners easily. |
| Quotas for resources | You must check your service limits, especially for VPCs and NAT Gateways in the target AWS Region, to ensure the CloudFormation stack can provision the necessary network infrastructure to avoid deployment failures. |
| Deploying permissions | The deploying account must be an admin or have equal to an administrator’s rights: - Create all resources defined in the stack, such as VPC, EKS, S3, IAM Roles, and Lambda. - Access the nested CloudFormation templates stored in the Securiti S3 registry. - Access ECR to establish the image pull-through cache. |

### Required AWS services

Securiti deploys Hybrid Outpost using the cloud template to provision and configure complete infrastructure for it. For the list of all services it creates in your AWS environment, see the table below:

| AWS service | Use case |
| --- | --- |
| VPC | Provisions the network foundation, including public and private subnets, route tables, an Internet Gateway, and S3 VPC endpoint. |
| EKS | Provisions the Kubernetes cluster in Auto Mode with Karpenter-managed node pools for running Outpost workloads. |
| IAM | Provisions roles and policies for the cluster, pod identities, Lambda functions, and cross-account access required by Securiti. |
| ECR | Provisions a private repository and pull-through cache rule for storing and pulling Securiti container images. |
| S3 | Provisions two buckets for metadata and data storage, with bucket policies scoped to Securiti cross-account roles. |
| ElastiCache | Provisions a managed Redis replication group used by Outpost for caching and job coordination. |
| KMS | Provisions encryption keys for securing S3 bucket data and ElastiCache at rest. |
| Amazon Managed Prometheus (AMP) | Provisions a managed Prometheus workspace for collecting and storing Outpost metrics. |
| RDS | Provisions a PostgreSQL database instance for Outpost when enabled. Disabled by default. |
| Secrets Manager | Provisions a secret to store deployment configuration and credentials used by Securiti pods. |
| Lambda | Provisions two functions: - It deploys the Securiti Helm chart onto the EKS cluster. - It registers the Outpost deployment with the Securiti platform. |
| CloudWatch | Provisions log groups for Lambda execution logs and a dashboard for monitoring Outpost health and metrics. |
| NAT Gateway / NAT Instance | Provisions outbound internet access for private subnet workloads. Deploys either a managed NAT Gateway or an EC2-based NAT Instance based on your selection. |
| EC2 | Provisions security groups for EKS, Lambda, ElastiCache, and RDS to control inbound and outbound traffic. |
| CloudFormation | Provisions custom resources used to trigger Lambda-based deployment and registration steps during stack creation. |

### Permissions

The table below describes the AWS environment requirements for the Hybrid deployment with Outpost.

| IAM Role | Key Permissions and Policies |
| --- | --- |
| EKS Cluster role `securiti-eks-cluster-role-{suffix}` | Managed policies: - `AmazonEKSClusterPolicy` - `AmazonEKSComputePolicy` - `AmazonEKSBlockStoragePolicy` - `AmazonEKSLoadBalancingPolicy` - `AmazonEKSNetworkingPolicy` Inline Actions (scoped to cluster-tagged resources): - `ec2:CreateFleet` - `ec2:RunInstances` - `ec2:CreateLaunchTemplate` - `ec2:CreateVolume` - `ec2:CreateSnapshot` - `ec2:CreateNetworkInterface` - `elasticloadbalancing:CreateLoadBalancer` - `elasticloadbalancing:CreateTargetGroup` - `shield:CreateProtection` - `shield:TagResource` |
| EKS Auto Mode Node role `securiti-eks-automode-node-role-{suffix}` | Managed policies: - `AmazonEKSWorkerNodeMinimalPolicy` - `AmazonEC2ContainerRegistryPullOnly` Inline Actions (ECR pull-through cache on `securiti-outpost*` repositories): - `ecr:BatchImportUpstreamImage` - `ecr:InitiateLayerUpload` - `ecr:PutImage` - `ecr:CreateRepository` - `ecr:SetRepositoryPolicy` |
| Observability Service Account role `securiti-observability-service-account-role-{suffix}` | Type: - Pod Identity-based Inline Actions (scoped to the AMP workspace): - `aps:RemoteWrite` - `aps:QueryMetrics` - `aps:GetSeries` - `aps:GetLabels` - `aps:GetMetricMetadata` |
| ECR Pull Through Cache role `securiti-ecr-pull-through-cache-role-{suffix}` | Inline Actions (scoped to `securiti-outpost*` repositories): - `ecr:BatchCheckLayerAvailability` - `ecr:GetDownloadUrlForLayer` - `ecr:BatchGetImage` - `ecr:DescribeRepositories` - `ecr:CreateRepository` - `ecr:InitiateLayerUpload` - `ecr:PutImage` |
| Application Pod role `securiti-application-pod-role-{suffix}` | Type: - Pod Identity-based Permissions: - S3: Read, write, and delete on metadata bucket - KMS: `kms:Decrypt` and `kms:GenerateDataKey` using Securiti KMS key - Secrets Manager: `secretsmanager:GetSecretValue` and `secretsmanager:DescribeSecret` for Outpost secrets - Secrets Manager: Full CRUD on connector secrets under `/securiti/outpost/{tenantId}/{outpostId}/connectors*` - AMP: Read and write access |
| Detector Pod role `securiti-detector-pod-role-{suffix}` | Type: - Pod Identity-based Permissions: - Inherits all Application Pod role permissions - S3: Read, write, and delete on data storage bucket - KMS: Access scoped to Securiti KMS key |
| Orchestrator Pod role `securiti-orchestrator-pod-role-{suffix}` | Type: - Pod Identity-based Permissions: - EKS: `eks:DescribeCluster` and `eks:ListClusters` on the cluster - Lambda: Full lifecycle management (`lambda:CreateFunction`, `lambda:UpdateFunctionCode`, `lambda:DeleteFunction`, `lambda:InvokeFunction`) scoped to `securiti-*` functions - IAM: `iam:PassRole` for `securiti-*` roles - S3: Read and write on metadata bucket - Secrets Manager: Read access for Outpost secrets - CloudWatch: Logs management for Lambda and EKS log groups - EC2: VPC network interface operations - ECR: Pull-through cache access on `securiti-outpost*` repositories |
| Controller Pod role `securiti-controller-pod-role-{suffix}` | Type: - Pod Identity-based Permissions: - Secrets Manager: `secretsmanager:GetSecretValue` and `secretsmanager:DescribeSecret` for Outpost secrets - Secrets Manager: Full CRUD on registration secrets under `/securiti/outpost/{tenantId}/{outpostId}/registration*` - KMS: `kms:Decrypt`, `kms:GenerateDataKey`, and `kms:Encrypt` using Securiti KMS key |
| Update Pod role `securiti-update-pod-role-{suffix}` | Type: - Pod Identity-based Permissions: - ECR: Pull-through cache access on `securiti-outpost*` repositories - ECR: Global `ecr:GetAuthorizationToken` access |
| Metadata Access role `securiti-metadata-access-role-{suffix}` | Type: - Cross-account trust Permissions: - S3: Read, write, and delete on metadata bucket - KMS: `kms:Decrypt` and `kms:GenerateDataKey` using Securiti KMS key |
| Application Lambda role `securiti-application-lambda-role-{suffix}` | Managed Policies: - `AWSLambdaBasicExecutionRole` - `AWSLambdaVPCAccessExecutionRole` Permissions: - S3: Read and write on metadata bucket - Secrets Manager: Read for Outpost secrets - Secrets Manager: Write for connector secrets - ECR: Read access on `securiti-outpost*` repositories - AMP: Read and write access |
| Downloader Lambda role `securiti-downloader-lambda-role-{suffix}` | Permissions: - Inherits all Application Lambda role permissions - S3: Read, write, and delete on data storage bucket - Secrets Manager: Read for registration and `deployment-info` secrets |
| Deployer Lambda role `securiti-deployer-lambda-role-{suffix}` | Managed Policies: - `AWSLambdaBasicExecutionRole` - `AWSLambdaVPCAccessExecutionRole` Permissions: - EKS: `eks:DescribeCluster`, `eks:AccessKubernetesApi`, `eks:CreateAddon`, `eks:UpdateAddon`, and `eks:DeleteAddon` on the cluster - EKS: Granted `cluster-admin` access via EKS Access Entry - ECR: Full pull-through cache access on `securiti-outpost*` repositories - Secrets Manager: Full CRUD on registration secrets - Secrets Manager: Read on `deployment-info` secrets - CloudWatch: Logs management for Lambda and EKS log groups |
| Subnet Validator role `securiti-subnet-validator-role-{suffix}` Only required for **Fully Manual (Bring your own IAM)** IAM Provisioning Strategy | Type: - Lambda execution role (created only when you deploy into existing network infrastructure) Managed Policies: - AWSLambdaBasicExecutionRole Permissions: - EC2: Read-only access using `ec2:DescribeSubnets`, `ec2:DescribeRouteTables`, and `ec2:DescribeVpcEndpoints` - These EC2 APIs do not support resource-level permissions, so the actions are granted on all resources |
| Monitoring Access role `securiti-monitoring-access-role-{suffix}` | Type: - Cross-account trust Permissions: - AMP: Read and write access scoped specifically to the AMP workspace |

## Installation of Hybrid Outpost

For installing Hybrid Outpost in your AWS account, see [Installation of Hybrid Outpost](/latest/docs/installation-in-securiti).

## Related

- [Advanced Settings of Hybrid deployment with Outpost - AWS](/advance-settings-of-hybrid-outpost-aws.md)
- [Managing Hybrid deployments with Outpost](/managing-securiti-outpost-deployments-1.md)
- [Upgrading hybrid deployment with Outpost](/upgrading-hybrid-deployment-with-outpost.md)
