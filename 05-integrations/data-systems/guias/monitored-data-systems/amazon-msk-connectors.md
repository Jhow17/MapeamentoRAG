---
title: "Amazon MSK"
slug: "amazon-msk-connectors"
status: "new"
updated: 2026-07-16T05:21:43Z
published: 2026-07-16T05:21:43Z
canonical: "helpcenter.securiti.ai/amazon-msk-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon MSK

Amazon MSK falls under the category of Monitored, streaming data systems, as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect Amazon MSK with Securiti

To configure the Amazon MSK connector, perform the procedures in the following topics:

1. [Obtain credentials in Amazon MSK](/latest/docs/obtain-credentials-in-amazon-msk)
2. [Connecting Amazon MSK with Securiti](/latest/docs/connecting-amazon-msk-with-securiti)
3. [Configure discovery scans in Amazon MSK](/latest/docs/configure-discovery-scans-in-amazon-msk)

## Related

- [Obtain credentials in Amazon MSK](/obtain-credentials-in-amazon-msk.md)
- [(Optional) Grant permissions for Amazon MSK cluster running ACL](/optional-grant-permissions-for-amazon-msk-cluster-running-acl.md)
- [Configure discovery scans in Amazon MSK](/configure-discovery-scans-in-amazon-msk.md)
