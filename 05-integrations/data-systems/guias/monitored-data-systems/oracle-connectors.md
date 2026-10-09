---
title: "Oracle"
slug: "oracle-connectors"
status: "new"
updated: 2026-07-31T09:00:02Z
published: 2026-07-31T09:00:10Z
canonical: "helpcenter.securiti.ai/oracle-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle

Oracle is a cloud-based enterprise services suite which include storage, networking and application solutions operating over a set of geographical disparate Oracle Data Centers. Oracle is suitable for network deployment and use among both local area networks as well as networks spanning continental distances.

In terms of its role in the data processing cycle for potential end-user, Oracle assumes the role of a processor to a client enterprise (which is designated as a controller of user information tentative for processing by Oracle as per the client’s needs.). Users of Oracle’s Cloud-based services are also expected to ensure breach detection within their databases as Oracle’s own suite of services alone do not yet distinguish authorized/unauthorized logins to a particular user’s account.

Oracle falls under the category of [Structured data systems](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Self-hosted connector | - DSR automation - Sensitive Data Intelligence - Workflow - Data Breach Management |

### Supported pod types

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

Oracle supports the following authentication type for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| Password Authentication | - Keyring - User (if keyring is not used) - Password (if keyring is not used) |
| Kerberos Authentication | **Authentication strategy: Password** - (Optional) Keyring - Kerberos Principal (if keyring is not used) - Password (if keyring is not used) - KDC - Kerberos Realm - (Optional) Service Name - (Optional) Kerberos Configuration File **Authentication strategy: Password** - Kerberos Principal - KDC - Kerberos Realm - (Optional) Service Name - Keytab File - (Optional) Kerberos Configuration File |

#### Keyring support for Oracle

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings).

- **HashiCorp**. For more information, see [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **CyberArk**. For more information, see [Configuring CyberArk credential vaults](/v1/docs/configuring-credential-vaults-cyberark-credential-vault).
- **AWS Secrets Manager**. For more information, see [Configuring AWS Secrets Manager credential vaults](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash**. See [Configuring Credstash credential vaults](/v1/docs/configuring-credential-vaults-credstash-credential-vault) for more information.
- **Azure Key Vault**. For more information, see [Configuring Azure Key Vault](/v1/docs/configuring-credential-vaults-azure-key-vault).

### Supported items for discovery scans

- Oracle Databases
- Schemas
- Tables
- Views

### Prerequisites for configuring Oracle in Securiti

You must complete these prerequisites before connecting your Oracle connector with Securiti

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Oracle with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Rights to create a user

You must have an elevated privileges in Oracle database instance to create a user and assign permissions.

- For more information on creating a user and assigning permissions, see [Granting DB permissions for Oracle](/latest/docs/granting-db-permissions-for-oracle).

#### 3. Uploading JDBC drivers

You must upload the JDBC driver for Oracle data system instance if you want to establish connection using the driver. Fore more information, see [Uploading JDBC driver files in Securiti](/latest/docs/uploading-jdbc-driver-files-in-securiti).

#### 4. Permissions and use cases for Oracle

| Modules use case | Permissions | Explanation of use case |
| --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | **SELECT** permission on ALL_USERS | These permissions let Securiti to read the tables and schema metadata in Oracle for classification purposes and to build the Personal Data Index for DSR Automation. |
| Security Posture Management Rule Evaluation | Assign `SYSDBA` role. | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

### Connect your Oracle with Securiti

Perform the following steps to connect your Oracle with Securiti.

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Granting DB permissions for Oracle](/latest/docs/granting-db-permissions-for-oracle)
3. [Connect to your Oracle Account](/latest/docs/connect-to-your-oracle-account)
4. [Connecting Oracle with Securiti](/latest/docs/connecting-oracle-with-securiti)
5. [Configuring General permissions for Oracle](/latest/docs/configuring-general-permissions-for-oracle)
6. [Configure discovery scans in Oracle](/latest/docs/configure-discovery-scans-in-oracle)

**Additional Resources**

- [Fulfilling DSR requests for Oracle](/latest/docs/fulfilling-dsr-requests-for-oracle).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
