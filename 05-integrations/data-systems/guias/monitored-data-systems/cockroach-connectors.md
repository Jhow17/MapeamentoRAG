---
title: "CockroachDB"
slug: "cockroach-connectors"
status: "update"
updated: 2026-07-16T05:46:32Z
published: 2026-07-16T05:46:32Z
canonical: "helpcenter.securiti.ai/cockroach-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# CockroachDB

CockroachDB is a source-available distributed SQL database management system developed by Cockroach Labs. CockroachDB is designed for building highly resilient and scalable mission-critical applications, providing a single-node database interface with global distribution. It is built on a transactional and strongly consistent key-value store, offering familiar SQL and ACID-compliant transactions, horizontal scalability, and high availability that can survive hardware, network, or regional failures.

CockroachDB falls under the category of Monitored, Structured data systems. For more information, see [data system classifications](/v1/docs/managing-data-system-connectors).

## Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| CockroachDB (Self-hosted) | - DSR automation - Sensitive Data Intelligence (Discovery scan) |

## Supported pod types

- Standard Securiti pod

## Supported authentication methods

CockroachDB supports the **Basic** authentication type for authenticating and integrating with Securiti.

### Keyring support for CockroachDB

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/v1/docs/managing-credentials-using-keyrings).

- [HashiCorp Vault](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault)

## Supported items for classification scans

- Database(s)
- Schemas
- Tables and Views

For more information, see [Configure discovery scans for CockroachDB](/v1/docs/configure-discovery-scans-in-cockroachdb-en).

## Prerequisites for configuring CockroachDB in Securiti

You must complete these prerequisites before connecting your Cockroach connector with Securiti.

### 1. Pod deployment

> [!NOTE]
> Note
> 
> Pod deployment is required for self-hosted connectors only.

You must deploy a Securiti pod in your environment to connect your CockroachDB with a self-hosted connector. Make sure the pod deployment has appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

### 2. CockroachDB instance and access

We assume you have an existing CockroachDB instance running and have privileges to create a user and assign required permissions.

### 3. Permissions and use cases for CockroachDB

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Scoping Metadata Sync - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | SDI Discovery Scans and DSR Automation Indexing are only available on the self-hosted connector | - `Connect` permission on all databases. - `USAGE` permission on schemas - `SELECT` permissions on tables in each schema of every database | These permissions let Securiti to discover and scan tables and schemas in a database for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |

### 

## Steps to connect CockroachDB (Self-hosted) connector with Securiti

To configure the CockroachDB self-hosted connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Granting DB permissions for CockroachDB.](/latest/docs/granting-db-permissions-for-cockroachdb-en)
3. [Obtain database credentials for CockroachDB configuration](/latest/docs/granting-db-permissions-for-cockroachdb-en).
4. [Connecting CockroachDB with Securiti.](/latest/docs/activate-the-cockroachdb-connector-in-securiti-en)
5. [Configure discovery scan for CockroachDB](/latest/docs/configure-discovery-scans-in-cockroachdb-en).

For more information about how Securiti uses the data to respond to DSR requests, see [Fulfilling DSR requests for CockroachDB](/latest/docs/fulfilling-dsr-requests-for-cockroachdb).
