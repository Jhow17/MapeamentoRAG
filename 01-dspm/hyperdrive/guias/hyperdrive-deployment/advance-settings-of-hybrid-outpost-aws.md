---
title: "Advanced Settings of Hybrid deployment with Outpost - AWS"
slug: "advance-settings-of-hybrid-outpost-aws"
updated: 2026-09-28T13:08:57Z
published: 2026-09-28T13:08:57Z
canonical: "helpcenter.securiti.ai/advance-settings-of-hybrid-outpost-aws"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Advanced Settings of Hybrid deployment with Outpost - AWS

Under **Advanced Settings** in the **New Outpost** popup, you can change how the Hybrid Outpost connects to your network and who creates its IAM roles. Every setting has a default, so you can deploy the Outpost without changing any of them. This page explains what each setting in the **Advanced Settings** section does. It also gives the steps for the options that require you to create resources in your AWS account before you deploy.

## Privilege Analysis Configuration

The data scanning nodes in the Hybrid Outpost send outbound requests to your target data systems and to Securiti. Many enterprise security teams permit outbound traffic only from approved source IP addresses, and the firewalls or security groups protecting your data systems often apply the same restriction. To support this, Securiti lets you select an egress strategy under **Advanced Settings** in the New Outpost popup.

The strategy you select determines the source IP address that outbound requests carry, and where the data scanning nodes sit inside your Virtual Private Cloud (VPC). Both options are created inside your own AWS account. Neither option affects inbound access to your environment, because Securiti does not initiate connections into your VPC.

> [!WARNING]
> **Important**
> 
> Select the egress strategy before you deploy the Outpost. The strategy controls subnet placement and network routing, so changing it later requires a CloudFormation stack update.

Use the following table to compare the two strategies before you select one:

| Parameter | What the template creates | What you provide |
| --- | --- | --- |
| Dynamic Managed NAT | The CloudFormation template places the data scanning nodes in public subnets, where each node receives an automatically assigned public IP address and reaches the internet directly. As it does not add Elastic IPs, it reduces the cost of required services significantly. | Confirm that no firewall, proxy, or target data system on the outbound path restricts access by source IP address. |
| Single Static Elastic IP (EIP) (default) | The CloudFormation template places the data scanning nodes in private subnets, and routes their outbound traffic through a managed NAT gateway. Each Availability Zone receives its own static Elastic IP address. | Collect the Elastic IP address of every Availability Zone, and add all of them to the allow list on your egress firewall and on each target data system. |

### Dynamic Managed NAT

