---
title: "Microsoft 365 OneDrive"
slug: "microsoft-365-onedrive-connectors"
status: "update"
updated: 2026-09-28T05:14:36Z
published: 2026-09-28T05:14:36Z
canonical: "helpcenter.securiti.ai/microsoft-365-onedrive-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 OneDrive

Microsoft OneDrive is a cloud-based file storage and collaboration platform. By connecting OneDrive with Securiti, organizations can discover and classify sensitive data through Sensitive Data Intelligence, automate privacy request fulfillment with DSR Automation, strengthen security with Security Posture Management, enforce Quarantine and Retention Policies, and gain visibility into permissions through Data Access Governance and Data Access Intelligence (Privilege Analysis). Microsoft 365 OneDrive falls under [Monitored data systems](/latest/docs/managing-data-system-connectors) category.

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| OneDrive (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation - Data Access Governance - Only supports Data Access Intelligence (Privilege Analysis) - Security Posture Management - Quarantine Policies and Retention Policies |
| OneDrive (Securiti-Cloud) | Securiti Cloud connector supports: - Sensitive Data Intelligence - DSR Automation - Security Posture Management - Data Breach Management |

### Supported Pod types

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported Credential Types

Refer to the table below to see the supported credential types of OAuth authentication for Microsoft 365 OneDrive Self-hosted and Securiti-Cloud connectors:

| Connector | Credential Type | Credentials |
| --- | --- | --- |
| Microsoft 365 OneDrive (Self-hosted) | Client Secret | - Application (Client) ID - Client Secret |
| Certificate | - Application (Client) ID - Certificate |
| Microsoft 365 OneDrive (Securiti-Cloud) | Client Secret | - Client ID - Client Secret |

#### Keyring support for Microsoft OneDrive (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: HashiCorp for OneDrive can be used with or without OAuth plugin. For more information, see:
  - [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
  - [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp).

> [!NOTE]
> Note
> 
> Keyring support is available only for Client Secret authentication .

### Supported items for Inventory and Classification scans

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Groups
- Folders
- Files

### Prerequisites for configuring OneDrive Self-hosted connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft 365 OneDrive with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints, Microsoft Graph API endpoints, and OneDrive API endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Admin access in Microsoft Entra ID

You must be an administrator to grant permissions to the applications created in the Microsoft Entra ID.

- Refer to [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted) for connecting Microsoft 365 OneDrive to Securiti
- Refer to [Grant permissions and obtain credentials in OneDrive Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-cloud) for connecting OneDrive Cloud connector to Securiti

#### 3. Allowlisting APIs for Data Inventory Sync with OneDrive (Self-hosted)

You must allowlist the following APIs to successfully run the Data Inventory Sync for OneDrive (Self-hosted) connector.

Default URL is `https://graph.microsoft.com/`

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | `https://graph.microsoft.com/v1.0/users/{{user_id}}/drive` | Get drive |
| 2 | GET | `https://graph.microsoft.com/v1.0/drives/{{drive_id}}/root/delta` | Get drive delta |
| 3 | GET | `https://graph.microsoft.com/v1.0/users` | Get users |
| 4 | GET | `https://graph.microsoft.com/v1.0/users/{{user_id}}/drive/items/{{file_id}}/content` | Download file |
| 5 | GET | `https://graph.microsoft.com/sites/{{site_id}}/drive` | Get drive info by site ID |
| 6 | GET | `https://graph.microsoft.com/users/{{user_id}}/drive/items/{{file_id}}` | Get file |

#### 4. Allowlisting URLs for Discovery Scan with OneDrive (Self-hosted)

Securiti requires the following URLs to be allowlisted on the customer's firewall for the Microsoft 365 OneDrive (Self-hosted) connector for Sensitive Data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:

- `https://graph.microsoft.com`
- `https://login.microsoftonline.com`

Additionally, you must allowlist either of the following URLs:

- `*.sharepoint.com`

Or
- `https://{{&lt;customer_tenant_name&gt;}}-my.sharepoint.com`

To obtain the tenant's name for the allowlisted URL, perform the following steps.

1. See **Record Obtain Tenant Name and Domain step** in the [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted) to obtain the Tenant's name.
2. Replace the `&lt;customer_tenant_name&gt;` with the Tenant Name in the above URL.

#### 5. Use cases and permissions for Microsoft 365 OneDrive

This section covers use cases and permissions required for Microsoft 365 OneDrive self-hosted and cloud connectors.

> [!NOTE]
> **Note**
> 
> When you authenticate using OAuth based authentication, an Microsoft 365 administrator must provide consent to the permissions you have configured for the Azure application.

If you wish to provide the OneDrive connectors access to all of your OneDrive libraries, and folders for data discovery and classification, use the following use cases and permissions.

> [!NOTE]
> **Note**
> 
> You can select the the permissions from the following table depending on the:
> 
> - Type of OneDrive connector (Self-hosted or Securiti cloud).
> - Number and type of modules.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | **Microsoft Graph API Application Permissions:** For Self-hosted connector: - [GroupMember.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupmemberreadall) - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) - [Reports.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#reportsreadall) - [Group.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupreadall) - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) For cloud connector: - [GroupMember.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupmemberreadall) - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) - [Reports.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#reportsreadall) - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) | These permissions let Securiti read the files and file metadata in OneDrive for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Data Inventory Sync and Gencore AI Entitlement scanning | - Available for self-hosted connector only. - Requires whitelisting APIs between your deployed Securiti pod and the Microsoft Graph and OneDrive APIs. See [above](/v1/docs/microsoft-365-onedrive-connectors). | **Microsoft Graph API Application Permissions:** - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) | These permissions let Securiti read the files and file metadata in OneDrive for inventory. The permission also let Securiti discover entitlements and read sharing settings. |
| MIP Label Collection | MIP Label Collection happens during the Data Inventory Sync or Discovery Scans | **Microsoft Graph API Application Permissions:** - [InformationProtectionPolicy.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#informationprotectionpolicyreadall) - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) | These permissions let Securiti to collect all sensitivity labels across the organization and the files they are applied on. |
| MIP Labeling Policies | MIP Labeling policies are only available for self-hosted connectors. | **Microsoft Graph API Application Permissions:** - [Files.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadwriteall) - [Sites.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadwriteall) | These permissions let Securiti create labeling policies for files and documents in OneDrive. |
| Quarantine Policy | Quarantine policies are only supported only on the self-hosted connector. | **Microsoft Graph API Application Permission:** - [Sites.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadwriteall) - [Files.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadwriteall) | This permission lets Securiti enable Quarantine Policies to move data between locations in your OneDrive tenant |
| Security Posture Management Rule Evaluation | This capability lets Securiti to evaluate posture findings in OneDrive using Microsoft Graph APIs. | **Microsoft Graph API Application Permissions:** - [Policy.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#policyreadall) - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) - [UserAuthenticationMethod.Read](https://learn.microsoft.com/en-us/graph/permissions-reference#userauthenticationmethodread) - [Directory.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadall) - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |
| DSR Automation through Smart Search | This capability lets Securiti to find PII data in your OneDrive tenant using Microsoft Graph API searches. Only available on the Securiti-Cloud connector | **Microsoft Graph API Application Permission** - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) | This permission lets Securiti read all of the data within your OneDrive for DSR searches |
| Data Access Intelligence | Data Access Intelligence is supported for Self-hosted connector only. | **For Privilege Analysis:** - **Microsoft Graph API Application Permissions:** - [Directory.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadall) - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) - **Microsoft Graph API Delegated Permissions:** - [User.Read](https://learn.microsoft.com/en-us/graph/permissions-reference#userread) > [!NOTE] > **Note** > > User.Read is added as default permission when you create an Azure application, you must not disable it. | These permissions let Securiti leverages these Microsoft Graph API permissions as part of determining which users and user groups have access to data in OneDrive and what level of permissions they have on that data. |

### Connect Microsoft 365 OneDrive with Securiti

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for this data system. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> See [API quota tracking for SaaS connectors](/v1/docs/api-quota-tracking-for-saas-connectors), for more information.

> [!WARNING]
> **Important**
> 
> Securiti emits logs and shows audit trails/activity log for OneDrive data system connector. You can view emitted logs for overall stats during each of their auth, learning, and discovery scan phases. However, Securiti does not guarantee all data processing because scanning or discovery scans have scoped options and only emit logs for the overall connector account in question.

#### Steps to connect OneDrive (Self-hosted) connector with Securiti

To configure the OneDrive (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. (Optional) For Quarantine policy, see [(Optional) Acquire Quarantine Policy parameters in OneDrive](/latest/docs/optional-acquire-quarantine-policy-parameters-in-onedrive).
3. [Grant permissions and obtain credentials in OneDrive (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-self-hosted).
4. [Connecting the OneDrive (Self-hosted) data system](/latest/docs/create-microsoft-365-onedrive-self-hosted-connector-instance-new-ui).
5. [Configuring Data Inventory Sync](/latest/docs/configuring-data-inventory-sync-for-onedrive-self-hosted).
6. [Configure discovery scans in Microsoft 365 OneDrive](/latest/docs/configure-discovery-scans-in-microsoft-365-onedrive).
7. [Configuring General permissions for OneDrive (Self-hosted)](/latest/docs/new-ui-configuring-general-permissions).

#### Steps to connect OneDrive Securiti-Cloud connector with Securiti

To configure the OneDrive Securiti-Cloud connector, perform the procedures in the following topics:

1. [Grant permissions and obtain credentials in OneDrive Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-cloud).
2. [Connecting the OneDrive (Securiti-Cloud) data system](/latest/docs/new-ui-connecting-microsoft-365-onedrive-cloud-with-securiti).
3. [Configuring General permissions for OneDrive (Securiti-Cloud)](/latest/docs/configure-general-permissions-for-microsoft-365-onedrive-self-hosted).

#### Additional resources

1. [Fulfilling OneDrive DSR Request](/latest/docs/fulfilling-onedrive-self-hosted-dsr-requests).
2. If you have previously configured a OneDrive connector and want to enable DSR automation, see [Configure DSR automation setup](/v1/docs/configure-dsr-automation-setup).
3. [Microsoft 365 OneDrive FAQs](/latest/docs/microsoft-365-onedrive-faqs).
