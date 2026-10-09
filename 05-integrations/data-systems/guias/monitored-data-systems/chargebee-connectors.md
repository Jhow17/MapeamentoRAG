---
title: "Chargebee"
slug: "chargebee-connectors"
status: "new"
updated: 2026-07-30T09:56:37Z
published: 2026-07-30T09:57:47Z
canonical: "helpcenter.securiti.ai/chargebee-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Chargebee

Chargebee is a billing platform for subscription-based service providers that lets them automate billing and customer notification workflows. The Chargebee platform integrates with other billing platforms such as Stripe and PayPal. It also supports productivity platforms such as Salesforce, Quickbooks, and Slack.

Chargebee is a monitored, scanless connector, as explained below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and therefore support automation for DSR requests. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

### Connect Chargebee connectors with Securiti

To configure the Chargebee connector, perform the procedures in the following topics:

1. [Register a full access key in Chargebee](/latest/docs/register-a-full-access-key-in-chargebee)
2. [Connecting Chargebee with Securiti](/latest/docs/connecting-chargebee-with-securiti)

## Additional resources

See [Fulfilling DSR requests for Chargebee](/latest/docs/fulfilling-dsr-requests-for-chargebee) for information about responding to Chargebee DSR requests.

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.
