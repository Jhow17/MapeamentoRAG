---
title: "Google Cloud Storage (Hyperdrive)"
slug: "google-cloud-storage-hyperdrive"
status: "new"
updated: 2026-05-25T20:50:03Z
published: 2026-05-25T20:50:08Z
canonical: "helpcenter.securiti.ai/google-cloud-storage-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Google Cloud Storage (Hyperdrive)

Google Cloud Storage (GCS) is a highly scalable, durable, and secure object storage service designed for various data storage needs. It is optimized for storing large volumes of unstructured data, such as images, videos, and backups. GCS provides flexible data management through a web interface and APIs. The Google Cloud Storage connector falls under the [category of monitored, unstructured data systems](/v1/docs/managing-data-system-connectors).

## Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Google Cloud Storage (Self-hosted) | It supports: - Sensitive Data Intelligence - Discovery Scan (Only Listing method) - Data Inventory Sync |

## Supported pod type

- Securiti Outpost deployment

## Supported authentication methods

You must select the authentication method according to the modules or scans you want to run. For more information on supported authentication method for specific scans or modules, see the permissions and use cases table below.

| Authentication method | Authentication credentials |
| --- | --- |
| Credentials File | - Project ID - Bucket - Credentials File (JSON file) |
| IAM Service Account | - Project ID - Bucket - IAM Service Account |

### Keyring support

Keyring support is not available for data systems using Hyperdrive.

## Supported items for Inventory and Classification Scans

Securiti supports [discovery scan](/latest/docs/configure-discovery-scans-in-google-cloud-storage-1) as well as [discovery scan](/latest/docs/configure-discovery-scans-in-google-cloud-storage) for sensitive data discovery for the following items:

- Objects in GCP buckets.

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors) and [Understanding Discovery Scans](/latest/docs/discovery-scans).

#### Data Inventory sync methods

Securiti offers two primary methods for performing data inventory syncs: *Listing* and *Native Inventory*. Each method uses a different approach to discover your data assets. The table below explains the difference between the two data inventory sync methods you have.

| Method | Explanation |
| --- | --- |
| Listing | This is the standard and default method that directly queries the cloud storage service to build an inventory of objects in real-time. It iterates through the list of objects provided by the provider's API. > [!NOTE] > **Note** > > The *Listing* method is not a content scan of each object; however, it can be less efficient than *Native Inventory* for very large data stores. |
| Native inventory | This method leverages the inventory reports generated directly by your GCS Inventory Reports. This approach is highly efficient as Securiti ingests metadata from these pre-existing reports rather than querying each object individually. To use this method, you must enable the **Use Native Inventory toggle** while activating the connector and configure the inventory reporting feature within your cloud provider's console. |

## Prerequisites

### Outpost deployment

If you use Hyperdrive mode while creating a data system instance, you must deploy Securiti Outpost, which uses AWS services to scale scanning operations. For more information, see [Securiti Outpost deployment](/latest/docs/securiti-outpost-deployment).

#### Admin access in Google Cloud Platform (GCP)

We assume you have access to the GCP account with admin privileges.

#### Service Account creation in GCP

You must create a service account with required roles and permissions in GCP.

#### Create inventory report configuration for Data inventory sync

If you want to run data inventory sync using the *Native Inventory* method, you must create inventory report configuration in your GCP account. Securiti uses these inventory reports to pull inventory information.

For more information, see [Inventory report configuration for Google Cloud Storage (Hyperdrive)](/latest/docs/inventory-report-configuration-for-blob-hyperdrive).

#### Use cases and permissions for Google Cloud Storage

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync | NA | - `monitoring.timeSeries.list` - `monitoring.viewer` - `storage.buckets.get` - `storage.buckets.getIamPolicy ` - `storage.buckets.list ` - `storage.objects.get` - `storage.objects.list` For *Native Inventory* method in Data Inventory Sync: - `roles/storage.objectViewer` (on the destination bucket) - `roles/storageinsights.viewer` (on the project) | - These permissions let Securiti read the objects and their metadata in GCS for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. - The `storage.buckets.getIamPolicy` permission is used to fetch the bucket ACL (owner) in case object owner is not found during the scans. - The `monitoring.timeSeries.list` permission is used to evaluate bucket size. - The **Monitoring Viewer** (`roles/monitoring.viewer` roles is required to view statistics for soft deleted and multipart uploads in IAM service account. - The `roles/storage.objectViewer` and `roles/storageinsights.viewer` roles must be added to the service account to use *Native Inventory* method. |

### Connect Google Cloud Storage with Securiti

To configure the Google Cloud Storage connector, perform the procedures in the following topics:

1. Configure the Outpost as described in [Securiti outpost deployment](/latest/docs/securiti-outpost-deployment)..

To use the Google Cloud Storage data system, you must link your structured on-premises database to Securiti.
2. [Inventory report configuration for Google Cloud Storage (Hyperdrive)](/latest/docs/inventory-report-configuration-for-blob-hyperdrive) to use the *Native Inventory* method for Data Inventory Sync.

> [!NOTE]
> **Note**
> 
> Skip this step if you are using the default *Listing* method for running Data Inventory Syncs.
3. Obtain authentication credentials in Google Cloud Storage. For more information, see [Prerequisites for Google Cloud Storage connector](/latest/docs/prerequisites-for-google-cloud-storage-connector).
  - For **Credentials File** authentication, see [Using Credentials File authentication](/latest/docs/using-credentials-file-authentication)
  - For **IAM Service Account**, see [Using IAM Service Account authentication](/latest/docs/using-iam-service-account-authentication)
4. [(New UI) Connecting Google Cloud Storage with Securiti](/latest/docs/new-ui-connecting-google-cloud-storage-with-securiti).
5. [Configuring Data Inventory Sync for Google Cloud Storage (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-google-cloud-storage-1).
6. [Configure discovery scans in Google Cloud Storage (Hyperdrive)](/latest/docs/configure-discovery-scans-in-google-cloud-storage-1).

> [!NOTE]
> Note
> 
> Native inventory method support is not available for Google Cloud Storage discovery scan.

## Additional resources

- [Troubleshooting for Google Cloud Storage connector (Hyperdrive)](/latest/docs/troubleshooting-for-google-cloud-storage-connector-1).
