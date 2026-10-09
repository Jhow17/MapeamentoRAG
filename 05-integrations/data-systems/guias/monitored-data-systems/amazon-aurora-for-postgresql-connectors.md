---
title: "Amazon Aurora for PostgreSQL"
slug: "amazon-aurora-for-postgresql-connectors"
status: "new"
updated: 2026-07-16T05:20:31Z
published: 2026-07-16T05:20:31Z
canonical: "helpcenter.securiti.ai/amazon-aurora-for-postgresql-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon Aurora for PostgreSQL

Amazon Aurora for PostgreSQL falls under the category of Monitored, Structured data systems, as shown in the table below:

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Amazon Aurora for PostgreSQL with Securiti

To configure the Amazon Aurora for PostgreSQL connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and obtain credentials in Amazon Aurora for PostgreSQL](/latest/docs/grant-permissions-and-obtain-credentials-in-amazon-aurora-for-postgresql)
3. [Connecting Amazon Aurora for PostgreSQL with Securiti](/latest/docs/connecting-amazon-aurora-postgresql-with-securiti)
4. [Configure discovery scans for Amazon Aurora for PostgreSQL](/latest/docs/configure-discovery-scans-in-amazon-aurora-for-postgresql)

### Additional resources

- [Fulfilling DSR requests for Amazon Aurora for PostgreSQL](/latest/docs/fulfilling-dsr-requests-for-amazon-aurora-for-postgresql)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

## Related

- [Grant permissions and obtain credentials in Amazon Aurora for PostgreSQL](/grant-permissions-and-obtain-credentials-in-amazon-aurora-for-postgresql.md)
- [Configure discovery scans in Amazon Aurora for PostgreSQL](/configure-discovery-scans-in-amazon-aurora-for-postgresql.md)
- [Fulfilling DSR requests for Amazon Aurora for PostgreSQL](/fulfilling-dsr-requests-for-amazon-aurora-for-postgresql.md)
