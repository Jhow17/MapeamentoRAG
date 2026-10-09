---
title: "Braze"
slug: "braze-connectors"
status: "update"
updated: 2026-07-30T09:49:14Z
published: 2026-07-30T09:49:14Z
canonical: "helpcenter.securiti.ai/braze-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Braze

This document covers integration and activation process for both self-hosted and Securiti Cloud connectors.

Braze (Self-hosted) connector falls under the category of Monitored, structured data systems. Braze (Securiti-Cloud) connector is a monitored, scanless connector, as shown below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the Braze connector, perform the following procedures in sequence:

#### Steps to connect Braze (Self-hosted) connector with Securiti

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods)
3. [Prerequisites for Braze (self-hosted) connector](/latest/docs/prerequisites-for-braze-self-hosted-connector)
4. [Obtain permissions and authentication credentials in Braze](/latest/docs/obtain-permissions-and-authentication-credentials-in-braze)
5. [Connecting the Braze (Self Hosted) with Securiti](/latest/docs/connecting-braze-with-securiti)
6. [Configure discovery scans in Braze](/v1/docs/configure-discovery-scans-in-braze)
7. [Troubleshooting for Braze (self-hosted) connector](/latest/docs/troubleshooting-for-braze-self-hosted-connector)

#### Steps to connect Braze (Securiti-Cloud) connector with Securiti

1. [Obtain permissions and authentication credentials in Braze](/v1/docs/obtain-permissions-and-authentication-credentials-in-braze)
2. [Connecting the Braze (Securiti-Cloud) with Securiti](/latest/docs/connecting-the-braze-cloud-with-securiti)

#### Additional resources

- [Fulfilling DSR requests for Braze](/v1/docs/fulfilling-dsr-requests-for-braze)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

## Related

- [Prerequisites for Braze (self-hosted) connector](/prerequisites-for-braze-self-hosted-connector.md)
- [Obtain permissions and authentication credentials in Braze](/obtain-permissions-and-authentication-credentials-in-braze.md)
- [Configure discovery scans in Braze](/configure-discovery-scans-in-braze.md)
- [Fulfilling DSR requests for Braze](/fulfilling-dsr-requests-for-braze.md)
- [Troubleshooting for Braze (self-hosted) connector](/troubleshooting-for-braze-self-hosted-connector.md)
