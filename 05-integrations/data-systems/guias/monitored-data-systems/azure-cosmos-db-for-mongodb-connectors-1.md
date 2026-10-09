---
title: "Azure Cosmos DB for MongoDB"
slug: "azure-cosmos-db-for-mongodb-connectors-1"
status: "new"
updated: 2026-07-16T05:40:26Z
published: 2026-07-16T05:40:26Z
canonical: "helpcenter.securiti.ai/azure-cosmos-db-for-mongodb-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Azure Cosmos DB for MongoDB

Azure Cosmos DB for MongoDB falls under the category of Monitored, structured data systems as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Azure Cosmos DB for MongoDB with Securiti

To configure the Azure Cosmos DB for MongoDB connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Acquire authentication credentials in Azure Cosmos DB for MongoDB](/latest/docs/acquire-authentication-credentials-in-azure-cosmos-db-for-mongodb).
3. [Connecting Azure Cosmos DB for MongoDB with Securiti](/latest/docs/connecting-azure-cosmos-db-for-mongodb-with-securiti).
4. [Configuring discovery scans in Azure Cosmos DB for MongoDB](/latest/docs/configuring-discovery-scans-in-azure-cosmos-db-for-mongodb).

### Additional resources

- [Fulfilling DSR requests for Azure Cosmos DB for MongoDB](/latest/docs/fulfilling-dsr-requests-for-azure-cosmos-db-for-mongodb).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

## Related

- [Acquire authentication credentials in Azure Cosmos DB for MongoDB](/acquire-authentication-credentials-in-azure-cosmos-db-for-mongodb.md)
- [Configuring discovery scans in Azure Cosmos DB for MongoDB](/configuring-discovery-scans-in-azure-cosmos-db-for-mongodb.md)
- [Fulfilling DSR requests for Azure Cosmos DB for MongoDB](/fulfilling-dsr-requests-for-azure-cosmos-db-for-mongodb.md)
