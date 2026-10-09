---
title: "Snowflake"
slug: "snowflake-connectors"
status: "update"
updated: 2026-07-31T12:11:04Z
published: 2026-07-31T12:13:22Z
canonical: "helpcenter.securiti.ai/snowflake-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Snowflake

Snowflake is a cloud-based data warehousing solution for concurrently storing and retrieving data. Using large-scale organization storage systems, Snowflake-based systems are noted for their versatile scalability and unified access to storage data due to their underlying multi-cluster infrastructure. This allows resource-intensive queries to be processed concurrently, both complexity and quantity-wise, with existing processes.

Snowflake falls under the category of Monitored, Structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Snowflake (Self-hosted) | - DSR automation - Sensitive Data Intelligence (Discovery scan) - Data Access Governance - Data Access Control - Data Access Intelligence - Security Posture Management |
| Snowflake (Securiti Cloud) | - DSR automation - Sensitive Data Intelligence (Standard data scan) - Data Access Governance - Only Data Access Intelligence |

### Supported pod types for self-hosted connector

- Standard Securiti pod

### Supported authentication methods

Snowflake supports the following authentication type for authenticating and integrating with Securiti

| Authentication Type | Authentication Credentials |
| --- | --- |
| Basic (Deprecated) | - User Name - Password > [!WARNING] > **Important** > > Securiti has disabled the Basic authentication for new connector activations and reconfigurations. Because Snowflake is deprecating its basic username and password authentication method. To avoid future connection failures, we recommend you opt for Key Pair or OAuth 2.0 authentication methods. |
| OAuth 2.0 | - User Name - Client ID - Client Secret > [!CAUTION] > Caution > > OAuth 2.0 support is not available for Snowflake connection over PrivateLink in the setup, because the initial OAuth authorization and token exchange must occur outside the PrivateLink. As a result, OAuth-based authentication fails when PrivateLink is enforced end-to-end. > > To resolve the issue: > > - You can Configure the connector with other authentication methods such as Key pair Authentication. > - If OAuth is mandatory, enable public access (public link) for the OAuth flow so the connector can reach the IdP and token endpoints. |
| Key Pair Authentication | - User Name - Private Key File - (Optional) Passphrase |

#### Keyring support for Snowflake (Self-hosted)

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

> [!NOTE]
> Note
> 
> Keyrings are supported only for **Basic** (deprecated) and **Key Pair** authentication methods in Snowflake.

The table below shows the supported credential vaults for Snowflake.

| Authentication methods | Supported keyrings |
| --- | --- |
| Basic (Deprecated) | - [HashiCorp](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti) - [CyberArk](/latest/docs/cyberark-credential-vault) - [CyberArk Conjur](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault) - [CredStash](/latest/docs/configuring-credential-vaults-credstash-credential-vault) |
| OAuth 2.0 | Keyring not supported |
| Key Pair | - [HashiCorp](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti) - [CyberArk](/latest/docs/cyberark-credential-vault) - [CyberArk Conjur](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault) - [CredStash](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault) > [!NOTE] > Note > > CyberArk credential vault is not supported with the Key Pair authentication method because it cannot store authentication files. |

### Supported items for classification scans

- Database(s)
- Schemas
- Tables and Views

For more information, see [Configure discovery scans in Snowflake](/latest/docs/configure-discovery-scans-in-snowflake).

### Prerequisites for configuring Snowflake in Securiti

You must complete these prerequisites before connecting your Snowflake connector with Securiti

#### 1. Pod deployment

> [!NOTE]
> **Note**
> 
> Pod deployment is required for self-hosted connectors only.

You must deploy Securiti pod in your environment to connect your Snowflake with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/getting-started-with-securiti-pods).

#### 2. Snowflake instance and administrative access

We assume you have an existing Snowflake instance running and have admin access to configure the required permissions.

#### 3. Allowlist Snowflake URLs

