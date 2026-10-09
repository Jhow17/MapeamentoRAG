---
title: "Configuring Data Inventory Sync for ADLS connector"
slug: "configuring-data-inventory-sync-for-adls-connector-en"
updated: 2026-08-31T08:43:40Z
published: 2026-08-31T08:43:40Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-adls-connector-en"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for ADLS connector

Securiti supports data inventory sync and entitlement scanning for Azure Data Lake Storage (ADLS) (Self-hosted) data system connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

You can configure data inventory sync scanning for your data system instance after the connector is activated. Before the connector activation process, fulfill any required prerequisites as described below for successful scanning.

### Prerequisites for running Data Inventory Sync for OneDrive

#### Permissions required for ADLS Data Inventory Sync

You must configure the required permissions in [Obtain authentication credentials in ADLS](/latest/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2) for running Data Inventory sync on the ADLS data system instance.

To retrieve the last access time for your ADLS files, in the **Connector** tab, mark the **Retrieve Last Access Time** checkbox, as shown below.

> [!CAUTION]
> Caution
> 
> Last access time is not included in the Azure Data Lake Storage inventory by default. When the checkbox is enabled, an additional API call is triggered for each document to retrieve the data. This can significantly increase API consumption and extend processing time.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configuring-data-inventory-sync-for-adls-connector-en-image-3um9wip6.png)

### Configuring Data Inventory Sync

After activating the ADLS connector, wait until the discovery scan metadata is synced. Perform the following steps to run the Data Inventory Sync and entitlement scan for ADLS.

1. In the **Inventory** tab, under the **Data Inventory Sync**, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Enable Data Inventory Sync | Enable the toggle to sync the metadata for your data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Azure Data Lake file system(s) - Data inventory: Containers or Folder path(s) |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - File systems
  - Folder paths

> [!NOTE]
> **Note**
> 
> For new connectors, the scope is selected "None" by default with Inventory Sync Options disabled. For existing connectors, you must reconfigure the connector to add scopes.
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory scans:

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

For more information on Scan statistics, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

For more information on viewing ADLS metadata in graph, proceed to [Viewing ADLS (self-hosted) metadata in Securiti](/latest/docs/viewing-adls-self-hosted-metadata-in-securiti-en).
