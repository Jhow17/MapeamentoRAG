---
title: "Microsoft 365 Outlook"
slug: "microsoft-365-outlook-connectors"
status: "update"
updated: 2026-09-25T07:33:27Z
published: 2026-09-25T07:33:27Z
canonical: "helpcenter.securiti.ai/microsoft-365-outlook-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 Outlook

> [!WARNING]
> Important
> 
> Securiti recommends using the **Microsoft 365 Outlook** (latest) connector for this data system to access new capabilities, ongoing improvements, and full platform support.
> 
> **Legacy connectors are in maintenance mode and do not receive new features or enhancements.** This includes, but is not limited to:
> 
> - API version upgrades
> - Additional Keyrings for this connector
> - New or enhanced scopes for Discovery Scan and Data Inventory Sync
> - Additional modules (for example, HyperDrive, Data Inventory Sync and DSR)
> - Any future functionality introduced for this connector
> 
> Some of the enhancements listed above may not be available on this connector. Refer to the recommended connector’s documentation for currently supported modules and capabilities.

Microsoft Outlook is a personal information manager software system from Microsoft, available as a part of the Microsoft 365 software suites. It allows you to send and receive email messages, manage your calendar, store names and numbers of your contacts, and track your tasks.

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft 365 Outlook (Self-hosted) > [!NOTE] > Note > > Securiti recommends you to use this connector. | - Sensitive Data Intelligence (Discovery scan) - Data Subject Rights |
| Microsoft 365 Outlook (Securiti Cloud) | - Sensitive Data Intelligence (Data scan) - Data Subject Rights |
| Microsoft 365 Outlook Attachments (Legacy) (Self-hosted) | - Sensitive Data Intelligence (Discovery scan) - Data Subject Rights |
| Microsoft 365 Outlook Message Body (Legacy) (Self-hosted) | - Sensitive Data Intelligence (Discovery scan) - Data Subject Rights |

### Supported Pods type for self-hosted connector

- Standard Securiti pods.
- Elastic Pods (EDSS).

### Supported Credential Types

Refer to the table below to see the supported credential types of OAuth authentication for Microsoft 365 Outlook Self-hosted and Securiti-Cloud connectors:

| Connector | Authentication Method | Credentials |
| --- | --- | --- |
| Microsoft 365 Outlook (Self-hosted) | Client Secret | - Application (Client) ID - Client Secret |
| Certificate | - Application (Client) ID - Certificate |
| Microsoft 365 Outlook (Securiti-Cloud) | Client Secret | - Client ID - Client Secret |

#### Keyring support for Microsoft 365 Outlook (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/v1/docs/using-keyrings) for more information.

- **Azure Key Vault:** For more information, see [Azure Key Vault documentation](/latest/docs/configuring-credential-vaults-azure-key-vault).
- **HashiCorp**: Outlook supports authentication with HashiCorp Vault for credential management, both with and without the OAuth plugin. For more information, see the topics below.
  - [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)
  - [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)
- **CyberArk:** For more information, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault).

> [!NOTE]
> Note
> 
> Keyring support is available only for Client Secret credential type.

### Supported items for Inventory and Classification Scans

Refer to [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors) for more information about Inventory scans. Refer to [Understanding Discovery Scans](/v1/docs/discovery-scans) for more information about Classification Scans.

- Folders and child folders in Outlook
- Messages
- Attachments

> [!NOTE]
> Note
> 
> - Securiti scans messages and attachments available in all mailbox folders, such as Inbox, Drafts, Sent Items, for scoped users, regardless of whether emails originate from internal or external senders.
> - To include all mailboxes and nested folders in the scanning, you must upgrade the pod version to release 1.146 or higher.

### Prerequisites for configuring Microsoft 365 Outlook connectors

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Outlook with a Self-hosted connector. Make sure the Pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti.ai endpoints, Microsoft Graph API endpoints, and Outlook API endpoints. Refer to the [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later) for more information on configuring Pods.

#### 2. Admin access in Microsoft Entra ID

You must be an administrator to grant permissions to the applications created in the Microsoft Entra ID.

#### 3. Allowlisting APIs for Data Inventory Sync for Outlook (Self-hosted)

You must allowlist the following APIs to successfully run the Data Inventory Sync for Microsoft 365 Outlook.

