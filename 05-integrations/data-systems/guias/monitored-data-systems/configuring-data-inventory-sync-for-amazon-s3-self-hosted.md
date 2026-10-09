---
title: "Configuring Data Inventory Sync for Amazon S3 (Self-hosted)"
slug: "configuring-data-inventory-sync-for-amazon-s3-self-hosted"
updated: 2026-08-31T08:39:10Z
published: 2026-08-31T08:39:10Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-amazon-s3-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Amazon S3 (Self-hosted)

Securiti supports data inventory sync for Amazon S3 (Self-hosted) data system connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure data inventory sync for your data system instance from the **Connector** tab, after the connector activation. Prior to the connector activation process, fulfill any required prerequisites as highlighted in the [Prerequisites section in Configuring Amazon S3 connector](/latest/docs/amazon-s3-connectors-1), for successful scanning.

### Prerequisites

#### Permissions

| Permission | Description |
| --- | --- |
| **s3:ListBucket**: | This permission is required for discovering metadata from Amazon S3 objects in a bucket. |
| **s3:GetObject** | This permission is required for discovering metadata from Amazon S3 downloaded objects. |
| **kms:Decrypt** | This permission is required for discovering metadata from Amazon S3 objects using a customer-managed KMS key |
| **s3:GetObjectAcl** | This permission is required for discovering owners information and fetching S3 tags. |
| **s3:ListBucketVersions** | This permission is required for discovering metadata from Amazon S3 objects including all their versions in a bucket. |
| **s3:GetBucketVersioning** | This permission is required to verify whether versioning is enabled on the bucket before executing the data inventory sync. |
| **s3:ListBucketMultipartUploads** | This permission is required to identify ongoing multipart uploads, which are later used to count incomplete parts. > [!NOTE] > **Note** > > This permission is only required if you want to determine the count of multipart files. |
| **s3:ListMultipartUploadParts** | This permission is required to count all the individual parts of a multipart upload. > [!NOTE] > **Note** > > This permission doesn't work on its own and must be used together with **s3:ListMultipartUploads** to get the count of multipart uploads. |
| **s3:GetObjectVersionTagging** | This permission retrieves additional metadata or all versions of an object, including past versions. > [!NOTE] > **Note** > > This permission is only required if the following toggles are enabled for data inventory sync: |
| **s3:GetObjectVersionAcl** | This permission retrieves the owner info for all versions of an object, including past versions. > [!NOTE] > **Note** > > This permission is only required if the following toggles are enabled for data inventory sync: |
| **Include all versions** setting | To include multiple versions in the inventory scope, you must enable the **Include all versions** setting in Amazon, as shown below. ![s3_includeallversions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cdfa18aa-1fb5-08bd-e652-de05fe730b84.png) |

#### Supported authentications for data inventory sync methods

You must [activate the Amazon S3 connector](/v1/docs/activate-the-amazon-s3-connector-in-securiti) using authentication type that matches your preferred data inventory sync method. Securiti performs the data inventory sync for Amazon S3 depending on the authentication type you selected while activating the connector. See the list of data inventory sync methods below.

| Method | Supported authentication type | Explanation |
| --- | --- | --- |
| Listing | - IAM Role - IAM Key - Auto-generate Dynamic Credentials | This is the standard and default method that directly queries the cloud storage service to build an inventory of S3 objects from the buckets. It iterates through the list of objects provided by the provider's API. > [!NOTE] > **Note** > > The *Listing* method is not a content scan of each object; however, it can be less efficient than *Native Inventory* for very large data stores. |
| Native inventory | - IAM Role - IAM Key - S3 Inventory - Auto-generate Dynamic Credentials | *Native Inventory* method enables more efficient data inventory syncs and lists object metadata by retrieving only the downloadable inventory files. We recommend that you enable the following fields when configuring the inventory report in AWS S3 console: - Bucket name - Key name - Size - Last modified date - Storage class - Object access control list For more information, see [Amazon's documentation on Cataloging data with S3 inventory](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html#storage-inventory-contents). |

#### Configuring inventory in AWS for data inventory sync

For *Native Inventory* method, you must configure inventory in AWS for S3 buckets to list the objects in the bucket and publish the list to a destination account and bucket. For more information, see [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/configure-inventory.html).

> [!NOTE]
> **Note**
> 
> You must have at least one inventory generated report for scanning results. It might take up to 48 hours for Amazon S3 to deliver the first inventory report. For more information, see [S3 inventory list management documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-inventory.html).

## Configuring Data Inventory Sync

After activating the Amazon S3 (Self-hosted) connector, wait until the [Scoping Metadata Sync](/v1/docs/scoping-metadata-syncs-for-connectors) is complete. Perform the following steps to run the Data Inventory Sync for Amazon S3.

1. In the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Not applicable - Data inventory: S3 Objects in Buckets. |
| Fetch Owner? | Enable the toggle if you want to scan and fetch the owner's information. > [!NOTE] > **Note** > > It requires additional API calls per object because fetching owner information is not supported in the *Native Inventory* method | Owner’s information. |
| Fetch Resource Tags? | Enable the toggle if you want to scan tags with S3 objects. > [!NOTE] > **Note** > > It requires additional API calls per object because fetching Resource tags is not supported in the *Native Inventory* method | S3 tags. |
| Process All Versions? | Enable this toggle to process all object versions if versioning is enabled on your S3 bucket. Processing versions include the following: - Existing version - Updated version - Deleted version Securiti processes only the latest version of the file if the toggle is deactivated. > [!NOTE] > **Note** > > Processing all versions requires additional permissions that are mentioned in the [Permissions table](/v1/docs/configuring-data-inventory-sync-for-amazon-s3-self-hosted) above. You can view the version of files processed in the Data Command Graph using the **Version Of** property for the **Files**, as shown below. ![versionof_property.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59f043d3-93eb-ee3a-b322-f0f09dec1b89.png) | Versions of objects. |
2. Click **Save**

![Settings page for enabling inventory sync with various options and status information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Inventory-sync.png)
3. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
4. To view the scan statistics for Inventory scans, see [Viewing Inventory statisitics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

## Related

- [Viewing scan results in Data Command Graph](/viewing-scan-results-for-data-system-connectors.md)
- [Data Inventory Sync and Entitlement Scan for data systems](/data-inventory-sync-for-self-hosted-connectors.md)
