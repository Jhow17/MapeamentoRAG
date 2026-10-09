---
title: "Creating widgets"
slug: "creating-widgets"
status: "update"
updated: 2026-09-16T10:53:25Z
published: 2026-09-16T11:08:13Z
canonical: "helpcenter.securiti.ai/creating-widgets"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Creating widgets

You can create widgets from your data in Graph Explorer, Inventory, and module-specific Data Command Graph pages, then save them to your custom dashboards. Widgets let you summarize and visualize your data as grids, metrics, charts, or maps.

You can create a widget using one of the following methods:

- Creating a custom query in Graph Explorer and creating a widget directly from the results.
- Apply filters in Inventory or a module-specific Data Command Graph page, and create a widget from the results.
- Writing or pasting a JSON query directly into a widget popup in Graph Reporting dashboards.

## Creating widgets from Data Command Graph

To create a widget from a query in Graph Explorer:

1. Apply a query by selecting entities of your choice. For more information, see [Applying filters](/latest/docs/managing-queries-in-the-graph-explorer).
2. Near the upper-right corner of the page, click **Create Widget**.
3. On the **Widgets** popup, select the widget type you want to create for your metadata. The following widget types are supported:
  - Metric
  - Grid
  - Chart
4. Select the dashboard and dashboard group you want to create the widget in. You can also create a new dashboard and group.
5. Click **Add Widget** to add your widget to the dashboard.

Adding a widget to the dashboard displays a success message. Click **View Dashboard** in the message to view your dashboard and the added widget.

You can also create widgets from aggregate and JSON queries in Graph Explorer. For more information, see [Creating widgets from aggregate queries](/latest/docs/creating-widgets-from-aggregate-queries) and [Creating widgets from JSON queries](/latest/docs/creating-widgets-from-json-queries).

## Key considerations

- Widget type conversion, such as converting a grid widget to metric type, is not supported for the following entities:
  - Column
  - Files
  - Folders
  - Workflow Execution
  - Discovery Scan File
  - Activity Log
  - IAM Resource Access
- In Graph Explorer, widget type conversion is also disabled when creating widgets for the Relationship grid or for a secondary entity's grid in a query.
- The **Sum of node** option in the widget creation modal is not available for graph queries that include multiple child entities.
- Queries that use the **Total Count** aggregate operation in the Graph Explorer query, support the Metric widget type only. The Grid and Chart widget types are not available for these queries.
- Queries that use the **Map Count** operation do not go through widget type conversion. Securiti uses the same query across the Grid, Metric, and Chart widget types, and the **Select X-Axis** setting is disabled for these queries.
- For scans run in Securiti release 1.149.0 or later, widgets created with the **Content Profile** property on the **Column** entity return only the columns that contribute to the table's Content Profile. For scans run before release 1.149.0, these widgets return all columns in the matching table. Widget results can differ between older and newer scans for this reason.

![Dashboard displaying data classification with highlighted columns and security posture metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reporting_contentprofilewidgets.png)
