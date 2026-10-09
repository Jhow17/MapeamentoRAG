---
title: "Structured Data Overview dashboard"
slug: "structured-data-overview-dashboard"
updated: 2026-08-18T14:18:12Z
published: 2026-08-18T14:18:12Z
canonical: "helpcenter.securiti.ai/structured-data-overview-dashboard"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Structured Data Overview dashboard

The **Structured Data Overview** dashboard provides a centralized view of structured data across your connected data systems. You can use this dashboard to quickly identify databases, tables, and columns that contain sensitive data and require attention.

This dashboard aggregates insights from classification scans to help you:

- Understand where structured data exists
- Track the sensitive data that exists in data systems
- Overall security posture of your databases

![Overview of structured data metrics including connected databases and sensitive data tables.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddataoverview_dashboard(1).png)

> [!WARNING]
> Important
> 
> You must configure at least one structured data system and run an active discovery scan on the target data systems for the dashboard widgets to display data.

The table below provides an overview of the predefined widgets in the **Structured Data Overview** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| Connected Structured Data Systems | Trend Chart | Displays the total number of structured data systems connected to Securiti over time |
| Total Connected Databases | Trend Chart | Displays the total number of databases discovered across all connected structured data systems. |
| Tables With Sensitive Data | - Trend Chart - Grid | The trend widget displays the number of database tables that contain sensitive data elements. This grid widget lists tables that contain sensitive data. It includes details such as the number of data elements, total columns, classified columns, database name, schema, and data system type. |
| Columns With Sensitive Data Elements | Trend Chart | Displays the total number of columns that contain detected sensitive data elements. |
| All Connected Databases | Grid | Lists all discovered databases and provides key details, such as data system name, total schemas, classified tables, and detected data elements. |
| Structured Data Systems with Open Findings | - Trend Chart - Grid | The trend widget shows the number of structured data systems that currently have open posture or security findings. It helps you monitor risk trends across your structured data environment. The grid widget provides a breakdown of structured data systems with open findings, along with the corresponding finding count. |
| Unencrypted Structured Data Systems | - Trend Chart - Grid | The trend widget shows the number of structured data systems that are not encrypted. The grid widget lists unencrypted structured data systems and provides details such as asset name, asset type, and account name. |
