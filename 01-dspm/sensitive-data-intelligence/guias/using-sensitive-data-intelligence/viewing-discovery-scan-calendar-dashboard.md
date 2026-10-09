---
title: "Viewing the discovery scan calendar dashboard"
slug: "viewing-discovery-scan-calendar-dashboard"
updated: 2026-09-29T11:32:20Z
published: 2026-09-29T11:32:20Z
canonical: "helpcenter.securiti.ai/viewing-discovery-scan-calendar-dashboard"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing the discovery scan calendar dashboard

**Scenario**

As a Data Security Officer, you need to ensure regular scans run across all your data systems. Manually tracking schedules in spreadsheets is time-consuming and often leads to missed overlaps or gaps. With the Scan Calendar dashboard, you can visualize all scans in one calendar, filter by system or owner, and quickly spot conflicts. This helps you streamline oversight, avoid risks, and ensure consistent coverage.

## Overview

The Scan Calendar dashboard directly addresses the challenges of managing discovery scans. It enhances visibility and planning by giving you a clear, intuitive visualization of all scheduled scans. This makes it easier to spot overlaps, gaps, and upcoming activities at a glance, letting you proactively manage scan schedules and avoid conflicts.

This visibility streamlines the management of large numbers of scans across multiple organizations, enabling you to quickly locate, analyze, and share relevant scan information.

## Prerequisites

- You must enable Data Command Graph and Discovery Scan for your tenant to use Scan Calendar. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.
- You must have the **​Essential Classification Features**​​ submodule enabled. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your tenant.

## Working with the scan calendar

The consolidated view of Scan Calendar improves visibility and ensures you can manage scanning activities efficiently across your environment. The Scan Calendar lets you take direct actions and offers a centralized view to track, plan, and manage discovery scans.

To work on the scan calendar dashboard, see:

### Viewing scans on the calendar

You can view all the scans on the calendar for up to 6 months using Scan Calendar in **Weekly** or **Monthly** view. However, the default view of **Scan Calendar** is the current week of the weekly view.

#### Weekly view

View scans based on hours from 1:00 a.m. to 11:00 p.m. in your local time zone, as shown below.

![Schedule displaying various tasks and their timings for daily and weekly activities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(666).png)

The date range shifts by one week when you use the navigation arrows, as shown below. This lets you review and plan discovery scans on a week-by-week basis.

![Scan calendar showing scheduled tasks and their statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(667).png)

#### Monthly view

On the upper left of the calendar panel, click the **Monthly** tab to shift to Monthly View, as shown below.

![Scan calendar showing daily tasks and scheduling options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(668).png)

The date range shifts by one month with each arrow click, as shown below. This view provides a broader perspective, making it easier to analyze scans across the entire month.

![Scan calendar displaying scheduled tasks and daily activities for the month.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(669).png)

### Getting back to today

The **Today** button instantly brings you back to the current date, as shown below. This is especially useful when you are exploring historical or upcoming schedules and want to quickly return to the present day.

![Scan calendar displaying scheduled tasks and events.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(670).png)

### Applying the filters

The filters let you combine different properties of the discovery scans, such as Data System Name, Data System Type, Owner, Primary Scan, and Scan ID. These filters take precedence over other filters, working top-down to determine what appears in both the grid view and the right-side panel.

To use the filters, follow the steps below:

1. From the upper left corner of the **Scan Calendar** dashboard, click the **Add Filters** icon (plus), as shown below.![Scan calendar showing scheduled tasks and events for each day.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(672).png)
2. Select the filters from the list. The available filters include **Data System Name**, **Data System Type**, **Owner**, **Primary Scan**, **Scan ID**, **Scan Job Status**, and **Scan name**.

For example, to filter scans based on the **Data System Type** and **Primary Scan**, click **Data System Type** and select **Google Drive**. Then click **Primary Scan** and select **True**.
3. Click **Apply**, as shown below.

![Filter options for Primary Scan with True and False selections highlighted in the interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(673).png)
4. To clear the filter, click **Clear Search**, as shown below.

![Scan calendar showing scheduled daily scans and their statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(674).png)

### Saving searched views

Securiti lets you save your built queries for later use. For example, once you save a query, it gets saved as a **Saved View** with the filters you applied and the results that matched them. This ensures you can access commonly used searches from the **Saved View** section instead of rebuilding the same filter combination each time.

To save a built query as a saved view:

1. After filtering the scans from the filter, click **Save View**, as shown below.

