---
title: "Configuring Data Inventory Sync for NFS (Hyperdrive)"
slug: "configuring-data-inventory-sync-for-nfs-hyperdrive"
updated: 2026-03-10T20:02:24Z
published: 2026-03-10T20:02:24Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-nfs-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for NFS (Hyperdrive)

Securiti supports Data Inventory Sync for NFS (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

See [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors), for more information.

You can configure Data Inventory Sync and for your Data system Instance from the **Connector** tab, after the Connector Activation.

#### Prerequisites for configuring Data Inventory Sync for NFS

- Prior to the Data Inventory Sync process, fulfill any required prerequisites as highlighted in the [NFS](/latest/docs/nfs#prerequisites), for successful scanning.
- The Appliance version must be at least 1.127.

#### Scanning limitation

Securiti doesn't collect NFS owner's information as part of Discovery scan or Data Inventory Sync.

#### Configuring Data Inventory Sync

After authenticating the NFS Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for NFS.

1. In the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Not applicable - Data inventory: Files in NFS shares |
| Exclude Snapshot Directories? | Enable the toggle if you want to exclude `.snapshot` or `~snapshot` directories from the data inventory to reduce the scanning time. > [!NOTE] > Note > > To use this feature, you must upgrade your pod version to release 1.140 or higher. | Excludes files that reside in snapshot directories |
2. Click **Save**
3. Click **Execute** after the update is saved successfully.

See Data Inventory Sync for self-hosted connectors for more information about the data scanned for inventory.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** message in the **Inventory Sync Options** section.
  - If you want to cancel the **Data Inventory Sync**, perform the following steps:
    1. Under the **Inventory Sync Options** beside **Status**, click on the **Cancel Scan** link.

![iaasDIS_cancelscan_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-92b09589-1ad3-031b-faaf-1f9fd73abfea(2).png)
    2. On the **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.

![iaasDIS_cancelscan_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a90a67b6-aae0-eb99-2176-239fdcbe3293(2).png)
4. To view the Scan statistics for Inventory scans:

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

For more information on Scan statistics, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive).
