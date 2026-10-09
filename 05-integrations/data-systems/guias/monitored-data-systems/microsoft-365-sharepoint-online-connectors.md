---
title: "Microsoft 365 SharePoint Online"
slug: "microsoft-365-sharepoint-online-connectors"
status: "update"
updated: 2026-09-28T05:18:16Z
published: 2026-09-28T05:18:27Z
canonical: "helpcenter.securiti.ai/microsoft-365-sharepoint-online-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 SharePoint Online

Microsoft 365 SharePoint is a cloud-based collaboration and document management platform that enables organizations to store, share, and manage content securely across teams. By connecting Microsoft 365 SharePoint with Securiti, organizations can discover and classify sensitive data through Sensitive Data Intelligence, automate privacy request fulfillment with DSR Automation, and strengthen security with Security Posture Management.

The integration also enables Quarantine and Retention Policy enforcement, Data Access Governance, Data Access Intelligence, Privilege Analysis, Activity Analysis, and Data Access Control, helping organizations gain deeper visibility into data usage, reduce access risks, and maintain compliance across their SharePoint environment.

SharePoint Online falls under the category of [monitored, unstructured data system](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| SharePoint Online (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation - Security Posture Management - Quarantine Policies and Retention Policies - Data Access Governance - Data Access Intelligence - Privilege Analysis - Activity Analysis - Data Access Control |
| SharePoint Online (Securiti Cloud) | Securiti Cloud connector supports: - Sensitive Data Intelligence - DSR Automation - Data Access Governance - Data Access Intelligence - Privilege Analysis - Activity Analysis - Security Posture Management - Data Breach Management |

### Supported pod types for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported Credential Types

Refer to the table below to see the supported credential types of OAuth authentication for Microsoft 365 SharePoint Self-hosted and Securiti-Cloud connectors:

| Connector | Credential Type | Credentials |
| --- | --- | --- |
| Microsoft 365 SharePoint (Self-hosted) | Client Secret | - Application (Client) ID - Client Secret |
| Certificate | - Application (Client) ID - Certificate |
| Microsoft 365 SharePoint (Securiti-Cloud) | Client Secret | - Client ID - Client Secret |

#### Keyring support for Self-hosted connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**. SharePoint supports authentication with HashiCorp Vault for credential management, both with and without the OAuth plugin. For more information, see the topics below.
  - [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)
  - [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)
- **Azure Key Vault**. For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). Azure Key Vault is OAuth-supported for SharePoint Online.
- **CyberArk Vault:** For more information, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault).

> [!NOTE]
> Note
> 
> Keyring support is available only for Client Secret credential type.

### Supported items for Inventory and Classification Scans

For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors). For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- SharePoint sites and subsites, including all child Document libraries.
  - OneDrive, Team drives, and Microsoft Teams storage are contained within SharePoint and are scanned as part of SharePoint Discovery and Classification scans.
- SharePoint Files
- Sensitivity label assigned to each SharePoint site

> [!NOTE]
> Note
> 
> - Sensitivity label ingestion does not require you to run a Data Inventory Sync or Discovery Scan for the connector. Securiti collects the sensitivity labels for SharePoint sites during the Scoping Inventory Sync once you activate your connector.
> - You must configure your connector using pod version 1.142.0 and above to enable sensitivity label collection during the Scoping Inventory Sync.
> - You must authenticate your connector with certificate and thumbprint to let Securiti discover sensitivity labels.
> - Securiti can also ingest sub-labels created for a site label.

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your SharePoint with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and SharePoint API endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Admin access in Microsoft Entra ID

You must be an administrator to grant permissions to the applications created in the Microsoft Entra ID.

- For more information on connecting Microsoft 365 SharePoint Online (Self-hosted) full access application to Securiti, see [Obtain credentials for SharePoint Online (Self-hosted)](/latest/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted).
- For more information on connecting Microsoft 365 SharePoint Online **Selective Site(s) Access** application to Securiti, see [Obtain credentials for SharePoint Online Selective Site(s) Access](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access).
- For more information on connecting SharePoint Online (Securiti Cloud) application to Securiti, see [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud).

