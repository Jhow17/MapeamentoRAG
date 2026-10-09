---
title: "Apache Phoenix"
slug: "apache-phoenix-connectors"
status: "update"
updated: 2026-09-11T09:05:12Z
published: 2026-09-11T09:06:06Z
canonical: "helpcenter.securiti.ai/apache-phoenix-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Apache Phoenix

Apache Phoenix is a high performance, relational database layer over HBase that provides low latency, high-throughput data access using standard SQL semantics. It takes your SQL query, compiles it into a series of HBase scans, and orchestrates running those scans to produce regular JDBC result sets. Apache Phoenix falls under the category of [monitored, structured data systems](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported pod types

- Standard Securiti pod.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Apache Phoenix (Self-hosted) | - Sensitive Data Intelligence (Standard Data Scan) - DSR Automation |

### Supported authentication method

- OAuth and basic authentication.

### Supported items for classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schemas
- Tables

### Prerequisites for configuring Apache Phoenix connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Apache HBase with a (Self-hosted) connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints, and Apache Phoenix API endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-v2).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Running Apache Phoenix database instance

You must have a running Apache Phoenix database instance that is an additional layer on Apache HBase database.

For more information on creating a user and assign permissions, see [Grant permissions and obtain credentials in Apache HBase](/latest/docs/grant-permissions-and-obtain-credentials-in-apache-hbase).

#### 3. Use cases and permissions for Apache Phoenix

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | Sensitive Data Intelligence is supported through Data Scan policy. Discovery scan is not supported for Apache Phoenix. | **Read** and **Write** permissions in [Apache HBase database](/latest/docs/grant-permissions-and-obtain-credentials-in-apache-hbase) | These permissions let Securiti read the files and file metadata in Apache Phoenix for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Connect your Apache Phoenix with Securiti

To configure the Apache Phoenix connector:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and obtain credentials in Apache HBase](/latest/docs/grant-permissions-and-obtain-credentials-in-apache-hbase)

> [!NOTE]
> **Note**
> 
> Apache Phoenix is a SQL query engine over the HBase database service. You must create user and assign permissions in Apache HBase before moving to Apache Phoenix connector activation.
3. [Connecting Apache Phoenix with Securiti](/latest/docs/activate-the-apache-phoenix-connector-in-securiti)
4. [Configuring general scan settings for Apache Phoenix](/latest/docs/initiate-apache-phoenix-data-scanning)
5. Do [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) for your Apache Phoenix data system.
6. [Fulfilling DSR requests for Apache Phoenix](/latest/docs/fulfilling-dsr-requests-for-apache-phoenix)

## Related

- [Grant permissions and obtain credentials in Apache HBase](/grant-permissions-and-obtain-credentials-in-apache-hbase.md)
- [Connecting Apache Phoenix with Securiti](/activate-the-apache-phoenix-connector-in-securiti.md)
- [Configuring General scan settings for Apache Phoenix](/initiate-apache-phoenix-data-scanning.md)
