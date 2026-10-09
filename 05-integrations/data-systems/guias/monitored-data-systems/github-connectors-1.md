---
title: "GitHub"
slug: "github-connectors-1"
status: "new"
updated: 2026-07-08T19:39:32Z
published: 2026-07-08T19:39:32Z
canonical: "helpcenter.securiti.ai/github-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# GitHub

GitHub is a software application that lets developers and businesses to store and manage code. GitHub falls under the category of Monitored, unstructured data systems as shown in the table below.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

## Steps to connect GitHub with Securiti

To configure the GitHub connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Create an application and obtain authentication credentials in GitHub](/latest/docs/create-an-application-and-obtain-authentication-credentials-in-github)
3. [Connecting GitHub with Securiti](/latest/docs/connecting-github-with-securiti)
4. [Configure Data Inventory Sync for GitHub](/latest/docs/configure-data-inventory-sync-for-github)
5. [Configure discovery scans in GitHub](/latest/docs/configure-discovery-scans-in-github)
