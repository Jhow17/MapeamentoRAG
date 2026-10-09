---
title: "Amazon S3"
slug: "amazon-s3-connectors-1"
status: "update"
updated: 2026-08-05T09:24:00Z
published: 2026-08-05T13:38:08Z
canonical: "helpcenter.securiti.ai/amazon-s3-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon S3

The Amazon S3 (Simple Storage Service) is a web service that provides scalable storage solutions for data archival, backup, and recovery. These functions can be used through a web-based control interface. Amazon S3 offers an opt-in option for customers to implement server-side security protocols for their stored data. Customer information disclosure is only done if a legally binding clause is in place for a particular data request. The AWS privacy policy only applies to data that constitutes account information, rather than including their uploaded contents (referred to by Amazon as “Consumer Content”).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Amazon S3 (Self-hosted) | - Sensitive Data Intelligence (Discovery Scan) - DSR Automation using Full Scan - Data Access Governance (Privilege Analysis) - Breach Analysis |

### Supported pod types for the self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

You must select the authentication method according to the modules or scans you want to run. For more information on supported authentication methods for specific scans or modules, see the permissions table in the Permissions and use cases section below.

| Authentication method | Authentication credentials |
| --- | --- |
| IAM Keys | - Region - Bucket(s) - Token ID - Token Secret |
| IAM Roles | - AWS Master Account ID - Data Scan Master IAM Role - AWS Member Account IDs - Data Scan Member IAM Role - (Optional) External Id for Master and Member IAM Roles > [!NOTE] > **Note** > > **IAM Roles** authentication operates natively within the AWS infrastructure and assigns access to AWS resources through the attached policies. This authentication method is only supported when your **Amazon S3** connector is running within the AWS environment. It doesn't work if you attempt to run the **Amazon S3** connector on a self-hosted virtual machine outside of AWS. |
| S3 Inventory | - Inventory Report Bucket - Inventory Report Path - Inventory Token Id - Inventory Token Secret - Region - Bucket(s) |
| Auto-generate Dynamic Credentials | - Bucket(s) - Federation or session token in HashiCorp Keyring |

