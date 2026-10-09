---
title: "Clicksign"
slug: "clicksign-connectors"
status: "new"
updated: 2026-07-30T10:10:30Z
published: 2026-07-30T10:10:37Z
canonical: "helpcenter.securiti.ai/clicksign-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Clicksign

Clicksign falls under the category of Monitored, unstructured data systems, as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

### Connect Clicksign connectors with Securiti

To configure the Clicksign connector, perform the procedures in the following topics:

1. If you haven’t already done so, install and configure a Securiti pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Acquire authentication credentials in Clicksign](/latest/docs/acquire-authentication-credentials-in-clicksign).
3. [Connecting Clicksign with Securiti](/latest/docs/connecting-clicksign-with-securiti).

## Additional resources

- See [Fulfilling DSR requests in Clicksign](/latest/docs/fulfilling-dsr-requests-in-clicksign) for information about how Securiti fulfills DSR requests for Clicksign data systems.
