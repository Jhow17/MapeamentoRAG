---
title: "MixPanel"
slug: "mixpanel-connectors"
status: "new"
updated: 2026-07-31T06:25:28Z
published: 2026-07-31T06:25:28Z
canonical: "helpcenter.securiti.ai/mixpanel-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# MixPanel

MixPanel falls under the category of Monitored, Scanless data systems as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the MixPanel connector, perform the procedures in the following topics:

1. [Acquire the API access token in MixPanel](/latest/docs/acquire-the-api-access-token-in-mixpanel).
2. [Connect MixPanel connector with Securiti](/latest/docs/connecting-mixpanel-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for MixPanel](/latest/docs/fulfilling-dsr-requests-for-mixpanel).
- [MixPanel data element types for enhanced DSR processing](/latest/docs/mixpanel-data-element-types-for-enhanced-dsr-processing).
