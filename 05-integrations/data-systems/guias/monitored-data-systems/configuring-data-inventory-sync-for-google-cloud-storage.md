---
title: "Configuring Data Inventory Sync for Google Cloud Storage"
slug: "configuring-data-inventory-sync-for-google-cloud-storage"
updated: 2026-08-31T09:11:33Z
published: 2026-08-31T09:11:33Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-google-cloud-storage"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Google Cloud Storage

Securiti supports Data Inventory Sync for Google Cloud Storage (Self-hosted) Data system Connector to collect an inventory of all objects stored in Google Cloud Platform (GCP) buckets and their associated metadata.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

After the connector activation, you can configure Data Inventory Sync and entitlement scanning for your data system instance. Before the connector activation process, fulfill any required prerequisites as highlighted in the section below for successful scanning.

### Prerequisites for configuring Data Inventory Sync

To run the Data Inventory Sync, you must provide the Permissions as described in [Prerequisites for Google Cloud Storage connector](/latest/docs/prerequisites-for-google-cloud-storage-connector). See the section below for Permissions required when using the *Native Inventory* method.

#### Data Inventory sync methods

Securiti offers two primary methods for performing data inventory syncs: *Listing* and *Native Inventory*. Each method uses a different approach to discover your data assets. The Table below explains the difference between the two Data Inventory Sync methods you have.

| Method | Explanation |
| --- | --- |
| Listing | This is the standard and default method that directly queries the Cloud storage service to build an inventory of objects in real-time. It iterates through the list of objects provided by the GCS's API. > [!NOTE] > **Note** > > The *Listing* method is not a content scan of each object; however, it can be less efficient than *Native Inventory* for very large data stores. |
| Native inventory | This method leverages the inventory reports generated directly by your GCS Inventory Reports. This approach is highly efficient as Securiti ingests metadata from these pre-existing reports rather than querying each object individually. To use this method, you must enable the **Use Native Inventory toggle** while [activating the connector](/v1/docs/activate-the-google-cloud-storage-connector-in-securiti) and configure the inventory reporting feature within your Cloud provider's console. To use the *Native Inventory* method, create an inventory report Configuration for GCS buckets, as described in [Inventory report configuration for Blob](/v1/docs/inventory-report-configuration-for-blob). |

#### Permissions for Native Inventory method

- **Roles:** You must assign the following roles to your service account, to use the *Native Inventory* method:
  - `roles/storage.objectViewer` on the destination bucket
  - `roles/storageinsights.viewer` on the project
- **Metadata fields:** Enable the following metadata fields for GCS inventory report, to include non-current versions of a file and ensure that all versions are processed:
  - `timeDeleted`
  - `generation`

![gcs_metadatfields_inventory.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be1ff19e-ba35-84c7-38d2-94329732614b.png)

**​**
- **Delimiter for CSV files**: Securiti ​successfully processes CSV files that use either a comma (`​,`​​) or a semicolon (`​;`​​) as a delimiter. However, as best practice we recommend that you use comma (`​,`​​) as the delimiter when configuring GCS Native Inventory, as shown below.

![Configuration settings for Google Cloud Storage report generation and destination bucket selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/gcs_delimiter.png)

### Configuring Data Inventory Sync

After activating the Google Cloud Storage (Self-hosted) Connector, wait until the Discovery scan metadata is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Google Cloud Storage.

1. On the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: GCP buckets - Data inventory: All objects in the GCP buckets |
| Fetch Resource Tags? | Enable the toggle to fetch tags for the GCS files. > [!NOTE] > **Note** > > It requires additional API calls per object because fetching owner information is not supported in the *Native Inventory* method | GCS file tags |
| Process All Versions? | Enable the toggle to process all versions of the objects if enabled on your GCP bucket. This setting is not supported for *Native Inventory* method. Securiti processes only the latest version of the file if the toggle is deactivated. > [!NOTE] > **Important** > > - Version processing is supported for Pod versions 1.132.0 and above. > - For *Native Inventory* method, the Pod version must be 1.133 and above. > - You must provide the necessary Permissions as specified in [Enabling object versioning for buckets](/v1/docs/securiti-pods-and-elastic-pods). > - You must select the required metadata fields during [Inventory report configuration for Blob](/v1/docs/securiti-pods-and-elastic-pods) You can view the version of files processed in the Data Command Graph using the **Version Of** property for the **Files**. For more information, see [Viewing GCS scan results in the Data Command Graph](/v1/docs/viewing-gcs-scan-results-in-the-data-command-graph). | GCP bucket objects |
2. Click **Save**
3. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
4. To view the Scan statistics for Inventory and Entitlement scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
5. Proceed to [Viewing GCS scan results in the Data Command Graph](/v1/docs/viewing-gcs-scan-results-in-the-data-command-graph) to view the metadata in Data Command Graph.
