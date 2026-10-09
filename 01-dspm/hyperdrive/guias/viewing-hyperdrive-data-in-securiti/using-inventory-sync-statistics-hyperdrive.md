---
title: "Using Inventory Sync statistics"
slug: "using-inventory-sync-statistics-hyperdrive"
updated: 2026-08-17T09:58:58Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/using-inventory-sync-statistics-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Inventory Sync statistics

# 

The **Statistics** page provides a consolidated view of inventory and scan-related metrics for an application. It helps you monitor scan progress, duration, and data processing activity in near real time.

## Accessing Statistics page

- On the left sidebar of the authenticated data system, click **Statistics**
- On the **Statistics** page, scroll down to see the data inventory sync and entitlements sync statistics.

![Statistics overview for SharePoint Online OnPrem scan duration and cataloged files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Statistics(1).png)

## Viewing data inventory sync statistics

The data inventory sync statistics provide a consolidated view of inventory and scan-related metrics for an application. It helps you monitor scan progress, duration, and data processing activity.

Use the following table to understand the inventory sync statistics metrics.

| **Metric** | **Description** | **Example** |
| --- | --- | --- |
| Total Scan Duration | Displays the total time taken by the scan, shown in days, hours, minutes, and seconds. This represents the cumulative runtime from scan start until completion. | 0 days, 0 hours, 15 mins, 31 secs |
| Scan Started On | Displays the exact date and time when the scan was initiated. | 1:11 AM, Jan 30, 2026 |
| Files Cataloged | Total number of files successfully cataloged | 60k |
| Files per Hour Cataloged | Average rate at which files are cataloged per hour | 12k/hr |
| Files per Hour Discovered | Total number of files discovered per hour | 15k/hr |
| Data Size Cataloged | Total volume of data cataloged. | 29.90 MiB |
| Total Number of Large Files | Total number of files that are larger than 100 MB in size. | 10 |
| Maximum Folder Depth | The deepest level of folder hierarchy encountered during the scan, expressed as a single numeric value. | 12 |
| Oldest Modified File Date | Displays the earliest last-modified timestamp among all scanned files | 2026 - 03 - 31 |
| Total Number of Files Scanned | Total count of all files processed during the scan, including both cataloged and analyzed files. | 75k |
| Files Eligible for Extrapolation | Number of files that qualify for extrapolation logic based on scan criteria and sampling rules. | 20k |

## Extended data inventory sync statistics

Use the following table to understand the additional metrics about data composition, risk posture, ownership distribution, and aging characteristics.

| **Metric** | **Description** | **Examples** |
| --- | --- | --- |
| Most ROT Files Older Than 1 Year | Redundant, Obsolete, Trivial (ROT) Files represent number of files not modified for over one year. | - PDF - 3110 - JSON - 100 - XML - 200 - PLAIN - 10 |
| Most Unique Extensions | Total number of distinct file extensions identified during the scan. Also includes a breakdown of the top 10 extensions based on file count or data size. | - .pdf - 40,000 - .docx - 20,000 - .csv - 10,400 |
| Most Special Extensions | Identifies files with extensions considered risky or sensitive, such executables, AI model files, and others. It Includes total count and top 10 such extensions. | - KEY - 2 |
| Unique MIME Types | Total number of distinct Multipurpose Internet Mail Extensions (MIME) types detected across scanned files, along with the top 10 MIME types by volume or size. | - PDF - 50,200 - DOCUMENT - 1029 - VALUES - 240 - CSV - 10 |
| Data Distribution by Owner | Shows distribution of scanned data across file owners, including total number of unique owners and the top 10 owners based on data size or file count. | - John - 100,000 files - Allen - 63,000 files - David - 10,350 files |

## Viewing entitlement sync statistics

Use the following table to understand the entitlement sync statistics metrics.

| **Metric** | **Description** | **Example** |
| --- | --- | --- |
| AI Agents Cataloged | Total number of AI agents discovered and cataloged. | 14 |
| Applications Cataloged | Total number of applications cataloged during entitlement sync. | 11 |
| Groups Cataloged | Total number of groups cataloged. | 64 |
| Users Cataloged | Total number of users cataloged. | 79 |
