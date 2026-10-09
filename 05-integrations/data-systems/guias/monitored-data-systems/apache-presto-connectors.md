---
title: "Apache Presto"
slug: "apache-presto-connectors"
status: "new"
updated: 2026-07-16T05:35:56Z
published: 2026-07-16T05:35:56Z
canonical: "helpcenter.securiti.ai/apache-presto-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Apache Presto

Apache Presto is an open-source distributed SQL query engine designed for high-performance queries on datasets ranging from gigabytes to petabytes. Originally developed at Facebook for querying Hive-based data warehouses, it has since evolved to support multiple data sources.

Presto is not a general-purpose relational database and does not store data. Instead, it relies on connectors to query databases, data warehouses, and data lakes across cloud and on-premises environments, enabling efficient ad-hoc analytics. Apache Presto falls under the category of monitored, structured data system connectors. For more information, see [Data systems classification](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported pod types

- Standard Securiti pod.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Apache Presto (Self-hosted) | - Sensitive Data Intelligence - DSR Automation - Data Access Governance |

### Supported authentication method

- Basic authentication with **User** and **Password** as optional parameters.

### Supported items for classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schemas
- Tables

### Prerequisites for configuring Apache Presto connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Apache Presto with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints, and Apache Phoenix API endpoints. For more information, see the allow-listed URLs section in [Elastic pod deployment guide](/latest/docs/elastic-pods-v2) .

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. JDBC driver for connection

Apache Presto requires the Presto JDBC driver to access data from Java-based and non-Java applications running in a JVM.

The JDBC driver version must match or be newer than the Presto cluster version. While older versions may still work, only a subset is regularly tested.

Use the links below to download the driver:

- Download [presto-jdbc-0.290.jar](http://https://repo1.maven.org/maven2/com/facebook/presto/presto-jdbc/0.290/presto-jdbc-0.290.jar)
- Alternatively, get the driver from the [Maven repository](/v1/docs/securiti-pods-and-elastic-pods).

#### 3. Providing database permissions

Apache Presto does not manage users or storage. It relies on the underlying data source or connectors for this functionality. When configuring Apache Presto with connectors, you must have at least `SELECT (Read)` permissions for the database to execute queries.

#### 4. Use cases and permissions for Apache Presto

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing - Data Access Governance | NA | `SELECT (read)` permission for user credentials in database | This permission enables Securiti to read files and file metadata in the data system queried by Apache Presto for data classification. It also helps build the Personal Data Index for DSR Automation. |

### Connect your Apache Presto with Securiti

To configure the Apache Presto connector:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and obtain credentials in Apache Presto](/latest/docs/grant-permissions-and-obtain-credentials-in-apache-presto)
3. [Connecting Apache Presto with Securiti](/latest/docs/activate-the-apache-presto-connector-in-securiti)
4. [Configure discovery scans in Apache Presto](/latest/docs/configure-discovery-scans-in-apache-presto)
5. [Configuring general scan settings for Apache Presto](/latest/docs/configuring-general-scan-settings-for-apache-presto)
6. Do [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) for your Apache Presto data system.
7. [Fulfilling DSR requests for Apache Presto](/latest/docs/fulfilling-dsr-requests-for-apache-presto)

## Related

- [Grant permissions and obtain credentials in Apache Presto](/grant-permissions-and-obtain-credentials-in-apache-presto.md)
- [Connecting Apache Presto with Securiti](/activate-the-apache-presto-connector-in-securiti.md)
- [Configure discovery scans in Apache Presto](/configure-discovery-scans-in-apache-presto.md)
- [Fulfilling DSR requests for Apache Presto](/fulfilling-dsr-requests-for-apache-presto.md)
