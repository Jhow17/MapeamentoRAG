---
title: "Assessments list (Search and exports)"
slug: "assessments-list-search-and-exports"
updated: 2026-05-25T08:04:56Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/assessments-list-search-and-exports"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Assessments list (Search and exports)

The grid search lets you narrow down Assessments. For example, when you enter the numeric identifier, for example, “1”, Securiti displays all search results with query 1 in either the ID column, the Assessment Title column, or both, as shown in the table below.

| Use case | Search query (Numeric identifier) | Example ID displayed | Example Assessment Title displayed | Description |
| --- | --- | --- | --- | --- |
| A | 1 | 3203 | Copy of Process ESCL 196 | Securiti displays the result because search query 1 is in the Assessment Title, “196.” |
| B | 14 | 14 | Testing Skip Legacy Template | Securiti displays the result because search query 14 matches the ID column. |
| C | 21 | 21 | Testing Skip Legacy Template 21 | Securiti displays the result because search query 21 matches both columns. |

Also, the list view lets you export two types of assessment reports.

- **Assessment Details -** A CSV report showing you information about each question in the assessment you selected for export.
- **Assessment Summary -** A CSV report containing assessment information based on the columns showing on the grid. For example, the summary export may contain details about ID, Assessment Title but not Risk Rating. For more information, see the section on [column selector](/latest/docs/using-the-internal-assessments-list-view#to-configure-columns).

### Configure exports

To configure an export:

1. On the grid, select the assessment(s) you want to export.
2. Near the upper right corner of the page, click **Export**.
3. On the **Export Assessment Report** popup, from the **Select Report Type** menu, select **Assessment Details** or **Assessment Summary**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-05-25 at 12.59.35 PM.png)

Click **Export Report**

Securiti sends you an email containing the "Download File" link.

> [!NOTE]
> Note
> 
> These exports contain details on assessment tags and managing organization (if any).

As with many Securiti pages and dashboards, you can filter the list of assessments on various criteria. For more information, see [Assessments list Filter panel and Saved Views](/v1/docs/assessments-list-filter-panel-and-saved-views) .

## Related

- [Using tags to organize and filter assessments](/managing-assessment-tags.md)
