---
title: "Configuring Data Inventory Sync for Azure Blob Storage (Self-hosted) (Hyperdrive)"
slug: "configuring-data-inventory-sync-for-azure-blob-storage-self-hosted-1"
updated: 2026-05-25T20:28:48Z
published: 2026-05-25T20:28:48Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-azure-blob-storage-self-hosted-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Azure Blob Storage (Self-hosted) (Hyperdrive)

Securiti supports data inventory sync for Azure Blob Storage (Self-hosted) data system connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

See [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors), for more information.

### Prerequisites for configuring Data Inventory Sync for Azure Blob Storage

Before the connector activation process, fulfill any required prerequisites as highlighted in the [Azure Blob Storage connectors](/v1/docs/azure-blob-storage-connectors) for successful scanning.

#### Permissions required

| Authentication type | Permission | Description |
| --- | --- | --- |
| Storage Account | **Read** | This permission is required for discovering metadata from Azure Blobs in containers. |
| - Service Principal - Service Principal with Certificate | **Storage Blob Data Reader** | This role is required for discovering metadata from Azure Blobs in containers and to process all versions of the blob. |
| - Service Principal - Service Principal with Certificate | **Monitoring Reader role** | This role is required for processing all versions of the Azure Blob Storage blobs. |

#### Supported authentications for data inventory sync methods

You must activate the Azure Blob Storage connector using authentication type that matches your preferred data inventory sync method. Securiti performs the data inventory sync for Azure Blob Storage depending on the authentication type you selected while activating the connector. See the list of data inventory sync methods below.

| Method | Supported authentication type | Explanation |
| --- | --- | --- |
| Listing | - Storage Account - Service Principal - Service Principal with Certificate | To use this method, you must not be enabling the **Use Native Inventory toggle** This is the standard method that directly queries the cloud storage service to build an inventory of Blob storage containers in real-time. It iterates through the list of objects provided by the provider's API. > [!NOTE] > **Note** > > The *Listing* method is not a content scan of each object; however, it can be less efficient than *Native Inventory* for very large data stores. |
| Native inventory | - Storage Account - Service Principal - Service Principal with Certificate | This method leverages the inventory reports generated directly by Azure Inventory Reports. This approach is highly efficient as Securiti ingests metadata from these pre-existing reports rather than querying each object individually. To use this method, you must enable the **Use Native Inventory toggle** while [activating the connector](/v1/docs/activate-the-azure-blob-storage-connector-in-securiti) and configure the inventory reporting feature within your cloud provider's console. You must do the following to use the *Native Inventory* method: - Enable [blob inventory in your Azure account](/v1/docs/enable-blob-inventory-in-your-azure-account) - Enable **Use Native Inventory** toggle while [activating the connector](/v1/docs/activate-the-azure-blob-storage-connector-in-securiti) For discovery scans, *Native Inventory* method is enabled if you configure your discovery scan without the prefix scan condition, along with fulfilling the above mentioned prerequisites. > [!NOTE] > **Note** > > Securiti doesn’t list the Blob containers if the inventory report generated in your Microsoft Azure account is older than 30 days. By default, the latest inventory report is used for listing blobs in containers. |

### Configuring Data Inventory Sync

After activating the Azure Blob Storage (Self-hosted) connector, wait until the discovery scan meta is synced. Perform the following steps to run Data Inventory Sync for Azure Blob Storage.

1. In the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Azure Containers. - Data inventory: Azure Blobs in containers. |
| Process All Versions? | Enable the toggle to process all versions of the blob if enabled on your Azure account. This setting is not supported for the *Native Inventory* method. Securiti processes only the latest version of the file if the toggle is deactivated. > [!NOTE] > **Important** > > - Version processing is not supported for **Storage Account** authentication method. > - Version processing is supported for pod versions 1.132.0 and above only. > - For *Native Inventory* method, the pod version must be 1.133 and above. > - You must provide the necessary permissions as specified in the section above. > - You must select the required blob subtypes to process all versions in data inventory sync. For more information, see [Enable blob inventory in your Azure account](/latest/docs/enable-blob-inventory-in-your-azure-account). You can view the version of files processed in the Data Command Graph using the **Version Of** property for the **Files**, as shown below. ![versionof_property.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59f043d3-93eb-ee3a-b322-f0f09dec1b89(1).png) | Versions of blobs |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.

![Interface displaying Azure Blob Storage with selected container and save button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/blobscopes.png)
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

For more information on Scan statistics, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive).

> [!NOTE]
> **Note**
> 
> Scan statistics are available only after the scan is successfully completed.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.
  - If you want to cancel the Data Inventory Sync, perform the following steps:
    1. Under the **Inventory Sync** section beside **Status**, click on **Cancel Scan** link.
    2. On **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.

## Related

- [Data Inventory Sync and Entitlement Scan for data systems](/data-inventory-sync-for-self-hosted-connectors.md)
- [Enable blob inventory in your Azure account](/enable-blob-inventory-in-your-azure-account.md)
