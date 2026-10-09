---
title: "Progress OpenEdge DB"
slug: "progress-openedge-db-connectors"
status: "new"
updated: 2026-07-20T16:49:15Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/progress-openedge-db-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Progress OpenEdge DB

Progress OpenEdge DB is a comprehensive application development and deployment platform built around a high-performance relational database engine. Designed for building and running mission-critical business applications, it combines a robust data management layer with an integrated development environment and application server.

The Progress OpenEdge DB connector lets you integrate with Securiti to discover and govern structured data stored across your OpenEdge application databases.

Progress OpenEdge DB falls under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Progress OpenEdge DB(Self-hosted) | - Sensitive Data Intelligence (Standard Data Scan) - DSR Automation using SQL queries |

### Supported Pod types

Standard Securiti Pod.

### Supported authentication methods

Progress OpenEdge DB (self-hosted) supports Basic authentication method, using username and password.

### Supported items for classification scans

The standard inventory data scan supports scanning entities for Progress OpenEdge DB. For more information, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

### Prerequisites for configuring Progress OpenEdge DB (Self-hosted) connector

#### 1. Admin access

You must have admin access to Progress OpenEdge DB Cloud application (DB terminal in Windows, data admin tool), etc., so you can proceed with the Authentication. For more information, see [Acquire authentication credentials for your Progress OpenEdge DB configuration](/latest/docs/acquire-authentication-credentials-in-progress-openedge-db).

#### 2. Pod deployment

You must deploy a Securiti pod in your environment to connect your Progress OpenEdge DB (Self-hosted) connector. For more information on configuring pods, see [Securiti pods](/latest/docs/getting-started-with-securiti-pods).

#### 3. Use cases and Permissions

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | N/A | - **Credentials** access to create a machine, database, and users. - Access to **Progress DB terminal** in Windows to create: - Database using **prodb <db-name>** - User using **prowin32 dbname -p _admin.p** on Windows; **prowin3dbname -p _admin.p** on Windows (64) | These permissions let Securiti connect with the database in Progress OpenEdge DB. These permissions also build the Personal Data Index for DSR Automation and enables PII data search. |

### Steps to connect your Progress OpenEdge DB with Securiti

To configure the Progress OpenEdge DB connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in Progress OpenEdge DB](/latest/docs/acquire-authentication-credentials-in-progress-openedge-db).
3. [Connect Progress OpenEdge DB connector with](/latest/docs/connect-progress-openedge-db-connector-with-securiti) Securiti.
4. [Configure General scan settings for Progress OpenEdge DB](/latest/docs/initiate-progress-openedge-db-learning).

#### Additional resources

- [Table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) for the Progress Openedge DB data system instance.
- [Fulfilling DSR requests for Progress OpenEdge DB](/latest/docs/fulfilling-dsr-requests-for-progress-openedge-db).
