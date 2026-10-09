---
title: "Using the Duplicate Files dashboard"
slug: "duplicate-files-dashboard"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/duplicate-files-dashboard"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Using the Duplicate Files dashboard

**Scenario**

As a Data Security Officer, you are responsible for reducing storage risk and cost across your organization's data environment. Identifying duplicate files manually across dozens of connected systems is time-consuming and gives you no clear picture of exposure. The Duplicate Files dashboard gives you a single view of how much storage you can reclaim. It also shows you which systems, owners, and folders hold the most redundant data. It flags which duplicates carry sensitive labels, so you can prioritize cleanup and take action without guesswork.

## Overview

The Duplicate Files dashboard gives you an overview of duplicate file activity across your connected data systems. It surfaces storage waste metrics, data distribution insights, and details about files that exist in multiple identical copies. You can use this dashboard to track where duplicates are concentrated across data systems, owners, and folders, and take targeted remediation action.

## Prerequisites

Before you use the Duplicate Files dashboard, ensure that you have successfully run a Discovery Scan for the data systems where you want to detect duplicate files.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Accessing the Duplicate Files dashboard

To access the Duplicate Files dashboard:

1. From the upper left corner, click the **Jewel** icon to open the main menu, as shown below.

![Overview of data systems and hosting options in the Universal Data Explorer interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-28 at 12.26.30 PM(4).png)
2. Click **Dashboard**, as shown below.

![Dashboard displaying cloud hosting data with various metrics and options for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-28 at 12.27.55 PM.png)
3. In the left navigation menu, under **Data Remediation**, click **Duplicate Files**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0PICHLXB.png)

## Duplicate Files dashboard widgets

The following table describes the widgets available in the Duplicate Files dashboard:

| Widget name | Widget type | Description |
| --- | --- | --- |
| Reclaimable Storage | Metric | Displays the total storage you can reclaim by removing duplicate file copies across your data systems. |
| Duplicate Files | Metric | Displays the estimated number of duplicate files identified across your data systems. |
| Sensitive Duplicate Size | Metric | Displays the total storage used by duplicate files that contain sensitive labels. |
| Duplicate File Types | Donut chart | Displays the distribution of duplicate files by file type, such as `Machine Readable Data`. |
| Duplicate File Format | Donut chart | Displays the distribution of duplicate files by file format, such as `application/pdf`. |
| Duplicate File Categories | Donut chart | Displays the distribution of duplicate files by file category, such as `Research Paper`. |
| Sensitive Labeled Files | Grid | Displays the sensitivity labels assigned to duplicate files and the number of duplicate files associated with each label. |
| Top Data Systems with duplicate data | Grid | Displays the data systems with the highest number of duplicate files, sorted by file count in descending order. |
| Top Owners | Grid | Displays the file owners with the highest number of duplicate files, sorted by file count in descending order. |
| Top Folders | Grid | Displays the folders or resource paths with the highest number of duplicate files, sorted by file count in descending order. |
