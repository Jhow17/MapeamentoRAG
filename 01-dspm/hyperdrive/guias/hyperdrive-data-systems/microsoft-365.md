---
title: "Microsoft 365 (Hyperdrive)"
slug: "microsoft-365"
status: "update"
updated: 2026-10-05T06:47:52Z
published: 2026-10-05T06:47:52Z
canonical: "helpcenter.securiti.ai/microsoft-365"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 (Hyperdrive)

> [!NOTE]
> Note
> 
> - If Microsoft 365 connector is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - The Microsoft 365 connector works only when Hyperdrive is enabled for your tenant.
>   - If Hyperdrive is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

The Microsoft 365 connector enables connection with four Microsoft 365 applications, providing flexible connectivity options to suit different deployment needs. It supports two authentication methods, Automatic and Manual, and offers Hyperdrive Mode through Securiti Outpost deployment for fast, secure, and high-performance data access.

## Supported Microsoft applications and modules

| Application type | Supported module features |
| --- | --- |
| Microsoft 365 SharePoint Online | - Sensitive Data Intelligence - Discovery scan - Data Inventory sync - Policies - Files quarantine - Data Labeling - Activity Analysis |
| Microsoft 365 OneDrive | - Sensitive Data Intelligence: - Discovery scan - Data Inventory sync - Policies: - Files quarantine - Data Labeling - Activity Analysis |
| Microsoft 365 Outlook | - Sensitive Data Intelligence - Discovery scan - Data Inventory sync - Activity Analysis |
| Microsoft Teams | - Sensitive Data Intelligence - Discovery scan - Data Inventory sync - Activity Analysis |

## Supported authentication methods

| Authentication option | Supported credentials | Description |
| --- | --- | --- |
| Automatic authentication (Recommended) | - OAuth-based credentials - Certificate-based credentials | - It automatically connects to Microsoft applications without requiring you to create an Entra ID application or manage credentials. - Securiti securely handles application creation and permission assignment, enabling faster and simpler authentication. |
| Manual authentication | - OAuth-based credentials | - It requires you to create a single Entra ID application for the selected Microsoft applications. - You must generate credentials and explicitly assign the required permissions to complete the connection. > [!NOTE] > Note > > Entitlement Syncs support is not available for manual authentication due to unavailability of Certificate-based credentials. |

### Keyrings support

Keyrings support is not available for Microsoft 365 (Hyperdrive).

## Supported pod types

- Securiti Outpost Deployment

## Prerequisites

Complete the following prerequisites to authenticate the Microsoft 365 applications.

1. ### Outpost deployment

If you use Hyperdrive mode while creating a data system instance, you must deploy Securiti Outpost, which uses AWS services to scale scanning operations. For more information, see [Securiti Outpost deployment](/latest/docs/full-saas-hyperdrive-deployment).
2. ### Admin access in Microsoft Entra ID

You must be a global administrator in Microsoft Entra ID to authenticate the Microsoft 365 connector using automatic and manual authentication methods.
3. ### Enable Microsoft unified audit logging

Enable Microsoft unified audit logging, which is used to capture user and admin activity events in the activity analysis, see [Activity Analysis for Microsoft 365](/latest/docs/activity-analysis-for-microsoft365).
4. ### Permissions and use cases

Use the following table to understand the permissions required to access Microsoft 365 resources:
  - In case of automatic authentication, Securiti assigns these permissions to the Entra ID application.
  - In case of manual authentication, you must assign these permissions to the Entra ID application