![Scan calendar showing scheduled daily scans and options to save views.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(675).png)
2. On the **Save View** side panel, select the **Group** or click **Add New** to create a new group.
3. Enter the **Name** for the view.
4. Enter the **Description.**
5. Click **Save View**, as shown below.

![Scan calendar showing scheduled tasks and filters for Google Drive.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(678).png)

### Understanding color-coding for scans

Securiti uses color codes to represent the status of each discovery scan. This visual categorization helps you quickly understand the state of your scans without needing to open each entry.

Use the following table to understand the color coding for scan identification:

| Color | Name | Description |
| --- | --- | --- |
| Blue | Upcoming / Scheduled | Identifies upcoming scans scheduled to run in the future. |
| Gray | In Progress | Highlights scans currently in progress or running. |
| Green | Completed | Highlights completed scans. |
| Red | Error | Flags scans that encountered errors during execution. |
| Black | Canceled / Cancel Scheduled | Indicates scans that were canceled before completion. |
| Orange | Timed Out | Indicates scans that ran longer than the allotted time and stopped automatically. |
| Purple | Paused / Pause Scheduled | Highlights scans that were actively running, but then paused manually or by the system. |

You can determine the status of any discovery scan by looking at the colored bar displayed at the start of the scan entry in the calendar.

By checking the color next to a scan name, you can instantly understand its standing without opening detailed scan information, as shown below.

![Calendar displaying scheduled tasks and their statuses for each day.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(679).png)

### Searching for a specific scan

The search bar lets you locate specific scans by **name** or **description** without relying on filters. It saves time when navigating large schedules and improves efficiency by filtering out irrelevant entries so you can focus on the scans most relevant to your task.

Type in the **name** or **description** of your desired scan in the search bar to locate its position directly in the calendar, as shown below.

![Scan calendar showing scheduled tasks and events for each day.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(680).png)

### Creating a new discovery scan from the calendar view

You can initiate a new scan directly from the **Scan Calendar** page. To do so, follow the steps below:

1. From the top-right, click **+ Create Discovery Scan** to redirect to the **Scan Definitions** page, where you can create a discovery scan for your data system.

![Scan calendar showing scheduled tasks and their statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(695).png)

For more information, see [Discovery scans for structured connectors](/latest/docs/creating-a-discovery-scan-for-structured-connectors), [Discovery scans for unstructured connectors](/latest/docs/discovery-scans-for-unstructured-connectors), and [Discovery scans for streaming connectors](/latest/docs/discovery-scans-for-streaming-connectors).

### Exporting the scan calendar

Securiti lets you **Export** the scans by downloading scan schedules to a **CSV** file for offline analysis, reporting, and sharing. You can customize the export by selecting a specific time range and the data properties you want to include in your export. It saves time by letting you analyze scan results outside the platform using familiar tools like Excel or Google Sheets.

To export scan details:

1. From the top-right, click **Export**, as shown below. ![Scan calendar showing scheduled tasks and export option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(688).png)

This opens the **Export Discovery Scan Calendar** pop-up.
2. Click the **Time Range** dropdown to choose how far ahead you want to export data, as shown below. The available options include:

![Export Discovery Scan Calendar with options for time range selection and data properties.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(689).png)
  - Next 24 hours
  - Next 7 days
  - Next 30 days
  - Next 90 days
  - Custom Range
3. (Optional) If you select **Custom Range**, choose a start and end date.
  1. Specify the start date in the **From** field using the date selector, as shown below.

![Calendar interface displaying date selection and scan properties for data export.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(690).png)
  2. Specify the end date in the **To** field using the date selector, as shown below.

![Calendar interface showing scan schedule and properties for data export.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(691).png)
4. In the **Select properties** section, add or remove pre-added properties, such as **Scan ID**, **Job Status**, **Files Scanned**, and **Owner**.
  1. (Optional) Cross out unwanted scan properties to remove from the export details, as shown below.

![Export Discovery Scan Calendar with selected properties and custom date range options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(692).png)
  2. (Optional) Click the **Select Properties** dropdown to mark or clear the checkboxes to customize the export file, as shown below. Scroll down to view all properties. ![Export Discovery Scan Calendar with selected properties and custom date range options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(693).png)
  3. (Optional) Click **Apply Properties** to confirm your choices, as shown below.

![Export Discovery Scan Calendar with selected properties and date range options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(694).png)
5. Click **Export as CSV**, as shown below. ![Export Discovery Scan Calendar with date range and selected properties for data export.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(681).png)

For more information, see [Discovery scan FAQs](/latest/docs/discovery-scan-faqs).

## Related

- [Discovery scans](/discovery-scans.md)
