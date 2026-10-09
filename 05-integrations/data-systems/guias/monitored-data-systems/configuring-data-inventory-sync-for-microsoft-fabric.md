---
title: "Configuring Data Inventory Sync for Microsoft Fabric"
slug: "configuring-data-inventory-sync-for-microsoft-fabric"
updated: 2026-03-09T08:18:21Z
published: 2026-03-09T08:18:21Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-microsoft-fabric"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Microsoft Fabric

> [!WARNING]
> Important
> 
> If the new UI or Data Inventory Sync isn't available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements to activate it.

The Data Inventory Sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync for your data system instance after the connector activation. Before the connector activation process, fulfill any required prerequisites as highlighted in the [Prerequisites for configuring Microsoft Fabric connector](/latest/docs/prerequisites-for-microsoft-fabric-connector), for successful scanning.

## Prerequisites for Microsoft Fabric Data Inventory Sync

You must fulfill the following prerequisites for your Microsoft Fabric connector to successfully run a Data Inventory Sync on your data system.

### Permissions

> [!WARNING]
> **Important**
> 
> You must activate your connector for Data Inventory Sync results to show in the [Data Command Graph](/latest/docs/using-data-command-graph).

The Microsoft Entra ID application must be granted permissions for:

- Microsoft Fabric APIs
- Power BI Service APIs
- OneLake (storage layer) APIs
- Microsoft Graph (basic user access)

For more information, see [Permissions and use cases section in the Microsoft Fabric landing page](/latest/docs/microsoft-fabric).

### Allowlisting APIs

You must allowlist the following base URLs:

- `https://api.fabric.microsoft.com/`
- `https://onelake.dfs.fabric.microsoft.com/`
- `https://api.fabric.microsoft.com/`
- `https://graph.microsoft.com/`

## Configuring Data Inventory Sync settings

**Classic UI**

After activating the Microsoft Fabric (Self-hosted) connector, wait until the discovery meta is synced. Perform the following steps to run the Data Inventory Sync for Microsoft Fabric.

1. On the **Connector** tab, in the **Inventory Sync Options** section, enable the following settings to suit.

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Enable Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Fabric workspaces - Data inventory: Lakehouse |
2. Select the collections of data resources to be included in your inventory as your scope.

> [!NOTE]
> Note
> 
> Microsoft Fabric contains structured data such as tables. However, because this data is sourced and processed through files, Securiti processes it as unstructured data.

You can select the following scopes:
  - All
  - Workspace(s)
  - Lakehouse(s)
3. Click **Save**

![System settings interface showing inventory sync options and workspace selections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_oldUI_inventorysync.png)
4. Click **Execute** after the update is saved successfully.

For more information, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** message in the **Inventory Sync Options** section.
  - If you want to cancel to the **Data Inventory Sync**, perform the following steps:
    1. Under the **Inventory Sync Options** beside **Status**, click on **Cancel Scan** link.

![Cancel_Sync.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1770575075022.png)
    2. On **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.

![cancel_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1770575121720.png)
5. To view the Scan statistics for inventory scans:

> [!WARNING]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
  1. Once the scan is successful, hover over the tooltip for the **Run Data Inventory Sync** toggle and click **View Inventory Stats.**
  2. On the popup, you can view the statistics for your inventory scans, as described in the table below:

| Scan | Statistics |
| --- | --- |
| Data Inventory Sync | - **Objects Processed**: Displays the total number of objects scanned during the sync. For example, 25. - **Data Size Inventoried**: Displays the total data size scanned during the sync. For example, 338.6 MiB. - **Folders Processed**: Displays the total number of folders scanned during the sync. For example, 2. - **Total Scan Duration**: Displays the total time of the scan. For example, 7m 41s. ![inventorystats_popup_cropped.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5a3cc453-310f-038b-9470-e95b1883dacc(4).png) |

**New UI**

After activating the Microsoft Fabric (Self-hosted) connector, wait until the discovery meta is synced. Perform the following steps to run the Data Inventory Sync for Microsoft Fabric.

1. In the **Inventory** tab, under **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Fabric workspaces - Data inventory: Lakehouse |
2. In the **Inventory Scope** section, select the collections of data resources to be included in your inventory as the scope.

> [!NOTE]
> Note
> 
> Microsoft Fabric contains structured data such as tables. However, because this data is sourced and processed through files, Securiti processes it as unstructured data.

You can select the following scopes:
  - All
  - Workspace(s)
  - Lakehouse(s)

![Settings page for enabling Inventory Sync and selecting workspaces in fabric-test integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_newUI_Inventorysync.png)
3. Click **Save**, and **Execute** after the update is saved successfully.

For more information about the data scanned for inventory, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.
  - If you want to cancel the Data Inventory Sync, perform the following steps:
    1. Under the **Inventory Sync** section beside **Status**, click on **Cancel Scan** link.

![Inventory sync status shows scheduled scan and option to enable inventory sync.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/newUI_cancelscan.png)
    2. On **Cancel the Data Inventory Sync** popup, click **Okay**.

![cancel_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1770575121720.png)

It takes time to complete the Cancel Scan process.
4. To view the Scan statistics for inventory scans:

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

For more information on Scan statistics, see [(New UI) Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).
