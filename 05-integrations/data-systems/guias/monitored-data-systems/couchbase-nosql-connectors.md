---
title: "Couchbase NoSQL"
slug: "couchbase-nosql-connectors"
status: "update"
updated: 2026-09-11T09:00:04Z
published: 2026-09-11T09:00:45Z
canonical: "helpcenter.securiti.ai/couchbase-nosql-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Couchbase NoSQL

The Couchbase NoSQL suite is an open-source document-based relational database client. Based on the notion of providing scalability and efficiency in terms of performance, the Couchbase NoSQL connector utilizes a JSON-based data model for the purpose of constructing buckets for subsequent data synchronization to external applications.

Couchbase NoSQL falls under the category of [Monitored, Structured data systems](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Couchbase NoSQL (Self-hosted) | - Sensitive Data Intelligence (Standard Data Scan) - DSR Automation using SQL queries |

### Supported pod types for self-hosted connector

Couchbase NoSQL supports Standard Securiti Pods.

### Supported authentication methods

Couchbase NoSQL supports the basic authentication method to integrate with Securiti

#### Keyring support for Couchbase NoSQL (Self-hosted)

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault.

For more information, see [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

To learn more about keyrings, refer to [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

### Connect the Couchbase NoSQL connector with Securiti

See the sections below to connect your Couchbase NoSQL (Self-hosted) connector with Securiti.

#### Steps to connect Couchbase NoSQL connector with Securiti

To configure the Couchbase NoSQL self-hosted connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Connecting Couchbase NoSQL with Securiti](/latest/docs/connecting-couchbase-nosql-with-securiti).
3. [Configuring General permissions for Couchbase NoSQL](/latest/docs/configuring-general-permissions-for-couchbase-nosql)

#### Additional resources

- [Fulfilling Couchbase NoSQL DSR requests](/latest/docs/fulfilling-couchbase-nosql-dsr-requests).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)
