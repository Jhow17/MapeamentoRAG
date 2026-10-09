---
title: "Apache HBase"
slug: "apache-hbase-connectors"
status: "new"
updated: 2026-07-16T05:29:58Z
published: 2026-07-16T05:29:58Z
canonical: "helpcenter.securiti.ai/apache-hbase-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Apache HBase

Apache HBase is an open-source, distributed, column-oriented database built on top of the Hadoop Distributed File System (HDFS). It is designed to host very large tables with billions of rows and millions of columns and provides real-time read and write access to big data. Apache HBase falls under the category of [monitored, structured data systems](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Apache HBase (Self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported pod types

- Standard Securiti pod.

### Supported authentication methods

- Basic (username and password)
- Kerberos (Keytab file)

### Supported items for classification scans

Securiti scans the following items for Apache HBase. For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Tables

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Apache HBase with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints, and Apache HBase API endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-v2).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Use cases and permissions

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | NA | **Read** and **Write** permissions. For more information, see [Grant permissions and obtain credentials in Apache HBase](/latest/docs/grant-permissions-and-obtain-credentials-in-apache-hbase). | These permissions let Securiti read the tables and metadata in Apache HBase for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Connect your Apache HBase with Securiti

To configure the Apache HBase connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and obtain credentials in Apache HBase](/latest/docs/grant-permissions-and-obtain-credentials-in-apache-hbase)
3. [Connecting Apache HBase with Securiti](/latest/docs/activate-the-apache-hbase-connector-in-securiti)
4. [Configure discovery scans in Apache HBase](/latest/docs/configure-discovery-scans-in-apache-hbase)
5. Do [table training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) for the Apache HBase data system instance.

For more information on how Securiti uses the Apache HBase data to respond to DSR requests, see [Fulfilling DSR requests for Apache HBase](/latest/docs/fulfilling-dsr-requests-for-apache-hbase).

## Related

- [Grant permissions and obtain credentials in Apache HBase](/grant-permissions-and-obtain-credentials-in-apache-hbase.md)
- [Connecting Apache HBase with Securiti](/activate-the-apache-hbase-connector-in-securiti.md)
- [Configure discovery scans in Apache HBase](/configure-discovery-scans-in-apache-hbase.md)
- [Fulfilling DSR requests for Apache HBase](/fulfilling-dsr-requests-for-apache-hbase.md)
