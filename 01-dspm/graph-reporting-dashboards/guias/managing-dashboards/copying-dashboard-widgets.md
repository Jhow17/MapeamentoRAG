---
title: "Copying dashboard widgets"
slug: "copying-dashboard-widgets"
updated: 2026-07-15T11:03:43Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/copying-dashboard-widgets"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Copying dashboard widgets

You can copy widgets from one dashboard to another. The copy feature lets you make modifications to widgets in a different dashboard to suit your needs, or reuse the widgets by copying them without having to create new widgets in a dashboard.

> [!NOTE]
> **Note**
> 
> You can copy widgets to Custom dashboard only.

To copy a widget in your dashboard.

1. Click **Actions** on the upper right corner of the dashboard page.
2. Select **Copy Widgets** from the menu.

![Dashboard overview displaying security metrics and options for copying widgets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/copywidgetoption_reportingdashboard.png)
3. On the **Widgets** pop-up, select the widgets you want to copy from the selected dashboard, and specify the settings as shown in the table below.

| Setting | Description |
| --- | --- |
| Select Widgets | From the menu, select the widgets you want to copy in your dashboard. The menu lists all the widgets present in a selected dashboard. |
| Widget Name | Enter the name of your choice for the widget you wish to copy. The widget name uses an alphanumeric string value with the following special characters allowed. > [!NOTE] > **Note** > > The name is set by default automatically. - Space - Underscore "**_**" - Dashes "**-**" - Parenthesis "**()**" - Forward slash "**/**" - Dot "**.**" - Colon "**:**" See an example below. *AWS_regions* |
| Group | Select the dashboard group from the menu to copy the widgets in. You can select an existing dashboard group from the menu or add a new one. |
| Link Group with Module | Choose a Securiti module to link your dashboard group with, from the menu. Linking groups to modules lets you access the dashboard directly from within that module. For example, you can link dashboards with access governance widgets to **Data Access Governance** module. |
| Select Dashboard | Select the dashboard to copy the widgets in. You can select an existing dashboard from the menu or add a new one. |
| (Optional) Description | Enter a description for your widget such as the details about the insights being displayed on the widget. |
4. Click **Add Widgets**.

![Dashboard displaying security findings categorized by risk severity levels and data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/addingcopiedwidget_reportingdashboard.png)

The widgets will be copied to another dashboard as is.

You can also add widgets using JSON queries. See [Creating widgets from JSON queries](/v1/docs/creating-widgets-from-json-queries) for more information.

Dashboards that can be customized as needed. These dashboards are created by you from the **Graph Explorer**, **Inventory,** and **Data Command Graph** pages in modules.
