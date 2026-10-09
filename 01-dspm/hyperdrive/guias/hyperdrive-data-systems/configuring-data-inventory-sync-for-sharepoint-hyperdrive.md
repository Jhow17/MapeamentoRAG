---
title: "Configuring Data Inventory Sync for SharePoint (Hyperdrive)"
slug: "configuring-data-inventory-sync-for-sharepoint-hyperdrive"
updated: 2026-09-21T12:04:00Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-sharepoint-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for SharePoint (Hyperdrive)

Securiti supports Data inventory sync and entitlement scanning for the Microsoft 365 SharePoint Online data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

## Prerequisites

1. You must allowlist the APIs between your deployed Securiti Pod and the Microsoft Graph and SharePoint APIs to successfully run the Data Inventory Sync. For more information, see [Allowlisting URLs and APIs for SharePoint Online (Hyperdrive)](/latest/docs/allowlisting-urls-and-apis-for-sharepoint-online-hyperdrive).
2. You must ensure that the Entra ID application has the required permissions to run the data inventory sync successfully. For more information, see the permissions required for SharePoint Data Inventory Sync section in [use cases and permissions for Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-1).

### Run data inventory sync for Microsoft SharePoint Online

To perform the Data Inventory Sync:

1. On the left sidebar, choose **Inventory.**
2. On the Inventory Sync page, mark the **Enable Inventory Sync** checkbox to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources.

Use the following table to understand the scoping inventory for Microsoft 365 SharePoint Online:

| Scan setting | Scoping inventory | Data Inventory |
| --- | --- | --- |
| Run Data Inventory Sync | SharePoint Sites and libraries. > [!NOTE] > Note > > Data Inventory Sync doesn’t process SharePoint Online locked or blocked sites for any Securiti module. | All Files and Folders for all scoped document libraries and/or sites. |
3. Under **Enable Inventory Sync**, click **Show More Options**, and mark the **Run Entitlement Scan** checkbox. Entitlement sync provides visibility into how access and ownership of data are structured within your SharePoint Online environment. Entitlement sync captures the following entities and relationships:

| Category | Description |
| --- | --- |
| SharePoint Online resources | - SharePoint Site Groups - Microsoft 365 Groups - Microsoft 365 Users - Internal and linked Organizations - AI Agents - Microsoft Entra ID applications |
| Relationship mapping | Mapping of which users, groups, application, or AI agents have access to specific SharePoint Files and Folders. |
4. Mark the **Include System Libraries** checkbox to sync the system-managed libraries in your SharePoint sites.

This option includes Style Library, Master Page Gallery, and Form Templates
5. Under the **Inventory Scope**, select the data system scoping items from the menu to include in the data inventory sync. You can select the following scopes:
  - All
  - Group(s)
  - User(s)
6. Once the Inventory scopes configuration is complete, click **Execute** and then **Save**.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the Status and Ingestion Status message in the Inventory Sync section.
    - To view the Scan statistics for Inventory and Entitlement scans
    - For more information about the data scanned for inventory and Genstack entitlements, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
  - If you want to cancel the Data Inventory Sync, perform the following steps:
    1. Under the Inventory Sync section beside Status, click on the **Cancel Scan** link.
    2. On the **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.

## Incremental data inventory sync

Securiti lets you run incremental data inventory sync for Microsoft 365 SharePoint Online using Hyperdrive mode. After the initial full Data Inventory Sync, all subsequent syncs run incrementally.

Incremental data inventory sync for Microsoft 365 SharePoint Online use Activity Analysis logs to identify and process only the changes made since the last inventory scan, instead of rescanning the entire data source.

To run an incremental inventory scan, **Activity Analysis** must be enabled and must have completed at least one run after the previous inventory scan finishes. Securiti uses the activity data collected during this run to determine which resources have changed.

During an incremental scan, Securiti processes changes from the start time of the previous inventory scan to the end time of the last completed Activity Analysis run, provided that the Activity Analysis run completed after the previous inventory scan.
