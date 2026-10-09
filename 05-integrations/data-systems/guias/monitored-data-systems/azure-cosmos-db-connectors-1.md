---
title: "Azure Cosmos DB"
slug: "azure-cosmos-db-connectors-1"
status: "new"
updated: 2026-07-16T05:40:09Z
published: 2026-07-16T05:40:09Z
canonical: "helpcenter.securiti.ai/azure-cosmos-db-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Azure Cosmos DB

You can integrate your Azure Cosmos DB with Securiti and scan data for your data system. Azure Cosmos DB falls under the category of [monitored, unstructured data system](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Azure Cosmos DB (self-hosted) | - Sensitive Data Intelligence - DSR Automation |

### Supported pod types for self-hosted connector

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported authentication methods

| Authentication method | Authentication credentials |
| --- | --- |
| Storage Account | Account Key |
| Azure Service Principal | - Tenant Id - Client Id - Client Secret |

### Supported items for Classification Scans

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring Azure Cosmos DB Storage connector

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Azure Cosmos DB with a Self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see [Allow-listing domains or IPs for data system connectors](/latest/docs/allow-listing-domains-or-ips-for-data-system-connectors).

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### 2. Create a Microsoft Entra ID app

You must create a Microsoft Entra ID app in order to facilitate the connector activation process between your Azure Cosmos DB and the Securiti app.

For more information, see [Prerequisites for Azure Cosmos DB](/latest/docs/prerequisites-for-azure-cosmos-db).

#### 4. Use cases and permissions for Azure Cosmos DB

To provide the Azure Cosmos DB access for classification, use the following use cases and permissions.

| Use case | Permissions | Explanation of use case |
| --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) | Assign the `Reader` role. | This permission lets Securiti discover and scan databases for classification purposes and to build the Personal Data Index for DSR Automation. |

## Steps to connect Azure Cosmos DB with Securiti

To configure the Azure Cosmos DB connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Prerequisites for Azure Cosmos DB](/latest/docs/prerequisites-for-azure-cosmos-db).
3. [Connecting Azure Cosmos DB with Securiti](/latest/docs/connecting-azure-cosmos-db-with-securiti).
4. [Configure discovery scans in Azure Cosmos DB](/latest/docs/configure-discovery-scans-in-azure-cosmos-db).

### Additional resources

- [Fulfilling DSR requests for Azure Cosmos DB](/latest/docs/fulfilling-dsr-requests-for-azure-cosmos-db).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

## Related

- [Prerequisites for Azure Cosmos DB](/prerequisites-for-azure-cosmos-db.md)
- [Configure discovery scans in Azure Cosmos DB](/configure-discovery-scans-in-azure-cosmos-db.md)
