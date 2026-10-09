---
title: "Creating widgets from JSON queries"
slug: "creating-widgets-from-json-queries"
updated: 2026-09-13T19:58:10Z
published: 2026-09-13T19:58:10Z
canonical: "helpcenter.securiti.ai/creating-widgets-from-json-queries"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Creating widgets from JSON queries

Securiti Reporting dashboard lets you create custom widgets in your dashboards using JSON queries. With this feature, you can create widgets by combining or aggregating data from across multiple entities or tables in graph modules such as Graph Explorer and Inventory. You can also create widgets by sourcing data from a single table or grid.

Custom widget creation using JSON queries provides flexibility and improved reporting as you create detailed and dynamic dashboards with customized widgets tailored to your specific reporting needs.

> [!NOTE]
> **Note**
> 
> If you edit a widget's JSON query from **Update Widget Details** in edit mode, the widget no longer supports click-through to Graph Explorer. To restore click-through, recreate the widget from a query instead of editing its JSON directly.

To create widgets using JSON queries.

1. In the Reporting dashboard, select your custom dashboard and click **Actions.**
2. From the menu, select **Create Widget from JSON**, as shown below.

![Dashboard overview displaying asset posture score and security findings metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/createwidgetfromjson_reportingdashboard.png)
3. In the **Create a Widget from JSON** modal, specify the following settings:

| Setting | Description |
| --- | --- |
| Widget Name | Enter the name of your choice for the widget you wish to copy. The widget name uses an alphanumeric string value with the following special characters allowed. > [!NOTE] > **Note** > > The name is set by default automatically. - Space - Underscore "**_**" - Dashes "**-**" - Parenthesis "**()**" - Forward slash "**/**" - Dot "**.**" - Colon "**:**" See an example below. *AWS_regions* |
| Widget Type | Choose the widget type from the available options i.e **Grid** or **Metric**. |
| Insert JSON Query | Enter or paste the JSON query for your widget's data. The JSON query includes an entity's type, properties, and relationships to fetch the required data. JSON queries can be fetched from the existing widgets in system dashboards or the [JSON View in Graph Explorer](/latest/docs/using-json-expression-for-queries). See the example below for a sample JSON query code. Click **Apply & Preview** to view your widget in the left window. |
| Group | Select the dashboard group you want to add your widget to or create a new group. |
| (Optional) Link Group with Module | Link the group to a module for swift access directly from within that module. |
| Dashboard | Select the dashboard you want to add your widget to or create a new dashboard in the group you selected previously. |
| (Optional) Description | Provide any description for your widget. |

![Widget displaying findings count for various types of security assessments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/createwidgetJSON_popup.png)
  1. For **Grid** widgets, in the **Columns** section of the modal, select and reorder the columns to display in the widget, as shown below.

![Widget displaying findings count for various types of security assessments and tests.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnwidget_settings.png)

Click **Quick Reorder** to restore the original order of columns.
  2. For **Metric** widgets, in the **Metrics** section of the modal, configure the following settings:

![Dashboard displaying findings count metrics with various numerical values listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reporting_metricwidgetsettings.png)
    - **Order:** Search, select and reorder the metrics to display in your widget.

> [!NOTE]
> Note
> 
> Securiti supports a maximum of four metrics per widget.
    - **Time Series:** In **Time Series** section, mark the **Enable Time Series** checkbox to display a time series for data along with metric(s).
    - **Color**: Select the color for your metric widget. You can select from the available Blue, Orange, and Green colors.
    - **Layout**: Select a horizontal or vertical layout for your metric widget.

> [!NOTE]
> Note
> 
> In horizontal layout, the widget height adjusts to half of the default height to optimize dashboard space. In export mode, the height expands to the default size to preserve layout integrity in PDF reports. The widget width remains fixed to prevent layout breakage.

## Using time series for metric widgets

You can capture trends for your metric widgets and display them as time series widgets in your dashboard. You can create a time series for widgets when creating widgets from JSON and track data over time, with options to set predefined or custom date ranges. The time series option enables easier time-based analysis while retaining historical data for up to 12 months.

> [!NOTE]
> **Note**
> 
> Time series can be used when creating single metric widgets only and is not supported for grid widgets or multiple metric widgets.

