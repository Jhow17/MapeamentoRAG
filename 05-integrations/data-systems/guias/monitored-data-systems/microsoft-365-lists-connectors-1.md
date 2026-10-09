---
title: "Microsoft 365 Lists"
slug: "microsoft-365-lists-connectors-1"
status: "update"
updated: 2026-07-31T06:14:01Z
published: 2026-07-31T06:14:03Z
canonical: "helpcenter.securiti.ai/microsoft-365-lists-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 Lists

The Microsoft 365 Lists connector falls under the category of Monitored, Unstructured data systems, as shown in the table below.

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for this data system. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> See [API quota tracking for SaaS connectors](/v1/docs/api-quota-tracking-for-saas-connectors), for more information.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and have no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the Microsoft 365 Lists connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).
3. [Grant permissions and obtain credentials in Microsoft 365 Lists](/v1/docs/grant-permissions-and-obtain-credentials-in-microsoft-365-lists).
4. [Connect Microsoft 365 Lists connector with Securiti](/latest/docs/connecting-microsoft-365-lists-connector-with-securiti).
5. [Configure discovery scan in Microsoft 365 Lists](/v1/docs/configure-discovery-scans-in-microsoft-365-lists).