Default URL is *https://graph.microsoft.com/*

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://graph.microsoft.com/v1.0/organization | Get organization |
| 2 | GET | https://graph.microsoft.com/v1.0/groups | Get a list of groups |
| 3 | GET | https://graph.microsoft.com/v1.0/groups/$group_id/members | Get a list of group members |
| 4 | GET | https://graph.microsoft.com/v1.0/users/$user_id | Get user |
| 5 | GET | https://graph.microsoft.com/v1.0/users | Get a list of users |
| 6 | GET | https://graph.microsoft.com/v1.0/users/$user_id/mailFolders | Get a list of mailFolders |
| 7 | GET | https://graph.microsoft.com/v1.0/users/$user_id/mailFolders/$mail_folder_id/messages/delta | Get a list of messages |
| 8 | GET | https://graph.microsoft.com/v1.0/users/$user_id/messages/$message_id/attachments | Get a list of attachments |

#### 4. Allowlisting URLs for Outlook Discovery scan from Self-hosted connectors

Securiti requires the following URLs to be whitelisted on the customer's firewall for the Microsoft 365 Outlook for Sensitive Data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:

- *https://graph.microsoft.com*
- *https://login.microsoftonline.com*

#### 5. Use cases and permissions for Microsoft 365 Outlook

This section covers use cases and permissions required for Microsoft 365 Outlook Self-hosted and cloud connectors.

> [!NOTE]
> **Note**
> 
> When you authenticate using OAuth based authentication, an Microsoft 365 administrator must provide consent to the Microsoft **Graph API permissions** you have configured for the Azure application.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | **For Self-hosted connector** - Mail.Read - Reports.Read.All - User.Read.All - GroupMember.Read.All **For** Securiti **Cloud connector:** - User.ReadBasic.All - Mail.Read - Reports.Read.All - User.Read.All | These permissions let Securiti read the files and file metadata in for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Data Inventory Sync and Gencore AI Entitlement scanning | - Available for self-hosted connectors only. - Requires whitelisting APIs between your deployed Securiti pod and the Microsoft Graph and Outlook APIs. See section above | - Mail.Read - User.Read.All - GroupMember.Read.All | These permissions let Securiti read the files and file metadata in Outlook for inventory. The permission also lets Securiti discover entitlements and read sharing settings. |
| GenCore Entitlement Scanning | N/A | - Mail.Read - User.Read.All - GroupMember.Read.All | These permissions let Securiti collect file level user entitlements for using Outlook messages and content in GenCore AI Pipelines |
| DSR Automation through Smart Search | - This capability allows Securiti to find PII data in your Outlook tenant using Microsoft Graph API searches. | - Mail.Read - User.ReadBasic.All | These permissions let Securiti read all of the data within your Outlook users, messages, and content for DSR searches |

### Connect Microsoft Outlook connectors with Securiti

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for this data system. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> See [API quota tracking for SaaS connectors](/v1/docs/api-quota-tracking-for-saas-connectors), for more information.

#### Steps to connect Outlook (Self-hosted) connector with Securiti

This procedure covers the configuration of following Outlook self-hosted connector:

- Outlook (Self-hosted)
- Outlook Attachments (Legacy) (Self-hosted)
- Outlook Message Body (Legacy) (Self-hosted)

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in Securiti [pods](/latest/docs/pods-cluster-version-v128-and-later).
3. [Obtain authentication credentials and grant permissions in Outlook Self-hosted](/latest/docs/obtain-authentication-credentials-and-grant-permissions-in-outlook-self-hosted).
4. [Connecting Microsoft 365 Outlook (Self-hosted) connector with Securiti](/latest/docs/new-ui-create-microsoft-365-outlook-self-hosted-connector-instance)
5. [Configuring Data Inventory Sync for Outlook](/latest/docs/configuring-data-inventory-sync-for-outlook)
6. [Configure discovery scans in Microsoft 365 Outlook (Self-hosted)](/latest/docs/configure-discovery-scans-in-microsoft-365-outlook-self-hosted)

#### Steps to connect Outlook Securiti-Cloud with Securiti

To configure the Outlook Securiti Cloud connector, perform the following steps:

1. [Obtain authentication credentials and grant permissions in Outlook Cloud](/latest/docs/obtain-authentication-credentials-and-grant-permissions-in-outlook-cloud).
2. [Connecting Microsoft 365 Outlook (Securiti-Cloud) with Securiti](/latest/docs/new-ui-activating-microsoft-365-outlook-securiti-cloud-connector-with-securiti)
3. [Configuring General permissions for Microsoft 365 Outlook (Securiti-Cloud)](/latest/docs/configuring-general-permissions-for-microsoft-365-outlook-securiti-hosted)

#### Additional resources

- [Fulfilling Microsoft 365 Outlook (Message Body) DSR requests](/latest/docs/fulfilling-microsoft-365-outlook-message-body-dsr-requests).
- [Fulfilling Microsoft 365 Outlook (Attachments) DSR requests](/latest/docs/fulfilling-microsoft-365-outlook-attachments-dsr-requests)
- [Microsoft 365 Outlook FAQs](/latest/docs/microsoft-365-outlook-faqs)