Dynamic Managed NAT is an alternative to the default option. Select it under **Advanced Settings** before you download the template, and then proceed with the steps given in [Installation of Hybrid Outpost](/latest/docs/hybrid-deployment-with-outpost#installation-of-hybrid-outpost) to finish your Hybrid deployment with Outpost. However, this section gives you details about background of this advanced setting.

When you select **Dynamic Managed NAT IP**, the following settings apply:

- Securiti places the data scanning nodes in public subnets.
- Each node receives an automatically assigned public IP address, and reaches the internet directly without passing through a NAT gateway.
- Node IP addresses change as the Outpost scales nodes up and down to match scan demand, and nodes start in either Availability Zone. The set of source addresses is therefore not fixed.
- Outbound traffic does not pass through a NAT gateway, so it does not incur NAT gateway data processing charges.
- Because no fixed address exists to add to an allow list, select this option only when neither your egress firewall nor any data system that the Outpost scans restricts access by source IP address. Any such restriction on the path blocks the scan.

Continue your installation with the steps given on [Installation of Hybrid Outpost](/latest/docs/installation-in-securiti).

### Single Static Elastic IP (EIP) (default)

Single Static Elastic IP (EIP) is the default option already selected for your Hybrid Outpost deployment. You can proceed with the steps given in [Installation of Hybrid Outpost](/latest/docs/installation-in-securiti) to finish your installation. However, this section gives you details about background of this advanced setting.

When you select **Single Static Elastic IP (EIP)**, the following settings apply to your Hybrid Outpost:

- Securiti places the data scanning nodes in private subnets, so the nodes have no public IP address of their own.
- Outbound traffic from those nodes routes through a managed NAT gateway.
- Each Availability Zone receives its own static Elastic IP address. A deployment across two Availability Zones therefore creates two addresses.
- Every outbound request carries one of those static addresses as its source IP address, so the set of source addresses stays fixed for the life of the deployment.
- To reach those data systems which are behind a firewall or restricted inbound traffic, you must allow list the NAT gateway IP address of your Hybrid Outpost. This lets the Hybrid Outpost access and scan the data system.

Continue your installation with the steps given on [Installation of Hybrid Outpost](/latest/docs/installation-in-securiti).

## Network Infrastructure Strategy

By default, the CloudFormation template provisions a new network for the Hybrid deployment with Outpost in your AWS account. During installation, under **Advanced Settings**, check **Deploy in existing network infrastructure** to place the Outpost in a VPC and subnets that your organization already manages instead.

When you check this:

- The template creates no network resources, and skips every parameter that provisions a new VPC.
- You provide your existing network related details in the additional parameters during the installation mentioned in [Installing Outpost through AWS console using CloudFormation service](/latest/docs/installation-in-securiti#installing-outpost-through-aws-console-using-cloudformation-service1) and [Installing Outpost through AWS CLI](/latest/docs/installation-in-securiti#installing-outpost-in-aws-through-cloudformation-template).
- Your VPC must already have two private and two public subnets in different Availability Zones. The EKS worker nodes and application pods run in the private subnets.
- Outbound traffic uses your existing NAT and egress IP addresses, so your current routing, egress, and security controls continue to apply to the Outpost.

Continue your installation with the steps given on [Installation of Hybrid Outpost](/latest/docs/installation-in-securiti).

## IAM Provisioning Strategy

By default, the CloudFormation template that deploys the Hybrid Outpost also creates every IAM role the Outpost requires. Many enterprise security teams do not permit an automated template to create IAM entities, and require roles to be pre-approved and provisioned by their own IAM team. To support this, Securiti lets you select an **IAM Provisioning Strategy** under **Advanced Settings** in the **New Outpost** popup, and supply the roles you have created yourself.

Use the following table to compare the three strategies before you select one:

| Parameter | What the template creates | What you provide |
| --- | --- | --- |
| Fully Automated (default) | The main CloudFormation template creates and configures all the IAM roles listed in the [Permissions](/latest/docs/hybrid-deployment-with-outpost#local-tools). | No IAM work is required in your AWS account. |
| Modular | The main CloudFormation template creates every role except the two cross-account roles, and references the two roles you provide as is. These two roles are: - Metadata Access role (`securiti-metadata-access-role-{suffix}`) - Monitoring Access role (`securiti-monitoring-access-role-{suffix}`) | Create the Metadata Access and Monitoring Access roles with the required trust policies, and provide their ARNs in the New Outpost popup. |
| Fully Manual (Bring your own IAM) | The main CloudFormation template creates no IAM role, and references roles that already exist in your account. The separate IAM roles template creates the pod, Lambda, and service roles. | Create the Metadata Access and Monitoring Access roles with the required trust policies, enter their ARNs in the New Outpost popup, and deploy the IAM roles using the template to create the remaining roles. After you create these roles, deploy the Outpost using its template. |

### Fully Automated (default)

When you select **Fully Automated** as the **IAM Provisioning Strategy**, the CloudFormation template creates and configures every IAM role the Hybrid Outpost requires. No IAM work is required in your AWS account.

Continue with the installation steps described in [Installation of Hybrid Outpost](/latest/docs/installation-in-securiti).

### Modular

When you select **Modular** as the **IAM Provisioning Strategy**, you create two IAM roles in your AWS account and provide their ARNs to Securiti. The CloudFormation template creates all the remaining roles provided in [Permissions](/latest/docs/hybrid-deployment-with-outpost#local-tools) table.

The two roles you create are:

- Metadata Access role
- Monitoring Access role

To deploy Hybrid Outpost with Modular IAM provisioning strategy, proceed with the following steps:

1. In the **New Outpost** popup, under **Advanced Settings**, set **IAM Provisioning Strategy** to **Modular**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EJZKAFL5.png)
2. On your **New Outpost** popup, locate and copy the **External ID**. You need it for the trust policy of both roles.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-35KWGJYX.png)

> [!WARNING]
> **Important**
> 
> Keep the popup open until you have entered both role ARNs. Securiti generates a new External ID each time you open the popup, and the roles you create would no longer match.
3. Obtain the principal ARN values for your environment from the Securiti **Account Details** area, and keep them available throughout the deployment. Both roles you create must trust Securiti's principal.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8LJRI4UI.png)
4. In your AWS account, create the **Metadata Access role** with the trust policy below. Replace the principal ARN with the value for your environment from step 3, and replace `&lt;EXTERNAL-ID&gt;` with the value you copied in step 2.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": [
            "<Cross-Account Role ARN EKSNODE>",
            "<Cross-Account Databricks instance role>"
            ]
      },
      "Action": "sts:AssumeRole",
      "Condition": {
        "StringEquals": { "sts:ExternalId": "<EXTERNAL-ID>" }
      }
    }
  ]
}
```

Save the policy as `metadata-trust-policy.json`, and create the role using the following command:

```bash
aws iam create-role \
--role-name securiti-metadata-access-role \
--assume-role-policy-document file://metadata-trust-policy.json
```
5. Create the **Monitoring Access role** with the trust policy below. It has the same statement as the Metadata Access role, plus a second statement for Securiti's monitoring principal.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": [
            "<Cross-Account Role ARN EKSNODE>",
            "<Cross-Account Databricks instance role>"
            ]
      },
      "Action": "sts:AssumeRole",
      "Condition": {
        "StringEquals": { "sts:ExternalId": "EXTERNAL-ID" }
      }
    },
    {
      "Sid": "MonitoringReadOnly",
      "Effect": "Allow",
      "Principal": {
        "AWS": "<Monitor Role ARN>"
      },
      "Action": ["sts:AssumeRole", "sts:TagSession"],
      "Condition": {
        "StringEquals": { "aws:RequestTag/access-level": "read-only" }
      }
    }
  ]
}
```

