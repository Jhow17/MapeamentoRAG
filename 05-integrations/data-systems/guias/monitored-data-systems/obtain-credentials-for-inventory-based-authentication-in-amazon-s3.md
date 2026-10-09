---
title: "Obtain credentials for Inventory-based authentication in Amazon S3"
slug: "obtain-credentials-for-inventory-based-authentication-in-amazon-s3"
updated: 2025-10-31T09:45:09Z
published: 2025-11-03T06:13:51Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-inventory-based-authentication-in-amazon-s3"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for Inventory-based authentication in Amazon S3

In addition to the [Key-based and Role-based authentication methods](/v1/docs/amazon-s3-connectors-1), Amazon S3 data systems provide an Inventory-based authentication method to establish a successful connection in Securiti.

Use the matching procedure below.

1. Log in to your AWS S3 account.

> [!NOTE]
> **Note**
> 
> We assume you're the admin of your AWS S3 instance, or you have access to the account with admin privileges before proceeding with the connector activation.
> 
> - It is in accordance with AWS best practices.
> - A master account typically manages centralized identity access, authentication, and billing, without hosting actual resources.
> - Member accounts host the workloads while access is controlled through the master account
> 
> However, if you operate within a single account environment, you can set the Master and Member account IDs to be identical in CF template, allowing both templates to deploy in the same account.
> 
> You can either create these roles manually or use the sample Cloud Formation (CF) template before connector activation. [See below](/v1/docs/securiti-pods-and-elastic-pods) if you want to use a sample template by Securiti.
2. Record the following for later use:

> [!NOTE]
> **Important**
> 
> - Amazon S3 Inventory provides a flat file list of your objects and metadata on a schedule you define. You can use S3 Inventory as a scheduled alternative to the Amazon S3 synchronous List API operation. This helps when you have a lot of data in S3 and want to reduce the processing time spent on List API operations otherwise. To set up Amazon S3 Inventory for an S3 bucket, see [Amazon's official guide to configure inventory.](http://https://docs.aws.amazon.com/AmazonS3/latest/userguide/configure-inventory.html)
> - Inventory auth currently supports unencrypted CSV-based export.
> - We recommend that you enable the following fields when configuring the inventory report in AWS S3 console:
>   - Bucket name
>   - Key name
>   - Size
>   - Last modified date
>   - Storage class
>   - Object access control list
> 
> For more information, see [Amazon's documentation on Cataloging data with S3 inventory](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html#storage-inventory-contents).
  - **Inventory Report Bucket** — Destination bucket name where the S3 inventory report is generated.
  - **Inventory Report Path** — Path to the inventory directory excluding the destination bucket name. For example:

<*/inventory//****{SOURCE_BUCKET_NAME}****/inventory-details/*>

> [!NOTE]
> **Note**
> 
> When you initiate a scan, the scanner picks up the latest inventory directory from the list of inventories available in the Inventory report path.
  - **Inventory Token ID and Secret** — See the [AWS guide on Manage access keys (console)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html) for more information.
  - **Region** — The AWS S3 region for the S3 bucket.

> [!NOTE]
> **Note**
> 
> The field is pre-filled based on the defined region in data system instance properties.
  - **Bucket(s)** - The name of the bucket you want to scan.

> [!NOTE]
> **Note**
> 
> The field is pre-filled based on the data system and source bucket name for which you have created the inventory.

## Related

- [Connecting Amazon S3 with Securiti](/connecting-amazon-s3-with-securiti.md)
- [Configure discovery scans in Amazon S3](/configure-discovery-scans-in-amazon-s3.md)
- [Configuring Data Inventory Sync for Amazon S3 (Self-hosted)](/configuring-data-inventory-sync-for-amazon-s3-self-hosted.md)
