---
title: "Data Explorers"
slug: "data-explorers"
status: "update"
updated: 2026-02-12T11:43:21Z
published: 2026-02-12T11:43:21Z
canonical: "helpcenter.securiti.ai/data-explorers"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Data Explorers

Securiti platform provides dashboards to visualize the results of discovery scans for structured, unstructured, and streaming data systems. They offer deep insights into the specific *data elements* discovered, the content profiles, and the data systems they belong to. This comprehensive view helps you better understand and manage your data.

If you've already completed discovery scans and have sensitive data in your systems, you can now locate that data using filters in the [structured](https://helpcenter.securiti.ai/docs/discovery-scans#discovery-scans-for-structured-data-systems), [unstructured](https://helpcenter.securiti.ai/docs/discovery-scans#discovery-scan-for-unstructured-data-systems), [streaming](https://helpcenter.securiti.ai/docs/discovery-scans#discovery-scan-for-streaming-data-systems) data discovery dashboards or the [Graph Explorer](/v1/docs/using-graph-explorer) dashboards. You can also save searches to quickly identify new files, objects, or tables that may contain sensitive data at risk, helping you monitor and respond proactively.

| Dashboard | Purpose |
| --- | --- |
| Data Systems Overview | Provides stats related to your IaaS and SaaS cloud account onboarding and asset discovery. For more information, see [Using the Data Systems Overview dashboard](/v1/docs/using-the-data-systems-overview-dashboard). |
| Universal Data Explorer | Lets you create custom queries to filter data using properties and relationships such as "data system with high risk". You can also create custom widgets not only for discovery scans but other nodes, such as data systems, classification, and so on, in the data command graph. To view different stats after discovery scans in Graph Explorer as well as relationships among different entities such as discovery scans, data systems, and classification, see [Using the Universal Data Explorer](https://helpcenter.securiti.ai/docs/using-the-universal-data-explorer). |
| Structured Data Discovery | Provides valuable insights about the data discovered from database tables and columns, located in structured data systems such as MySQL, Snowflake, and so on. For more information, see [Using the Structured Data Discovery](https://helpcenter.securiti.ai/docs/using-the-structured-data-discovery-classic-dashboard). |
| Unstructured Data Discovery | Provides valuable insights about the data discovered from files, images, and other document types, located in unstructured data systems such as Amazon S3, SharePoint, Box, and so on. For more information, see [Using the Unstructured Data Discovery](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data). To view insights about documents having duplicate and nearly similar content, see [Detecting and reducing duplicate and near-duplicate data](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data). |
| Streaming Data Discovery | Provides valuable insights about the data discovered from topics, fields, and schemas for data in motion residing in streaming data systems such as Kafka, Amazon MSK, and so on. For more information, see [Using the Streaming Data Discovery](https://helpcenter.securiti.ai/docs/using-the-streaming-data-discovery-dashboard). |
| Data Risk Explorer | Displays risks associated with data systems, discovered after running scan jobs. For more information, see [Using the Data Risk Explorer](/v1/docs/using-the-data-risk-explorer). |

## Related

- [Using the Unstructured Data Scans dashboard](/using-the-unstructured-data-discovery.md)
- [Using the Structured Data Discovery dashboard](/using-the-structured-data-discovery-classic-dashboard.md)
- [Using the Streaming Data Discovery dashboard](/using-the-streaming-data-discovery-dashboard.md)
- [Using the Universal Data Explorer](/using-the-universal-data-explorer.md)
