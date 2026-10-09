---
title: "Configure Data Inventory Sync for Gmail (Google Workspace) (Hyperdrive)"
slug: "configure-data-inventory-sync-for-gmail-google-workspace-hyperdrive"
updated: 2026-09-26T19:52:05Z
published: 2026-09-26T19:52:05Z
canonical: "helpcenter.securiti.ai/configure-data-inventory-sync-for-gmail-google-workspace-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configure Data Inventory Sync for Gmail (Google Workspace) (Hyperdrive)

Securiti supports data inventory sync and entitlement scanning for Configure discovery scans in Gmail (Google Workspace) (self-hosted) data system connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure data inventory sync and entitlement scanning for your data system instance, after the connector activation. Prior to the connector activation process, fulfill any required prerequisites as highlighted in the [section below](/v1/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

## Prerequisites

Complete the following prerequistes run Data Inventory Sync for Gmail (Google Workspace) using Hyperdrive mode:

### 1. Authenticate and connect Gmail (Google Workspace)

You must authenticate and connect your Gmail (Google Workspace) using Self-hosted connector and Hyperdrive mode to run the data inventory sync successfully.

### 2. Assing the scopes

You must assign the following permissions for Domain Wide Delegation run the Data Inventory Sync successfully for Gmail (Google Workspace) using Hyperdrive mode:

| Permissions | Purpose |
| --- | --- |
| `https://www.googleapis.com/auth/admin.directory.customer.readonly` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read the organization's primary domain name, and verifies that users belong to the organization before adding them to the entitlements graph. |
| `https://www.googleapis.com/auth/admin.directory.user.readonly,` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read all workspace users (email, name, org unit, admin status), and build the full user inventory for access mapping. |
| `https://www.googleapis.com/auth/admin.directory.domain.readonly,` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read all domains configured in the workspace and defines the scope or boundary of the scan. |
| `https://www.googleapis.com/auth/admin.directory.group.readonly` | This permission is required for Data Inventory Sync and Entitlement Scan. It lets Securiti read groups and their membership and maps which users belong to which groups. |
| `https://www.googleapis.com/auth/gmail.readonly` | This permission is required for Discovery Scan, Data Inventory Sync, and Entitlement Scan. It lets Securiti read email messages, headers, body, attachments, and mailbox delegate relationships. This permission also scans email content for sensitive data, and for incremental sync via email history |
| `https://www.googleapis.com/auth/drive.metadata.readonly` | This permission is required for Discovery Scan, Data Inventory Sync, and Entitlement Scan. It lets Securiti read metadata, such as name, type, size, owner, sharing for Drive files. This permission also discovers follow Drive-linked attachments found inside emails. |

### Configure Data Inventory Sync for Gmail (Google Workspace)

After activating the Gmail (Google Workspace) connector, wait until the discovery scan meta is synced.

Perform the following steps to run the Data Inventory Sync and entitlement scan for Gmail (Google Workspace).

1. In the **Inventory** tab, under the **Data Inventory Sync**, configure the following settings:
  1. On the **Data Inventory Sync** page, mark the **Enable Inventory Sync** checkbox to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources.
  2. Under the **Enable Inventory Sync**, click **Show More Options**, and mark the **Run Entitlement Scan** checkbox.

Entitlement sync provides visibility into how access and ownership of data are structured within your Gmail (Google Workspace) environment.

| Scan setting | Type of data scanned |
| --- | --- |
| Enable Data Inventory Sync | - Scoping inventory: Domains and Groups - Data inventory: Message content and Attachments |
| Run Entitlement Scan | **Confluence resources:** - Users - Groups - Applications - AI Agents **Relationship mapping:** - Mapping of which users, groups, application, or AI agents have access to specific Gmail mailboxes and files. |
2. (Optional) In the **Data Inventory Sync and Gencore Entitlements Scope** section on the same **Inventory** tab, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - Domains
  - Groups
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

for more information about the data scanned for inventory and Genstack entitlements, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
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
