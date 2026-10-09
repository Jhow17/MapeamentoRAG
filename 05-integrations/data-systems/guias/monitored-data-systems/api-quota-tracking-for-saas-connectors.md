---
title: "API quota tracking for SaaS connectors"
slug: "api-quota-tracking-for-saas-connectors"
updated: 2025-10-30T19:54:38Z
published: 2025-11-03T06:13:35Z
canonical: "helpcenter.securiti.ai/api-quota-tracking-for-saas-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# API quota tracking for SaaS connectors

Securiti provides an API Quota Tracking mechanism to ensure that the API limits set by various Cloud services, like Microsoft 365 OneDrive, are not exceeded during the data scanning or syncing processes. It is designed to help prevent hitting API rate limits, which can result in slower performance or temporary loss of access to services.

Many Cloud services limit how often you can make API calls in a given time period. For example, Microsoft 365 OneDrive allows only 12,000 API calls per 10 minutes. Exceeding these limits can cause delays or interruptions in processing your data. If these limits are hit too frequently, you may start seeing errors that delay or interrupt tasks, like scanning or syncing data. To prevent this, Securiti supports a system that tracks how many API calls are being made and adjusts accordingly to avoid triggering these rate limits.

Following are the key features of how the API quota tracking system works.

- **Tracking API calls**: When communicating with a Cloud service (like Microsoft 365), Securiti keeps track of how many API calls are made within a set time window (e.g., 10 minutes).
- **Deferring new API calls**: Once the API limit is reached (based on the provider’s documentation), Securiti temporarily pauses new API requests until the limit resets. This ensures that your data scans do not get interrupted and no errors occur due to exceeding API limits.
- **Error Notification**: If an API limit is hit, you may see an error message in your logs such as, "*API Quota Limit Exhausted: <time remaining for quota to refresh>"*

This message informs you that Securiti is waiting for the quota to reset before continuing.

When you see an API quota error, Securiti automatically manages these limits and continues the process once the API limit resets. You can monitor your logs to see when Securiti resumes the API calls.

The API quota tracking system is supported for the following Data system connectors.

| Data system | Supported Pod type |
| --- | --- |
| Box | - Self-hosted - Securiti Cloud hosted |
| DocuSign | Self-hosted |
| GitLab | Self-hosted |
| G Suite Google Drive | Self-hosted |
| Microsoft 365 Lists | Self-hosted |
| Microsoft 365 OneDrive | - Self-hosted - Securiti Cloud hosted |
| Microsoft 365 Outlook | Securiti Cloud hosted |
| Microsoft 365 Outlook (Attachments) | Self-hosted |
| Microsoft 365 Outlook (Message Body) | Self-hosted |
| Microsoft 365 SharePoint Online | - Self-hosted - Securiti Cloud hosted |
| OpenText Content Server | Self-hosted |
| Salesforce CRM | Self-hosted |
| Securiti for Box | Self-hosted |
| Slack Enterprise Grid | Self-hosted |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
