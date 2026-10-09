---
title: "Refreshing dashboards and widgets"
slug: "refreshing-dashboards-and-widgets"
updated: 2026-08-30T12:17:27Z
published: 2026-08-30T12:17:27Z
canonical: "helpcenter.securiti.ai/refreshing-dashboards-and-widgets"
stale: true
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Refreshing dashboards and widgets

The Reporting Dashboard populates widgets with data by accessing the graph database through the graph API. However, data retrieval from the graph database is an extensive and expensive process that requires traversal through the nodes and their relationships, thus causing delays in updating the widgets with the latest data.

Securiti Reporting Dashboard overcomes this limitation by using a cache layer on the graph API that stores data from the graph database in a cache layer. Integrating cache functionality with the **Refresh Widget Data** button results in smoother operation with complex data requests. This lets you retrieve data for your widgets by reducing load times.

To refresh data in your dashboard widgets.

1. Go to **Dashboard** and open a dashboard of your choice.
2. Near the upper right corner of the dashboard page, click **Actions** and select **Refresh Widget Data** from the menu.

![Dashboard overview displaying security posture scores and widget data refresh options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/refreshwidgetdata_reportingdashboard.png)

Clicking on the button refreshes and populates all the data in your widgets, with the latest information from the graph database.

> [!NOTE]
> **Note**
> 
> - To ensure data accuracy and access to the latest information, the cache automatically invalidates the data after a certain period of time and fetches the latest data from the graph database.
> - Securiti displays a “Last Updated” timestamp only for widgets that use cached or stored results. Widgets that show live data refresh continuously in real time, so they do not display a “Last Updated” timestamp.

You can refresh data at the widget level to avoid refreshing the entire dashboard and update only the data you need. To refresh widgets:

- Click the refresh button for your widget as shown below. The widget also shows the last refreshed timestamp, such as "7 hours ago". For widgets with hidden headers, hover over the widget name and click the refresh button.

![Dashboard displaying security findings, asset posture score, and data posture score metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/lastrefreshedtime_reportingdashboard.png)
- Click **Cancel Refresh** to cancel an ongoing data refresh operation for a widget, as shown below.

![Dashboard displaying security findings, asset posture score, and data posture score metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cancelrefresh_reportingdashboard.png)

## Refreshing trend widgets automatically

Trend widget do not include a manual refresh option. Instead, each trend widget recollects data automatically every 24 hours. Securiti checks for trend widgets that are due for recollection several times a day.

Use the following behavior to understand when trend widgets recollect and display new data:

- Each trend trend widget recollects data once per day, based on a fixed 24-hour frequency.
- Securiti checks for due widgets several times a day. Only the first check after the 24-hour period triggers recollection.
- If Securiti checks before the 24-hour period ends, the widget is not due and recollection does not start.
- A trend widget’s refresh cycle starts when you create the widget. It does not start at a fixed time, such as midnight.
- For instance, if you create a trend widget at 6 PM, Securiti recollects data during the first check on or after 6 PM the next day.
- Trend data collection starts when you create the widget. Data from before widget creation is not available.

> [!NOTE]
> Note
> 
> The time range menu on a trend widget, such as **Last 30 days**, **Last 12 weeks**, or **Last 12 months**, controls which period of already collected data appears in the widget. It does not change how often the widget recollects new data.
> 
> ![Graph showing active AI agents over time, currently at 67 for the last 30 days.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/trendwidget_datarange.png)
