---
title: "Quickbase"
slug: "quickbase-connectors"
status: "new"
updated: 2026-07-20T16:27:10Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/quickbase-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Quickbase

Quickbase is a low-code platform that empowers businesses to build and deploy custom applications without extensive development expertise. It provides tools for streamlining processes, managing data, and enhancing team collaboration. It supports a wide range of use cases including project management, CRM, task tracking, and inventory management, all tailored to specific business needs.

The Quickbase connector lets you integrate your Quickbase environment with Securiti to discover and govern data stored across your custom-built business applications.

Quickbase falls under the category of monitored, unstructured data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Quickbase (Self-hosted) | - Sensitive Data Intelligence - DSR Automation using Full Scan |

### Supported pod types for self-hosted connector

- Standard Securiti
- Elastic pods (EDSS)

### Supported authentication methods

- Quickbase application based authentication
  - OAuth based authentication

### Supported items for inventory and classification scans

For more information about Inventory scans and Classification scans, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors) and [Understanding Discovery Scans](/latest/docs/discovery-scans).

- Quickbase Databases
- Files
- Apps

### Prerequisites for configuring Quickbase in Securiti

You must complete these prerequisites before connecting your Quickbase connector with Securiti.

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Quickbase with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints.

For more information on configuring pods, see [Securiti pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

You must have an admin account in Quickbase or you have authorization to create a Token for successful Connector Authentication.

#### 3. Permissions and use cases for Quickbase

This section covers use cases and permissions required for Quickbase Self-hosted connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing | You must grant admin access to authorize token creation and more. | - Permission to obtain **Realm** and **User Token**. - Authorization to **create a Token** and **assign the tokens to apps** for successful Connector authentication. | These permissions let Securiti to read files and schema metadata in Quickbase for classification purposes and to build the Personal Data Index for DSR Automation. |

### Steps to connect the Quickbase (Self-hosted) connector with Securiti

To configure the Quickbase connector, perform the procedures in the following topics:

1. [Obtain the access token in Quickbase](/latest/docs/obtain-the-access-token-in-quickbase).
2. [Connect Quickbase connector with Securiti](/latest/docs/connect-quickbase-connector-with-securiti).
3. [Configure discovery scans in Quickbase](/latest/docs/configure-discovery-scans-in-quickbase)

#### Additional resources

- [Fulfilling DSR requests for Quickbase](/latest/docs/fulfilling-dsr-requests-for-quickbase).
