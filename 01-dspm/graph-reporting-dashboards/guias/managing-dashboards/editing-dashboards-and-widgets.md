---
title: "Editing dashboards and widgets"
slug: "editing-dashboards-and-widgets"
updated: 2026-09-13T19:57:49Z
published: 2026-09-13T19:57:49Z
canonical: "helpcenter.securiti.ai/editing-dashboards-and-widgets"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Editing dashboards and widgets

You can view and make changes to the dashboards you have access to. You can edit the following items in the **Edit** mode of your custom dashboard.

- Dashboard
- Dashboard Group
- Widget

You can manage or edit the widgets on a dashboard in this mode. To edit a dashboard and its widgets.

1. In the grid, in the right corner of the dashboard group name, click options (three dots).
2. Select **Edit**. Selecting the option will take you to the widgets page.

![Dashboard interface displaying various security posture options and editing features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/editingreportingdashboards.png)
3. Alternatively, when you view a dashboard on the Reporting dashboard page, near the top right corner select **Edit**.

You can perform the following actions in the Edit mode:

- **Drag and drop** to resize and reposition widgets or dashboards for insights.
- **Update Widget Type** by changing the chart type, such as bar, pie, donut, or choose how you want to represent a series of data in your widget. For more information, see [Updating widget types](/latest/docs/editing-dashboards-and-widgets#updating-widget-types) section below.
- **Add rich text widgets** in your dashboard to suit your reporting requirements. For more information, see the [Adding rich text widgets](/latest/docs/editing-dashboards-and-widgets#adding-rich-text-widgets) section below.
- **Expand grid widgets to show more rows.** By default, a grid widget displays five rows. Enable the **More data in grid widget** option when you create a widget from JSON or copy a widget, as shown below. This option lets you display up to 25 rows instead. You can resize an expanded grid widget without losing the expanded row count.

![Dashboard widget displaying data systems and their respective counts for various services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reporting_2xwidth(2).png)

> [!NOTE]
> Note
> 
> PDF and PPTX exports always use the default row count, regardless of this setting.
- **Update Widget Details** such as the JSON query, widget name, and grid or metric type for a widget. Click options (three dots) and select **Update Widget Details** to update details.

> [!NOTE]
> **Note**
> 
> If you edit a widget's JSON query from **Update Widget Details** in edit mode, the widget no longer supports click-through to Graph Explorer. To restore click-through, recreate the widget from a query instead of editing its JSON directly.
- **Update columns in grid widgets** using the column selector. You can add or remove columns in your grid widgets in edit mode by clicking on the column selector icon and selecting properties you want to include as columns. On the contrary, you can uncheck the columns you do not want in your grid widgets.
- **Delete widget** by selecting **Delete** from the widget options (three dots).
- **Delete or rename dashboard** or dashboard groups by selecting **Rename** or **Delete** from the options (three dots). On the right end of the dashboard name, click the pen icon to rename your dashboard.

To undo any change, from the upper right corner of the page, click **Cancel** and click **Save Changes** to save your edits.

## Updating widget types

To change widget type:

1. Select **Change Widget Type** from options (three dots).

![Dashboard displaying security findings, asset posture score, and risk severity metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/changingwidgettype_reportingdashboard.png)
2. In the **Chart Settings** modal, in the **Chart Type** field you can select the type of chart for your widget and in the **X axis** field, select the property you want to display on the x-axis of the chart.

Following chart types are supported for widgets:

> [!NOTE]
> Note
> 
> In addition to the segmented bar, the widget displays a total metric count that reflects the aggregate value across all segments.
  - Column
  - Stacked Column
  - Bar
  - Stacked Bar
  - Donut Pie
  - One Stacked Bar
  - Line
  - Spline
  - Area
  - Treemap
3. Additionally, you can customize the X-axis labels for your charts in the **X-Axis Label** field as shown below.

![Column chart displaying security findings types and their respective finding counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aixsnaming_reportingdashboard.png)
4. Click the **Grid** option to convert your widget into a grid.

![Widget configuration for displaying security findings type in a column chart format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/gridview_reportingdashboard.png)
5. In the **Select Series** section, select the data you want to represent in your widget as series. You can choose one or multiple series to display in your widget. Additionally, you can rename the series displayed on the chart as shown below.

![Bar chart displaying security findings types and their respective finding counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/editlabel_reportingdashboard.png)
6. Click **Update Widget** after making the desired changes as shown below.

![Column chart displaying security findings types and their respective counts for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/updatewidget_reportingdashboard.png)

## Adding rich text widgets

Reporting Dashboard lets you add **rich text** widgets to your custom dashboards to enhance the data analytics and reporting experience. You can edit and generate report for rich text widgets like regular widgets in the Reporting Dashboard.

You can add the following data as rich text widgets:

- Hyperlinks to glossaries or important documentation
- External links
- Text and notes
- Code blocks
- Tables

> [!NOTE]
> Note
> 
> Securiti lets you adjust height for the Rich Text widgets within defined limits, making it easier to fit headings or short text blocks without unnecessary whitespace.

To add a rich text widget.

1. In the Reporting Dashboard module, select the dashboard you want to add widgets in.
2. Near the upper right corner of the page, click **Edit**.
3. Near the upper right corner of the page in edit mode, click **Actions.**
4. Select **Add Rich Text Widget** from the menu, as shown below.

![Dashboard displaying data classification, asset types, and options for adding widgets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reporting_addrichtext_option.png)
5. In the **Add Rich Text** modal, configure the following fields, as shown below.

| Field | Description |
| --- | --- |
| Widget Name | Enter your widget name, such as `Data systems and AI models` |
| Display widget name on dashboard | Mark the checkbox to display the widget name as section header. When left unmarked, the widget name does not appear as header in the view mode. Instead, the header remains hidden by default and is only shown on hover in edit mode, letting you access actions like rename, delete, or duplicate without affecting the widget’s displayed height. |
| Display as page break in PDF/PPTX export | Mark the checkbox to mark a Rich Text widget to act as a page divider in exported reports. When enabled, the widget is rendered as a full-width page break in PDF/PPTX output to maintain consistent report formatting. > [!NOTE] > Note > > This setting affects exports only and does not change the widget’s appearance on dashboards. |
| Text box | Enter your text, links, or code in the provided text box. |

![Widget displaying data systems and AI models scanned for the report, including Amazon S3.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reporting_addrichtext_modal.png)
6. Click **Save**.

The rich text widget shows in your dashboard, you can edit it like other dashboard widgets.
7. Click options (three dots) for your widget and select **Update Rich Text** to update the widget details.

![Dashboard displaying data classification elements and options for updating widgets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reporting_editrichtextwidget.png)

## Related

- [Creating widgets from JSON queries](/creating-widgets-from-json-queries.md)
- [Copying dashboard widgets](/copying-dashboard-widgets.md)
- [Refreshing dashboards and widgets](/refreshing-dashboards-and-widgets.md)
- [Using Instance Explorer for widgets](/using-instance-explorer-for-widgets.md)
