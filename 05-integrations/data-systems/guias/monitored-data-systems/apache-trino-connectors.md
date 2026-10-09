---
title: "Apache Trino"
slug: "apache-trino-connectors"
status: "new"
updated: 2026-07-16T05:36:22Z
published: 2026-07-16T05:36:22Z
canonical: "helpcenter.securiti.ai/apache-trino-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Apache Trino

Apache Trino is a distributed SQL query engine designed for running fast, interactive analytic queries against data sources of all sizes. It supports querying data in place without the need to move it, connecting to a wide variety of data sources through connectors. Apache Trino falls under the category of [monitored, structured data systems](/latest/docs/managing-data-system-connectors#data-systems-classification).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Apache Trino (Self-hosted) | - Sensitive Data Intelligence - DSR Automation - Data Access Control |

### Supported pod types

- Standard Securiti pod.

### Supported authentication methods

- Basic (username and password)

### Supported items for classification scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Databases
- Schemas
- Tables

### Prerequisites

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Apache Trino with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints, and Apache Trino API endpoints. For more information, see the allow-listed URLs section in [Elastic pod deployment guide](/latest/docs/elastic-pods-deployment) .

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Use cases and permissions

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | NA | `GRANT SELECT` on tables. For more information, see [Grant permissions and obtain authentication credentials in Apache Trino](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-apache-trino). | These permissions let Securiti read tables and metadata in Apache Trino for classification purposes. These permissions also build the Personal Data Index for DSR Automation. |

### Connect your Apache Trino with Securiti

To configure the Apache Trino connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and obtain authentication credentials in Apache Trino](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-apache-trino).
3. [Connecting Apache Trino with Securiti](/latest/docs/activate-the-apache-trino-connector-in-securiti).
4. [Configuring general scan settings for Apache Trino](/latest/docs/configuring-general-scan-settings-for-apache-trino).
5. [Configure discovery scans in Apache Trino](/latest/docs/configure-discovery-scans-in-apache-trino).

For more information on how Securiti uses the Apache Trino data to respond to DSR requests, see [Fulfilling DSR requests for Apache Trino](/latest/docs/fulfilling-dsr-requests-for-apache-trino).

## Related

- [Grant permissions and obtain authentication credentials in Apache Trino](/grant-permissions-and-obtain-authentication-credentials-in-apache-trino.md)
- [Connecting Apache Trino with Securiti](/activate-the-apache-trino-connector-in-securiti.md)
- [Configure discovery scans in Apache Trino](/configure-discovery-scans-in-apache-trino.md)
- [Fulfilling DSR requests for Apache Trino](/fulfilling-dsr-requests-for-apache-trino.md)