Save the policy as `monitoring-trust-policy.json`, and create the role using the following command:

```bash
aws iam create-role \
--role-name securiti-monitoring-access-role \
--assume-role-policy-document file://monitoring-trust-policy.json
```

> [!NOTE]
> **Note**
> 
> Create both roles with their trust policy only. Do not attach any permission policy yet.
6. Go back to the New Outpost popup, and enter the ARN of each role you created:

Both ARNs must use the format `arn:aws:iam::ACCOUNT-ID:role/ROLE-NAME`. If either ARN is not in this format, the field does not validate and you cannot download the template.
  - In **Metadata Access Role ARN** field, enter the ARN of the Metadata Access role.
  - In **Monitoring Access Role ARN** field, enter the ARN of the Monitoring Access role.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ANU7YB8K.png)
7. At the bottom of **New Outpost** popup, click **Prepare & Download Template**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CAD3BQ6G.png)

It prepares the template and downloads in to your local storage.
8. Deploy the Hybrid Outpost in your cloud. For more information, see [Installing Outpost through AWS console using CloudFormation service](/latest/docs/installation-in-securiti#installing-outpost-through-aws-console-using-cloudformation-service1) or [Installing Outpost through AWS CLI](/latest/docs/installation-in-securiti#installing-outpost-in-aws-through-cloudformation-template).
9. After deploying the Hybrid Outpost, collect the following values and keep them for next steps to replace them in the JSON policies. You can use Output tab of your CloudFormation stack on the AWS console, or using the following command on the AWS CLI:

```bash
aws cloudformation describe-stacks \
  --stack-name <StackName> \
  --query "Stacks[0].{UniqueSuffix: Parameters[?ParameterKey=='UniqueSuffix'].ParameterValue | [0], MetadataStorageS3BucketName: Outputs[?OutputKey=='MetadataStorageS3BucketName'].OutputValue | [0], AMPWorkspaceArn: Outputs[?OutputKey=='AMPWorkspaceArn'].OutputValue | [0], EKSClusterName: Outputs[?OutputKey=='EKSClusterName'].OutputValue | [0], OutpostLogsS3BucketName: Outputs[?OutputKey=='OutpostLogsS3BucketName'].OutputValue | [0]}"
```

Collect the values for the following variables:

Collect the following values from your AWS Account:

Keep the value for the following that you collected during deployment:
  - `&lt;MetadataStorageS3BucketName&gt;`
  - `&lt;AMPWorkspaceArn&gt;`
  - `&lt;EKSClusterName&gt;`
  - `&lt;OutpostLogsS3BucketName&gt;`
  - `&lt;UniqueSuffix&gt;`
  - `&lt;Region&gt;`
  - `&lt;AccountId&gt;`
  - `&lt;SecuritiKMSKeyArn&gt;`
10. After the stack deploys, attach the permission policies listed in [Permissions](/latest/docs/hybrid-deployment-with-outpost#local-tools) to both cross-account roles. For the `Metadata Access role`, use the following policy file:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:DeleteObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::<MetadataStorageS3BucketName>/*",
        "arn:aws:s3:::<MetadataStorageS3BucketName>"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "kms:Decrypt",
        "kms:GenerateDataKey"
      ],
      "Resource": "<SecuritiKMSKeyArn>"
    }
  ]
}
```

Replace the variables with their actual values.

Save the above policy as `metadata-permissions.json`, and attach the policy using the following command:

```bash
aws iam put-role-policy \
--role-name securiti-metadata-access-role \
--policy-name MetadataS3BucketAccess \
--policy-document file://metadata-permissions.json
```
11. For the `Monitoring Access role`, attach a single policy covering AMP, CloudWatch Logs, and S3 access:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AMPAccess",
      "Effect": "Allow",
      "Action": [
        "aps:QueryMetrics",
        "aps:GetSeries",
        "aps:GetLabels",
        "aps:GetMetricMetadata"
      ],
      "Resource": "<AMPWorkspaceArn>"
    },
    {
      "Sid": "CloudWatchLogsAccess",
      "Effect": "Allow",
      "Action": [
        "logs:DescribeLogGroups",
        "logs:DescribeLogStreams",
        "logs:GetLogEvents",
        "logs:FilterLogEvents",
        "logs:StartQuery",
        "logs:GetQueryResults"
      ],
      "Resource": [
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/lambda/securiti-*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/lambda/securiti-*:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/cluster",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/cluster:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/application",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/application:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/host",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/host:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/postgresql",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/postgresql:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/upgrade",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/upgrade:log-stream:*"
      ]
    },
    {
      "Sid": "OutpostLogsS3Access",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:ListBucket",
        "s3:DeleteObject"
      ],
      "Resource": [
        "arn:aws:s3:::<OutpostLogsS3BucketName>",
        "arn:aws:s3:::<OutpostLogsS3BucketName>/*"
      ]
    }
  ]
}
```

