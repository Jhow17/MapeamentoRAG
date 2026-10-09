---
title: "Discovery scans"
slug: "discovery-scans"
status: "update"
updated: 2026-09-29T11:00:14Z
published: 2026-09-29T11:08:38Z
canonical: "helpcenter.securiti.ai/discovery-scans"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Discovery scans

Sensitive data discovery is the process of identifying and locating sensitive information, such as personal data, intellectual property, and confidential business data, within an organization's data assets and systems, whether on-premises, in the cloud, or in hybrid environments.

As data-driven organizations generate and manage large volumes of sensitive data, they require robust security and compliance measures to protect against breaches and exploitation risks. Automated sensitive data discovery helps organizations identify, classify, and protect sensitive data that, if exposed, could lead to reputational damage. Unlike manual discovery, which is time-consuming and prone to human errors, automated solutions provide greater accuracy and efficiency in securing data assets.

Discovery scans are how Securiti performs this discovery across your environment. You can run discovery scans against Structured data systems (relational databases and data warehouses), Unstructured data systems (file shares and cloud storage), and streaming data systems (Kafka topics), so you get consistent classification results regardless of where your sensitive data lives.

Each discovery scan classifies the data it finds against your configured data elements and content classifiers, so you know not just where sensitive data exists, but what kind of data it is. You can use this classification to drive downstream actions, such as applying data protection policies, triggering breach impact assessments, or feeding results into your broader data risk and compliance workflows.

You can use discovery scans to target specific data systems and look for specific data elements, on specific schedules, by specific owners, and so on. You can launch scan jobs on demand or periodically. You can also configure responses to be taken at the completion of the scan.

This feature helps you accommodate situations where a data system may be used or shared by multiple teams for different purposes and contain different types of sensitive data. Each team can control the scan jobs for the portions of the data system they manage.

### Prerequisites

Before running a discovery scan, ensure the following:

- Configure and [activate the data system](/latest/docs/configuring-connectors-for-monitored-data-systems).
- For self-hosted data systems, [activate a pod or an elastic pod](https://helpcenter.securiti.ai/v1/docs/securiti-pods-and-elastic-pods).
- Configure the following classification types:
  - [Data elements](/latest/docs/configuring-custom-data-element-types)
  - [Content profiles](/latest/docs/configuring-content-profiles)
  - [Data dictionaries](/latest/docs/configuring-dictionaries)
  - [Document categories](/latest/docs/configuring-document-categories-and-types-1)
  - [File formats](/latest/docs/configuring-file-formats)
  - [Exact data indexes and profiles](/latest/docs/using-exact-data-indexes-and-profiles)

### Types of data systems supported

Discovery scans support four connector types, each with its own scan configuration:

| Type | Description |
| --- | --- |
| **Structured** | Data stored in tables, rows, and columns. For example, databases and data warehouses. |
| **Unstructured** | Data stored in files, folders, emails, and documents. For example, SharePoint and Amazon S3. |
| **Streaming** | Data flowing through topics and messages. For example, Kafka. |
| **Hybrid** | Data systems that combine structured and unstructured data. |

For more information, see [Supported data systems for discovery scans](/latest/docs/supported-data-systems-for-discovery-scans).

### Additional resources

- [Using the scan definitions page](/latest/docs/using-the-scan-definitions-page)
- [Classification validation and fine tuning](/latest/docs/classification-validation-and-fine-tuning-for-structured-data)
- [Discovery scans for structured connectors](/latest/docs/creating-a-discovery-scan-for-structured-connectors)
- [Discovery scans for unstructured connectors](/latest/docs/discovery-scans-for-unstructured-connectors)
- [Discovery scans for streaming connectors](/latest/docs/discovery-scans-for-streaming-connectors)
- [Managing scan definitions](/latest/docs/managing-scan-definitions)
- [File skip and error reasons](/latest/docs/file-skip-and-error-reasons)
- [Discovery scan FAQs](/latest/docs/discovery-scan-faqs)

Structured data systems refer to the systems that are used to store structured data in the form of databases, tables, and schemas. The most common examples of unstructured data include MySQL, Oracle, Snowflake, and so on.

An unstructured data systems refers to the systems that are used to store unstructured data. The most common examples of unstructured data include Microsoft OneDrive, Google Drive, AWS S3, and so on.

## Related

- [Viewing scan results](/viewing-discovery-scan-results.md)
- [Supported data systems for discovery scans](/supported-data-systems-for-discovery-scans.md)
- [Managing scan definitions](/managing-scan-definitions.md)
- [Viewing the discovery scan calendar dashboard](/viewing-discovery-scan-calendar-dashboard.md)
