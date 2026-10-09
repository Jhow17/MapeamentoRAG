---
title: "Configuring Data Inventory Sync for Teams (Hyperdrive)"
slug: "configuring-data-inventory-sync-for-teams-hyperdrive"
updated: 2026-04-06T11:30:05Z
published: 2026-04-06T11:30:05Z
canonical: "helpcenter.securiti.ai/configuring-data-inventory-sync-for-teams-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for Teams (Hyperdrive)

Securiti supports Data Inventory Sync and entitlement scanning for the Microsoft Teams Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync.

## Prerequisites

1. Allowlist the URLs for discovery scans specified in [Allowlisting URLs and APIs for Teams (Hyperdrive)](/latest/docs/allowlisting-urls-and-apis-for-outlook-hyperdrive-1).
2. Assign application permissions for the data inventory sync use case. For more information, see [Use cases and permissions for Microsoft Teams](/latest/docs/microsoft-teams-1).

### Run data inventory sync for Microsoft Teams

To perform the Data Inventory Sync:

1. On the left sidebar, choose **Inventory.**
2. On the Inventory Sync page, mark the **Enable Inventory Sync** checkbox to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources.

| Scan setting | Scoping inventory | Data Inventory |
| --- | --- | --- |
| Run Data Inventory Sync | Teams and Channels | Chat and Channel messages |
3. Under **Enable Inventory Sync**, click **Show More Options**, and mark the **Run Entitlement Scan** checkbox. Entitlement sync provides visibility into how access and ownership of data are structured within your SharePoint Online environment.

Entitlement sync captures the following entities and relationships:

| Category | Description |
| --- | --- |
| Teams resources | - Microsoft 365 Users - Teams - Channels - Internal and Linked Organizations - AI Agents - Microsoft Entra ID applications |
| Relationship mapping | Mapping of which users, groups, application, or AI agents have access to specific Microsoft Teams Files and Folders. |
4. Under the **Inventory Scope**, select the data system scoping items from the menu to include in the data inventory sync.

For more information on available scopes for each data system, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors). ![Settings for inventory sync and user selection in a configuration interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory-scope.png)
5. Once the Inventory scopes configuration is complete, click **Execute** and then **Save**.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the Status and Ingestion Status message in the Inventory Sync section.
    - To view the Scan statistics for Inventory and Entitlement scans
    - For more information about the data scanned for inventory and Genstack entitlements, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
  - If you want to cancel the Data Inventory Sync, perform the following steps:
    1. Under the Inventory Sync section beside Status, click on the **Cancel Scan** link.
    2. On the **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.