The `/aws/lambda/securiti-*` entries need no changes. For the `/aws/rds/instance/securiti-rds-&lt;UniqueSuffix&gt;/...` entries, replace `&lt;UniqueSuffix&gt;` with this Hybrid Outpost's actual value.

Save the policy as `monitoring-permissions.json`, and attach the policy using the following command:

```bash
aws iam put-role-policy \
  --role-name securiti-monitoring-access-role \
  --policy-name MonitoringAccessPolicy \
  --policy-document file://monitoring-permissions.json
```

After attaching these policies, your Hybrid Outpost is deployed with the `Metadata Access role` and `Monitoring Access role` that you provisioned yourself in your AWS account.

### Fully Manual (Bring your own IAM)

When you select **Fully Manual (Bring your own IAM)** as the **IAM Provisioning Strategy**, the main CloudFormation template that deploys Hybrid Outpost creates no IAM role at all. You create every role the Outpost requires in your AWS account.

- You create the **Metadata Access role** and the **Monitoring Access role** yourself, and enter their ARNs in the New Outpost popup.
- You create the remaining roles by deploying a separate **IAM roles template** that Securiti generates for this Hybrid Outpost.

To create all the roles and provide the required ARNs, proceed with the steps below before you download the main template:

1. In the New Outpost popup, under **Advanced Settings**, set **IAM Provisioning Strategy** to **Fully Manual (Bring your own IAM)**, and copy the **External ID**. You need it for the trust policy of both cross-account roles.

