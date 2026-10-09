---
title: "Elasticsearch"
slug: "elasticsearch-connectors"
status: "update"
updated: 2026-07-16T05:55:48Z
published: 2026-07-16T05:55:48Z
canonical: "helpcenter.securiti.ai/elasticsearch-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Elasticsearch

Elasticsearch is a distributed search and analytics engine, scalable data store, and vector database optimized for speed and relevance on production-scale workloads. Elasticsearch is the foundation of Elastic’s open stack platform. Search in near real-time over massive datasets, perform vector searches, integrate with generative AI applications, and much more.

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Elasticsearch (Self-hosted) | It supports: - Sensitive Data Intelligence - DSR Automation |

### Supported Pods type for self-hosted connector

- Standard Securiti Pods.

### Supported authentication methods

- For Self-hosted connector:
  - Basic authentication.

### Supported items for Classification Scans

Refer to [Understanding Discovery Scans](/latest/docs/discovery-scans) for more information about Classification Scans.

It scans:

- Elasticsearch databases
- Schemas
- Tables

### Prerequisites for configuring Elasticsearch connectors

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Elasticsearch with a Self-hosted connector.

Refer to the [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods) for more information on configuring Pods.

#### 2. Running Elasticsearch database

You must have a running Elasticsearch database prior to activating the connector.

#### 3. Use cases and permissions for Elasticsearch

> [!NOTE]
> **Note**
> 
> You must assign these permissions to viewer role to the user in your Elasticsearch database. To assign permissions to the Elasticsearch user role, see [Assign permissions to predefined role in Elasticsearch](/latest/docs/assign-permissions-to-pre-defined-role-in-elasticsearch-en). Assign permissions to predefined role in Elasticsearch

| Use case | Constraints | Permissions | Explanation for use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector. | Elasticsearch viewer role must have: - **read** - **view_index_metadata** | These permissions let Securiti read the Elasticsearch databases, schemas, and tables for classification purpose. These permissions also build the Personal Data Index for DSR Automation. |

## Steps to connect Elasticsearch with Securiti

To configure the Elasticsearch connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in Elasticsearch](/latest/docs/acquire-authentication-credentials-in-elasticsearch).
3. [Connecting Elasticsearch with Securiti](/latest/docs/connecting-elasticsearch-with-securiti).
4. [Configure discovery scans in Elasticsearch](/latest/docs/configure-discovery-scans-in-elasticsearch).

### Additional resources

- [Fulfilling DSR requests for Elasticsearch](/latest/docs/fulfilling-dsr-requests-for-elasticsearch)
