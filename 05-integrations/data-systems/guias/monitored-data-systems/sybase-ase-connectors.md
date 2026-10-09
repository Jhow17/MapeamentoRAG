---
title: "Sybase ASE"
slug: "sybase-ase-connectors"
status: "update"
updated: 2026-09-22T03:37:03Z
published: 2026-09-22T03:37:03Z
canonical: "helpcenter.securiti.ai/sybase-ase-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Sybase ASE

Sybase ASE is a relational database suite for the in-house storage and analysis of both private proprietary and publicly accessible data. The focus for Sybase ASE is to deploy both public and private virtual cloud servers to enable efficient dispersal of information. Some differentiating elements of Sybase ASE database configurations from other contemporary relational databases are that of its concurrent computations on both a data and backup server, and also that of its ability to host multiple databases on a singular processing engine.

The Sybase ASE connector lets you integrate your Sybase ASE environment with Securiti to discover and govern structured data stored across your relational databases and processing engines.

Sybase ASE falls under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Sybase ASE (Self-hosted) | - Sensitive Data Intelligence (Discovery scan) - DSR Automation using SQL queries |

### Supported pod types

Standard Securiti Pod.

### Supported authentication methods

Sybase ASE (self-hosted) supports Basic authentication method, using username and password.

#### Keyring support for Self-hosted connector

You can use a keyring support to store authentication credentials in a vault during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **HashiCorp**: For more information, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

### Supported items for inventory scans

The standard inventory data scan supports scanning entities for Sybase ASE. For more information, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

### Prerequisites for configuring Sybase ASE (Self-hosted) connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Sybase ASE (Self-hosted) connector. For more information on configuring pods, see [Securiti pods](/latest/docs/getting-started-with-securiti-pods).

#### 2. Admin access

You must have admin access to Sybase jConnect account to configure synchronization of your local Sybase ASE database, so you can proceed with the Authentication. For more information, see [Configure your local Sybase ASE database for synchronization](/latest/docs/configure-your-local-sybase-ase-database-for-synchronization).

#### 3. Use cases and permissions

This table covers use cases and permissions required for Sybase ASE (Self-hosted) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | N/A | - Access to database System client for synchronization. - Access to SQL Server Connection Settings to record: - Server Host - Port - Database - Username - Password | These permissions let Securiti connect with the database in Sybase ASE. These permissions also build the PII financial data, across your Sybase ASE tables for DSR Automation. |

### Steps to connect your Sybase ASE with Securiti

To configure the Sybase ASE connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Configure your local Sybase ASE database for synchronization](/latest/docs/configure-your-local-sybase-ase-database-for-synchronization).
3. [Connect Sybase ASE connector with Securiti](/latest/docs/connect-sybase-ase-connector-with-securiti).
4. [Configure discovery scans in Sybase ASE](/latest/docs/configure-discovery-scans-in-sybase-ase)
5. [Configure General Scan settings for Sybase ASE](/latest/docs/initiate-sybase-ase-learning).

#### Additional resources

- [Fulfilling DSR requests for Sybase ASE](/latest/docs/fulfilling-dsr-requests-for-sybase-ase).
- [Table training for the Sybase data system instance](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

Securiti’s sensitive data scanning feature which lets you target specific locations by looking for specific data elements, on specific schedules and by specific owners. These settings are configured when creating a discovery scan for a data system. Discovery scan is used when a data system containing sensitive information is shared by multiple teams. Each user can create a scan job for the portion of the data system they manage. See Understanding discovery scans for more information.
