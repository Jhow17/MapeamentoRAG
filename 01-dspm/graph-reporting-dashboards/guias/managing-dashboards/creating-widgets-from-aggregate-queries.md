---
title: "Creating widgets from aggregate queries"
slug: "creating-widgets-from-aggregate-queries"
status: "update"
updated: 2026-09-16T11:18:30Z
published: 2026-09-16T11:18:30Z
canonical: "helpcenter.securiti.ai/creating-widgets-from-aggregate-queries"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Creating widgets from aggregate queries

You can create widgets for aggregate queries in the Graph Explorer and save them to your custom dashboards in Graph Reporting Dashboards. Aggregate widgets let you summarize and visualize data across entities, such as counting records, grouping results by a property, or displaying high-level metrics.

> [!WARNING]
> Important
> 
> - The widget type conversion is not supported for the following entities:
>   - Column
>   - Files
>   - Folders
>   - Workflow Execution
>   - Discovery Scan File
>   - Activity Log
>   - IAM Resource Access
> - In the Graph Explorer, the conversion is also disabled when creating widgets for the Relationship grid or for a secondary entity's grid in a query.
> - The **Sum of node** option is not available for graph queries that include multiple child entities.

## Prerequisites

To create aggregate widgets, you must fulfill the following prerequisites:

- You must have access to Securiti’s **Data Command** **Graph**.
- Your query must use an aggregate operation, such as Count, Sum, etc in your graph query. For more information, see [Using aggregate operations in queries](/latest/docs/using-aggregate-operations-in-queries).

## Creating an aggregate widget for dashboard

To create a widget for your aggregate query:

1. In **Graph Explorer**, create your query and apply an aggregate operation to an entity. For example, you can create a query to determine how many security postures of High severity levels and active policies are associated with a data system.

For more information, see [Using aggregate operations in queries](/latest/docs/using-aggregate-operations-in-queries).
2. Click **Run Query** to view and verify the results.
3. In the upper right corner of the page, click **Create Widget**, as shown below.

![Graph Explorer interface displaying security posture and policy counts for assets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aggregatequery_createwidget.png)
4. On the **Widgets** popup, configure the following widget settings:
  1. Configure the following basic settings:
    - **Select Widget(s)**: From the menu, select one or more widgets from the query.
    - **Widget Name**: Enter your widget name, such as “Data systems with security posture”. Mark or clear the **Display widget name on dashboard** to display or hide the widget name in dashboard.
    - **Widget Type:** Select the aggregate widget type. You can choose between **Grid**, **Metric**, and **Chart** types.
  2. Configure the following settings based on the selected widget type:

### Grid widgets

| Setting | Description |
| --- | --- |
| Columns | Select the columns to display in the Grid widget. You can also search for columns as well as rename and reorder them. Click **Quick Reorder** to restore the default column order. |

![Dashboard displaying Aggregate Grid with asset and security posture counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grid_widget.png)

### Metric widgets

| Setting | Description |
| --- | --- |
| Metrics | - **Select parent metric:** Select the primary value that the widget displays. The parent metric defines the top-level aggregate result, and you must select one. The available options depend on the entities in your query: - **Sum of <entity>:** Displays a single consolidated total for the parent entity in your query, such as **Sum of Data System**. - **Numeric property:** Displays a separate value for each record the query returns, such as **Files - Count** or **Data Size**. Securiti lists every numeric property available for the entities in your query, so these options change with the query you run. Selecting a numeric property lists the individual records the for the entity. - **Select Metrics:** Select or search for the metrics to display additional aggregate values in the widget, such as “Security Posture - Total Count”. You can also use the following capabilities: - Use the search field to quickly locate available metrics. - Use **Quick Reorder** to reorder selected series to default order. - Hover over a metric name and click **Edit Label** to rename a series to improve readability. |
| Time Series | Mark the **Enable Time-series** checkbox to track metric changes over time. |
| Color | Select a color theme for the metric values. You can choose between Blue, Orange, and Green colors. |
| Layout | Select how multiple metrics appear inside the widget. You can choose between **Vertical** or **Horizontal** layouts. |

![Dashboard displaying aggregate grid with security posture and policy total counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/metric_widget.png)

### Chart widgets

| Setting | Description |
| --- | --- |
| Choose a Chart Type | From the menu, select a chart type to display results in your widget. You can select from the following available chart types: - Column - Stacked Column - Bar - Stacked Bar - Donut Pie - One Stacked Bar - Line - Spline - Area - Treemap |
| Select X-Axis/Grouping Category | - **Select X-Axis:** For column, line, and area charts, select the independent variable that appears along the horizontal axis. - **Enable axis relabeling:** Mark the checkbox to rename the X-axis label for clarity. You can use relabeling to replace technical property names with business-friendly labels or standardize names across dashboards - **Select Grouping Category:** For pie, treemap and one stacked bar charts, select the property that defines how data is grouped into slices. Each unique value in the selected category appears as a slice in the chart. |
| Select Series | Select the metrics that appear as plotted values in the chart. Each selected series represents a metric from your aggregate query. You can also use the following capabilities: - Use the search field to quickly locate available metrics. - Use **Quick Reorder** to reorder selected series to default order. - Hover over a metric name and click **Edit Label** to rename a series to improve readability. |
| (For Treemap chart type only) Select Color | Select a color palette for your treemap chart widget. You can choose between Blue, Orange, and Green colors. |

![Aggregate grid displaying security posture and policy count for OneDrive Automation test.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/chart_widget(1).png)
  3. For chart widgets, click **Update Preview** to review your final changes.
  4. In **Group and dashboard selection** section of the popup, select the dashboard and group where you want to place the widget.
  5. (Optional) In the **Description** textbox, add a description for your widget.
5. Click **Add Widgets**.

Adding the widget to the dashboard displays a success message on the screen. Click **View Dashboard** to view your dashboard and the added widget.

![Overview of data classification with security posture and policy total counts displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aggregatewidget_dashboard.png)

Widgets that are used to display tabular data in the form of rows and columns.
