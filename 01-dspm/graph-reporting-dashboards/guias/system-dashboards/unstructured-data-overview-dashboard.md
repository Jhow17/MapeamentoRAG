---
title: "Unstructured Data Overview dashboard"
slug: "unstructured-data-overview-dashboard"
updated: 2026-08-18T14:18:01Z
published: 2026-08-18T14:18:01Z
canonical: "helpcenter.securiti.ai/unstructured-data-overview-dashboard"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Unstructured Data Overview dashboard

The **Unstructured Data Overview** dashboard provides a centralized view of unstructured data across your connected data systems.

This dashboard aggregates insights from classification scans to help you:

- Track the volume of unstructured data over time
- Identify files containing sensitive data or classification labels
- Detect exposure risks caused by sharing, encryption gaps, or stale data
- Review findings by severity and data system to prioritize remediation

![Overview of unstructured data metrics including total files and sensitive data counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/unstructureddataoverview_dashboard(1).png)

> [!WARNING]
> Important
> 
> You must configure at least one unstructured data system and run an active discovery scan on the target data systems for the dashboard widgets to display data.

The table below provides an overview of the predefined widgets in the **Unstructured Data Overview** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| Total Files Discovered | Trend Chart | Displays the total number of unstructured files discovered over time across all scoped data systems. |
| Volume of All Files Discovered | Trend Chart | Displays the total storage volume of all discovered unstructured files. |
| Total Files Containing Sensitive Data | Trend Chart | Displays the number of files that contain one or more sensitive data elements identified through classification. |
| Files with Classification Labels | Trend Chart | Displays the number of files that have classification labels applied, such as sensitivity or compliance labels. |
| Files with Public Sharing Links | Trend Chart | Displays the number of files shared using public or anonymous links. This widget helps identify externally exposed data |
| Files with Org Wide Sharing Links | Trend Chart | Displays the number of files shared broadly within the organization, such as “Everyone” or “All users” access. |
| Total Open Unstructured Posture Findings | Trend Chart | Displays the total number of open posture findings related to unstructured data. |
| Unstructured Findings By Severity | Bar Chart | Displays open findings by severity level, such as Medium, High, and Very High. This widget helps you prioritize remediation. |
| Unencrypted Unstructured Data Systems | Trend Chart | Displays the number of unstructured data systems that do not meet encryption requirements. |
| Files in Unencrypted Unstructured Data Systems | Trend Chart | Displays the number of files stored in unencrypted unstructured data systems. |
| Open Posture Findings Per Data System | Grid | Lists data systems with open posture findings and shows the total finding count per system. |
| File Distribution by 20 Most Common Sensitive Data Types | Treemap | Shows the distribution of files by the most commonly detected sensitive data types, such as PII or financial data. |
| Files with Data Elements Per Data System | Treemap | Displays the distribution of files that contain detected data elements across each unstructured data system. Each rectangle represents a data system, and its size reflects the number of files with identified data elements. Use this widget to quickly identify which data systems contribute the most to sensitive data exposure based on detected elements. |
| Files Matching Content Profiles Per Data System | Treemap | Displays the number of files that match defined content profiles across unstructured data systems. Each block represents a data system, and the block size indicates how many files match one or more content profiles. |
| Files By File Format | Treemap | Displays file distribution by format, such as documents, images, archives, or source code. |
| Files By Document Type | Treemap | Displays file distribution by document category, such as reports, spreadsheets, presentations, or forms. |
| Files Not Modified in Greater Than 1 Year Per Data System | Grid | Displays files that have not been modified for more than one year, grouped by data system. This widget helps identify stale data. |
| Files Greater Than 3 Years Old | Trend Chart | Displays files older than three years based on last modified time. |
| Files Greater Than 5 Years Old | Trend Chart | Displays files older than five years based on last modified time. |
| Files Greater Than 7 Years Old | Trend Chart | Displays files older than seven years based on last modified time. |
