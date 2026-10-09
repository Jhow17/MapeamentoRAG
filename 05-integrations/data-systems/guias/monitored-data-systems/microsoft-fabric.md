---
title: "Microsoft Fabric"
slug: "microsoft-fabric"
status: "update"
updated: 2026-05-25T21:21:26Z
published: 2026-05-25T21:21:39Z
canonical: "helpcenter.securiti.ai/microsoft-fabric"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Fabric

The Microsoft Fabric connector lets you discover unstructured data stored in Microsoft Fabric. Securiti uses this connector to run discovery scans and collect metadata from supported Fabric workspaces and items.

This connector is a self-hosted, unstructured connector and currently supports discovery scans only. The Microsoft Fabric connector falls under the [Monitored, Unstructured data systems](/latest/docs/managing-data-system-connectors) category.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft Fabric (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - Data Subject Rights (DSR) Automation |

### Supported pods type for self-hosted connector

- Standard Securiti pods

### Supported authentication methods

Microsoft Fabric connector supports the OAuth-based authentication. Securiti requires the following credentials to authenticate with the connectors:

- Tenant ID
- Client ID
- Client Secret

For more information, see Prerequisites for Microsoft Fabric (Self-hosted).

#### Keyring support for self-hosted connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings) for more information.

Securiti currently supports the following keyrings for Microsoft Fabric:

- **Azure Key Vault**. For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault)
- **HashiCorp.** For more information, see [HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)

### Supported items for inventory and classification scans

Securiti discovers metadata and unstructured content from supported Microsoft Fabric objects, including:

- Workspace(s) and folders in it

> [!WARNING]
> Important
> 
> Securiti does not support **My Workspace** because it cannot be shared with service principals.
- Lakehouse(s) files

> [!NOTE]
> Note
> 
> - Microsoft Fabric contains structured data such as tables. However, because this data is sourced and processed through files, Securiti processes it as unstructured data.
> - Securiti does not modify data or move files during discovery scans.

For more information, see [Configuring discovery scans for Microsoft Fabric](/latest/docs/configuring-discovery-scans-for-microsoft-fabric).

### Prerequisites for configuring the Microsoft Fabric connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft Fabric with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints and Microsoft Fabric API endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 2. Allowlist Microsoft Entra ID endpoints

- Microsoft Fabric APIs must be enabled for service principal access.
- The Securiti pod must have outbound network access to Microsoft Fabric and Microsoft Entra ID endpoints.
- You must allowlist the following base URLs:
  - `https://api.fabric.microsoft.com/`
  - `https://onelake.dfs.fabric.microsoft.com/`
  - `https://api.fabric.microsoft.com/`
  - `https://graph.microsoft.com/`

#### 3. Admin account for application

You must have an admin account for Microsoft Fabric application.

#### 4. Admin consent for API permissions

You must grant admin consent for all required permissions before activating the connector.

#### 5. Permissions and use cases

The Microsoft Entra ID application must be granted permissions for:

- Microsoft Fabric APIs
- Power BI Service APIs
- OneLake (storage layer) APIs
- Microsoft Graph (basic user access)

Use the table below to understand the permissions required for scanning Microsoft Fabric data.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scans via Sensitive Data Intelligence - Data Inventory Sync - DSR Automation | You must grant admin consent to all API permissions | **Azure Storage API:** - `user_impersonation` **Power BI Service API:** - **App**: `App.Read.All` - **Capacity**: - `Capacity.Read.All` - `Capacity.ReadWrite.All` - **Code & Fabric Extensions:** - `Code.AccessFabric.All` - `Fabric.Extend` - `Fabric.Extend.IframeSandbox` - **Connections:** - `Connection.Read.All` - `Connection.ReadWrite.All` - `Connection.Reshare.All` - **Content:** - `Content.Create` - **Gateway:** - `Gateway.Read.All` - `Gateway.ReadWrite.All` - **Item (General Fabric items):** - `Item.Execute.All` - `Item.ExternalDataShare.A`ll - `Item.Read.All` - `Item.ReadWrite.All` - `Item.Reshare.All` - **Item Metadata:** - `ItemMetadata.Read.All` - `ItemMetadata.ReadWrite.All` - **Lakehouse:** - `Lakehouse.Read.All` - `Lakehouse.ReadWrite.All` - **OneLake (Storage Layer permissions):** - `OneLake.Read.All` - `OneLake.ReadWrite.All` - **Organizational Apps:** - `OrgApp.Read.All` - `OrgApp.ReadWrite.All` - **Storage Accounts:** - `StorageAccount.Read.All` - `StorageAccount.ReadWrite.All` - **Tenant:** - `Tenant.Read.All` - `Tenant.ReadWrite.All` - **Warehouse:** - `Warehouse.ReadWrite.All` - **Workspace:** - `Workspace.Read.All` - `Workspace.ReadWrite.All` **Microsoft Graph API:** - **Users:** - `User.Read` - `User.Read.All` - `Directory.Read.All` | These permissions let Securiti read the files and file metadata in Microsoft Fabric for classification and inventory purposes. These permissions also let Securiti build the Personal Data Index for DSR Automation. |

### Steps to connect Microsoft Fabric with Securiti

To connect your Microsoft Fabric (Self-hosted) with Securiti:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system connector on the pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
3. [Grant permissions and obtain credentials in Microsoft Fabric](/latest/docs/prerequisites-for-microsoft-fabric-connector)
4. [Activate the Microsoft Fabric connector in Securiti](/latest/docs/activate-microsoft-fabric-self-hosted-connector-in-securiti)
5. [Configure Microsoft Fabric discovery scans](/latest/docs/configuring-discovery-scans-for-microsoft-fabric)
6. [Configure Data Inventory Sync for Microsoft Fabric](/latest/docs/configuring-data-inventory-sync-for-microsoft-fabric)

For more information about how Securiti uses the Fabric data to respond to DSR requests, see [Fulfilling Microsoft Fabric DSR requests](/latest/docs/fulfilling-dsr-requests-for-microsoft-fabric-connector).
