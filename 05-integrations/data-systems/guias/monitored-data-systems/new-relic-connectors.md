---
title: "New Relic"
slug: "new-relic-connectors"
status: "new"
updated: 2026-07-31T06:59:25Z
published: 2026-07-31T06:59:25Z
canonical: "helpcenter.securiti.ai/new-relic-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# New Relic

New Relic is a Software as a Service (SaaS) platform that lets enterprise users monitor and collect data from mobile and web-based applications in real-time.

New Relic uses the REST API for integrating other monitoring services into the platform along with providing manual submission forms for users who wish to delete their personal data and accounts. New Relic states that all data processing done on its end is automated and cross-compatible with other systems. They provide an optional setting for users to disable collection of data pertaining to the query strings of URLs.

New Relic falls under the category of Monitored, Scanless data systems as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the New Relic connector, perform the procedures in the following topics:

1. [Grant permissions and acquire authentication credentials in New Relic](/latest/docs/grant-permissions-and-acquire-authentication-credentials-in-new-relic).
2. [Connect New Relic connector with Securiti](/latest/docs/connecting-relic-connector-with-securiti).

See [Fulfilling DSR requests for New Relic](/latest/docs/fulfilling-dsr-requests-for-new-relic) for more information.
