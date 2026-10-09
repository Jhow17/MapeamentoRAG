---
title: "Amazon RDS MariaDB"
slug: "aws-rds-mariadb-connectors"
status: "new"
updated: 2026-08-10T14:25:24Z
published: 2026-08-10T14:25:36Z
canonical: "helpcenter.securiti.ai/aws-rds-mariadb-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon RDS MariaDB

Amazon RDS MariaDB falls under the category of Monitored, Structured data systems, as shown in the table below:

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Amazon RDS MariaDB with Securiti

To configure the Amazon RDS MariaDB connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Obtain permissions and authentication credentials in Amazon RDS MariaDB](/latest/docs/obtain-permissions-and-authentication-credentials-in-aws-rds-mariadb).
3. [Connecting Amazon RDS MariaDB with Securiti](/latest/docs/connecting-aws-rds-mariadb-with-securiti).
4. [Configure discovery scans in Amazon RDS MariaDB](/latest/docs/configure-discovery-scans-in-amazon-rds-mariadb)

### Additional resources

- [Fulfilling DSR requests in Amazon RDS MariaDB](/latest/docs/fulfilling-dsr-requests-in-aws-rds-mariadb)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

## Related

- [Obtain permissions and authentication credentials in Amazon RDS MariaDB](/obtain-permissions-and-authentication-credentials-in-aws-rds-mariadb.md)
- [Configure discovery scans in Amazon RDS MariaDB](/configure-discovery-scans-in-amazon-rds-mariadb.md)
- [Fulfilling DSR requests in Amazon RDS MariaDB](/fulfilling-dsr-requests-in-aws-rds-mariadb.md)
