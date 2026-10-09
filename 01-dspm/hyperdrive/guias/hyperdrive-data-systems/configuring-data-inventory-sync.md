---
title: "Configuring Data Inventory Sync for OneDrive (Hyperdrive)"
slug: "configuring-data-inventory-sync"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for OneDrive (Hyperdrive)

Securiti supports Data Inventory Sync and entitlement scanning for the Microsoft 365 OneDrive Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

## Prerequisites

Complete the following steps before proceeding to configure data inventory sync:

1. Allowlist the URLs for discovery scans specified in [Allowlisting URLs and APIs for OneDrive (Hyperdrive)](/latest/docs/allowlisting-urls-and-apis-for-onedrive-hyperdrive).
2. Assign application permissions for the data inventory sync use case. For more information, see [Use cases and permissions for Microsoft 365 OneDrive](/latest/docs/connect-microsoft-365-sharepoint-online).

### Run data inventory sync for Microsoft OneDrive

To perform the Data Inventory Sync:

1. On the left sidebar, choose **Inventory.**
2. On the Inventory Sync page, mark the **Enable Inventory Sync** checkbox to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources.

| Data system | Scoping inventory | Data Inventory |
| --- | --- | --- |
| Microsoft 365 OneDrive | Groups or Users | Files and folders for all personal (default) drives. |
3. Under **Enable Inventory Sync**, click **Show More Options**, and mark the **Run Entitlement Scan** checkbox. It syncs the entitlement metadata for the discovered resources.

Use the following table to understand the scoping inventory for Microsoft 365 OneDrive:
4. Under **Enable Inventory Sync**, click **Show More Options**, and mark the **Run Entitlement Scan** checkbox. Entitlement sync provides visibility into how access and ownership of data are structured within your OneDrive environment. Entitlement sync captures the following entities and relationships:

| Category | Description |
| --- | --- |
| OneDrive resources | - Microsoft 365 Groups - Microsoft 365 Users - Internal and Linked Organizations - AI Agents - Microsoft Entra ID applications |
| Relationship mapping | Mapping of which users, groups, application, or AI agents have access to specific OneDrive Files and Folders. |
5. Under the **Inventory Scope**, select the data system scoping items from the menu to include in the data inventory sync. You can select the following scopes:
  - All
  - Group(s)
  - User(s) ![Settings for inventory sync and user selection in a configuration interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory-scope.png)
6. Once the Inventory scopes configuration is complete, click **Execute** and then **Save**.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the Status and Ingestion Status message in the Inventory Sync section.
    - To view the Scan statistics for Inventory and Entitlement scans
    - For more information about the data scanned for inventory and Genstack entitlements, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
  - If you want to cancel the Data Inventory Sync, perform the following steps:
    1. Under the Inventory Sync section beside Status, click on the **Cancel Scan** link.
    2. On the **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.

## Incremental data inventory sync

Securiti lets you run incremental data inventory sync for Microsoft 365 OneDrive using Hyperdrive mode. After the initial full Data Inventory Sync, all subsequent syncs run incrementally.

Incremental data inventory sync for Microsoft 365 OneDrive use Activity Analysis logs to identify and process only the changes made since the last inventory scan, instead of rescanning the entire data source.

To run an incremental inventory scan, **Activity Analysis** must be enabled and must have completed at least one run after the previous inventory scan finishes. Securiti uses the activity data collected during this run to determine which resources have changed.

During an incremental scan, Securiti processes changes from the start time of the previous inventory scan to the end time of the last completed Activity Analysis run, provided that the Activity Analysis run completed after the previous inventory scan.
