---
title: "Amazon RDS for Sql Server"
slug: "amazon-rds-for-ms-sql-server-connector"
status: "update"
updated: 2026-07-16T05:26:33Z
published: 2026-07-16T05:26:33Z
canonical: "helpcenter.securiti.ai/amazon-rds-for-ms-sql-server-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon RDS for Sql Server

Amazon RDS for SQL Server is a managed relational database service that simplifies the setup, operation, and scaling of Microsoft SQL Server deployments in the cloud. It is part of Amazon's Relational Database Service (RDS) and provides a fully managed solution for running SQL Server databases, eliminating the need for extensive infrastructure management.

Amazon RDS for Sql Server falls under the category of monitored, structured data systems, as described in [data systems classification](/latest/docs/managing-data-system-connectors).

## Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Amazon RDS for Sql Server (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation |

## Supported pod types

Securiti supports a self hosted pod connector for connecting to Amazon RDS for Sql Server data system. For more information, see [Configuring Securiti pods](https://helpcenter.securiti.ai/docs/securiti-pods-and-elastic-pods).

## Supported authentication methods

Amazon RDS for Sql Server supports the following authentication types for authenticating and integrating with Securiti.

| Authentication Type | Authentication Credentials |
| --- | --- |
| Basic | - Host - Port - User (if keyring is not used) - Password (if keyring is not used) |

### Keyring support for Amazon RDS for Sql Server

You can use a keyring during the connector configuration process to securely access your credentials from a vault. For more information, see [Using Keyrings](https://helpcenter.securiti.ai/docs/managing-credentials-using-keyrings).

- **AWS Secret Manager**. For more information, see [Configuring AWS Secrets Manager credential vaults](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault).
- **CredStash**. For more information, see [Configuring CredStash credential vaults](/latest/docs/configuring-credential-vaults-credstash-credential-vault).
- **CyberArk**. For more information, see [Configuring CyberArk credential vaults](/latest/docs/cyberark-credential-vault).
- **HashiCorp**. For more information, see [Configuring HashiCorp credential vault](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

## Supported items for classification scans

Securiti supports discovery scans for Amazon RDS for Sql Server databases. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

Following entities scanned for databases:

- Tables
- Schemas
- Columns

For more information, see [/document/preview/705708#UUID-5f071677-977b-eb32-72fc-48bdac4272f9](/document/preview/705708#UUID-5f071677-977b-eb32-72fc-48bdac4272f9).

## Prerequisites for configuring Amazon RDS for Sql Server (Self-hosted) connector

### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Amazon RDS for Sql Server with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/modules/appliances/en/index-en.html?contextId=settingsElasticsPods).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/modules/appliances/en/index-en.html?contextId=podsConfigPods).

### 2. Read access to Microsoft SQL Server user

You must provide read access to the newly created user in the SQL Server.

### 3. Allowlist appliance IP

You must allowlist appliance Public IP required on SQL Server host for connector activation.

### 4. Use cases and permissions for Amazon RDS for Sql Server

This section covers use cases and permissions required for Amazon RDS for Sql Server self-hosted connector.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self-hosted connector. | - **select** permission on Schemas - **Read-only** role to user | These permissions let Securiti to read the tables and schema metadata in SQL Server for inventory and classification purposes and to build the Personal Data Index for DSR Automation. |

## Steps to connect Amazon RDS for Sql Server with Securiti

To configure the Amazon RDS for Sql Server connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Prerequisites for Amazon RDS for Sql Server](/latest/docs/prerequisites-for-amazon-rds-for-ms-sql-server-en)
3. [Connecting Amazon RDS for Sql Server with Sercuiti](/latest/docs/connecting-amazon-rds-for-ms-sql-server-with-sercuiti)
4. [Configure discovery scans in Amazon RDS for Sql Server](/latest/docs/configure-discovery-scan-in-amazon-rds-for-mysql)

### Additional resources

- [Fulfilling DSR requests in Amazon RDS for Sql Server](/latest/docs/fulfilling-dsr-requests-in-amazon-rds-for-ms-sql-server-en)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