To use the time series option for widgets.

1. On the **Create widget from JSON** modal, enter your widget name.
2. Select **Metric** in the **Widget Type** field.
3. In the **JSON Query** box, paste the JSON query for your metric widget.

> [!NOTE]
> **Important**
> 
> The time series option supports only JSON queries with `aggregateLookup` as the request type. The option is disabled for all other request types such as `getTable`.

![Widget displaying security findings with an aggregation count of 33.7k.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/addingjsonforwidget_reportingdashboard.png)
4. Click **Apply and Preview**. After applying the JSON query, **Time Series** section becomes visible where you can enable and configure time series for your widget.
5. In the **Time Series** section, enable the **Use Time-Series** toggle to capture time-based trends for your widget.
6. On the left side of the modal showing widget preview, enable the **Preview with example trend** toggle to visualize how trends appear in widget.

![Widget displaying security findings over the last twelve months with trend visualization options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/enabletimeseries_reportingdashboards.png)
7. Configure the following time series settings for displaying data trends in your widget.

| Setting | Description |
| --- | --- |
| Date Range | Select the period over which data is displayed. This defines the overall timeframe (e.g., Last 30 days) for the time series data shown in the widget. Select the date range from one of the following available options from the menu. - Last 30 days - Last 12 weeks - Last 12 months |
| Frequency | Set the interval for data points within the selected date range. For example, choosing a frequency of "2 days" displays data points at two-day intervals. You can set frequency as number of days. |
| Trend Visualization | Choose one of the following styles for visualizing data trends in the widget. - Column Chart: Displays data as vertical bars, ideal for showing discrete values over time. - Area Chart: Represents data as a shaded area, helping to visualize cumulative trends over time. |
| Color | Select the color for the trend visualization to distinguish this widget within the dashboard. You can choose one of the following colors for the trends. - Blue - Orange - Green |
8. Select **Group** and **Dashboard** to place your widget in and click **Save**.
9. The created time series widget shows in your dashboard.

## Combining metric widgets using JSON

Reporting Dashboard lets you group multiple metrics into a single widget. This helps you compare data across entities without cluttering your dashboard with separate widgets.

> [!NOTE]
> **Important**
> 
> - Securiti lets you combine metric widgets only. Grid, chart, or other widget types are not compatible.
> - Securiti currently supports grouping up to four metric widgets in one combined widget.

To group multiple metric widgets into a single widget.

1. In your dashboard, from the upper right corner, click **Widgets**.
2. From the menu, click **Create Widget from JSON**.

![Dashboard overview displaying asset posture score and security findings metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/createwidgetfromjson_reportingdashboard(1).png)
3. On the popup, provide the following:
  - **Widget Name**: Provide a widget name for the combined metric.
  - **Widget Type**: Select **Metric** as the widget type.
  - **Insert JSON Query**: Use a query with the `getMultiQuery` request type. Click **Apply & Preview** to view the combined widget.
  - **Metrics**: From the list, enable toggles for up to four metric widgets to include.
  - **Color**: Choose from Blue, Orange, or Green..
  - **Group**: Select the dashboard group.
  - **Dashboard**: Select the dashboard where the widget should appear.

![Aggregation widget displaying a count of 33.7k findings for data analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creatingwidgetfromjson_reportingdashboard.png)
4. Click **Save** to add the new widget to your dashboard.

![Dashboard displaying security findings with an aggregation count of 33.7k.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/createdwidgetondashboard_reportingdashboard.png)

#### Using `getMultiQuery` request type in JSON

To combine metrics, your JSON query must use the `getMultiQuery` request type. This request type lets you combine multiple metric queries into one payload. Key components of the JSON query include:

- `req_type`: Set this to `getMultiQuery` to indicate a multi-metric request.
- `args`: Include a `queries` array in this object for grouping metrics.
- `queries`: Include an array of query objects, each defining a metric(s) query. Each query object has its `req_type` and `args` for that metric. The dashboard combines the results of these queries into one widget.

Below is a sample JSON snippet illustrating a query with two metric queries:

> [!NOTE]
> **Note**
> 
> Only queries compatible with metric widgets are supported. Queries like `graphLookup` are not valid.