#### Keyring support for Amazon S3

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**: For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **AWS Secrets Manager**: For more information, see [AWS Secrets Manager credential vault](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash**: For more information, see [CredStash credential vault](/latest/docs/configuring-credential-vaults-credstash-credential-vault).
- **CyberArk**: For more information, see [CyberArk credential vault](/latest/docs/cyberark-credential-vault).

> [!NOTE]
> Note
> 
> If you use CyberArk Credentials vault to manage AWS credentials, Securiti recommends registering the credentials using the **Cloud Services → AWS Access Keys** platform in CyberArk. To learn more about configuration, see [*(Optional) Storing AWS Credentials using CyberArk Cloud Services platform*](/latest/docs/optional-storing-aws-credentials-using-cyberark-cloud-services-platform)*.*

### Supported items for inventory and classification Scans

For more information on inventory scans, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- S3 Objects in Buckets.

#### S3 listing methods

Use the table below to understand the difference between two methods to fetch Amazon S3 objects in data inventory syncs and discovery scans:

| Method | Explanation |
| --- | --- |
| APIs-based listing | This is the standard and default method that directly queries the cloud storage service to build an inventory of S3 objects in real-time. It iterates through the list of objects provided by the AWS's API. > [!NOTE] > **Note** > > - The APIs-based listing is not a content scan of each object; however, it can be less efficient than native inventory-based listing for very large data stores. > - Use this method if your pods are working with nodes less than 50. |
| Native inventory-based listing | This method leverages the inventory reports generated directly by your Amazon Inventory Reports. This approach is highly efficient as Securiti ingests metadata from these pre-existing reports rather than querying each object individually. To use this method, you must enable the **Use Native Inventory toggle** while [activating the connector](/v1/docs/activate-the-amazon-s3-connector-in-securiti) and configure the inventory reporting feature within your cloud provider's console. > [!NOTE] > Note > > - Native Inventory-based listing method is recommended for discovery workloads on clusters with 50+ nodes, as it leverages consistent performance and near-linear scaling. > - It eliminates throttling and producer bottlenecks by distributing workload evenly across nodes. In smaller clusters, parallelism benefits are limited, but at scale, Native Inventory maximizes throughput and significantly reduces scan time. |

### Prerequisites for configuring Amazon S3 connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Amazon S3 with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and Amazon S3 API endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-v2).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access in Amazon S3 instance

We assume you're the admin of your AWS S3 instance, or you have access to the account with admin privileges.

#### 3. Master and member accounts

This procedure assumes you have the AWS Master and Member account IDs before connector activation in case of IAM Role-based authentication.

For more information, see [Obtain credentials for role based authentication in Amazon S3](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-s3).

#### 4. Configure inventory in AWS for data inventory sync

You must configure inventory in AWS for S3 buckets to list the objects in the bucket and publish the list to a destination account and bucket. For more information, see [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/configure-inventory.html).

> [!NOTE]
> **Note**
> 
> - You must have at least one inventory generated report for scanning results. It might take up to 48 hours for Amazon S3 to deliver the first inventory report. For more information, see [S3 inventory list management documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html).
> - You must select Include all versions in the Inventory scope while creating the inventory report in Amazon S3. For more information, see [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/configure-inventory.html).

#### 5. Use cases and permissions for Amazon S3

> [!WARNING]
> **Warning**
> 
> Ensure proper permissions are granted to avoid misleading scan results and skipping objects during the scanning process.
> 
> - If permission is not provided, the pod displays an error while listing objects. Despite the error, upon completion, the scan job on the UI turns green, potentially misleading the end customer into believing the scan was successful.
> - Additionally, when initiating a new scan and the connector has permission to list objects, it skips all objects with the message "Ignoring item, as it isn't falling under the scan time boundary."

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | - kms:Decrypt - s3:ListBucket - s3:GetObject - cloudwatch:GetMetricStatistics - s3:GetObjectTagging - s3:GetObjectAcl | These permissions let Securiti read the files and file metadata in Amazon S3 for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Data Inventory Sync | Data Inventory Sync methods depend on authentication methods. *APIs-based listing* method is supported in: - IAM Role authe ntication - IAM Key authentication - Auto-generate Dynamic Credentials authentication *Native Inventory-based listing* method is supported for all authentication types: > [!NOTE] > **Important** > > When using the *Native Inventory* method, ensure the pod version is 1.130.0 or above for authentication types other than S3 Inventory. - S3 Inventory authentication - IAM Role - IAM Keys - Auto-generate dynamic credentials | - kms:Decrypt - s3:ListBucket - s3:GetObject - s3:GetObjectAcl - s3:ListBucketVersions - s3:GetBucketVersioning - s3:ListBucketMultipartUploads - s3:ListMultipartUploadParts - GetObjectVersionTagging - GetObjectVersionAcl | These permissions let Securiti read the files and file metadata in Amazon S3 for inventory. These permissions also let Securiti discover entitlements and read sharing settings. |
| Data Access Governance | Data Access Intelligence for Amazon is only supported for IAM Role and IAM Key authentication methods. | **Read** permissions to the following AWS policies: - SecurityAudit - AmazonInspector2ReadOnlyAccess - AmazonGlacierReadOnlyAccess - AmazonDocDBElasticReadOnlyAccess - AmazonBedrockReadOnly | These permissions let Securiti leverages these Amazon S3 permissions as part of determining which users and user groups have access to S3 buckets and what level of permissions they have on that data. For more information, see [Data Access Governance for Amazon S3.](/v1/docs/amazon-services) |
| Data labeling policy | Data labelling policy is supported for IAM Role and IAM Key authentication methods. | Assign these permissions to Amazon S3 objects: - s3:GetObject (for downloading) - s3:PutObject (for uploading) - s3:PutObjectTagging (for labeling) | These permissions let Securiti view, manage, and apply labels to S3 buckets and prefixes. With these permissions, you can apply Data Labelling Policy to your files. |

## Steps to connect Amazon S3 with Securiti

To configure the Amazon S3 connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

To use the Amazon S3 data system, you must link your structured on-premises database to Securiti.
2. Obtain authentication credentials in Amazon S3. See the topics below for supported authentication types in the Amazon S3 connector.
  - For **IAM Roles**, see [Obtain credentials for role based authentication in Amazon S3](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-s3).
  - For IAM Roles with IRSA, see [Creating IRSA Role and establish trust relationship](/latest/docs/irsa-authentication-steps-for-iam-role-in-securitii).
  - For **IAM Keys**, see [Amazon's access keys documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) to record Token ID and Token Secret.
  - For **S3 Inventory**, see [Obtain credentials for Inventory-based authentication in Amazon S3](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3).
  - For **Auto-generate Dynamic Credentials**, see [Auto-generate dynamic credentials authentication in Amazon S3](/latest/docs/auto-generate-dynamic-credentials-authentication-in-amazon-s3).
3. [Connecting Amazon S3 with Securiti](/latest/docs/connecting-amazon-s3-with-securiti).
4. [Configuring Access permissions for Amazon S3](/latest/docs/configuring-access-permissions-for-amazon-s3).
5. [Configuring Data Inventory Sync for Amazon S3 (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-amazon-s3-self-hosted).
6. [Configure discovery scans in Amazon S3](/latest/docs/configure-discovery-scans-in-amazon-s3).

**Additional resources**

- [Troubleshooting for Amazon S3 connector](/latest/docs/troubleshooting-for-amazon-s3-connector).
- [Fulfilling DSR requests for Amazon S3](/latest/docs/fulfilling-dsr-requests-for-amazon-s3).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

Type of scan focused on identifying metadata rather than content for files in a data system. Data Inventory sync includes identifying file attributes such as name, size, creation date etc and information such as access permissions, ownership, and entitlement for resources. Data Inventory scan includes inventory and entitlement scanning for Genstack, and is supported for monitored, self-hosted data systems only

## Related

- [Obtain credentials for role based authentication in Amazon S3](/obtain-credentials-for-role-based-authentication-in-amazon-s3.md)
- [Obtain credentials for Inventory-based authentication in Amazon S3](/obtain-credentials-for-inventory-based-authentication-in-amazon-s3.md)
- [Auto-generate dynamic credentials authentication in Amazon S3](/auto-generate-dynamic-credentials-authentication-in-amazon-s3.md)
- [Connecting Amazon S3 with Securiti](/connecting-amazon-s3-with-securiti.md)
- [Configure discovery scans in Amazon S3](/configure-discovery-scans-in-amazon-s3.md)
- [Configuring Data Inventory Sync for Amazon S3 (Self-hosted)](/configuring-data-inventory-sync-for-amazon-s3-self-hosted.md)
- [Fulfilling DSR requests for Amazon S3](/fulfilling-dsr-requests-for-amazon-s3.md)
- [Troubleshooting for Amazon S3 connector](/troubleshooting-for-amazon-s3-connector.md)
