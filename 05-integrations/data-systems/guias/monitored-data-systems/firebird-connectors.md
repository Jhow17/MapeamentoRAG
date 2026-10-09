---
title: "Firebird"
slug: "firebird-connectors"
status: "new"
updated: 2026-07-20T19:50:57Z
published: 2026-07-20T21:00:01Z
canonical: "helpcenter.securiti.ai/firebird-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Firebird

Firebird is a relational database management system (RDBMS) that utilizes tables to store data. It offers many ANSI SQL standard features that run on Linux, Windows, and a variety of Unix platforms. Firebird offers excellent concurrency, high performance, and powerful language support for stored procedures and triggers.

The Firebird (Self-hosted) connector lets you integrate your Firebird database environment with Securiti to discover and govern structured data stored across your Firebird tables and database instances.

Firebird falls under the category of Monitored, Structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Firebird (Self-hosted) | - Sensitive Data Intelligence (Discovery scan) - DSR Automation using SQL Queries |

### Supported pod types for self-hosted connector

- Standard Securiti Pods.

### Supported authentication methods

Firebird (Self-hosted) supports Basic authentication method, using username and password.

### Supported items for classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Files

### Prerequisites for configuring Firebird connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Firebird with a Self-hosted connector. For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have admin access to grant required permissions depending on your operating system.

- For more information, see [Prerequisites for creating a Firebird server](/latest/docs/prerequisites-for-creating-a-firebird-server).

#### 3. Use cases and permissions for Firebird

This section covers use cases and permissions required for Firebird connectors.

This table covers use cases and permissions required for Firebird (Self-hosted) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Sensitive Data Intelligence (SDI) | N/A | - Access to scan your databases with the following permissions: - **Read** - **Write** - **Execute** - Access to create a Firebird database and run commands. | These permissions let Securiti read the databases and fetch metadata for PII scanning. |
| Data Subject Request (DSR) | N/A | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Firebird (Self-hosted) connector with Securiti

To configure the Firebird connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Prerequisites for creating a Firebird server](/latest/docs/prerequisites-for-creating-a-firebird-server)
3. [Create and configure a Firebird server](/latest/docs/create-and-configure-a-firebird-server) (Recommended).
4. [Set up a Firebird instance using the docker image](/latest/docs/set-up-a-firebird-instance-using-the-docker-image) (An alternative to creating a Firebird server)
5. [Connect Firebird connector with Securiti](/latest/docs/connect-firebird-connector-with-securiti).
6. [Configure discovery scans in Firebird](/latest/docs/configure-discovery-scans-in-firebird).

#### Additional resources

- [Fulfilling Firebird DSR requests](/latest/docs/fulfilling-firebird-dsr-requests).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

Structured data systems refer to the systems that are used to store structured data in the form of databases, tables, and schemas. The most common examples of unstructured data include MySQL, Oracle, Snowflake, and so on.

Securiti’s sensitive data scanning feature which lets you target specific locations by looking for specific data elements, on specific schedules and by specific owners. These settings are configured when creating a discovery scan for a data system. Discovery scan is used when a data system containing sensitive information is shared by multiple teams. Each user can create a scan job for the portion of the data system they manage. See Understanding discovery scans for more information.

Securiti uses SQL queries for the structured data systems (both cloud and self-hosted) that contain relational databases. For example, Amazon RDS, Google Cloud SQL, and Azure SQL Database. DSR using SQL queries finds primary data elements such as email, SSN, passport number, etc in the tables and columns within the database.
