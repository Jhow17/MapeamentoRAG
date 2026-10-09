---
title: "Amazon RDS for PostgreSQL"
slug: "amazon-rds-for-postgresql-connectors"
status: "new"
updated: 2026-07-16T05:27:45Z
published: 2026-07-16T05:27:45Z
canonical: "helpcenter.securiti.ai/amazon-rds-for-postgresql-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon RDS for PostgreSQL

Amazon RDS for PostgreSQL falls under the category of Monitored, Structured data systems, as shown in the table below:

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Amazon RDS for PostgreSQL with Securiti

To configure the Amazon RDS for PostgreSQL connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain permissions and authentication credentials in Amazon RDS for PostgreSQL](/latest/docs/obtain-permissions-and-authentication-credentials-in-amazon-rds-for-postgresql).
3. [Connecting Amazon RDS for PostgreSQL with Securiti](/latest/docs/connecting-amazon-rds-for-postgresql-with-securiti).
4. [Configure discovery scans in Amazon RDS for PostgreSQL](/latest/docs/configure-discovery-scans-in-amazon-rds-for-postgresql)

### Additional resources

- [Fulfilling DSR requests in Amazon RDS for PostgreSQL](/latest/docs/fulfilling-dsr-requests-in-amazon-rds-for-postgresql)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.

## Related

- [Obtain permissions and authentication credentials in Amazon RDS for PostgreSQL](/obtain-permissions-and-authentication-credentials-in-amazon-rds-for-postgresql.md)
- [Configure discovery scans in Amazon RDS for PostgreSQL](/configure-discovery-scans-in-amazon-rds-for-postgresql.md)
- [Fulfilling DSR requests in Amazon RDS for PostgreSQL](/fulfilling-dsr-requests-in-amazon-rds-for-postgresql.md)