#### 3. Allowlisting APIs for Data Inventory Sync Self-hosted connector

You must allowlist the Microsoft APIs to successfully run the Data Inventory Sync for SharePoint Online (self-hosted) connector.

Default Graph URL is `https://graph.microsoft.com/`

Default SharePoint site URL is `https://{tenant}.sharepoint.com/`

For more information on the complete list of allowlisting URLs, see [Allowlisting URLs for SharePoint Online](/latest/docs/allowlisting-urls-for-sharepoint-online).

#### 4. Allowlisting URLs for Discovery Scan with Self-hosted connector

Securiti requires the following URLs to be allowlisted on the customer's firewall for the Microsoft 365 SharePoint Online (Self-hosted) connector for Sensitive Data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:

- `https://graph.microsoft.com `
- `https://login.microsoftonline.com`

- Either:
  - `*.sharepoint.com`

OR
  - Both of the following:
    - `https://{{&lt;customer_tenant_name&gt;}}.sharepoint.com`
    - `https://{{&lt;customer_tenant_name&gt;}}-my.sharepoint.com`

For more information on the tenant name and the complete list of allowlisting URLs, see [Allowlisting URLs for SharePoint Online](/latest/docs/allowlisting-urls-for-sharepoint-online).

#### 5. Use cases and permissions

> [!NOTE]
> **Note**
> 
> A Global Administrator for your Microsoft Entra ID tenant must grant admin consent to the permissions for your Azure application.

This section includes the permissions and use cases for the following

- Permissions and use cases for connecting to SharePoint Online without limiting the connector’s access to specific sites.
- Permissions and use cases for Enforce Selective Sites Access to SharePoint Online.

#### 5 (a). Permissions and use cases for connecting to SharePoint Online without limiting the connector’s access to sites

If you wish to provide the SharePoint connectors access to all of your SharePoint sites for data discovery and classification, use the following use cases and permissions.

> [!NOTE]
> **Note**
> 
> You must use the **Application permissions** instead of **Delegated permissions** while assigning the permissions to the application you want to connect to Securiti.
> 
> Choose the permissions from the following table depending on the:
> 
> - Type of SharePoint Online connector (self-hosted or cloud-hosted).
> - Number of modules.

