---
title: "OpenText Content Server"
slug: "opentext-content-server-connectors"
status: "new"
updated: 2026-07-31T07:38:51Z
published: 2026-07-31T07:38:55Z
canonical: "helpcenter.securiti.ai/opentext-content-server-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# OpenText Content Server

OpenText Content Server data system falls under the Monitored, Unstructured data systems category, as shown in the table below.

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for OpenText Content connector. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> 
> 
> For more information, see [API quota tracking for SaaS connectors](/latest/docs/api-quota-tracking-for-saas-connectors).

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the OpenText Content Server connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/latest/docs/getting-started-with-securiti-pods).
3. [Grant permissions and obtain credentials in OpenText Content Server](/latest/docs/grant-permissions-and-obtain-credentials-in-opentext-content-server).
4. [Connect OpenText Content Server connector with Securiti](/latest/docs/connecting-opentext-content-server-connector-with-securiti).
5. [Configure discovery scans in OpenText Content Server](/latest/docs/configure-discovery-scans-in-opentext-content-server).

See [Fulfilling DSR requests in OpenText Content Server](/latest/docs/fulfilling-dsr-requests-in-opentext-content-server) for more information about how Securiti uses the OpenText Content Server data to respond to DSR requests.
