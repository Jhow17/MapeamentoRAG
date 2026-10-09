---
title: "Amazon DynamoDB"
slug: "amazon-dynamodb-connectors-1"
status: "new"
updated: 2026-07-28T10:57:13Z
published: 2026-07-28T11:00:12Z
canonical: "helpcenter.securiti.ai/amazon-dynamodb-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon DynamoDB

The Amazon DynamoDB is a service component of the Amazon Web Services (AWS) which derives its functionality from NoSQL-based databases. As an enhanced version of the preceding Amazon SimpleDB platform, DynamoDB offers synchronous replication of data across disparate data centers in order to ensure data integrity and spontaneous processing.

DynamoDB falls under the category of [monitored, structured data system](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Amazon DynamoDB (self-hosted) | - Sensitive Data Intelligence - DSR Automation using SQL queries - Access Intelligence Scan (Privilege Analysic |
| Amazon DynamoDB (Securiti cloud) | DSR Automation using APIS |

### Supported pod types for self-hosted connector

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported authentication methods

| Authentication method | Authentication credentials |
| --- | --- |
| Basic | - Access Key - Secret Key |
| IAM Roles (for self-hosted connector only) | - AWS Account - AWS IAM Role |

#### Keyring support for Amazon DynamoDB (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **AWS Secrets Manager**: For more information, see [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).

### Supported items for Classification Scans

Securiti supports all views for schema tables in databases. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring the Amazon DynamoDB connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Amazon DynamoDB with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see [Allow-listing domains or IPs for data system connectors](/latest/docs/allow-listing-domains-or-ips-for-data-system-connectors).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin credentials in AWS Account

You must have an Admin account in AWS to create the IAM role and assign permissions for the connector activation process between your Amazon DynamoDB and the Securiti app.

For more information, see [Using Storage Account authentication](/latest/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2) .

#### 3. Create IAM role and grant trusted entity access

Create an IAM role using your AWS Admin account. You must grant trusted entity access with EC2 use case as mentioned in [Obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance).

#### 3. Use cases and permissions for Amazon DynamoDB

To provide the Amazon DynamoDB access for data discovery and classification, use the following use cases and permissions.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) | Discovery Scan (Sensitive Data Intelligence) is only available for self-hosted connector. | Assing following permissions policy in the AWS: ```plaintext { "Version": "2012-10-17", "Statement": [ { "Sid": "AllowDynamoDBTableGetAndScanPermission", "Effect": "Allow", "Action": [ "dynamodb:BatchGetItem", "dynamodb:DescribeStream", "dynamodb:DescribeTable", "dynamodb:GetItem", "dynamodb:GetRecords", "dynamodb:GetShardIterator", "dynamodb:PartiQLSelect", "dynamodb:Query", "dynamodb:Scan" ], "Resource": "arn:aws:dynamodb:*:162495629559:table/*" }, { "Sid": "AllowDynamoDBListPermission", "Effect": "Allow", "Action": [ "dynamodb:ListTables", "dynamodb:ListGlobalTables", "dynamodb:ListStreams" ], "Resource": "*" } ] } ``` | These permissions let Securiti discover and scan files for classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect the Amazon DynamoDB connector with Securiti

#### Steps to connect the Amazon DynamoDB (Self-hosted) connector with Securiti

To configure the Amazon DynamoDB (self-hosted) connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance).
3. [Connecting Amazon DynamoDB (self-hosted) with Securiti](/latest/docs/connecting-amazon-dynamodb-self-hosted-with-securiti).
4. [Configure discovery scans in Amazon DynamoDB](/latest/docs/configure-discovery-scans-in-amazon-dynamodb).

#### Steps to connect the Amazon DynamoDB (Securiti-Cloud) connector with Securiti

To configure the Amazon DynamoDB (Securiti-Cloud) connector, perform the following procedures in sequence:

1. [Obtain credentials for your DynamoDB instance](/latest/docs/obtain-credentials-for-your-dynamodb-instance).
2. [Connecting Amazon DynamoDB (Securiti-Cloud) with Securiti](/latest/docs/connecting-amazon-dynamodb-securiti-cloud-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for Amazon DynamoDB](/latest/docs/fulfilling-dsr-requests-for-amazon-dynamodb).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

## Related

- [Obtain credentials for your DynamoDB instance](/obtain-credentials-for-your-dynamodb-instance.md)
- [Configure discovery scans in Amazon DynamoDB](/configure-discovery-scans-in-amazon-dynamodb.md)
- [Fulfilling DSR requests for Amazon DynamoDB](/fulfilling-dsr-requests-for-amazon-dynamodb.md)
