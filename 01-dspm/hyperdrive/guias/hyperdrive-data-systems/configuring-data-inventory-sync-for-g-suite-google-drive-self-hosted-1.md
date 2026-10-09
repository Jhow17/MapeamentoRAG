---
title: "Configuring Data Inventory Sync for Google Drive (Google Workspace)(Hyperdrive)"
slug: "configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted-1"
updated: 2026-07-20T20:56:59Z
published: 2026-07-20T20:56:59Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Google Drive (Google Workspace)(Hyperdrive)

Securiti supports Data Inventory Sync and entitlement scanning for Google Drive (Google Workspace) Self-hosted Data system connector using Hyperdrove. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance from the **Inventory** tab on , after the connector activation. Prior to the connector activation process, fulfill any required prerequisites as highlighted in the section below, for successful scanning.

## Prerequisites for configuring Data Inventory Sync for Google Drive (Google Workspace)

You must complete the following prerequisites for configuring Data Inventory Sync for Google Drive (Google Workspace) connector authenticated using Hyperdrive mode:

1. **Assign OAuth scopes**

To run the Data Inventory Sync and entitlement scan for Google Drive (Google Workspace) connector authenticated using Hyperdrive mode, add the permissions under OAuth scopes section of your Google Workspace domain, as described in the list below:
  - https://www.googleapis.com/auth/admin.directory.customer.readonly
  - https://www.googleapis.com/auth/admin.directory.user.readonly
  - https://www.googleapis.com/auth/admin.directory.domain.readonly
  - https://www.googleapis.com/auth/admin.directory.group.readonly
  - https://www.googleapis.com/auth/drive.readonly
  - https://www.googleapis.com/auth/drive.metadata.readonly
  - https://www.googleapis.com/auth/drive.photos.readonly
  - https://www.googleapis.com/auth/admin.directory.orgunit.readonly
2. **Enable Drive & Docs service** You must enable the Drive & Docs service for the user who is used in the connector activation, as shown below.

![Admin settings for Google Drive and Docs, showing service status options for users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/docs-n-drive-api.png)

### Configuring Data Inventory Sync

After activating the Google Drive (Google Workspace) Self-hosted connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for Google Drive (Google Workspace).

1. On the **Inventory** tab, under the **Inventory Sync** section, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Google groups - Data inventory: Files and folders in My Drive and Shared Drives. |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. | **Resources:** - Users - Groups - Applications - AI Agents **Relationship mapping:** - Mapping of which users, groups, application, or AI agents have access to specific Google Drive files. |
2. (Optional) In the **Inventory Scope** section on the same **Inventory Sync** section, select the collections of data resources to be included in your inventory.
  1. You can select either **Group(s)** or set the scope to **My Drive(s) and Shared Drive(s).**

> [!NOTE]
> **Important**
> 
> When you scope a scan to specific groups, Securiti only scans shared drives that those users have access to. Scans configured for "All Groups" continue to process all shared drives in your organization. This ensures more efficient and relevant scan results. Securiti does not scan any personal or shared drive if "None" is selected.
3. Click **Save**
4. Click **Execute** after the update is saved successfully.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.
  - If you want to cancel the Data Inventory Sync, perform the following steps:
    1. Under the **Inventory Sync** section beside **Status**, click on **Cancel Scan** link.
    2. On **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.
5. To view the Scan statistics for Inventory and Entitlement scans:

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

For more information on Scan statistics, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive).
