---
title: "Microsoft Azure SQL Database"
slug: "microsoft-azure-sql-database-connectors"
status: "new"
updated: 2026-06-22T14:47:59Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/microsoft-azure-sql-database-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft Azure SQL Database

Microsoft Azure SQL Database is a relational database service that uses structured query language (SQL) for database management, which organizes data into tables with predefined schemas, rows, and columns. This structured format allows for efficient querying, indexing, and data manipulation. It falls under the category of [monitored, structured data systems](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft Azure SQL Database | - Sensitive Data Intelligence - DSR Automation using SQL queries - Breach Analysis |

### Supported pod types

Microsoft Azure SQL Database (Self-hosted) supports standard Securiti Pod.

### Supported authentication methods

Microsoft Azure SQL Database (Self-hosted) supports following authentication methods:

- Service Principal
- Service Principal with Certificate
- Basic Authentication
- Azure AD Authentication

#### Keyring support for Microsoft Azure SQL Database (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **Azure Key Vault**: For more information, see [configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault).

### Supported items for Classification Scans

Securiti supports following items for classification in Discovery scans. For more information, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schemas
- Tables
- Views

### Prerequisites for configuring the Microsoft Azure SQL Database connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Microsoft Azure SQL Database with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see [Allow-listing domains or IPs for data system connectors](/latest/docs/allow-listing-domains-or-ips-for-data-system-connectors).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Azure Storage Account

You must have an Azure Storage account in order to facilitate the connector activation process between your Microsoft Azure SQL Database and the Securiti app.

For more information, see [Using Storage Account authentication](/latest/docs/obtain-authentication-credentials-in-azure-data-lake-storage-adls-gen2) .

#### 3. Use cases and permissions for Microsoft Azure SQL Database

To provide the Microsoft Azure SQL Database access for data discovery and classification, use the following use cases and permissions.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Data Inventory Sync (Sensitive Data Intelligence) - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) | Data Inventory Sync, Discovery Scan, and DSR is only available for self-hosted connector. | **For Azure Service Principal authentication:** - Storage Blob Data Reader role. **For Azure AD authentication:** - Directory Readers role. | These permissions let Securiti discover and scan files for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect the Microsoft Azure SQL Database connector with Securiti

#### Steps to connect the Microsoft Azure SQL Database connector with Securiti

To configure the Microsoft Azure SQL Database (self-hosted) connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Create a user and grant DB permissions](/latest/docs/create-a-user-for-azure-sql-server)
3. [Acquire credentials for Basic authentication](/latest/docs/prerequisites-for-microsoft-azure-sql-database).

if you are using Service Principal, see [Acquire credentials for Service Principal authentication](/latest/docs/obtain-credentials-for-service-principal-authentication).

or if you are using Azure AD authentication, see [Acquire credentials for Azure AD authentication](/latest/docs/acquire-credentials-for-azure-ad-authentication).
4. [Connecting Microsoft Azure SQL Database with Securiti](/latest/docs/connecting-microsoft-azure-sql-database-with-securiti).
5. [Configure discovery scans in Microsoft Azure SQL Database](/latest/docs/configure-discovery-scans-in-microsoft-azure-sql-database).

#### Additional resources

- [Fulfilling DSR requests for Microsoft Azure SQL Database](/latest/docs/fulfilling-dsr-requests-for-microsoft-azure-sql-database).
