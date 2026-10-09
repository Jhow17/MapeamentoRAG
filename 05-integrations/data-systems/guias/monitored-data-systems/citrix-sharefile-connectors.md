---
title: "Citrix ShareFile"
slug: "citrix-sharefile-connectors"
status: "new"
updated: 2026-07-30T10:01:29Z
published: 2026-07-30T10:01:54Z
canonical: "helpcenter.securiti.ai/citrix-sharefile-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Citrix ShareFile

ShareFile data system falls under the Monitored, Unstructured data systems category, as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

### Connect Citrix ShareFile connectors with Securiti

To configure the ShareFile connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
3. [Obtain permissions and authentication credentials in Citrix ShareFile](/latest/docs/obtain-permissions-and-authentication-credentials-in-citrix-sharefile).
4. [Connecting Critix Sharefile with Securiti](/latest/docs/connecting-critix-sharefile-with-securiti).
5. [Configure discovery scans in Citrix ShareFile](/latest/docs/configure-discovery-scans-in-citrix-sharefile).

**Additional resources**

See [Fulfilling DSR requests in Citrix ShareFile](/latest/docs/fulfilling-dsr-requests-in-citrix-sharefile) for more information about how Securiti uses the ShareFile data to respond to DSR requests.

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.
