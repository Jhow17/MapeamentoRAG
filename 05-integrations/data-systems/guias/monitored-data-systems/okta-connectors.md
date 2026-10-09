---
title: "Okta"
slug: "okta-connectors"
status: "new"
updated: 2026-07-31T07:34:22Z
published: 2026-07-31T07:34:27Z
canonical: "helpcenter.securiti.ai/okta-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Okta

Okta falls under the category of Monitored, Scanless data systems as shown in the table below.

| Data System and Connector Type | Characteristics |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and therefore support automation for DSR requests. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the Okta connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Okta](/latest/docs/acquire-authentication-credentials-in-okta).
2. [Connect Okta connector with Securiti](/latest/docs/connecting-okta-connector-with-securiti).

See [Fulfilling DSR requests for Okta](/latest/docs/fulfilling-dsr-requests-for-okta) for more information about how Securiti uses the Okta data to respond to DSR requests.
