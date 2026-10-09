---
title: "Amazon S3"
slug: "connect-amazon-s3-using-hyperdrive-mode"
status: "new"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/connect-amazon-s3-using-hyperdrive-mode"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Amazon S3

The Amazon S3 (Simple Storage Service) is a web service that provides scalable storage solutions for data archival, backup, and recovery. These functions can be used through a web-based control interface. Securiti offers Hyperdrive Mode through Outpost deployment for fast, secure, and high-performance data access.

## Supported modules

| Connector | Supported module features |
| --- | --- |
| Amazon S3 | - Sensitive Data Intelligence: - Discovery scan - Data Inventory sync |

## Supported pod type

- Securiti Outpost deployment

## Supported authentication types

| Authentication method | Authentication credentials |
| --- | --- |
| IAM Keys | - Region - Bucket(s) - Token ID - Token Secret |
| IAM Roles | - AWS Master Account ID - Data Scan Master IAM Role - AWS Member Account IDs - Data Scan Member IAM Role - External Id for Master and Member IAM Roles (Required for Full SaaS deployment model) > [!NOTE] > **Note** > > **IAM Roles** authentication operates natively within the AWS infrastructure and assigns access to AWS resources through the attached policies. This authentication method is only supported when your **Amazon S3** connector is running within the AWS environment. It doesn't work if you attempt to run the **Amazon S3** connector on a self-hosted virtual machine outside of AWS. |
| S3 Inventory | - Inventory Report Bucket - Inventory Report Path - Inventory Token Id - Inventory Token Secret - Region - Bucket(s) |
| Auto-generate Dynamic Credentials | Auto-generate Dynamic Credentials authentication support is not available for Hyperdrive mode. |

### Supported keyring types

Keyring support is not available for data systems using Hyperdrive.

## Prerequisites

1. #### Outpost deployment

If you use Hyperdrive mode while creating a data system instance, you must deploy Securiti Outpost, which uses AWS services to scale scanning operations. For more information, see [Securiti Outpost deployment](/latest/docs/securiti-outpost-deployment).
2. #### Amazon S3 account and role requirement.

You must meet the Amazon S3 instance access and roles requirement to obtain credentials and activate the connector.
  1. For more information, see [Obtain credentials for Inventory-based authentication in Amazon S3 (Hyperdrive)](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3-hyperdrive)
  2. For more information, see [Obtain credentials for role-based authentication in Amazon S3 (Hyperdrive)](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-s3-hyperdrive).
3. ### Permissions and use cases

You must assign the following permissions to access the Amazon S3

| Permission | Purpose |
| --- | --- |
| `s3:ListBucket` | This permission is required for discovering metadata from Amazon S3 objects in a bucket. This permission is also lets Securiti evaluate the bucket contents to create and run File ROT and Data Labeling policies, in SDI. |
| `s3:GetObject` | This permission is required for discovering metadata from Amazon S3 downloaded objects. This permission also lets Securiti read object content and metadata to evaluate files and execute File Quarantine, File ROT, and Data Labeling policies in SDI. |
| `kms:Decrypt` | This permission is required for discovering metadata from Amazon S3 objects using a customer-managed KMS key |
| `s3:GetObjectTagging` | This permission lets Securiti retrieve existing object tags to evaluate and enforce Data Labeling, File Quarantine and File ROT policies in SDI. |
| `s3:PutObjectTagging` | This permission lets Securiti apply or update object tags when executing Data Labeling, File Quarantine and File ROT policies in SDI. |
| `cloudwatch:GetMetricStatistics` | This permission lets Securiti evaluate the bucket size. |
| `s3:GetObjectAcl` | This permission is required for discovering owners in’s information and fetching S3 tags. This permission also lets Securiti retrieve object-level access control information to evaluate permissions before executing File ROT and Data Labeling policies in SDI. |
| `s3:GetBucketAcl` | This permission lets Securiti retrieve bucket-level access control information to validate access before creating and running File ROT and Data Labeling policies in SDI. |
| `s3:ListBucketVersions` | This permission is required for discovering metadata from Amazon S3 objects, including all their versions in a bucket. |
| `s3:GetBucketVersioning` | This permission is required to verify whether versioning is enabled on the bucket before executing the data inventory sync. |
| `s3:ListBucketMultipartUploads` | This permission is required to identify ongoing multipart uploads, which are later used to count incomplete parts. > [!NOTE] > **Note** > > This permission is only required if you want to determine the count of multipart files. |
| `s3:ListMultipartUploadParts` | This permission is required to count all the individual parts of a multipart upload. > [!NOTE] > **Note** > > This permission doesn't work on its own and must be used together with **s3:ListMultipartUploads** to get the count of multipart uploads. |
| `s3:AbortMultipartUpload` | This permission lets Securiti terminate incomplete multipart uploads to prevent partial or failed object operations during Quarantine, File ROT, Data Labeling policy actions in SDI. |
| `s3:GetObjectVersionTagging` | This permission retrieves additional metadata or all versions of an object, including past versions. > [!NOTE] > **Note** > > This permission is only required if the following toggles are enabled for data inventory sync: > > - Fetch Resource Tag? > - Process All versions? |
| `s3:GetObjectVersionAcl` | This permission retrieves the owner info for all versions of an object, including past versions. > [!NOTE] > **Note** > > This permission is only required if the following toggles are enabled for data inventory sync: > > - Fetch Owner? > - Process All versions? |
| `s3:PutObject` | This permission lets Securiti upload or move objects within the bucket when executing Quarantine, File ROT, and Data Labeling actions in SDI. |
| `s3:DeleteObject` | This permission lets Securiti delete objects from the bucket when executing deletion-based File ROT policies in SDI. The permission is also required for File Quarantine and Data Labeling policies. |
| `Include all versions setting` | To include multiple versions in the inventory scope, you must enable the **Include all versions** setting in Amazon, as shown below. |

## Connect Amazon S3 with Securiti

1. Obtain authentication credentials in Amazon S3. See the topics below for supported authentication types in the Amazon S3 connector:
  - For **IAM Roles**, see [Obtain credentials for role based authentication in Amazon S3 (Hyperdrive)](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-s3-hyperdrive)
  - For **IAM Keys**, see [Amazon's access keys documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) to record Token ID and Token Secret.
  - For **S3 Inventory**, see [Obtain credentials for Inventory-based authentication in Amazon S3 (Hyperdrive)](/latest/docs/obtain-credentials-for-inventory-based-authentication-in-amazon-s3-hyperdrive)
2. [Connecting the Amazon S3 with Securiti (Hyperdrive](/latest/docs/activate-the-amazon-s3-connector-in-securiti-hyperdrive)
3. [Using Authentication statuses (Hyperdrive)](/latest/docs/using-authentication-statuses-hyperdrive)

## Configure scans and policies

1. [Configuring Data Inventory Sync for Amazon S3 (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-amazon-s3-hyperdrive)
2. [Configure discovery scans in Amazon S3 (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-amazon-s3-hyperdrive)

## Additional resource

- [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive)
