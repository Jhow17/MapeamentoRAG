---
title: "Microsoft Dynamics 365 Finance & Operations"
slug: "microsoft-dynamics-365-finance-and-operations-connectors"
status: "update"
updated: 2026-08-11T10:14:07Z
published: 2026-08-11T10:20:48Z
canonical: "helpcenter.securiti.ai/microsoft-dynamics-365-finance-and-operations-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Dynamics 365 Finance & Operations

Microsoft Dynamics 365 Finance & Operations (F&O) is a comprehensive, cloud-based Enterprise Resource Planning (ERP) solution designed to meet the complex business needs of medium to large organizations. It unifies financial management and operational processes into a single, intelligent system, leveraging embedded analytics, financial reporting, and AI-driven insights to help businesses drive agility and growth. For more information, see [Microsoft Dynamics 365 F&O documentation](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops).

The Dynamics 365 F&O connector lets you integrate your ERP environment with Securiti to discover and govern sensitive financial and operational data stored across your Dynamics 365 Finance & Operations instance. Microsoft Dynamics 365 F&O falls under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft Dynamics 365 F&O (Self-hosted) | - Sensitive Data Intelligence |

### Supported pod types

- Standard Securiti Pods and ePods.

### Supported authentication methods

- Microsoft Azure application based authentication
  - OAuth based authentication

#### Supported Keyring for Microsoft Dynamics 365 Finance & Operations (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **Azure Key Vault**. Azure Key vault is OAuth supported with the Microsoft Dynamics 365 F&O connector. For more information, see [Configure the Azure Key Vaults](https://helpcenter.securiti.ai/docs/configuring-credential-vaults-azure-key-vault#6-configuring-the-azure-key-vault-instance-in).

### Supported items for classification scans

For more information about Classification Scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

The following entities are scanned:

- Database
- Schema
- Tables

### Prerequisites for configuring Microsoft Dynamics 365 F&O connectors

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft Dynamics 365 F&O with a Self-hosted connector. Make sure the Pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti.ai endpoints, Microsoft Graph API endpoints, and Microsoft Dynamics 365 F&O endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must be an administrator of the following entities to grant permissions and roles to apps and users.

- Azure Portal.
- Dynamics 365 F&O

#### 3. Permissions and use cases for Microsoft Dynamics 365 F&O

| Modules use case | Constraint | Permissions/ Roles | Explanation of use case |
| --- | --- | --- | --- |
| - Scoping Metadata Sync - Discovery Scan (Sensitive Data Intelligence) | SDI Discovery Scans and DSR Automation Indexing are only available on the self-hosted connector | **Dynamics ERP Delegated Permission:** - OData.FullAccess **Dynamics 365 F&O user duties:** - Read duties for required entities. | These permissions let Securiti read the tables for classification purposes. |

### Steps to connect Microsoft Dynamics 365 F&O connectors with Securiti

To configure the Microsoft Dynamics 365 F&O connector, perform the procedures in the following topics:

1. [Configure and deploy pod](/latest/docs/securiti-pods-and-elastic-pods).
2. [Grant permissions and obtain credentials for Microsoft Dynamics Dynamics 365 F&O](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en).
3. [Assign roles and permissions to Dynamics 365 F&O user](/latest/docs/assign-roles-and-permissions-to-dynamics-365-fo-user).
4. [Connect Microsoft Dynamics 365 F&O connector with Securiti](/latest/docs/connect-microsoft-dynamics-365-finance-operations-connector-with-securiti).
5. [Configure discovery scans for Microsoft Dynamics 365 F&O](/latest/docs/configure-discovery-scans-for-microsoft-dynamics-finance-operations).

#### Additional resources

- [Fulfilling DSR requests in Microsoft Dynamics 365 F&O](/latest/docs/fulfilling-dsr-requests-in-microsoft-dynamics-365-finance-operations).
- [Table Training for Microsoft Dynamics 365 F&O](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
