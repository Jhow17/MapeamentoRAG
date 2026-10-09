---
title: "Accessing source query for widgets"
slug: "accessing-source-query-for-widgets"
updated: 2026-09-17T16:25:45Z
published: 2026-09-17T16:25:45Z
canonical: "helpcenter.securiti.ai/accessing-source-query-for-widgets"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Accessing source query for widgets

Securiti's Graph Reporting Dashboards let you view the source data or graph query behind your grid and chart widgets in the Graph Explorer module. The feature helps you explore the source data behind their widgets directly in the Graph Explorer or in the module from which you created the widget, such as **Compliance**.

> [!NOTE]
> **Note**
> 
> Clicking a widget's value, cell, or chart segment opens Graph Explorer showing the individual records behind that result. Selecting **Go to Graph Explorer** from a widget's options (three dots) instead opens Graph Explorer with the widget's own underlying query.

To view the source data query for your grid or chart widget.

1. In your dashboard, locate the grid or chart widget that contains the data you want to explore.
2. Click on any cell, column, or chart segment within the widget as described in the table below.

| Widget type | Clickable entity |
| --- | --- |
| Grid widget | Click on the **Instance Viewer** icon of the cell or column you want to explore as shown below. ![Overview of public and SaaS cloud data with various metrics displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/gridwidgets_reportingdashboard.png) |
| Chart widgets | Click on the **chart segment** you want to view results for, as shown below. ![Overview of security findings with risk severity and asset posture scores displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/chartwidgets_reportingdashboard.png) |
| Trend widgets | Click on the **metric** showing score for an entity like findings, asset posture score or risk score as shown below. ![Dashboard displaying asset and data posture scores with detailed security overview metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/trendmetrics_reportingdashboards.png) |
3. Once clicked, the Graph Explorer or the relevant module page automatically opens in a new tab.

The source data query has all the filters applied as shown below.

![Graph Explorer interface displaying total count of security posture findings as 2844.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graphexplorerview_reportingdashboard.png)

Widgets that are used to display tabular data in the form of rows and columns.

## Related

- [Using Graph Explorer](/using-graph-explorer.md)
- [Managing queries in the Graph Explorer](/managing-queries-in-the-graph-explorer.md)
