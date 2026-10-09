---
title: "Amazon Athena"
slug: "amazon-athena-connectors"
status: "new"
updated: 2026-07-16T05:19:55Z
published: 2026-07-16T05:19:59Z
canonical: "helpcenter.securiti.ai/amazon-athena-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon Athena

Amazon Athena falls under the category of Monitored, structured data systems as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Amazon Athena with Securiti

To configure the Amazon Athena connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and acquire authentication credentials in Amazon Athena](/latest/docs/grant-permissions-and-acquire-authentication-credentials-in-amazon-athena).
3. [Connecting Amazon Athena with Securiti](/latest/docs/connecting-amazon-athena-with-securiti).
4. [Configure discovery scans in Amazon Athena](/latest/docs/configure-discovery-scans-in-amazon-athena)

### Additional resources

- [Fulfilling DSR requests for Amazon Athena](/latest/docs/fulfilling-dsr-requests-for-amazon-athena)

## Related

- [Grant permissions and acquire authentication credentials in Amazon Athena](/grant-permissions-and-acquire-authentication-credentials-in-amazon-athena.md)
- [Configure discovery scans in Amazon Athena](/configure-discovery-scans-in-amazon-athena.md)
- [Fulfilling DSR requests for Amazon Athena](/fulfilling-dsr-requests-for-amazon-athena.md)
