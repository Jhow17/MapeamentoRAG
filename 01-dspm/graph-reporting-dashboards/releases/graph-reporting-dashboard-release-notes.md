---
title: "Graph Reporting Dashboard release notes"
slug: "graph-reporting-dashboard-release-notes"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/graph-reporting-dashboard-release-notes"
area: dspm
modulo: graph-reporting-dashboards
tipo: release
data_captura: 2026-10-06
---

# Graph Reporting Dashboard release notes

## 1.151

### Release updates - September 2026

No updates

---

## 1.150

### Release updates - August 2026

#### Supporting expanded height for grid widgets

Securiti now lets you expand grid widgets in Graph Reporting Dashboards to display more data without increasing the number of widgets on your dashboard. You can now choose between the default view, which displays 5 rows, and an expanded view that displays up to 25 rows in a single widget.

The **More data in grid widget** option is available when you create a widget from `JSON` or copy a widget. Once enabled, you can resize the widget while retaining the expanded layout. This update improves dashboard readability and reduces the need to page through grid results, making it easier to review larger datasets at a glance.

![Widget configuration interface displaying data systems and their respective counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reporting_2xwidth(1).png)

For more information, see [Editing dashboards and widgets](/latest/docs/editing-dashboards-and-widgets).

---

## 1.149

### Release updates - August 2026

No updates

---

## 1.148

### Release updates - July 2026

#### Introducing the Duplicate Files reporting dashboard

We have now introduced the **Duplicate Files** reporting dashboard that provides a comprehensive view of duplicate files across connected data systems, as shown below. The dashboard surfaces key metrics such as reclaimable storage, duplicate file count, and sensitive duplicate data. It also highlights the top data systems, file owners, and folders with duplicate files. With this update, you can identify areas with the highest duplication, prioritize cleanup efforts, and make more informed data governance decisions.

![Dashboard displaying duplicate files, storage statistics, and sensitive labeled files overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3(8).png)

For more information, see [Using the Duplicate Files dashboard](/latest/docs/duplicate-files-dashboard).

#### Resolved issue

- Fixed an issue where trend widgets in the Graph Reporting Dashboards displayed combined data from all organizations, regardless of the selected organization(s). Trend widgets now collect and display data only for the active organization. In case, multiple organizations are selected, the widget combines data from the selected organizations into a single trend line. (PRIV-243715).

---

## 1.147

### Release updates - June 2026

#### Upcoming fix for trend widget organization scoping

We have identified an issue where trend widgets in the Graph Reporting Dashboards currently display combined data from all organizations, regardless of the selected organization(s). As a result, trend widgets may display data aggregated across all organizations instead of only the active organization, leading to inconsistent counts.

This issue will be resolved in the the Securiti release 1.148. After the fix, trend widgets will collect and display data only for the active organization. When you select multiple organizations, the widget combines data from the selected organizations into a single trend line.

> [!NOTE]
> Note
> 
> - This change applies only to tenants with multiple organizations enabled. If you use a single organization, your trend widgets continue to function as before.
> - Historical trend data collected before Securiti release **1.148** is not updated to reflect organization-scoped filtering. As a result, trend widget results for periods before this release may not accurately represent the currently selected organization and continue to display values calculated before this change.

For more information, see [Using dashboards with multiple organizations](/latest/docs/using-graph-reporting-dashboards#using-dashboards-with-multiple-organizations).

#### Improved metric visibility in segmented bar widgets

Securiti has enhanced widget visualization in Graph Reporting Dashboards to make insights clearer and more contextual. The segmented bar widgets now display a total metric alongside the segmented breakdown to view distribution and overall count in one place, as shown below.

![Distribution of 14K security findings categorized by severity levels: critical, moderate, low.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/segmentedbarwidget.png)

For more information, see [Editing dashboards and widgets](https://helpcenter.securiti.ai/docs/editing-dashboards-and-widgets).
