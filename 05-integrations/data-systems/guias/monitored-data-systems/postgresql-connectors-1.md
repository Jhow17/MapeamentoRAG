---
title: "PostgreSQL"
slug: "postgresql-connectors-1"
status: "new"
updated: 2026-05-29T05:35:46Z
published: 2026-05-29T05:35:46Z
canonical: "helpcenter.securiti.ai/postgresql-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# PostgreSQL

PostgreSQL is an open-source relational database suite which is regarded to possess certain superior traits compared to other database solutions in its category. These are respectively that of its ability to maintain concurrency while simultaneously remaining acid, a more efficient schema classification system, and a more user-friendly administrator/client hierarchical setup. However PostgreSQL has been noted to lag in terms of processing a large number of small workloads in a limited time interval.

PostgreSQL falls under the category of [Monitored, Structured](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| PostgreSQL (self-hosted) | - DSR Automation using SQL queries - Discovery Scan (Sensitive Data Intelligence) - Breach Analysis - Workflow |
| PostgreSQL Cloud (Securiti cloud) | - DSR Automation using SQL queries |

### Supported Pod types

Securiti supports standard Securiti Pod for PostgreSQL (self-hosted).

### Supported authentication method

Securiti supports basic authentication method for both PostgreSQL connectors.

#### Keyring support for PostgreSQL (self-hosted) connector

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/using-keyrings).

- **Basic keyring.**
- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).
- **CyberArk**: For more information, see [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault).
- **AWS Secrets Manager**: For more information, see [Configuring AWS Secrets Manager credential vaults](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash**: For more information, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault).
- **Azure Key Vault**: For more information, see [Configuring Azure Key Vault](/v1/docs/configuring-credential-vaults-azure-key-vault).

### Supported items for classification scans

Following items are supported for PostgreSQL. For more information on Discovery scans, see [Configure discovery scans in PostgreSQL](/latest/docs/configure-discovery-scans-in-postgresql-en).

- All database schemas in a data system.
- All table views in a database schema.

### Prerequisites for configuring PostgreSQL

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your PostgreSQL with a self-hosted connector. Make sure the pod deployment has appropriate reachability through firewalls and network routing to reach the appropriate endpoints.

For more information on configuring pods, see [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).

#### 3. Permissions and use cases

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans is only available on the self-hosted connector | - `pg_catalog` - `information_scheme` - all schemes on all databases that require scanning | These permissions let Securiti read the schema tables in PostgreSQL for classifications purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Connect PostgreSQL with Securiti

**New UI**

#### Steps to connect PostgreSQL (self-hosted) connector with Securiti

To configure the PostgreSQL (self-hosted) connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Granting DB permissions for PostgreSQL](/latest/docs/granting-db-permissions-for-postgresql)
3. [Obtain database credentials for your PostgreSQL configuration](/latest/docs/obtain-database-credentials-for-your-postgresql-configuration)
4. [(New UI) Connecting PostgreSQL (self-hosted) with Securiti](/latest/docs/new-ui-connecting-postgresql-self-hosted-with-securiti)
5. [Configure discovery scans in PostgreSQL](/latest/docs/configure-discovery-scans-in-postgresql-en)

#### Steps to connect PostgreSQL Securiti cloud connector with Securiti

To configure the PostgreSQL (Securiti cloud) connector, perform the following procedures in sequence:

1. [Granting DB permissions for PostgreSQL](/latest/docs/granting-db-permissions-for-postgresql)
2. [Obtain database credentials for your PostgreSQL configuration](/latest/docs/obtain-database-credentials-for-your-postgresql-configuration)
3. [(New UI) Connecting PostgreSQL Cloud (Securiti Cloud) with Securiti](/latest/docs/new-ui-connecting-postgresql-cloud-securiti-cloud-with-securiti)
4. [(New UI) Configuring General permissions for PostgreSQL (Securiti cloud)](/latest/docs/new-ui-configuring-general-permissions-for-postgresql-securiti-cloud)

**Classic UI (Deprecated**

To configure the PostgreSQL connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Granting DB permissions for PostgreSQL](/latest/docs/granting-db-permissions-for-postgresql)
3. [Obtain database credentials for your PostgreSQL configuration](/latest/docs/obtain-database-credentials-for-your-postgresql-configuration)
4. [Activate the PostgreSQL connector in Securiti](/latest/docs/activate-the-postgresql-connector-in-securiti)
5. [Initiate PostgreSQL learning](/latest/docs/initiate-postgresql-learning)

**Additional resources:**

- [Fulfilling DSR requests for PostgreSQL](/latest/docs/fulfilling-dsr-requests-for-postgresql).
- [(New UI) Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