> [!WARNING]
> **Important**
> 
> Keep the popup open until you have entered both role ARNs. Securiti generates a new External ID each time you open the popup, and the roles you create would no longer match.
2. Obtain the principal ARN values for your environment from the Securiti **Account Details** area, and keep them available throughout the deployment. Both roles you create must trust Securiti's principal.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A4L6K97J.png)
3. In your AWS account, create the **Metadata Access role** with the trust policy below. Replace the principal ARN with the value for your environment from step 2, and replace EXTERNAL-ID with the value you copied in previous step.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": [
            "<Cross-Account Role ARN EKSNODE>",
            "<Cross-Account Databricks instance role>"
        ]
      },
      "Action": "sts:AssumeRole",
      "Condition": {
        "StringEquals": { "sts:ExternalId": "EXTERNAL-ID" }
      }
    }
  ]
}
```

Save the policy as `metadata-trust-policy.json`, and create the role:

```plaintext
aws iam create-role \
--role-name securiti-metadata-access-role \
--assume-role-policy-document file://metadata-trust-policy.json
```
4. Create the **Monitoring Access role** with the trust policy below. It has the same statement as the Metadata Access role, plus a second statement for Securiti's monitoring principal.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": [
            "<Cross-Account Role ARN EKSNODE>",
            "<Cross-Account Databricks instance role>"
        ]
      },
      "Action": "sts:AssumeRole",
      "Condition": {
        "StringEquals": { "sts:ExternalId": "EXTERNAL-ID" }
      }
    },
    {
      "Sid": "MonitoringReadOnly",
      "Effect": "Allow",
      "Principal": {
        "AWS": "<Monitor Role ARN>"
      },
      "Action": ["sts:AssumeRole", "sts:TagSession"],
      "Condition": {
        "StringEquals": { "aws:RequestTag/access-level": "read-only" }
      }
    }
  ]
}
```

Save the policy as `monitoring-trust-policy.json`, and create the role:

```bash
aws iam create-role \
--role-name securiti-monitoring-access-role \
--assume-role-policy-document file://monitoring-trust-policy.json
```

> **Note**
> 
> Create both roles with their trust policy only. Do not attach any permission policy yet.
5. Go back to the New Outpost popup, and enter the ARN of each role you created:

Both ARNs must use the format `arn:aws:iam::ACCOUNT-ID:role/ROLE-NAME`. Until both ARNs are valid, the form does not validate and the option to download the IAM roles template stays disabled.
  - In the **Metadata Access Role ARN** field, enter the ARN of the Metadata Access role.
  - In the **Monitoring Access Role ARN** field, enter the ARN of the Monitoring Access role.
6. In the **IAM Roles Template** section, click **Download Template**, and deploy the downloaded template in your AWS account. It creates all the remaining IAM roles that the Outpost requires.

> **Note**
> 
> The **IAM Roles Template** section appears only when you select Fully Manual.
7. Once the IAM roles stack finishes deploying, return to the New Outpost popup, and click **Prepare & Download Template** to download the main template. For more information, see Installing in Securiti.
8. Deploy the main template in your AWS account, and leave the remaining role ARN parameters blank. The main template creates no IAM role, and references the roles that already exist in your account.

> [!WARNING]
> **Important**
> 
> Do not fill in the remaining role ARN parameters. The main template derives those ARNs itself, using the same naming that the IAM roles template applied in step 6, so they resolve to the roles you already created. You do not need to copy any value from the IAM roles stack's Outputs. The Metadata Access role and the Monitoring Access role remain the only role ARNs you supply on the UI.
9. After deploying the Hybrid Outpost, collect the following values. The next steps use them to replace the placeholders in the JSON policies. Use the **Outputs** tab of your CloudFormation stack in the AWS console, or run the following AWS CLI command:

```bash
aws cloudformation describe-stacks \
  --stack-name <StackName> \
  --query "Stacks[0].{UniqueSuffix: Parameters[?ParameterKey=='UniqueSuffix'].ParameterValue | [0], MetadataStorageS3BucketName: Outputs[?OutputKey=='MetadataStorageS3BucketName'].OutputValue | [0], AMPWorkspaceArn: Outputs[?OutputKey=='AMPWorkspaceArn'].OutputValue | [0], EKSClusterName: Outputs[?OutputKey=='EKSClusterName'].OutputValue | [0], OutpostLogsS3BucketName: Outputs[?OutputKey=='OutpostLogsS3BucketName'].OutputValue | [0]}"
```

