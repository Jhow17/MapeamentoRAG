---
title: "Oracle Autonomous Data Warehouse"
slug: "oracle-autonomous-data-warehouse-connectors-1"
status: "new"
updated: 2026-07-16T07:27:19Z
published: 2026-07-16T07:27:19Z
canonical: "helpcenter.securiti.ai/oracle-autonomous-data-warehouse-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle Autonomous Data Warehouse

Oracle Autonomous Data Warehouse is a cloud-based, self-managing data warehouse service optimized for analytics and reporting. By connecting Oracle Autonomous Data Warehouse with Securiti, organizations can discover and classify sensitive data through Sensitive Data Intelligence (SDI) and efficiently locate personal data for Data Subject Requests (DSR), helping strengthen data governance and privacy compliance.

Oracle Autonomous Data Warehouse falls under [Monitored, structured data systems](/latest/docs/managing-data-system-connectors).

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Oracle Autonomous Data Warehouse (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported Pod types

Oracle Autonomous Data Warehouse supports standard Securiti Pod.

### Supported authentication methods

Securiti supports basic authentication method for Oracle Autonomous Data Warehouse.

#### Keyring support for Oracle Autonomous Data Warehouse (Self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

- **Basic**.

### Supported items for Classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schemas
- Tables
- Views

### Prerequisites for configuring Oracle Autonomous Data Warehouse connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Oracle Autonomous Data Warehouse with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 2. Oracle Autonomous Data Warehouse instance

You must have access to a running Oracle Autonomous Data Warehouse instance. If you do not manage the instance, coordinate with your Oracle Cloud administrator to obtain the required access and configuration details.

#### 3. Database user with required permissions

You must create or use a database user with the required permissions to connect to the database. At a minimum, the user must have the required session and database access privileges (such as `CREATE SESSION`, `CONNECT`, and `DWROLE`) to support connector activation. For more information, see [Granting DB permissions for Oracle Autonomous Data Warehouse](/latest/docs/granting-db-permissions-for-oracle-autonomous-data-warehouse).

#### 4. Configured Oracle wallet

You must download and configure the Oracle Autonomous Data Warehouse wallet for secure remote connectivity. Update the required wallet configuration files (`ojdbc.properties` and `sqlnet.ora`) and place the wallet ZIP file in the appropriate driver directory before activating the connector. For more information, see [Acquire authentication credentials in Oracle Autonomous Data Warehouse](/latest/docs/acquire-authentication-credentials-in-oracle-autonomous-data-warehouse).

### Connect Oracle Autonomous Data Warehouse with Securiti

To configure the Oracle Autonomous Data Warehouse (Self-hosted) connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Granting DB permissions for Oracle Autonomous Data Warehouse](/latest/docs/granting-db-permissions-for-oracle-autonomous-data-warehouse).
3. [Acquire authentication credentials in Oracle Autonomous Data Warehouse](/latest/docs/acquire-authentication-credentials-in-oracle-autonomous-data-warehouse).
4. [Connecting Oracle Autonomous Data Warehouse with Securiti](/latest/docs/connecting-oracle-autonomous-data-warehouse-with-securiti).
5. [Configure discovery scans in Oracle Autonomous Data Warehouse](/latest/docs/configure-discovery-scans-in-oracle-autonomous-data-warehouse).

**Additional resources**

- [Fulfilling DSR requests for Oracle Autonomous Data Warehouse](/latest/docs/fulfilling-dsr-requests-for-oracle-autonomous-data-warehouse).
