---
title: "Google Cloud Storage"
slug: "google-cloud-storage-connector-1"
status: "new"
updated: 2026-04-28T04:36:08Z
published: 2026-04-28T04:36:08Z
canonical: "helpcenter.securiti.ai/google-cloud-storage-connector-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google Cloud Storage

Google Cloud Storage (GCS) is a highly scalable, durable, and secure object storage service designed for various data storage needs. It is optimized for storing large volumes of unstructured data, such as images, videos, and backups. GCS provides flexible data management through a web interface and APIs. The Google Cloud Storage connector falls under the [category of monitored, unstructured data systems](/v1/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Google Cloud Storage (Self-hosted) | It supports: - Sensitive Data Intelligence - DSR Automation |

### Supported pods type

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

You must select the authentication method according to the modules or scans you want to run. For more information on supported authentication method for specific scans or modules, see the permissions and use cases table below.

| Authentication method | Authentication credentials |
| --- | --- |
| Credentials File | - Project ID - Bucket - Credentials File (JSON file) |
| IAM Service Account | - Project ID - Bucket - IAM Service Account |

#### Keyring support for Google Cloud Storage

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**. For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **AWS Secrets Manager**. For more information, see [Configuring AWS Secrets Manager credential vaults](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash**. For more information, see [Configuring Credstash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault).
- **GCP Secret Manager**. For more information, see [Configuring GCP Secret Manager credential vaults](/latest/docs/configuring-credential-vaults-gcp-secret-manager-credential-vault).

### Supported items for Inventory and Classification scans

Securiti supports [Data Inventory Sync for Google Cloud Storage](/latest/docs/configuring-data-inventory-sync-for-google-cloud-storage) as well as [discovery scan](/latest/docs/configure-discovery-scans-in-google-cloud-storage) for sensitive data discovery for the following items:

- Objects in GCP buckets.

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

#### Data Inventory sync methods

Securiti offers two primary methods for performing data inventory syncs: *Listing* and *Native Inventory*. Each method uses a different approach to discover your data assets. The table below explains the difference between the two data inventory sync methods you have.

| Method | Explanation |
| --- | --- |
| Listing | This is the standard and default method that directly queries the cloud storage service to build an inventory of objects in real-time. It iterates through the list of objects provided by the provider's API. > [!NOTE] > **Note** > > The *Listing* method is not a content scan of each object; however, it can be less efficient than *Native Inventory* for very large data stores. |
| Native inventory | This method leverages the inventory reports generated directly by your GCS Inventory Reports. This approach is highly efficient as Securiti ingests metadata from these pre-existing reports rather than querying each object individually. To use this method, you must enable the **Use Native Inventory toggle** while activating the connector and configure the inventory reporting feature within your cloud provider's console. |

### Prerequisites for configuring Google Cloud Storage connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Google Cloud Storage with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and GCS API endpoints. For more information, see the allow-listed URLs section in [Elastic Pods V2](/latest/docs/elastic-pods-v2).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access in Google Cloud Platform (GCP)

We assume you have access to the GCP account with admin privileges.

#### 3. Service Account creation in GCP

You must create a service account with required roles and permissions in GCP.

#### 4. Create inventory report configuration for Data inventory sync

If you want to run data inventory sync using the *Native Inventory* method, you must create inventory report configuration in your GCP account. Securiti uses these inventory reports to pull inventory information.

For more information, see [Inventory report configuration for Google Cloud Storage](/latest/docs/inventory-report-configuration-for-blob).

#### 5. Use cases and permissions for Google Cloud Storage

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | NA | - `monitoring.timeSeries.list` - `monitoring.viewer` - `storage.buckets.get` - `storage.buckets.getIamPolicy ` - `storage.buckets.list ` - `storage.objects.get` - `storage.objects.list` For *Native Inventory* method in Data Inventory Sync: - `roles/storage.objectViewer` (on the destination bucket) - `roles/storageinsights.viewer` (on the project) | - These permissions let Securiti read the objects and their metadata in GCS for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. - The `storage.buckets.getIamPolicy` permission is used to fetch the bucket ACL (owner) in case object owner is not found during the scans. - The `monitoring.timeSeries.list` permission is used to evaluate bucket size. - The **Monitoring Viewer** (`roles/monitoring.viewer` roles is required to view statistics for soft deleted and multipart uploads in IAM service account. - The `roles/storage.objectViewer` and `roles/storageinsights.viewer` roles must be added to the service account to use *Native Inventory* method. |

### Connect Google Cloud Storage with Securiti

**New UI**

To configure the Google Cloud Storage connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

To use the Google Cloud Storage data system, you must link your structured on-premises database to Securiti.
3. [Inventory report configuration for Google Cloud Storage](/latest/docs/inventory-report-configuration-for-blob), to use the *Native Inventory* method for Data Inventory Sync.

> [!NOTE]
> **Note**
> 
> Skip this step if you are using the default *Listing* method for running Data Inventory Syncs.
4. Obtain authentication credentials in Google Cloud Storage. For more information, see [Prerequisites for Google Cloud Storage connector](/latest/docs/prerequisites-for-google-cloud-storage-connector).
  - For **Credentials File** authentication, see [Using Credentials File authentication](/latest/docs/using-credentials-file-authentication)
  - For **IAM Service Account**, see [Using IAM Service Account authentication](/latest/docs/using-iam-service-account-authentication)
5. [(New UI) Connecting Google Cloud Storage with Securiti](/latest/docs/new-ui-connecting-google-cloud-storage-with-securiti).
6. [Configuring Data Inventory Sync for Google Cloud Storage](/latest/docs/configuring-data-inventory-sync-for-google-cloud-storage).
7. [Configure discovery scans in Google Cloud Storage](/latest/docs/configure-discovery-scans-in-google-cloud-storage).
8. [Viewing GCS scan results in the Data Command Graph](/latest/docs/viewing-gcs-scan-results-in-the-data-command-graph).

**Classic UI**

To configure the Google Cloud Storage connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

To use the Google Cloud Storage data system, you must link your structured on-premises database to Securiti.
3. [Inventory report configuration for Google Cloud Storage](/latest/docs/inventory-report-configuration-for-blob), to use the *Native Inventory* method for Data Inventory Sync.

> [!NOTE]
> **Note**
> 
> Skip this step if you are using the default *Listing* method for running Data Inventory Syncs.
4. Obtain authentication credentials in Google Cloud Storage. For more information, see [Prerequisites for Google Cloud Storage connector](/latest/docs/prerequisites-for-google-cloud-storage-connector).
  - For **Credentials File** authentication, see [Using Credentials File authentication](/latest/docs/using-credentials-file-authentication)
  - For **IAM Service Account**, see [Using IAM Service Account authentication](/latest/docs/using-iam-service-account-authentication)
5. [Activate the Google Cloud Storage connector in Securiti](/latest/docs/activate-the-google-cloud-storage-connector-in-securiti).
6. [Configuring Data Inventory Sync for Google Cloud Storage](/latest/docs/configuring-data-inventory-sync-for-google-cloud-storage).
7. [Configure discovery scans in Google Cloud Storage](/latest/docs/configure-discovery-scans-in-google-cloud-storage).
8. [Viewing GCS scan results in the Data Command Graph](/latest/docs/viewing-gcs-scan-results-in-the-data-command-graph).

For more information about authentication and configuration issues, see [Troubleshooting for Google Cloud Storage connector](/latest/docs/troubleshooting-for-google-cloud-storage-connector).

For more information about how Securiti uses the GCS data to respond to DSR requests, see [Fulfilling DSR requests for Google Cloud Storage](/latest/docs/fulfilling-dsr-requests-for-google-cloud-storage).
