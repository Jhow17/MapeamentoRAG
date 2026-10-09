---
title: "Oracle Service Cloud"
slug: "oracle-service-cloud-connectors"
status: "new"
updated: 2026-07-25T16:39:41Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/oracle-service-cloud-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Oracle Service Cloud

Oracle Service Cloud, is a cloud-based omnichannel customer service solution that captures a 360-degree view of every customer through a unified agent desktop. It combines case management, knowledge management, and cross-channel engagement across email, phone, chat, and social media to help organizations deliver consistent, personalized customer service at scale.

The Oracle Service Cloud connector lets you integrate with Securiti to discover and govern structured customer service data stored across your cases, contacts, and interaction records.

Oracle Service Cloud falls under the category of Hybrid data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Oracle Service Cloud (Self-hosted) | - Sensitive Data Intelligence (Standard Data Scan) - DSR Automation using APIs and SQL queries - Breach Analysis |

### Supported pod types for self-hosted connector

- Standard Securiti pod

### Supported authentication types

Oracle Service Cloud (self-hosted) supports the following authentication types:

| Authentication Type | Authentication credentials |
| --- | --- |
| Basic | - Instance Id - Username - Password |

### Supported items for classification scans

The standard inventory data scan supports scanning entities for Oracle Service Cloud. For more information, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

### Prerequisites for configuring Oracle Service Cloud in Securiti

You must complete these prerequisites before connecting your Oracle Service Cloud connector with Securiti.

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Oracle Service Cloud with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have access to use required Permissions in Oracle Service Cloud for successful Connector Authentication.

#### 3. Permissions and use cases for Oracle

This section covers use cases and permissions required for Oracle Service Cloud Self-hosted connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing - Breach Analysis | You must grant admin consent to permissions. | Access to **Authentication params** and minimum **Permissions** for successful Connector authentication, including: - Custom objects - Incidents - Contacts - Accounts | These permissions let Securiti to read the files and schema metadata in Oracle for classification purposes and to build the Personal Data Index for DSR Automation. |

### Steps to connect your Oracle Service Cloud with Securiti

To configure the Oracle Service Cloud connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Oracle Service Cloud](/latest/docs/acquire-authentication-credentials-in-oracle-service-cloud).
2. [Connect Oracle Service Cloud connector with Securiti](/latest/docs/connect-oracle-service-cloud-connector-with-securiti).
3. [Configuring General scan settings for Oracle Service Cloud](/latest/docs/initiate-oracle-service-cloud-learning).

#### Additional resources

- [Fulfilling DSR requests for Oracle Service Cloud](/latest/docs/fulfilling-dsr-requests-for-oracle-service-cloud)