Collect the values for the following variables:

Collect the following values from your AWS Account:

Keep the value for the following that you collected during deployment:
  - `&lt;MetadataStorageS3BucketName&gt;`
  - `&lt;AMPWorkspaceArn&gt;`
  - `&lt;EKSClusterName&gt;`
  - `&lt;OutpostLogsS3BucketName&gt;`
  - `&lt;UniqueSuffix&gt;`
  - `&lt;Region&gt;`
  - `&lt;AccountId&gt;`
  - `&lt;SecuritiKMSKeyArn&gt;`
10. After the main stack deploys, attach the permission policies listed in [Permissions](/latest/docs/hybrid-deployment-with-outpost#local-tools) to both cross-account roles. For the `Metadata Access role`, use the following policy file:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:DeleteObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::<MetadataStorageS3BucketName>/*",
        "arn:aws:s3:::<MetadataStorageS3BucketName>"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "kms:Decrypt",
        "kms:GenerateDataKey"
      ],
      "Resource": "<SecuritiKMSKeyArn>"
    }
  ]
}
```

Replace the variables with their actual values.

Save the above policy as `metadata-permissions.json`, and create the role using the following command:

```bash
aws iam put-role-policy \
--role-name securiti-metadata-access-role \
--policy-name MetadataS3BucketAccess \
--policy-document file://metadata-permissions.json
```
11. Then, for the `Monitoring Access role`, attach a single policy covering AMP, CloudWatch Logs, and S3 access:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AMPAccess",
      "Effect": "Allow",
      "Action": [
        "aps:QueryMetrics",
        "aps:GetSeries",
        "aps:GetLabels",
        "aps:GetMetricMetadata"
      ],
      "Resource": "<AMPWorkspaceArn>"
    },
    {
      "Sid": "CloudWatchLogsAccess",
      "Effect": "Allow",
      "Action": [
        "logs:DescribeLogGroups",
        "logs:DescribeLogStreams",
        "logs:GetLogEvents",
        "logs:FilterLogEvents",
        "logs:StartQuery",
        "logs:GetQueryResults"
      ],
      "Resource": [
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/lambda/securiti-*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/lambda/securiti-*:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/cluster",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/cluster:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/application",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/application:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/host",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/eks/<EKSClusterName>/host:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/postgresql",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/postgresql:log-stream:*",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/upgrade",
        "arn:aws:logs:<Region>:<AccountId>:log-group:/aws/rds/instance/securiti-rds-<UniqueSuffix>/upgrade:log-stream:*"
      ]
    },
    {
      "Sid": "OutpostLogsS3Access",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:ListBucket",
        "s3:DeleteObject"
      ],
      "Resource": [
        "arn:aws:s3:::<OutpostLogsS3BucketName>",
        "arn:aws:s3:::<OutpostLogsS3BucketName>/*"
      ]
    }
  ]
}
```

The `/aws/lambda/securiti-*` entries need no changes. For the `/aws/rds/instance/securiti-rds-&lt;UniqueSuffix&gt;/...` entries, replace `&lt;UniqueSuffix&gt;` with this Hybrid Outpost's actual value.

Save the policy as `monitoring-permissions.json`, and create the role using the following command:

```bash
aws iam put-role-policy \
  --role-name securiti-monitoring-access-role \
  --policy-name MonitoringAccessPolicy \
  --policy-document file://monitoring-permissions.json
```

After attaching these policies, your Hybrid Outpost has deployed with the `Metadata Access role` and `Monitoring Access role` that you provisioned yourself in your AWS account. Your Hybrid Outpost deployment in your AWS account can now interact with these roles.

## Related

- [Managing Hybrid deployments with Outpost](/managing-securiti-outpost-deployments-1.md)
- [Upgrading hybrid deployment with Outpost](/upgrading-hybrid-deployment-with-outpost.md)
- [Hyperdrive connectors data flow architecture - AWS](/hyperdrive-connectors-data-flow-architecture-aws.md)
