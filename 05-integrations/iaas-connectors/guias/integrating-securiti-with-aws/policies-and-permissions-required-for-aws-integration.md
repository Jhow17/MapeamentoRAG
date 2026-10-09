---
title: "Policies and permissions required for AWS integration"
slug: "policies-and-permissions-required-for-aws-integration"
updated: 2026-09-21T14:44:52Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/policies-and-permissions-required-for-aws-integration"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Policies and permissions required for AWS integration

All the IAM permissions, policies, and roles described in this document are automatically deployed with the IaaS connector based on the deployment type.

### Required AWS managed policies

An AWS managed policy is a standalone policy that is created and administered by AWS. Standalone policy means that the policy has its own Amazon Resource Name (ARN) that includes the policy name. For example, arn:aws:iam::aws:policy/IAMReadOnlyAccess is an AWS managed policy.

> [!NOTE]
> **Note**
> 
> For more information, see [AWS managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#aws-managed-policies).

These policies are available by default in AWS. They are automatically attached to a role based on the permissions on the CloudFormation (CF) template.

By default, the following AWS managed policies are attached to the user/role, and these policies must be assigned to roles for detailed contextual asset discovery.

| Policy | Access Level | Purpose | Required for |
| --- | --- | --- | --- |
| [SecurityAudit](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/SecurityAudit.html) | List, Read | Provides permission to list resources and read security configurations. This policy includes permissions for 185 services. | - Asset Discovery - Posture Scan - Access Entitlements Scan |
| [AmazonGlacierReadOnlyAccess](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/AmazonGlacierReadOnlyAccess.html) | Full: Read, Limited: List | Provides permission to list and read resources and their configuration specific to Amazon Glacier. | Asset Discovery |
| [AmazonDocDBElasticReadOnlyAccess](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/AmazonDocDBElasticReadOnlyAccess.html) | List, Read | Provides permission to list and read configurations for Amazon Document DB, and includes permission for metrics collection of different types of resources. | Asset Discovery |
| [AmazonBedrockReadOnly](https://docs.aws.amazon.com/aws-managed-policy/latest/reference/AmazonBedrockReadOnly.html) | Limited: List, Read | Provides permission to list and read resources and their configuration specific to Amazon bedrock (foundational and custom models). | - Asset Discovery - Access Entitlements Scan |
| **Custom Inline Policy - Amazon Bedrock** ```json { "Version":"2012-10-17", "Statement":[ { "Effect":"Allow", "Action":[ "bedrock:GetCustomModel", "bedrock:GetModelInvocationLoggingConfiguration", "bedrock:ListCustomModels", "bedrock:GetFoundationModel", "bedrock:ListFoundationModels", "bedrock:GetProvisionedModelThroughput", "bedrock:ListProvisionedModelThroughputs", "bedrock:GetModelCustomizationJob", "bedrock:ListModelCustomizationJobs", "bedrock:ListTagsForResource", "bedrock:GetFoundationModelAvailability", "bedrock:ListAgents", "bedrock:ListAgentKnowledgeBases", "bedrock:ListAgentAliases", "bedrock:ListAgentVersions", "bedrock:ListKnowledgeBases", "bedrock:GetAgentKnowledgeBase", "bedrock:GetKnowledgeBase", "bedrock:ListAgentActionGroups", "bedrock:GetAgent", "bedrock:GetAgentActionGroup" ], "Resource":"*" } ] } ``` | Limited: List, Read | Provides permission to list and read resources and their configuration specific to Amazon bedrock (Agents and Knowledgebase). These are permissions that are not provided by Bedrock Read Only Role. | - Asset Discovery - Posture Scan - Access Entitlement Scan |
| **Custom Inline Policy - Amazon DynamoDB** ```json { "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Action": [ "dynamodb:GetResourcePolicy" ], "Resource": "*" } ] } ``` | Limited: Read, List | Provides permission to list and read resource-based policies for DynamoDB. | Asset Discovery |
| **Custom Inline Policy - Amazon Redshift Serverless** ```json { "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Action": [ "redshift-serverless:ListNamespaces", "redshift-serverless:ListRecoveryPoints", "redshift-serverless:ListSnapshotCopyConfigurations" ], "Resource": "*" } ] } ``` | Limited:List | Provides permission to list Redshift Serverless resources, including namespaces, recovery points, and snapshot copy configurations. | Asset Discovery |
| **Custom Inline Policy - Amazon MemoryDB** ```json { "Version":"2012-10-17", "Statement":[ { "Effect":"Allow", "Action":[ "memorydb:ListTags", "memorydb:DescribeSubnetGroups" ], "Resource":"*" } ] } ``` | Limited:List | Provides permission to list MemoryDB tags and describe subnet groups. | Asset Discovery |
| **Custom Inline Policy - Amazon Keyspaces** ```json { "Version":"2012-10-17", "Statement":[ { "Effect":"Allow", "Action":[ "cassandra:Select", "cassandra:SelectMultiRegionResource" ], "Resource":"*" } ] } ``` | Limited: Read, List | Provides permission to list Keyspaces cluster configurations on single and multi region. | Posture Scan |
| **Custom Inline Policy - Amazon Opensearch Serverless** ```json { "Version":"2012-10-17", "Statement":[ { "Effect":"Allow", "Action":[ "aoss:BatchGetCollection" "aoss:ListCollections" "aoss:ListTagsForResource" ], "Resource":"*" } ] } ``` | Limited: Read, List | Provides permission to list Opensearch Serverless collections and their associated tags. | Asset Discovery |
| **SecuritiAwsCustomPolicy - Amazon Q Business, Q Connect, Aurora DSQL, and S3 Vector Bucket** ```json { "Version":"2012-10-17", "Statement":[ { "Sid":"AllowQBusinessReadonlyAccess", "Effect":"Allow", "Action":[ "qbusiness:GetApplication", "qbusiness:GetIndex", "qbusiness:GetDataSource" "qbusiness:ListApplications" ], "Resource":"*" }, { "Sid":"AllowWisdomReadonlyAccess", "Effect":"Allow", "Action":[ "wisdom:ListAssistants", "wisdom:GetAssistant", "wisdom:ListAIAgents", "wisdom:ListAssistantAssociations", "wisdom:ListKnowledgeBases", "wisdom:GetKnowledgeBase", "wisdom:ListTagsForResource" ], "Resource":"*" }, { "Sid":"AllowDSQLReadonlyAccess", "Effect":"Allow", "Action":[ "dsql:ListClusters", "dsql:GetCluster" ], "Resource":"*" }, { "Sid":"AllowS3VectorReadonlyAccess", "Effect":"Allow", "Action":[ "s3vectors:ListVectorBuckets", "s3vectors:GetVectorBucket", "s3vectors:GetVectorBucketPolicy" ], "Resource":"*" }, { "Sid":"AllowKMSDecryptForServices", "Effect":"Allow", "Action":[ "kms:Decrypt", "kms:DescribeKey" ], "Resource":"*", "Condition":{ "StringLike":{ "kms:ViaService":[ "qbusiness.*.amazonaws.com", "wisdom.*.amazonaws.com", "qconnect.*.amazonaws.com", "dsql.*.amazonaws.com", "s3vectors.*.amazonaws.com" ] } } } ] } ``` | Limited: Read, List | Provides read-only access across multiple AWS services. This policy lets you view applications, indexes, and data sources in **Amazon Q Business**. It lists and gets information about assistants, agents, associations, and knowledge bases in **Amazon Q Connect**. It lists and retrieves details about **Amazon Aurora DSQL** clusters. It lists and reads vector bucket configurations in **Amazon S3 Vector Bucket**. It also grants permission to decrypt and describe **AWS KMS** keys when the connector reads encrypted data. The `kms:ViaService` condition limits these actions to the four services above, so the permission does not extend to other AWS services. Overall, the policy provides visibility into AI, data, and knowledge management resources without permitting modifications. | Asset Discovery |

#### KMS permissions for asset discovery

The `AllowKMSDecryptForServices` permission in `SecuritiAwsCustomPolicy` lets the connector decrypt and describe AWS Key Management Service (KMS) keys while it discovers encrypted resources in Amazon Q Business, Amazon Q Connect, Amazon Aurora DSQL, and Amazon S3 Vector Bucket.

The permission uses `Resource: "*"` because the connector does not know which KMS keys exist in your account before asset discovery runs. A `kms:ViaService` condition narrows that access to the four services above, so the permission does not extend to other AWS services.

> [!NOTE]
> Your title goes here
> 
> Your content goes here

**Scope KMS permissions to specific keys**

To restrict the permission to a known set of keys:

1. Identify the ARNs of the customer managed keys that encrypt the resources you want Securiti to discover.
2. In the CloudFormation template, replace `*` in the `kms:ViaService` statement with an array of those key ARNs.
3. Redeploy the stack.

### About custom inline policies

If customers prefer more control over the services accessed by these policies, they can create custom inline policies. However, it's important to note that if permissions are not granted for certain resources, the discovery process may not fully capture the relationships involving those resources. Additionally, since new services are continuously being added to the discovery process, customers using custom policies will need to update their connector settings whenever they wish to include newly discovered services.
