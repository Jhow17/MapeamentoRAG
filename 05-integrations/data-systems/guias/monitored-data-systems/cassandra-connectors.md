---
title: "Cassandra"
slug: "cassandra-connectors"
status: "new"
updated: 2026-07-20T21:00:01Z
published: 2026-07-20T21:00:01Z
canonical: "helpcenter.securiti.ai/cassandra-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Cassandra

Cassandra is an open-source, distributed NoSQL database system. Designed to handle massive amounts of data across many commodity servers with no single point of failure, it was built as an answer to the scalability limitations of traditional relational databases. Its decentralized, peer-to-peer architecture has made it a popular choice among large-scale web applications and enterprises requiring high availability and fault tolerance across multiple data centers.

The Cassandra connector lets you integrate your Cassandra deployments with Securiti to discover and govern data stored across distributed nodes in your environment.

Cassandra falls under the category of monitored, structured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Cassandra (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported pod types

Standard Securiti Pod.

### Supported authentication methods

Cassandra (self-hosted) supports Basic authentication method, using username and password.

### Supported items for classification scans

Securiti supports following items for classification. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schema
- Tables
- Views

### Prerequisites for configuring Cassandra Self-hosted connector

#### 1. Admin access

You must have admin access to obtain required permissions and activation parameters.

For more information, see [Obtain database credentials for your Cassandra configuration](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-cassandra).

#### 2. Pod deployment

You must deploy a Securiti pod in your environment to connect your Cassandra (Self-hosted) connector.

For more information on configuring pods, see [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).

#### 3. Use cases and Permissions

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | N/A | Grant **Select** permissions to the relevant keyspace and table. | These permissions let Securiti read the files and metadata in Cassandra for classification purposes. These permissions also build the Personal Data Index for DSR Automation and enables PII data search. |

### Steps to connect Cassandra with Securiti

To configure the Cassandra (Self-hosted) connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain database credentials for your Cassandra configuration](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-cassandra).
3. [Connecting Cassandra with Securiti](/latest/docs/connect-cassandra-with-securiti).
4. [Configure discovery scans for Cassandra](/latest/docs/configure-discovery-scans-in-cassandra).

> [!NOTE]
> **Note**
> 
> Row counting for Cassandra's data system is not supported either due to the data system's inability to provide this data or the performance impact Securiti would cause on the data system by counting rows.

#### Additional resources

- [Fulfilling DSR requests for Cassandra](/latest/docs/fulfilling-dsr-requests-in-cassandra).
- [Table training for structured data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

A horizontal arrangement of data in a table representing multiple attributes arranged in their respective columns.
