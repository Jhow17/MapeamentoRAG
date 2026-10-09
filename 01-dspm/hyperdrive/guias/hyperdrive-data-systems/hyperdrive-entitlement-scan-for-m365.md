---
title: "Hyperdrive Entitlement Scan for M365"
slug: "hyperdrive-entitlement-scan-for-m365"
updated: 2026-07-20T12:38:53Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/hyperdrive-entitlement-scan-for-m365"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Entitlement Scan for M365

Hyperdrive Entitlement Scan for M365 provides visibility into who, and what, can access data across M365 services, including Outlook, OneDrive, SharePoint, and Microsoft Teams.

You can configure Entitlement Scan centrally for all supported Microsoft 365 connectors using the M365 integration in Hyperdrive, which enables unified configuration for Outlook, OneDrive, SharePoint, and Microsoft Teams. Alternatively, you can configure Entitlement Scan individually for each connector based on your requirements.

By leveraging entitlement metadata collected during the scan, it enables organizations to identify which users, groups, applications, and AI agents have access to and ownership of discovered data, and what sensitive data that data contains. This helps security and governance teams validate access, reduce over-exposure, and scope Gencore AI pipelines with confidence.

If you prefer to configure Entitlement Scan separately for each Microsoft 365 connector, refer to the following articles:

- [Entitlement Scan for Microsoft Outlook](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-365-outlook)
- [Entitlement Scan for Microsoft OneDrive](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-onedrive)
- [Entitlement Scan for Microsoft SharePoint Online](/latest/docs/hyperdrive-entitlement-scan-for-m-sharepoint-online)
- [Entitlement Scan for Microsoft Teams](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-teams)

## Supported Connectors

Entitlement Scan is supported for the following Microsoft 365 connectors:

| Connector | Entitlement Entities Captured | Relationship Mapping |
| --- | --- | --- |
| Outlook | Microsoft 365 Groups (including distribution lists), Microsoft 365 Users, Internal and Linked Organizations, AI Agents, Microsoft Entra ID applications | Mapping of which users, groups, applications, or AI agents have access to specific Outlook files and folders |
| OneDrive for Business | Microsoft 365 Groups, Microsoft 365 Users, Internal and Linked Organizations, AI Agents, Microsoft Entra ID applications | Mapping of which users, groups, applications, or AI agents have access to specific OneDrive files and folders |
| SharePoint Online | SharePoint Site Groups, Microsoft 365 Groups, Microsoft 365 Users, Internal and Linked Organizations, AI Agents, Microsoft Entra ID applications | Mapping of which users, groups, applications, or AI agents have access to specific SharePoint files and folders |
| Microsoft Teams | Microsoft 365 Users, Teams, Channels, Internal and Linked Organizations, AI Agents, Microsoft Entra ID applications | Mapping of which users, groups, applications, or AI agents have access to specific Microsoft Teams files and folders |

## Prerequisites

Before configuring Entitlement Scan for any Microsoft 365 connector, ensure the following requirements are completed:

### Connector Setup

Ensure the Microsoft 365 connector is configured and synced in Hyperdrive. For detailed setup instructions of all the required steps, see:

