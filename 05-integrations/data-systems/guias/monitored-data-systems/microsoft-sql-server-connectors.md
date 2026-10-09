---
title: "Microsoft SQL Server"
slug: "microsoft-sql-server-connectors"
status: "new"
updated: 2026-06-19T13:39:56Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/microsoft-sql-server-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft SQL Server

The Microsoft SQL Server is a database management suite that focuses on hosting server-side relational data systems for fetching and caching information per authorized external applications' requirements. As such, the SQL Server can be deployed through either locally-hosted peer-to-peer connections on physically networked devices or across large-scale web interfaces (such as the World Wide Web). SQL Server is offered in a variety of configurations catering to both single-device systems to large-scale enterprise use cases.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Microsoft SQL Server (Self-hosted) | - DSR automation - Sensitive Data Intelligence - Security Posture Management - Workflow - Data Breach Management |

### Supported pod types

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

Microsoft SQL Server supports the following authentication types for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| - SQL Server Authentication - Azure AD Authentication | - Host - Port - User (if keyring is not used) - Password (if keyring is not used) |
| Windows Authentication | - Host - Port - Domain - User (if keyring is not used) - Password (if keyring is not used) |
| Kerberos Authentication | **Authentication Strategy: Password** - Host - Port - (Optional) Kerberos Configuration file - KDC - Kerberos Realm - Service Principle Name - User (if keyring is not used) - Password (if keyring is not used) **Authentication Strategy: Keytab** - Host - Port - (Optional) Keytab Principal - Keytab - (Optional) Kerberos Configuration file - KDC - Kerberos Realm - Service Principle Name |

#### Keyring support for Microsoft SQL Server

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings).

- **HashiCorp**. See [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information.
- **CyberArk**. See [Configuring CyberArk credential vaults](/v1/docs/configuring-credential-vaults-cyberark-credential-vault) for more information.
- **AWS Secrets Manager**. See [Configuring AWS Secrets Manager credential vaults](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) for more information.
- **CredStash**. See [Configuring Credstash credential vaults](/v1/docs/configuring-credential-vaults-credstash-credential-vault) for more information.
- **Azure Key Vault**. See [Configuring Azure Key Vault](/v1/docs/configuring-credential-vaults-azure-key-vault) for more information
- **Delinea Secret Server**. See [Configuring Delinea Secret Manager](/v1/docs/configuring-credential-vaults-delinea-secret-manager-credential-vault), for more information.

### Supported items for discovery scans

- SQL Server Databases
- Schemas
- Tables
- Views

### Prerequisites for configuring Microsoft SQL Server in Securiti

#### 1. Pod deployment

You must complete these prerequisites before connecting your SQL Server connector with Securiti

You must deploy a Securiti pod in your environment to connect your SQL Server with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 2. Read access to Microsoft SQL Server user

You must provide read access to the newly created user in the SQL Server

- For more information on providing read access to the newly SQL Server user, see [Prerequisites for Microsoft SQL Server connector](/v1/docs/prerequisites-for-microsoft-sql-server-connector).

#### 3. Allowlist appliance IP

You must allowlist appliance Public IP required on SQL Server host for connector activation.

#### 4. Permissions and use cases for Microsoft SQL Server

> [!WARNING]
> **Important**
> 
> You must have `sysadmin` role to run security posture scans for Microsoft SQL Server data system.

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector | - **select** permission on Schemas - **Read-only** role to user | These permissions let Securiti to read the tables and schema metadata in SQL Server for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |
| Security Posture Management (SPM) Rule Evaluation | - SPM is available for the user with *SYSADMIN* role. - It is available for **Windows authentication method**. | - **select** permission on Schemas | This permission let Securiti retrieves the configuration details required to evaluate the Security Posture rules. |

### Steps to connect Microsoft SQL Server to Securiti

To configure the Microsoft SQL Server connector, perform the following procedures in sequence:

1. [Grant DB permissions for SQL Server database](/latest/docs/prerequisites-for-microsoft-sql-server-connector)
2. Configure SQL Server database and obtain authentication credentials
3. [Connecting Microsoft SQL Server with Securiti](/latest/docs/new-ui-connecting-sql-server-self-hosted-with-securiti).
4. [Configuring General permissions for Microsoft SQL Server](/latest/docs/new-ui-configuring-general-permissions-for-microsoft-sql-server).
5. [Configure discovery scans in Microsoft SQL Server](/latest/docs/configure-discovery-scans-in-microsoft-sql-server).

**Additional resources**

- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

> [!NOTE]
> **Note**
> 
> Row counting for SQL Server data system is not supported either due to the data system's inability to provide this data or the performance impact Securiti would cause on the data system by counting rows.
- [Fulfilling Microsoft SQL Server DSR requests](/latest/docs/fulfilling-microsoft-sql-server-dsr-requests).
- [Microsoft SQL Server FAQs](/latest/docs/microsoft-sql-server-faqs).
- [Troubleshooting for Microsoft SQL Server connector](/latest/docs/troubleshooting-for-microsoft-sql-server-connector).
