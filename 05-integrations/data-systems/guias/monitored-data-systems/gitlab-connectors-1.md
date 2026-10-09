---
title: "GitLab"
slug: "gitlab-connectors-1"
status: "new"
updated: 2025-11-03T06:09:23Z
published: 2025-11-03T06:09:23Z
canonical: "helpcenter.securiti.ai/gitlab-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# GitLab connectors

GitLab is a development, security, and operations (DevSecOps) package to develop, operate, and maintain software. It provides comprehensive features to manage the software development life cycle (SDLC) from initiation to production. It provides functionalities such as:

- Version Control
- Code Hosting
- Merge Requests
- Issue Tracking
- Continuous Integration / Continuous Development (CI/CD)
- Automatic development and deployment
- Wikis and Discussions

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for the GitLab connector. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions. See [API quota tracking for SaaS connectors](/v1/docs/securiti-pods-and-elastic-pods), for more information.

| **Data system type** | **Characteristics** |
| --- | --- |
| Monitored | Scanless data systems | Connect with data systems that respond to queries on specific elements of personal data. Because Securiti can query them in real-time as DSR requests come in, it doesn’t have to scan them ahead of time and establish an internal inventory of personal data. |
| Unstructured data systems | Connect with data systems that store unstructured data and must be periodically scanned for PI content. |
| Structured data systems | Connect with structured data systems that permit selective scanning to build identities from the records they contain, but also respond to queries on specific elements of personal data and can therefore support automation for DSR requests. |
| Streaming | Connect with streaming data systems to identify sensitive data upstream in the data pipeline, and optionally protect it via masking. |
| Unmonitored | Data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in. |
| User-defined | Connect with your proprietary data system using webhooks (reverse APIs) that your IT teams develop to interface with Securiti. |

To configure the GitLab connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).
3. [Create an application and obtain authentication credentials in GitLab](/v1/docs/create-an-application-and-obtain-authentication-credentials-in-gitlab).
4. [Activate the GitLab connector in Securiti](/v1/docs/activate-the-gitlab-connector-in-securiti).
5. [Configuring Data Inventory Sync for GitLab Private Preview](/v1/docs/gitlab-connectors-configuring-data-inventory-sync-for-gitlab)
6. [Configure discovery scans in GitLab](/v1/docs/configure-discovery-scans-in-gitlab)

See [Fulfilling GitLab DSR requests](/v1/docs/fulfilling-gitlab-dsr-requests) for more information about how Securiti uses the GitLab data to respond to DSR requests.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