This table covers use cases and permissions required for Microsoft 365 SharePoint Online self-hosted and cloud connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing are only available on the self-hosted connector. | **Microsoft Graph API Application permissions:** - [Directory.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadall) - [Sites.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) - [Reports.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#reportsreadall) | These permissions let Securiti read the files and file metadata in SharePoint for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation. |
| Data Inventory Sync and Gencore AI Entitlement Scanning | - Available for self-hosted connector only. - Requires whitelisting APIs between your deployed Securiti pod and the Microsoft Graph and SharePoint APIs. - Requires the use of Certificate Credentials (Certificate thumbprint and private key file). | **Microsoft Graph API Application permissions:** - [Directory.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadall) - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) **SharePoint API Application permission:** - [Sites.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) - [Sites.FullControl.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesfullcontrolall) | These permissions let Securiti read the files and file metadata in SharePoint for inventory. The permission also let Securiti discover entitlements and read sharing settings. |
| SharePoint Site Inventory and Sharing Capabilities | Requires the use of Certificate Credentials (Certificate thumbprint and private key file). | **SharePoint API Application permission:** - [Sites.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) | This permission lets Securiti read the site type, sharing settings, and hubsite-to-site relationships. This is different than the **Graph API** permission `Sites.Read.All`. |
| MIP Label Collection | MIP Label Collection happens during the Data Inventory Sync or Discovery Scans. | **Microsoft Graph API Application permissions:** - [InformationProtectionPolicy.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#informationprotectionpolicyreadall) - [Files.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadall) | These permissions let Securiti collect all MIP file labels across the organization and the files they are applied to. |
| MIP Labeling Policies | MIP Labeling policies are only available for self-hosted connectors. | **Microsoft Graph API Application permissions:** - [Files.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadwriteall) - [Sites.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadwriteall) | These permissions let Securiti create labeling policies for files, documents, and list items in all site collections. |
| Sensitivity labels ingestion | - Sharepoint site-level sensitivity labels and any sub-labels are ingested during the Scoping Inventory Sync. - Sensitivity labels are ingested for Self-hosted connector only. - You must activate your connector using pod version 1.142.0 and above to ingest sensitivity labels. | **SharePoint API Application permission:** - [Sites.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) > [!WARNING] > Important > > You must authenticate your connector with certificate and thumbprint to let Securiti discover sensitivity labels. | This permission lets Securiti read the site type, sharing settings, and hubsite-to-site relationships. This is different than the **Graph API** permission `Sites.Read.All`. |
| Quarantine Policy | Quarantine policies are only supported for the self-hosted connector. | **Microsoft Graph API Application permission:** - [Sites.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadwriteall) | This permission lets enables Quarantine Policies to move data between locations in your SharePoint tenant. |
| Gencore Entitlement Scanning | Entitlement scanning requires providing the certificate thumbprint and the SSL Private Key of the Azure App used to authenticate with SharePoint. | **Microsoft Graph API Application permissions:** - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) - [Directory.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadall) **SharePoint API Application permission:** - [Sites.FullControl.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesfullcontrolall) | These permissions let Securiti collect file-level user entitlements for using SharePoint files in GenCore AI Pipelines |
| Security Posture Management Rule Evaluation | It is supported for OAuth-based authentication. | **Microsoft Graph API Application permissions:** - [Policy.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#policyreadall) - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) - [UserAuthenticationMethod.Read](https://learn.microsoft.com/en-us/graph/permissions-reference#userauthenticationmethodread) - [SharePointTenantSettings.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sharepointtenantsettingsreadall) | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |
| DSR Automation through Smart Search | This capability lets Securiti to find PII data in your SharePoint Online tenant using Microsoft Graph API searches. Only available on the Cloud-hosted connector | **Microsoft Graph API Application permission** - [Sites.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) | This permission lets Securiti read all of the data within your SharePoint sites for DSR searches |
| Data Access Intelligence | Data Access Intelligence requires that you use **certificate based credentials** for both the connector and the IAM metadata source for SharePoint due to a limitation in Microsoft's APIs. For more information, see [SharePoint Online Data Access Intelligence Prerequsites](/latest/docs/microsoft-365-sharepoint-online#access-intelligence2). | **For Privilege Analysis** - **Microsoft Graph API Application permissions:** - [Sites.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) - [Group.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupreadall) - **SharePoint API Application permission:** - [Sites.FullControl.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesfullcontrolall) **For Activity Analysis** > [!NOTE] > **Note** > > You must assign the following Microsoft Graph API permissions for activity analysis. Additionally, ensure that the privilege analysis permissions listed above are also granted alongside the activity analysis permissions. - **Microsoft Graph API Application permissions:** - [AuditLogsQuery-SharePoint.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#auditlogsquery-sharepointreadall) - [AuditLogsQuery-Entra.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#auditlogsquery-entrareadall) - [AuditLogsQuery-Endpoint.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#auditlogsquery-endpointreadall) | These permissions let Securiti leverages these Microsoft Graph API permissions as part of determining which users and user groups have access to data in SharePoint and what level of permissions they have on that data. |
| Data Access Control | Data Access Control is only available for a self-hosted connector. | **Microsoft Graph API Application permissions:** - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) - [User.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadwriteall) - [Group.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupreadall) - [Group.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupreadwriteall) - [GroupMember.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupmemberreadall) - [GroupMember.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#groupmemberreadwriteall) - [Directory.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadall) - [Directory.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadwriteall) - [Sites.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) **SharePoint API Application permission:** - [Sites.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadwriteall) - [Sites.FullControl.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesfullcontrolall) - [User.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) **SharePoint Admin Center permission** - Full control permission `&lt;AppPermissionRequests AllowAppOnlyPolicy="true"&gt;` `&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &lt;AppPermissionRequest ` `Scope="http://sharepoint/content/tenant" Right="FullControl" /&gt;` `&lt;/AppPermissionRequests&gt;` For more information, see [Configuring Data Access Control Policies for Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online#access-control1). | These permissions let Securiti leverages these Microsoft Graph API and SharePoint API permissions as part of restricting access of your users and groups to SharePoint sites. |

#### 5 (b). Permissions and use cases for selective sites access to SharePoint Online.

If you do not wish to provide the Securiti connector access to all of your SharePoint sites for data discovery and classification, we support the use of Microsoft's `Sites.Selected` permissions functionality to restrict our **Self-hosted** connector to a specific subset of sites.

> [!WARNING]
> **Warning**
> 
> When a connector is activated with the **​Enforce Selective Sites Access​​** option, the following capabilities are not available**:**.
> 
> - Site and Hub-site properties, such as sharing capabilities are not fetched during Scoping Metadata Sync.
> - Hub-site relationships are not fetched during Scoping Metadata sync.
> - Sub-sites of a site are not fetched by default during Scoping Metadata sync, Data Inventory Sync, or Discovery Scan. For more information, see [SharePoint Online FAQs](/latest/docs/microsoft-365-sharepoint-online-faqs).
> - SharePoint usage statistics, such as expected file count, storage usage, site count, are not collected during Scoping Metadata sync.
> - Data Access Intelligence is not supported.

**Permissions and use cases for Full control and selective sites access application**

> [!NOTE]
> **Note**
> 
> - When you authenticate using OAuth-based authentication, an Microsoft 365 administrator must provide consent to the permissions you have configured for the Azure application.
> - Enforcing Selective Sites Access requires the creation of two Microsoft Entra ID applications:
>   - The **Full Control Azure application** to configure and manage the Sites available through the Selective Site Access Azure Application. The Full Control app is not used to connect SharePoint to the Securiti Platform.
>   - The **Selective sites access application** to upload selected sites and configure connector with Securiti.

| Use case | Constraints | Permissions | Explanation for use case |
| --- | --- | --- | --- |
| **Permissions and use cases for Full Control Azure application** |
| N/A | This application does not connect to Securiti platform for any module feature. | **Microsoft Graph API Application permission** - [Sites.FullControl.All](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesfullcontrolall) | Granting this permission to this application lets you define the specific SharePoint sites that are accessible by the Selected Sites Azure application. |
| **Permissions and use cases for the Selective Sites Access Azure application** |
| - Sensitive Data Intelligence - Metadata Sync - DSR Automation Indexing | - It is not applicable to theSecuriti Cloud-hosted connector - Only applicable for Sensitive Data Intelligence, Inventory Metadata Scanning, and DSR Automation Indexing - Securiti can't retrieve SharePoint site properties with the Sites.Selected permission. | **Microsoft Graph API Application permissions** - [Sites.Selected](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesselected) **Role to each SharePoint Site**: - `Read` - `Write` > [!NOTE] > Note > > `Write` role is only required for Files Quarantine use case. | These permissions let Securiti read the files and file metadata in SharePoint for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |
| Data Inventory Sync and Gencore AI Entitlement Scanning | - Available for self-hosted connector only. - Requires whitelisting APIs between your deployed Securiti pod and the Microsoft Graph and SharePoint APIs. - Requires the use of Certificate Credentials (Certificate thumbprint and private key file). | **Microsoft Graph API Application permissions**: - [Sites.Selected](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesselected) - [Directory.Read.All](https://learn.microsoft.com/en-us/graph/permissions-reference#directoryreadall) **SharePoint API Application permission**: - [Sites.Selected](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesselected) **Role to each SharePoint Site**: - `fullcontrol` | These permissions let Securiti read the files and file metadata in SharePoint for inventory. The permission also let Securiti discover entitlements and read sharing settings. |
| Gencore Entitlement Scanning | Entitlement scanning requires providing the certificate thumbprint and the SSL Private Key of the Azure App used to authenticate with SharePoint. | **SharePoint API Application permission**: - [Sites.Selected](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesselected) **Role to each SharePoint Site**: - `fullcontrol` | These permissions let Securiti collect file-level user entitlements for using SharePoint files in GenCore AI Pipelines. |
| Quarantine Policy | Quarantine policies are only supported only on the self-hosted connector. | **Microsoft Graph API Application permission:** - [Sites.Selected](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesselected) **Role to each SharePoint Site**: - `Write` | These permissions let enables Quarantine Policies to move data between locations in your SharePoint tenant. |
| MIP Labeling Policies | MIP Labeling Policies | **Microsoft Graph API Application permissions**: - [Sites.Selected](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesselected) - [Files.ReadWrite.All](https://learn.microsoft.com/en-us/graph/permissions-reference#filesreadwriteall) | These permissions Securiti​​ create labeling policies for files, documents, and list items in all site collections. |

### Connect SharePoint Online connectors with Securiti

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for this data system. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> See [API quota tracking for SaaS connectors](https://helpcenter.securiti.ai/docs/api-quota-tracking-for-saas-connectors), for more information.

> [!WARNING]
> **Important**
> 
> Securiti emits logs and shows audit trails/activity log for SharePoint data system connector. You can view emitted logs for overall stats during each of their auth, learning, and discovery scan phases. However, Securiti does not guarantee all data processing because scanning or discovery scans have scoped options and only emit logs for the overall connector account in question.

#### Steps to connect the self-hosted connector

> [!NOTE]
> **Note**
> 
> This topic covers configuring applications and activating connectors with or without selective sites access to Microsoft 365 SharePoint Online sites.

To configure the Microsoft 365 SharePoint Online Self-hosted connector, perform the procedures in the following topics:

1. Deploy and configure a Pod using [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).
2. Grant access and obtain credentials for SharePoint Online, all sites, or selected sites access:
  - [Grant access and obtain credentials in SharePoint Online (Self-hosted)](/latest/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted)

Skip this step if you want to create applications for selected sites’ access in SharePoint.
  - [Obtain credentials for SharePoint Online Selective Site(s) Access](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access) (For selected sites access only)
3. [Connecting Microsoft SharePoint Online (Self-hosted) with Securiti](/latest/docs/connecting-microsoft-365-sharepoint-online-self-hosted-with-securiti)
4. [Configuring Data Inventory Sync for SharePoint Online (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted).
5. [Configure discovery scans in Microsoft 365 SharePoint Online](/latest/docs/configure-discovery-scans-in-microsoft-365-sharepoint-online)
6. [Configure General and Access scans settings for SharePoint Online.](/latest/docs/configuring-general-permissions-for-microsoft-365-sharepoint-online-securiti-hosted)
7. [Fulfilling SharePoint Online Self-hosted DSR requests.](/latest/docs/fulfilling-sharepoint-online-self-hosted-dsr-requests)

#### Steps to connect Securiti-Cloud connector

To configure the SharePoint Online (Securiti-Cloud) connector, perform the following steps:

1. [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud).
2. [Connecting Microsoft SharePoint Online Securiti Cloud with Securiti](/latest/docs/connecting-microsoft-365-sharepoint-online-securiti-cloud-connector).
3. [Configure General scans settings for SharePoint Online.](/latest/docs/configuring-general-permissions-for-microsoft-365-sharepoint-online-securiti-hosted)
4. [Fulfilling SharePoint Online Cloud DSR requests.](/latest/docs/fulfilling-sharepoint-online-cloud-dsr-requests)
5. [Configure DSR automation setup](/latest/docs/microsoft-365-sharepoint-connectors-configure-dsr-automation-setup).

#### Additional resources

- [Reviewing SharePoint scan results in Securiti](/latest/docs/reviewing-sharepoint-scan-results-in-securiti)
- [Microsoft 365 SharePoint Online FAQs](/latest/docs/microsoft-365-sharepoint-online-faqs).
