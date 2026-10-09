---
title: "Power BI Service"
slug: "power-bi-service-connectors"
status: "update"
updated: 2026-07-31T09:42:53Z
published: 2026-07-31T09:42:53Z
canonical: "helpcenter.securiti.ai/power-bi-service-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Power BI Service

Power BI Service is Microsoft’s cloud-based platform for hosting, sharing, and managing Power BI reports and dashboards. It enables users to publish reports, collaborate with others, and access insights through a web interface. The connector falls under the category of [Monitored, Structured](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Power BI Service (Self-hosted) | - Sensitive Data Intelligence (Discovery Scan) - DSR Automation using APIs and SQL queries |

### Supported pod types

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported authentication methods

- For Self-hosted connector:
  - Microsoft Azure application-based authentication
    - OAuth-based authentication

#### Keyring support for Power BI Service connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. See [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings) for more information.

- **HashiCorp**. For more information, see [Configuring HashiCorp vault instance in Securiti](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti).

HashiCorp is OAuth-supported.
  - To authenticate the Power BI Service connector without Service Principal authentication, you must configure the OAuth using [(Optional) Configure the Hashicorp OAuth token for Power BI Service](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-power-bi-service).
  - To authenticate the Power BI Service connector through Service Principal authentication, you must configure the OAuth using [Configuring OAuth token for Microsoft 365 applications](https://helpcenter.securiti.ai/docs/storing-data-system-credentials-in-hashicorp-vault#configuring-oauth-token-for-microsoft-365-applications).
- **AzureKey Vault**. For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). Azure Key Vault is OAuth-supported with Power BI Service.
- **CyberArk Vault:** For more information, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault).

### Supported items for classification scans

- Workspaces in the PowerBI tenant
- Datasets within workspaces
- Tables within datasets.

> [!NOTE]
> Note
> 
> - To see workspaces for your datasets, you must upgrade your pod version to release 1.144 or higher.
> - To update the workspaces attached to tables in existing connectors, you must reconfigure the Power BI Service connector.

For more information on Discovery scans, see [Configure discovery scans in Power BI Service](/latest/docs/configure-discovery-scans-in-power-bi-service).

### Prerequisites for configuring Power BI Service

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Power BI Service with a Self-hosted connector. Make sure the pod deployment has appropriate reachability through firewalls and network routing to reach the appropriate endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/getting-started-with-securiti-pods).

#### 2. Admin access in Power BI Service

You must be an administrator to grant permissions in the Power BI Service.

#### 3. Permissions and use cases

| Use case | Permissions | Explanation of use case |
| --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Inventory Metadata Sync - Data Subject Request (DSR) Automation Indexing | `Tenant.Read.All` `Dataset.Read.All` | These permissions let Securiti read the files and file metadata in Power BI Service for classifications purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Connect Power BI Service with Securiti

To configure the Power BI Service (Self-hosted) connector, perform the following procedures in sequence:

1. [Add a user to the Power BI workspace](/latest/docs/add-a-user-to-powerbi-workspace).
2. [Grant permissions and obtain credentials in Power BI Service](/latest/docs/grant-permissions-and-obtain-credentials-in-power-bi-service).
3. [Obtain credentials using Service Principal for Power BI](/latest/docs/grant-permissions-and-obtain-credentials-using-service-principal).
4. [Connecting Power BI with Securiti](/latest/docs/connecting-power-bi-service-with-securiti).
5. [Configure discovery scans in Power BI Service](/latest/docs/configure-discovery-scans-in-power-bi-service).

#### Additional resources

- [Fulfilling DSR requests for Power BI Service](/latest/docs/fulfilling-dsr-requests-for-power-bi-service).
