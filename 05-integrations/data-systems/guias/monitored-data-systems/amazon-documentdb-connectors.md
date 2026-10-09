---
title: "Amazon DocumentDB"
slug: "amazon-documentdb-connectors"
status: "new"
updated: 2026-07-16T05:20:59Z
published: 2026-07-16T05:20:59Z
canonical: "helpcenter.securiti.ai/amazon-documentdb-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon DocumentDB

Amazon DocumentDB (with MongoDB compatibility) is a fully managed database that works with JSON documents. It helps you run important document-based applications easily and cost-effectively, no matter how large they grow, without needing to manage any of the underlying infrastructure.

Amazon DocumentDB is a document database service that supports MongoDB workloads and provides virtually unlimited storage with real-time scalability. Amazon DocumentDB provides an attractive alternative to MongoDB. In addition to providing capabilities and functionality on par with MongoDB, many other AWS services integrate with or complement Amazon DocumentDB to reduce management overhead, enhance performance, and ensure reliability.

> [!NOTE]
> **Note**
> 
> Connecting to an Amazon DocumentDB cluster directly from a public endpoint, like your laptop or local development machine, fails. Amazon DocumentDB is VPC-only and does not support public endpoints. Therefore, you cannot connect directly to your Amazon DocumentDB cluster from your laptop or local development environment outside your VPC.

Amazon DocumentDB data system falls under the category of monitored, structured data systems as described in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Amazon DocumentDB with Securiti

To configure the Amazon DocumentDB connector, perform the procedures in the following topics:

1. [Prerequisites for Amazon DocumentDB connector](/latest/docs/prerequisites-for-amazon-documentdb-connector).
2. [Create an application and obtain authentication credentials in Amazon DocumentDB](/latest/docs/create-an-application-and-obtain-authentication-credentials-in-amazon-documentdb).
3. [Connecting Amazon DocumentDB with Securiti](/latest/docs/connecting-amazon-documentdb-with-securiti).
4. [Configure discovery scans in Amazon DocumentDB](/latest/docs/configure-discovery-scans-in-amazon-documentdb).

### Additional resources

- [Fulfilling DSR requests for Amazon DocumentDB](/latest/docs/fulfilling-dsr-requests-for-amazon-documentdb).
- [Troubleshooting for Amazon DocumentDB connector](/latest/docs/troubleshooting-for-amazon-documentdb-connector).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).

## Related

- [Prerequisites for Amazon DocumentDB connector](/prerequisites-for-amazon-documentdb-connector.md)
- [Create an application and obtain authentication credentials in Amazon DocumentDB](/create-an-application-and-obtain-authentication-credentials-in-amazon-documentdb.md)
- [Configure discovery scans in Amazon DocumentDB](/configure-discovery-scans-in-amazon-documentdb.md)
- [Fulfilling DSR requests for Amazon DocumentDB](/fulfilling-dsr-requests-for-amazon-documentdb.md)
- [Troubleshooting for Amazon DocumentDB connector](/troubleshooting-for-amazon-documentdb-connector.md)