- [Microsoft 365 (Hyperdrive)](/latest/docs/microsoft-365)
- [Creating an Entra ID app and obtain credentials for Microsoft 365](/latest/docs/creating-an-entra-id-app-and-obtain-credentials-for-microsoft-365)
- [Connecting Microsoft 365 using Hyperdrive](/latest/docs/connect-microsoft-365-using-hyperdrive)
- [Configure data inventory sync for Microsoft 365 applications (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive)

### Entitlement Scan Requirements

Ensure the following prerequisites are also completed:

**Enable the entitlement scan**

In the connector's Inventory Sync section (or Inventory Sync Options for classic UI), check the Entitlement Scan option to sync entitlement metadata for discovered resources.

> [!NOTE]
> **Important**
> 
> - Entitlement data appears in Graph Explorer only after the entitlement scan runs successfully at least once.
> - If Entitlement Scan is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Configure and Run Entitlement Scan

To configure Entitlement Scan for Microsoft 365:

1. In Securiti, navigate to **Integrations** and open your configured Microsoft 365 instance.
2. From the left navigation panel, click **Inventory**.
3. Mark the **Enable Inventory Sync** checkbox to sync the metadata for your data system.
4. Click **Show More Options**, and mark the **Run Entitlement Scan** checkbox.
5. Under the **Inventory Scope**, select the data system scoping items from the menu to include in the data inventory sync.
6. Once the inventory scope configuration is complete, click **Execute** and then **Save**.

> [!NOTE]
> **Note**
> 
> - It takes time to complete the Data Inventory Sync and Entitlement Scan. You can check the status in the Status and Ingestion Status message in the Inventory Sync section.
> - If you want to cancel the sync, click Cancel Scan beside Status in the Inventory Sync section, and click Okay on the confirmation popup.

## Entitlement Scan for Supported M365 Connectors

If you prefer to configure and use Entitlement Scan individually for a specific Microsoft 365 connector instead of centrally for all Microsoft 365 applications, see the following articles:

- [Entitlement Scan for Microsoft Outlook](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-365-outlook)
- [Entitlement Scan for Microsoft OneDrive](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-onedrive)
- [Entitlement Scan for Microsoft SharePoint Online](/latest/docs/hyperdrive-entitlement-scan-for-m-sharepoint-online)
- [Entitlement Scan for Microsoft Teams](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-teams)

## Using Entitlement Scan in Hyperdrive for Microsoft 365

Below are example use cases to help you use Securiti's **Data Command Graph** to analyze access and identify risks across your Microsoft 365 environment using Entitlement Scan. When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

### Identify and report on M365 files readable by users

This query helps you identify which users can read files discovered across your Microsoft 365 environment. It enables you to validate whether file access aligns with intended permissions.

To identify M365 files readable by users:

1. In **Securiti**, open **Graph Explorer** after clicking the top left jewel icon.
2. Near the upper left corner of the page, click + to open the filter menu.
3. On the filter menu, select the **Files entity**.
4. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select one or more of the following: Office 365 Outlook, Office 365 OneDrive, Office 365 SharePoint Online, Microsoft Teams.
5. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Readable by** User Principal.
6. Click **Apply**, and then click **Run Query**.
7. Click on the **User Principal** node to view the list of users that can read the selected files.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(31).png)

### Identify and report on M365 files writable by users

This query helps you identify which users can write to, or modify, files discovered across your Microsoft 365 environment. Users granted write access can create or modify content, so monitoring this level of access helps you enforce least-privilege access and detect overprivileged users.

To identify M365 files writable by users:

1. In **Securiti**, open **Graph Explorer** after clicking the top left jewel icon.
2. Near the upper left corner of the page, click + to open the filter menu.
3. On the filter menu, select the **Files entity**.
4. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select one or more of the following: Office 365 Outlook, Office 365 OneDrive, Office 365 SharePoint Online, Microsoft Teams.
5. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Writable by User Principal**.
6. Click **Apply**, and then click **Run Query**.
7. Click on the **User Principal** node to view the list of users that can write to the selected files.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(24).png)

### Identify and report on M365 files writable by applications

This helps you identify which M365 applications can write to, or modify, files discovered across your Microsoft 365 environment, and what sensitive data those files contain. It provides visibility into non-human access patterns and helps you scope AI pipelines before finalizing access.

To identify M365 files writable by applications:

1. In **Securiti**, open **Graph Explorer** after clicking the top left jewel icon.
2. Near the upper left corner of the page, click + to open the filter menu.
3. On the filter menu, select the **Files entity**.
4. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select one or more of the following: Office 365 Outlook, Office 365 OneDrive, Office 365 SharePoint Online, Microsoft Teams.
5. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Writable by Application**.
6. Click **Apply**, and then click **Run Query**.
7. Click on the **M365 Application** node to view the list of applications that can write to the selected files.

### Identify and report on M365 files accessible by AI agents

This helps you identify which AI agents have access to files discovered across your Microsoft 365 environment. It provides visibility into automated or agent-driven access patterns, enabling you to monitor AI-related exposure and investigate potential risks associated with sensitive data.

To identify M365 files accessible by AI agents:

1. In **Securiti**, open **Graph Explorer** after clicking the top left jewel icon.
2. Near the upper left corner of the page, click + to open the filter menu.
3. On the filter menu, select the **Files entity**.
4. Click the three dots next to the **Files entity**, select **Add Property**, choose **Data System Type**, and select one or more of the following: Office 365 Outlook, Office 365 OneDrive, Office 365 SharePoint Online, Microsoft Teams.
5. Click the three dots next to the **Files entity**, select **Add Relationship**, and choose **Controllable by Agent.**
6. Click **Apply**, and then click **Run Query**.
7. Click on the **M365 AI Agent** node to view the list of agents that can access the selected files.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(12).png)

An individual user interacts with the data system and accesses data. User Principle represents a user account in a Data System or an Identity in an identity Provider (IDP) like Active Directory, Okta, or similar.
