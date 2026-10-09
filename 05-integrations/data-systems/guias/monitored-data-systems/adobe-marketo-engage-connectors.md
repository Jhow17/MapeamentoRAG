---
title: "Adobe Marketo Engage"
slug: "adobe-marketo-engage-connectors"
status: "new"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/adobe-marketo-engage-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Adobe Marketo Engage

Adobe Marketo Engage is an AI-powered marketing automation platform that streamlines, automates, and measures marketing tasks and workflows to increase operational efficiency and accelerate revenue growth. It centralizes lead and account data, orchestrates cross-channel campaigns across email, web, events, chat, and ads, and scores and routes leads to sales.

The Adobe Marketo Engage connector lets you integrate your Marketo environment with Securiti to discover and govern the lead, account, and campaign data flowing through your marketing automation workflows.

- Adobe Marketo Engage (Self-hosted) falls under the category of monitored, hybrid data systems.
- Adobe Marketo Engage (Securiti Cloud) falls under the category of monitored, scanless data systems.

For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Adobe Marketo Engage (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence (Discovery scan) - DSR Automation using APIs |
| Adobe Marketo Engage (Securiti Cloud) | Securiti Cloud connector supports: - DSR Automation using APIs |

### Supported pod types for self-hosted connector

- Standard Securiti Pods.
- Elastic Pods (EDSS).

### Supported authentication methods

- For Self-hosted connector:
  - Microsoft Marketo Engage application-based authentication
    - OAuth-based authentication for APIs
- For Securiti Cloud connector:
  - Microsoft Marketo Engage application-based authentication
    - OAuth-based authentication for APIs

#### Keyring support for Self-hosted connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**. For more information, [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **CyberArk Vault:** For more information, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault).
- **Azure Key Vault**. For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault).

### Supported items for classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Lead Databases
- Asset Databases
- Custom Objects

### Prerequisites for configuring Adobe Marketo Engage connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Adobe Marketo Engage with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and Adobe Marketo Engage API endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have admin access to grant required permissions and create custom services for generating APIs.

- For more information on connecting Adobe Marketo Engage (Self-hosted) application to Securiti, see [Grant permissions and obtain credentials in Adobe Marketo Engage (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-self-hosted-adobe-marketo-engage).
- For more information on connecting Adobe Marketo Engage (Securiti Cloud) application to Securiti, see [Grant permissions and obtain credentials in Adobe Marketo Engage (Securiti-Cloud)](/latest/docs/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage).

#### 3. Use cases and permissions for Adobe Marketo Engage

This section covers use cases and permissions required for Adobe Marketo Engage connectors.

> [!NOTE]
> **Note**
> 
> When you authenticate using OAuth based authentication, an Adobe Marketo Engage administrator must provide consent to the permissions you have configured for the application.

This table covers use cases and permissions required for Adobe Marketo Engage (Self-hosted) and Adobe Marketo Engage (Securiti Cloud) connectors. For more information, see [Marketo Developer Guide](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/bulk-extract/bulk-extract).

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | Subject to **31-day** bulk extract window | **Adobe Marketo Engage API Application permissions:** - Read-Only Lead - Read-Only Asset - Read-Only Custom Object | These permissions let Securiti read the databases and fetch metadata for People, Companies, and Marketing Assets for PII scanning. |
| Data Subject Request (DSR) | N/A | **Adobe Marketo Engage API Application permissions:** - Read-Only Lead - Read-Only Asset - Read-Only Custom Object | These permissions let Securiti read the databases and identify specific person records and their associated behavioral touchpoints. These permissions also build the Personal Data Index for DSR Automation. |

### Connect Adobe Marketo Engage connectors with Securiti

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for this data system. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> For more information, see [Marketo Engage API Limits](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/marketo-integration-best-practices#api-limits) and [API quota tracking for SaaS connectors](/latest/docs/api-quota-tracking-for-saas-connectors).

#### Steps to connect Adobe Marketo Engage (Self-hosted) connector with Securiti

To configure the Adobe Marketo Engage connector, perform the procedures in the following topics:

1. [Grant permissions and obtain credentials in Adobe Marketo Engage (Self-hosted)](/latest/docs/grant-permissions-and-obtain-credentials-in-self-hosted-adobe-marketo-engage).
2. [Connecting Adobe Marketo Engage (Self-hosted) with Securiti](/latest/docs/connecting-the-adobe-marketo-engage-self-hosted-connector-with-securiti).
3. [Configuring discovery scans for Adobe Marketo Engage (Self-hosted).](/latest/docs/configuring-discovery-scans-for-adobe-marketo-engage)

#### Additional resources

- [Fulfilling DSR Requests for Adobe Marketo Engage (Self-hosted)](/latest/docs/fulfilling-dsr-requests-for-adobe-marketo-engage-self-hosted).

#### Steps to connect Adobe Marketo Engage (Securiti Cloud) connector with Securiti

To configure the Adobe Marketo Engage connector, perform the procedures in the following topics:

1. [Grant permissions and obtain credentials in Adobe Marketo Engage (](/latest/docs/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage).
2. [Connecting Adobe Marketo Engage (Securiti Cloud) with Securiti](/latest/docs/connecting-the-adobe-marketo-engage-securiti-cloud-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR Requests for Adobe Marketo Engage (Securiti Cloud)](/latest/docs/fulfilling-dsr-requests-for-adobe-marketo-engage-securiti-cloud).

Self-hosted systems refer to computer systems or software applications that are hosted and operated by organizations or individuals who use them, rather than being hosted and operated by service providers or third parties. It becomes the responsibility of the organization to host, maintain, and manage the system or software.

Securiti’s sensitive data scanning feature which lets you target specific locations by looking for specific data elements, on specific schedules and by specific owners. These settings are configured when creating a discovery scan for a data system. Discovery scan is used when a data system containing sensitive information is shared by multiple teams. Each user can create a scan job for the portion of the data system they manage. See Understanding discovery scans for more information.

## Related

- [Grant permissions and obtain credentials in Adobe Marketo Engage (Securiti-Cloud)](/grant-permissions-and-obtain-credentials-in-securiti-cloud-adobe-marketo-engage.md)
- [Connecting the Adobe Marketo Engage (Securiti-Cloud) connector with Securiti](/connecting-the-adobe-marketo-engage-securiti-cloud-connector-with-securiti.md)
- [Fulfilling DSR Requests for Adobe Marketo Engage (Securiti-Cloud)](/fulfilling-dsr-requests-for-adobe-marketo-engage-securiti-cloud.md)
