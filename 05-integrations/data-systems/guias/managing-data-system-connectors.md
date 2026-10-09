---
title: "Data Systems"
slug: "managing-data-system-connectors"
updated: 2026-07-06T13:11:12Z
published: 2026-07-06T13:11:12Z
canonical: "helpcenter.securiti.ai/managing-data-system-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Data Systems

Data Systems are the repositories you configure in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system. The table below describes the different data system types.

To access the monitored data system connectors:

1. On the Securiti **Dashboard** in the left side navigation, click the **Main Menu** icon.
2. On the **New Navigation** sidebar, choose **Integrations** and proceed to select Data System of your choice such as **Monitored Data Systems.**

![Securiti dashboard displaying integrations and scanned document statistics for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (1).png)

## Data systems classification

Securiti supports the following types and subtypes of data systems.

- [Monitored data systems](/latest/docs/new-ui-using-the-data-systems-dashboard): These data systems are actively monitored by Securiti and can either respond in real-time (Scanless) or through periodic scans (Scanning). They support automated DSR processing, sensitive data discovery, and more.
  - Scanless data systems: Data systems that respond to queries on specific elements of personal data in real-time, without the need for pre-scanning. No internal data inventory is required ahead of time.
  - Scanning data systems: Data systems that require full or periodic scans to retrieve and identify personal or sensitive data. Scanning is essential for compliance, DSR, and sensitive data discovery. Scanning systems are further divided into the following subtypes.
    - Structured data systems: These data systems store data in structured formats like relational databases with predefined schemas (e.g., MySQL, PostgreSQL). Securiti scans records to find personal data and responds to DSR requests.
    - Unstructured data systems: These data systems store information in unstructured formats such as documents, emails, and media files. For example, SharePoint Online and Google Drive connectors. You can scan data within these connectors to detect personal or sensitive information (PII). Scans can be scheduled to run periodically to maintain up-to-date visibility into your data.
    - Hybrid data systems: Data systems that combine structured and unstructured data, requiring a customized approach for scanning. These systems often manage multiple data formats in the same repository.
    - Streaming data systems: Data systems that handle continuous, real-time streams of data. Securiti monitors these pipelines to identify and secure sensitive data as it flows, with optional data masking.
- [Unmonitored data systems](/latest/docs/using-unmonitored-data-systems-page): These data systems are not directly connected to or scanned by Securiti. You define these data systems as placeholders in the [Data Mapping Automation](/latest/docs/using-data-mapping-automation) module, so that Securiti can alert subtask owners to check them for personal data when DSR requests come in.
- [User-defined data systems](/latest/docs/user-defined-systems): Custom data systems defined by your organization, often integrated using Webhooks. These systems provide flexibility for DSR requests and compliance workflows based on proprietary configurations.