```plaintext
{
    "req_type": "getMultiQuery",
    "args": {
        "queries": [
            {
                "args": {
                    "aggregateLookup": {
                        "nodeType": [
                            "AIMLMODEL"
                        ],
                        "withPropertyFilter": {
                            "cloud": {
                                "eq": "AZURE"
                            },
                            "isDeployed": {
                                "eq": true
                            }
                        },
                        "connections": [],
                        "ops": [
                            {
                                "op": "simplecount",
                                "propHeader": {
                                    "description": "Total Azure deployed models",
                                    "displayName": "Model Deployments",
                                    "gqlType": "Int",
                                    "sortable": false,
                                    "type": "int"
                                }
                            }
                        ]
                    }
                },
                "filters": [],
                "owner": "admin@securiti.ai",
                "uuid": "30551234-1234-abcd-6789-abcd12342b995",
                "tableName": null,
                "req_type": "aggregateLookup"
            },
            {
                "req_type": "getMetrics",
                "filters": [],
                "owner": "admin@securiti.ai",
                "uuid": "30551234-1234-abcd-6789-abcd12342b995",
                "args": {
                    "identifier": 9,
                    "readFromCache": true,
                    "updateCache": false
                }
            }
        ],
        "identifier": 8
    }
}
```

## Using JSON queries for widgets

You can use the following options to obtain a JSON query.

- Use the [Graph Explorer](/latest/docs/managing-queries-in-the-graph-explorer) to create queries and click **View JSON**. The JSON Expression for your graph query can be copied to the **Create Widget from JSON** modal.

Add any aggregation operations like sum or count to parts of the query.
- View the JSON queries and metadata of any of the widgets in the System Dashboards by clicking options (three dots) and selecting **Get Widget Details**. The queries can be copied and pasted to the **Create Widget from JSON** modal.

Modify or add the entities and properties to suit.

The following components in the JSON query are added for the widget:

| Object | Description |
| --- | --- |
| owner | Specify your user email address. |
| req_type | Specify the request type for the query. The following request types are supported. - `graphLookup`: Use this request type for graph explorer queries - `aggregateLookup`: Use this request type for aggregate queries having data from multiple entities such as "AWS - Data Systems Overview by Region" - `getTable`: Use this request type for entity data in grid or tables. - `getMultiQuery`: Use this request type for combining multiple metric widgets. |
| args | - Specify pagination and sorting details in the `args` object of the query, such as the number of rows per page - Add your query inside the `args` object. The query object name depends on the request type. For example, use `lookupQuery` for `graphLookup` and `aggregateLookup` for aggregate queries. - When combining multiple metric widgets, include each metric widget query in the `queries` array. |

For more information, see [Using JSON expression for queries](/latest/docs/creating-widgets-from-json-queries#combining-metric-widgets-using-json).

#### Example

To create a custom grid widget that fetches IaaS regions for your AWS cloud accounts, use the JSON query shown in the example below. This query uses data from a graphLookup request on the Graph Explorer page.

**JSON Query**:

```plaintext
{
  "owner": "securiti@admin.ai",
  "req_type": "graphLookup",
  "args": {
    "pagination": {
      "rowsPerPage": 50,
      "page": 1
    },
    "lookupQuery": {
      "nodeType": [
        "IAAS"
      ],
      "withPropertyFilter": {
        "displayName": {
          "eq": "AWS"
        }
      },
      "connections": [
        {
          "relationshipType": [
            {
              "label": "CLOUD_HAS_REGION",
              "backwards": false
            }
          ],
          "withNode": {
            "nodeType": [
              "REGION"
            ],
            "withPropertyFilter": {},
            "connections": []
          }
        }
      ]
    }
  }
}
```

A JSON code, which is generated for an applied filter. The JSON expression can be used as a query to fetch information about the nodes specified in the filter. The expression is typically formatted in JSON (JavaScript Object Notation), and serves as a structured representation of the specified conditions for querying or modifying graph database content.

## Related

- [Using JSON expression for queries](/using-json-expression-for-queries.md)
- [Creating widgets in Graph Explorer](/creating-widgets-in-graph-explorer.md)
