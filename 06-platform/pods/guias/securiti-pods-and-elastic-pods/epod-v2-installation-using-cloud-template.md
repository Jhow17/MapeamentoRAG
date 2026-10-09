---
title: "EPod V2 installation using cloud template"
slug: "epod-v2-installation-using-cloud-template"
updated: 2026-07-20T21:08:22Z
published: 2026-07-20T21:30:01Z
canonical: "helpcenter.securiti.ai/epod-v2-installation-using-cloud-template"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# EPod V2 installation using cloud template

If you are setting up EPod V2 for the first time in your infrastructure and you also do not have already running cloud managed Kubernetes service, deploy EPod V2 using the cloud template. It provisions a new Kubernetes cluster service and the required infrastructure in your selected cloud account. With this deployment, Securiti provides you with a cloud template to upload and provision complete infrastructure without any manual effort. This document covers complete deployment guide for EPod V2 using cloud template.

## Configuring in Securiti

1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section, click **Settings > Deployment > Elastic Pods V2**.
3. Near the right top of the page, click **+ New Cluster** and choose **Quick Install**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ANR6O660.png)

**Elastic Pods V2** popup appears.
4. On the **Elastic Pods V2** popup, apply the following settings:

| Parameter | Description |
| --- | --- |
| Cloud Provider | From the dropdown menu, for the EPod V2 deployment select one of the following clouds: - AWS |
| Region | Select the region where you wish to provision the Kubernetes cluster and associated infrastructure. |
| Compute Pod Name | Enter a unique name for the EPod V2 compute pod. By default, this it generates a name based on your cloud provider and region selection. |
| Redis | Select whether you want to use **Internal Redis** or **External Redis**. Selecting **Internal Redis** deploys Redis inside the Kubernetes cluster through the Helm chart. Selecting **External Redis** provisions a managed Redis instance, such as AWS ElastiCache, outside the cluster. |
| Deployment method | It is pre-selected for the cloud template. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-R4MG27RF.png)
5. Once you complete the configurations, at the bottom of the same popup, click **Prepare Template**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4HAXRPG5.png)

It downloads the cloud template file in your local file storage.

This process downloads a prepared cloud template file for deploying EPods V2. After applying it in your cloud, it builds and configures all the services required for EPods V2.

## Configuring in AWS

### Provisioning services

It provisions the following services through the CloudFormation template:

| AWS service | Description |
| --- | --- |
| VPC | Provisions the network foundation, including subnets, route tables, and gateways. |
| EC2 | Provisions the NAT gateways, security groups, and the deployer instance used to run the installation. |
| EKS | Provisions the Kubernetes cluster and node group used to run EPod V2. |
| IAM | Provisions the roles and policies required by the cluster, nodes, and pods. |
| ElastiCache | Provisions a managed Redis instance when you select external Redis. |
| Systems Manager (SSM) | Provisions parameters used to securely pass configuration and secrets to the deployer instance. |
| CloudWatch | Provisions a log group used to capture deployment logs. |
| CloudFormation | Provisions wait conditions used to track deployment progress and signal completion. |

### Creating roles and permissions

With deployment, it creates the following roles and permissions:

| IAM role | Key permissions and policies |
| --- | --- |
| EKS cluster role `{ClusterName}-eks-cluster-role` | `AmazonEKSClusterPolicy, AmazonEKSVPCResourceController` |
| EKS node role `{ClusterName}-eks-node-role` | `AmazonEKSWorkerNodePolicy`, `AmazonEKS_CNI_Policy`, `AmazonEC2ContainerRegistryReadOnly`, `AmazonSSMManagedInstanceCore`, plus inline policy for `s3:GetObject`, `s3:ListBucket`, and CloudWatch Logs actions |
| Securiti Pod role {ClusterName}-securiti-pod-role | IRSA-based (federated via OIDC), scoped to `system:serviceaccount:default:priv-appliance-*`. Inline policy for `s3:GetObject`, `s3:PutObject`, `s3:ListBucket`, `s3:DeleteObject`, `secretsmanager:GetSecretValue`, `secretsmanager:DescribeSecret` |
| AWS Load Balancer Controller role `{ClusterName}-aws-load-balancer-controller` | IRSA-based, scoped to `system:serviceaccount:kube-system:aws-load-balancer-controller`. `ElasticLoadBalancingFullAccess`, plus inline policy for EC2 networking actions, ELB actions, ACM, WAF/WAFv2, Shield, and `iam:CreateServiceLinkedRole` |
| EBS CSI Driver role `{ClusterName}-ebs-csi-driver` | IRSA-based, scoped to `system:serviceaccount:kube-system:ebs-csi-controller-sa`. `service-role/AmazonEBSCSIDriverPolicy` |
| Deployer EC2 role `{ClusterName}-deployer-ec2-role` | `AmazonSSMManagedInstanceCore`, plus inline policy for `eks:DescribeCluster`, `eks:CreateAccessEntry`, `eks:AssociateAccessPolicy`, `eks:AccessKubernetesApi`, S3 read, Secrets Manager read/write, CloudWatch Logs, `cloudformation:SignalResource`, `ssm:GetParameter`, `sts:GetCallerIdentity` |

### Deploying EPod V2 in AWS

To deploy EPods V2 in AWS using template, proceed with the following steps:

1. Log into your AWS account using the account with administrative or equivalent permissions.
2. Using the services search bar, search **CloudFormation** service.
3. On the **CloudFormation** service page, choose **Create a new stack**.
4. On the **Create Stack** page, apply the following settings:

| Parameter | Details |
| --- | --- |
| Prepare template | Select **Choose an existing template** |
| Template source | Select **Upload a template file** |
| Upload a template file | Upload your template file that you downloaded in previous steps. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod-quick-install-guides-cluster-version-v1.28-en-image-vefbgz64.png)

It opens **Specify stack details** page and displays all the fields from the template file.
5. Once you upload the template file and reviewing the fields, click **Submit**.

It starts provisioning the services and configurations for EPod V2.

When you upload the template, it starts building the stack according to the CloudFormation template file. It also redirects you to the **Event** tab automatically after the deployment starts. You can see the deployment progress of entire infrastructure until it finishes.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OLCTIA8U.png)

Once it finishes the deployment, the EPod V2 is installed and running in your cloud.

To review the deployment logs and connect to the Kubernetes cluster, Securiti deploys an EC2 (Elastic Compute Cloud) instance in your cloud that works as controlling hub for EPod V2. To access the EC2 instance, proceed with the following steps:

1. In your AWS console, search for EC2 service and open it.
2. In the running instances, search for your EC2 instance with the **Compute Pod Name** value you provided during template creation on Securiti UI. The EC2 instance name is generated with the following combination:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KW741LWC.png)
  - **Compute Pod Name** value
  - “*epodv2-deployer*” suffix
3. Select this EC2 instance, and at the top right corner of the **Instance** table, click **Connect**.

It opens a connected SSH shell to this instance.
4. You can now connect to the Kubernetes cluster to review the running pods, or review the deployment logs using the following command:

```bash
cat /var/log/securiti-deployment.log
```

Once EPod V2 is fully deployed, its gets active on the **Elastic Pods V2** page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-O795UYNB.png)
