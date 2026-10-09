---
title: "Configure data inventory sync for all Microsoft 365 applications (Hyperdrive)"
slug: "configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive"
updated: 2026-07-16T21:18:00Z
published: 2026-04-06T11:29:34Z
canonical: "helpcenter.securiti.ai/configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configure data inventory sync for all Microsoft 365 applications (Hyperdrive)

# 

This topic covers the data inventory sync for the following applications under the Microsoft 365 connector:

- Microsoft 365 SharePoint Online
- Microsoft 365 OneDrive
- Microsoft 365 Outlook
- Microsoft Teams

> [!NOTE]
> Note
> 
> If Data Inventory Sync is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Securiti supports Data Inventory Sync and entitlement scanning for the Microsoft 365 applications. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

## Prerequisites

- You must allowlist the APIs between your deployed Securiti Pod and the Microsoft Graph and SharePoint APIs to successfully run the Data Inventory Sync. For more information, see [Allowlisting APIs for Microsoft 365 applications](/latest/docs/allowlisting-urls-for-microsoft-365-applications).
- You must ensure that the Entra ID application has the required permissions to run the data inventory sync successfully. For more information, see the [Permissions and use cases section in Microsoft 365.](/latest/docs/microsoft-365#permissions-and-use-cases)

## Run data inventory sync

You can configure data inventory sync in the following ways:

- [Run data inventory sync for all apps](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive#run-data-inventory-sync-for-all-apps)
- [Run data inventory sync for each Microsoft app individually](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive#run-data-inventory-sync-for-each-microsoft-app-individually)

### Run data inventory sync for all apps

Securiti lets you run data inventory sync for all Microsoft apps you connect during the connector authentication. This option lets you save time and sync data inventory across all Microsoft apps.

To run data inventory sync for all apps:

1. Once authentication and scoping inventory sync is complete, in the left sidebar of the Microsoft 365 connector, click **Configuration**.
2. On the bottom of the **Manage** **Configuration** page, click **Run Inventory Sync for All Apps.** This lets you trigger an inventory synchronization for all configured Microsoft 365 applications at once.

> [!NOTE]
> Note
> 
> If you use **Run Inventory Sync for All Apps** option, you can’t modify the scopes because it runs by including **All** inventory scopes.
> 
> If you want to run data inventory sync for specific scopes, you must use the [Run data inventory sync for each Microsoft app individually](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications#run-data-inventory-sync-for-each-microsoft-app-individually).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Inventory-sync-all.png)

### Run data inventory sync for each Microsoft app individually

To perform the Data Inventory Sync:

1. On the left sidebar, choose **Configuration** > **Microsoft 365 (App)** > **Inventory.**
2. On the Inventory Sync page, mark the **Enable Inventory Sync** checkbox to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. Use the following table to understand the scoping inventory for each Microsoft 365 application:

| Microsoft 365 application | Scoping inventory | Data Inventory |
| --- | --- | --- |
| SharePoint Online | SharePoint Sites and libraries. > [!NOTE] > Note > > Data Inventory Sync doesn’t process SharePoint Online locked or blocked sites for any Securiti module. | All Files and Folders for all scoped document libraries and/or sites. |
| OneDrive | Microsoft 365 Groups | Files and folders for all personal (default) drives. |
| Outlook | Outlook groups or users. | Messages, attachments, and folders. > [!NOTE] > Note > > Externally linked inline attachments are not scanned, i.e. images linked in the email’s HTML. |
| Teams | Teams and Channels | Chat and Channel messages |
3. Under **Enable Inventory Sync**, click **Show More Options**, and mark the **Run Entitlement Scan** checkbox. It syncs the entitlement metadata for the discovered resources. This is used in Gencore pipelines. View Permissions on Microsoft 365 application files that are used to restrict prompt responses in our Gencore product.

> [!CAUTION]
> Caution
> 
> - You must connect Microsoft 365 using automatic authentication to run Entitlement scans.
> - Entitlement sync support is not available for manual authentication as Entitlements sync requires you to add Private and Thumbprint certificate

Use the following table to understand the supported entities for Entitlement syncs:

| Microsoft 365 application | Supported entities | Relationship mapping |
| --- | --- | --- |
| OneDrive | - Microsoft 365 Groups - Microsoft 365 Users - Internal and Linked Organizations - AI Agents - Microsoft Entra ID applications | Mapping of which users, groups, application, or AI agents have access to specific OneDrive Files and Folders. |
| Outlook | - Microsoft 365 Groups including distribution lists - Microsoft 365 Users - Internal and Linked Organizations - AI Agents - Microsoft Entra ID applications | Mapping of which users, groups, application, or AI agents have access to specific Outlook Files and Folders. |
| SharePoint Online | - SharePoint Site Groups - Microsoft 365 Groups - Microsoft 365 Users - Internal and linked Organizations - AI Agents - Microsoft Entra ID applications | Mapping of which users, groups, application, or AI agents have access to specific SharePoint Files and Folders. |
| Team | - Microsoft 365 Users - Teams - Channels - Internal and Linked Organizations - AI Agents - Microsoft Entra ID applications | Mapping of which users, groups, application, or AI agents have access to specific Microsoft Teams Files and Folders. |
4. Under the **Inventory Scope**, select the data system scoping items from the menu to include in the data inventory sync. ![Settings for inventory sync and user selection in a configuration interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory-scope.png)
5. Once the Inventory scopes configuration is complete, click **Execute** and then **Save**.
  - It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the Status and Ingestion Status message in the Inventory Sync section.
    - To view the Scan statistics for Inventory and Entitlement scans
    - For more information about the data scanned for inventory and Genstack entitlements, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
  - If you want to cancel the Data Inventory Sync, perform the following steps:
    1. Under the Inventory Sync section beside Status, click on the **Cancel Scan** link.
    2. On the **Cancel the Data Inventory Sync** popup, click **Okay**.

It takes time to complete the Cancel Scan process.
