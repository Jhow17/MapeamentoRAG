---
title: "MySQL"
slug: "mysql-connectors"
status: "new"
updated: 2026-07-31T06:42:37Z
published: 2026-07-31T06:42:54Z
canonical: "helpcenter.securiti.ai/mysql-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# MySQL

MySQL is an open source Relational Database Management System (RDBMS) that uses SQL to create and manage databases. As a relational database, MySQL stores data in tables of rows and columns organized into schemas. A schema defines how data is organized and stored and describes the relationship among various tables. With this format, developers can easily store, retrieve, and analyze many data types, including simple text, numbers, dates, times, and, more recently, JSON and vectors.

MySQL falls under the category of [structured data systems](/latest/docs/data-system-connectors) as shown in the table below:

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Self-hosted connector | - Sensitive Data Intelligence - DSR automation - Workflow - Data Breach Management |
| Securiti Cloud connector | - Sensitive Data Intelligence - DSR automation - Workflow |

### Supported pod types

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

MySQL connectors supports the following authentication type for authenticating and integrating with Securiti

- MySQL (self-hosted) connector supports basic authentication.
- MySQL Cloud connector also supports basic authentication.

#### Keyring support for MySQL (self-hosted)

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Managing Keyrings](/latest/docs/creating-keyrings).

- **HashiCorp**. See [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information.
- **CyberArk**. See [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault) for more information.
- **AWS Secrets Manager**. See [Configuring AWS Secrets Manager credential vaults](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) for more information.
- **CredStash**. See [Configuring Credstash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault) for more information.
- **Azure Key Vault**. See [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault) for more information

### Supported items for discovery scans

- MySQL Databases
- Schemas
- Tables
- Views

### Prerequisites for configuring MySQL in Securiti

You must complete these prerequisites before connecting your MySQL connector with Securiti

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your MySQL with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/getting-started-with-securiti-pods).

#### 2. Access to connect

The user account must have access to connect:

- From any host in the case of a MySQL Cloud connector
- From the pod host in case of a MySQL self-hosted connector.

For more information, see [MySQL documentation on MySQL 5.7 Reference Manual](https://dev.mysql.com/doc/refman/5.7/en/)

#### 3. Permissions and use cases for Microsoft SQL Server

| Modules use case | Constraint | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence - DSR Automation (Data Subject Rights) | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | Grant **select** permission to user connected with database. | These permissions let Securiti to read the tables and schema metadata in MySQL for classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect the MySQL with Securiti

#### Steps to Connect MySQL (self-hosted) with Securiti

To connect the MySQL (self-hosted), perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant DB permissions for MySQL self-hosted](/latest/docs/grant-db-permissions-for-mysql-self-hosted).
3. [Collect authentication information for MySQL self-hosted](/latest/docs/collect-authentication-information-for-mysql-self-hosted).
4. [Connecting MySQL (self-hosted) with Securiti](/latest/docs/connecting-mysql-self-hosted-with-securiti).
5. [Configure discovery scans in MySQL](/latest/docs/configure-discovery-scans-in-mysql).

#### Additional resources

- [Table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- [Fulfilling DSR requests for MySQL self-hosted](/latest/docs/fulfilling-dsr-requests-for-mysql-self-hosted).

#### Steps to Connect MySQL (Securiti Cloud) with Securiti

To connect the MySQL (Securiti Cloud), perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant DB permissions for MySQL Cloud](/latest/docs/grant-db-permissions-for-mysql-cloud).
3. [Collect authentication information for MySQL Cloud](/latest/docs/collect-authentication-information-for-mysql-cloud).
4. [Connecting MySQL (Securiti Cloud) with Securiti](/latest/docs/connecting-mysql-securiti-cloud-with-securiti).
5. [Configuring General permissions for MySQL (Securiti Hosted)](/latest/docs/configuring-general-permissions-for-mysql-securiti-hosted).

#### Additional resources

- [Table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
- [Fulfilling DSR requests for MySQL self-hosted](/latest/docs/fulfilling-dsr-requests-for-mysql-self-hosted).
