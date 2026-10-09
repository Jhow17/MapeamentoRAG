---
title: "Navigating the Risk Metrics Dashboard"
slug: "navigating-the-risk-metrics-dashboard"
updated: 2026-08-05T11:05:29Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/navigating-the-risk-metrics-dashboard"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Navigating the Risk Metrics Dashboard

The Risk Metrics Dashboard provides a centralized view of risk data across your tenant. It is available under Risk Management and displays risk distribution, trends, and tag breakdowns through a set of interactive widgets.

To open the Risk Metrics Dashboard, go to **Risk Management > Risk Metrics Dashboard**.

![Securiti interface displaying risk management options and assessment metrics for users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-05 at 4.05.05 PM.png)

![Dashboard displaying risk metrics, including overdue risks and risk status by level.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-05 at 3.31.17 PM.png)

## Filtering dashboard data

A global filter bar at the top of the dashboard lets you add filters that apply across all widgets. To add a filter, click **+ (New)** in the filter bar and select the filter criteria. Near the upper right corner, click **Options (three vertical dots)** to create a custom filter view or save it to retrieve later.

For more information, see [Assessments filter and custom views](/latest/docs/assessments-list-filter-panel-and-saved-views).

## Interacting with widgets

Each widget is interactive. Clicking a slice, segment, or bar on any widget opens a pre-filtered view of the corresponding risks. For example, clicking the **Flagged** slice on the Risk by Status widget opens the risk list filtered by Flagged status. Clicking **Assessment** on the Risk by Scope widget opens risks scoped to assessments, and so on.

![Risk Metrics Dashboard displaying various risk categories and their respective statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-05 at 4.00.52 PM.png)

![Overview of a risk register displaying flagged risks and their assessment details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-05 at 3.58.43 PM.png)

For more information, see [Risk Register grid](/latest/docs/using-the-risk-register-list-view).

Each widget also has a full-screen expand icon in the top right corner. Click it to expand the widget to a full-screen view.

![Pie chart showing risk distribution across assets, institutions, processes, and vendors.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-05 at 3.53.00 PM.png)

## Dashboard widgets

The Risk Metrics Dashboard includes the following widgets.

| Widget | Type | Description |
| --- | --- | --- |
| Risk by Status | Donut chart | Shows the distribution of risks by their current status, such as Flagged, Retained, Reduced, Reduced Pending, and Retained Pending |
| Residual Risk by Level | Donut chart | Shows residual risk counts broken down by risk level, such as Very Low, Low, Medium, and High |
| Overdue Risks | Table | Lists risks that are past their due date, including Risk ID, Residual Risk Level, Assignee, and Due Date; paginated to show a set number of records at a time |
| Risk Created by Quarter | Bar chart | Shows the volume of risks created per quarter |
| Risk by Scope | Donut chart | Shows the distribution of risks by scope type, such as Assessment, Asset, and Process |
| Risks Closed by Quarter | Stacked bar chart | Shows the number of risks closed per quarter, broken down by Remediated and Retained |
| Risk Levels per Organization | Stacked bar chart | Shows the distribution of risk levels across organizations in your tenant |
| Risk by Tag Type | Donut chart | Shows risk distribution by tag type; includes a dropdown to filter by tag type |
| Risk Breakdown by Tag Types | Bar chart | Shows a detailed breakdown of risks by individual tag values within each tag type |