To ensure the Securiti pod can connect to your Snowflake instance, you must allowlist the required Snowflake URLs. Run the command below in Snowflake to get a list of all required URLs and port combinations.

```pgsql
SELECT SYSTEM$ALLOWLIST()
```

For more information on allowlisting URLs and using `SNOWCD` tool for verification, see [Troubleshooting for Snowflake connector](/latest/docs/troubleshooting-for-snowflake-connector)

#### 4. Permissions and use cases for Snowflake

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Standard data scan (Sensitive Data Intelligence) - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | SDI Discovery Scans, Data Inventory Sync and DSR Automation Indexing is only available on the self- hosted connector | - `MONITOR` and `USAGE` privileges to schemas or tables for the role assigned to the user. - **GRANT SELECT** on tables for the role assigned to the user. | These permissions let Securiti to discover and scan tables and schemas in a database for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |
| Data Access Intelligence (Data Access Governance) | You must be an **SYSADMIN** or **ACCOUNTADMIN** to create role and assign permissions to the user. | - Grant the **OBJECT_VIEWER** to the custom role to grant SELECT privileges on the views in the ACCOUNT_USAGE schema. - Grant **Ownership** of the OAuth integration to the custom role for OAuth 2.0 authentication type. | These permissions let Securiti leverages Snowflake database permissions as part of determining which users and user groups have access to data in Snowflake and what level of permissions they have on that data. |
| Data Access Control (Data Access Governance) | Data Access Control is only available for self-hosted connector | - **CREATE ROW ACCESS POLICY** privilege for user account used for connector activation. - **CREATE MASKING POLICY** privilege for user account used for connector activation. Or you can provide: - **Ownership** permissions on the data sources, such as tables, columns, and schemas. > [!NOTE] > **Note** > > You don't need **CREATE ROW ACCESS POLICY** and **CREATE MASKING POLICY** permissions if you have assigned **Ownership** permission. | These permissions let Securiti leverage these Snowflake permissions as part of restricting access of your users and groups to Snowflake data sources, such as tables, columns, and schemas. |
| Security Posture Management rules evaluation | It is only supported for self-hosted connector. | `Sysadmin` role is required. | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |

## Connect Snowflake connectors with Securiti

See the sections below to connect your Snowflake self-hosted or Securiti Cloud connectors with Securiti.

### Steps to connect Snowflake (Self-hosted) connector with Securiti

To configure the Snowflake (Self-hosted) connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti pods](/latest/docs/getting-started-with-securiti-pods).
2. [Granting DB permissions for Snowflake](/latest/docs/granting-db-permissions-for-snowflake).
3. [Acquire authentication credentials in Snowflake](/latest/docs/acquire-authentication-credentials-in-snowflake).
4. [Connecting the Snowflake (Self-hosted) connector with Securiti](/latest/docs/connecting-snowflake-self-hosted-connector-with-securiti).
5. [Configure discovery scans in Snowflake](/latest/docs/configure-discovery-scans-in-snowflake).

#### Additional resources

- [Fulfilling Snowflake DSR Requests](/latest/docs/fulfilling-snowflake-dsr-requests).
- [Troubleshooting for Snowflake connector](/latest/docs/troubleshooting-for-snowflake-connector).

### Steps to connect Snowflake (Securiti Cloud) connector with Securiti

To configure the Snowflake (Securiti Cloud) connector, perform the following steps:

1. [Granting DB permissions for Snowflake](/latest/docs/granting-db-permissions-for-snowflake).
2. [Acquire authentication credentials in Snowflake](/latest/docs/acquire-authentication-credentials-in-snowflake).
3. [Connecting the Snowflake (Securiti-Cloud) connector with Securiti](/latest/docs/connecting-snowflake-cloud-connector-with-securiti).
4. [Configure General and Access scan settings for Snowflake (Securiti Cloud)](/latest/docs/configure-general-and-access-scan-settings-for-snowflake-securiti-cloud).
5. [Initiate Snowflake data scanning](/latest/docs/initiate-snowflake-data-scanning).
