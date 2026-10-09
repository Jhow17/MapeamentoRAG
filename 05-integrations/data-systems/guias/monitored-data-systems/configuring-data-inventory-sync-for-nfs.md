---
title: "Configuring Data Inventory Sync for NFS"
slug: "configuring-data-inventory-sync-for-nfs"
updated: 2026-08-31T09:51:21Z
published: 2026-08-31T09:51:21Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-nfs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for NFS

Securiti supports Data Inventory Sync for NFS (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

See [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors), for more information.

You can configure Data Inventory Sync and for your Data system Instance from the **Connector** tab, after the Connector Activation.

#### Prerequisites for configuring Data Inventory Sync for NFS

- Prior to the Data Inventory Sync process, fulfill any required prerequisites as highlighted in the [NFS connectors](/latest/docs/nfs), for successful scanning.
- The Appliance version must be at least 1.127.

#### Scanning limitation

Securiti doesn't collect the NFS owner's information as part of Discovery scan or Data Inventory Sync.

#### Configuring Data Inventory Sync

After authenticating the NFS Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for NFS.

1. In the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Not applicable - Data inventory: Files in NFS shares |
| Exclude Snapshot Directories? | Enable the toggle if you want to exclude `.snapshot` or `~snapshot` directories from the data inventory to reduce the scanning time. > [!NOTE] > Note > > To use this feature, you must upgrade your pod version to release 1.140 or higher. | Excludes files that reside in snapshot directories |
2. Click **Save**
3. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
4. To view the Scan statistics for Inventory scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