| Permission | Microsoft 365 Application | Purpose |
| --- | --- | --- |
| **Microsoft Graph API permissons** |
| `User.Read.All` | All | Use to inventory all users and groups in Entra to display their access to Microsoft 365 data. |
| `InformationProtectionPolicy.Read.All` | All | Use to read existing Sensitivity Labels from Microsoft Data Objects. |
| `ActivityFeed.Read` | All | Use to collect activity logs for Activity Analysis. |
| `AuditLogsQuery.Read.All` | All | Use to collect activity logs for Activity Analysis. |
| `Directory.Read.All` | SharePoint, OneDrive | Use to collect metadata about directories for scan scoping. |
| `Files.Read.All` | SharePoint, OneDrive | Use to download and scan SharePoint and OneDrive Files for sensitive data discovery. |
| `Reports.Read.All` | SharePoint, OneDrive | Use to retrieve activity information from logs if configured to provide insight into user and application activity, including AI agents. |
| `Files.ReadWrite.All` | SharePoint, OneDrive | This permission lets Securiti read, update, move, and label files in OneDrive to create and run Quarantine and Data Labeling policies in SDI. |
| `Sites.ReadWrite.All` | SharePoint, OneDrive | This permission lets Securiti read and modify OneDrive site content to create and run Quarantine and Data Labeling policies in SDI. |
| `Sites.Read.All` | SharePoint | Use to catalog SharePoint Sites in the Securiti Platform. |
| `Mail.Read` | Outlook | Use to read the mailbox content to identify sensitive data. |
| `Mail.ReadBasic` | Outlook | Use to read all mail in all inboxes for sensitive data discovery. |
| `Channel.ReadBasic.All` | Teams | Use to catalog Microsoft Teams channels. |
| `ChannelMessage.Read.All` | Teams | Use to read channel messages to identify sensitive data. |
| `Chat.Read.All` | Teams | Use to read Teams direct messages for sensitive data discovery. |
| `Chat.ReadBasic.All` | Teams | Use to catalog members of Teams chat conversations. |
| `Team.ReadBasic.All` | Teams | Use to catalog Microsoft Teams instances. |
| `TeamMember.Read.All` | Teams | Use to catalog members of Microsoft Teams. |
| **SharePoint Application API permission** |
| `Sites.FullControl.All` | SharePoint | Use this admin permission to gather metadata about the site and file sharing, as well as file permissions for users. This is the lowest permission Microsoft publishes, which lets the retrieval of this data*.* For information, see [Microsoft 365 FAQs](/latest/docs/faqs). |
| **Microsoft 365 Management Activity API permissions** > [!NOTE] > Note > > You must enable Microsoft unified audit logging, which is used to capture user and admin activity events in the activity analysis. |
| `Audit.General` | Teams | Use to capture collaboration activities and file operations in Activity Analysis. |
| `Audit.Exchange` | Outlook | Use to capture email activities such as mailbox access, message operations, and administrative actions in Activity Analysis. |
| `Audit.SharePoint` | SharePoint, OneDrive, Teams | Use to capture file-level activities such as access, sharing, and modifications in Activity Analysis. |

## Connect your Microsoft 365 applications

Securiti provides you with two options to connect your Microsoft 365 data systems:

1. [Deploy AWS-based Outpost](/latest/docs/full-saas-hyperdrive-deployment)
2. [Creating an Azure application and obtaining authentication credentials](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365) (applies only to manual authentication)
3. Authenticate Microsoft 365:
  - [Using automatic authentication (Recommended)](/latest/docs/connect-microsoft-365-using-automatic-authentication)
  - [Using manual authentication](/latest/docs/connect-microsoft-apps-using-manual-authentication)

## Configure scans and policies

1. [Configure Data Inventory Syncs for Microsoft 365 applications (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications)
2. [Configure discovery scans](/latest/docs/configure-discovery-scans-for-microsoft-365-instances)
3. [Create a file quarantine policy using Hyperdrive mode](/latest/docs/using-quarantine-policy-with-hyperdrive-mode)
4. [Configure Activity Analysis for Microsoft 365 (Hyperdrive)](/latest/docs/configure-activity-analysis-for-microsoft-365-hyperdrive)

## Additional resources

- [Using the authentication dashboard (Hyperdrive)](/latest/docs/using-authentication-statuses-hyperdrive)
- [Using the Inventory Sync Statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive)
