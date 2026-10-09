---
title: "Exporting universal consent data"
slug: "exporting-universal-consent-data"
updated: 2026-04-24T07:56:10Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/exporting-universal-consent-data"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Exporting universal consent data

**Scenario**

As a Data Privacy Officer, reviewing consent records for audits and internal analysis can be challenging when relying on ad hoc reports, as it becomes difficult to track data completeness and freshness, especially when managing multiple exports across different time periods. For instance, you may generate separate exports for different date ranges and struggle to keep track of their status and accuracy. With Export Consent Data, you can simplify this process by selecting a single date range and initiating one consolidated export, letting you easily monitor progress and receive the final dataset via email, ensuring complete and reliable records with significantly less manual effort.

You can use **Export Consent Data** to export universal consent records by selecting a time range of your choice for internal analysis and record-keeping. It also provides key capabilities such as email notifications and job status tracking.

> [!NOTE]
> Note
> 
> - Only **Super Admin** users can initiate consent data exports.
> - Consent data is available for export **starting from 2020** onwards.
> - Exports include consent data across all organizational units.
> - Securiti retains exported data for **30 days** and automatically deletes it after this period.
> - Securiti maintains all export operations in **audit logs**.

## Procedure

To export universal consent data:

1. In Securiti, open Universal Consent Management, and choose **Explorers > Export Consent Data**.
2. On the upper right corner of the page, click **Export**, as shown below.

![Overview of consent data export status and details for various date ranges.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_1.png)
3. From the **Export** pop-up, select date range using the date pickers, and then click **Export**, as shown below.

![Export consent data interface showing date range selection and export button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_2.png)

The export job **Status** turns to **In Progress**, as shown below.

![Export consent data table showing statuses and date ranges for various entries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_3.png)

> [!NOTE]
> Note
> 
> To ensure stability and optimal performance, Securiti processes **one export request at a time**.

Once the export processing completes, the **Status** changes to **Completed**, and Securiti sends a ZIP file via email, as shown below.

![Export consent data table showing completed statuses and date ranges for various entries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_6.png)
4. In the email body, click **Download File** to download the ZIP file containing the exported consent data.

![Email notification indicating exported Universal Consent data is ready for download.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_5.png)

Securiti provides a ZIP file that contains multiple compressed CSV files. Each CSV file contains consent records for a single day within the selected date range. For instance, if the selected range is 01-01-2026 to 01-02-2026, the ZIP file may contain 30 compressed CSV files, one for each day in that range.
5. If the job status remains **In Progress** state, at the upper right corner of the page, click **Refresh Dashboard** to update it, as shown below.

![Export consent data table showing statuses and date ranges for various entries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_4.png)

> [!NOTE]
> Note
> 
> Securiti retries the export job automatically if it fails due to processing failures. If the job still fails, the status changes to **Failed**, and Securiti notifies you via email including the details.

## Exporting universal consent data from completed jobs

You can also export universal consent records from the existing **Completed** jobs.

To export consent records from the existing jobs:

1. In Securiti, open Universal Consent Management, and choose the **Explorers > Export Consent Data**.
2. To the right of the jobs table, next to the **Updated On** column, click **Download**, as shown below.

![Export consent data table showing completed tasks and their details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_66(1).png)

> [!NOTE]
> Note
> 
> The **Download** option in the grid view is available for **30 days** and is automatically disabled after this period.
3. Securiti processes the export of consent records again and sends you via email.

> [!NOTE]
> Note
> 
> Securiti updates the **Updated On** column after you initiate the re-export.

## Using the top-level filter for export jobs

The top-level filter lets you combine different properties of the export jobs and apply filters accordingly. It works from the top down and determines the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Export Consent Data dashboard, click **+**, as shown below.

![Export consent data table showing completed statuses and date ranges for various entries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_7.png)
2. From the filters panel, apply one or more filters using the following properties.

| Property | Description |
| --- | --- |
| Created On | Filters export jobs by date range. You can filter export jobs using the following operator: - **between** to select a date range |
| Created By | Filters export jobs by the user who created them. You can filter export jobs using the following operator: - **is one of** to select one or more users from the provided list or use the search option |
| Status | Filters export jobs by job status, such as **In Progress**, **Completed**, or **Failed**. You can filter export jobs using the following operator: - **is one of** to select one or more consent states or use the search option |
| Updated On | Filters export jobs by the export job’s last updated time. For instance, when you initiate a re-export job, the **Updated On** date changes to the current date. You can filter export jobs using the following operator: - **between** to select a date range |

For instance, to filter export jobs by **Status** (property), from the left pane of the filter panel select **Status**, then from the right pane mark the checkboxes next to the desired status.
3. Repeat the same step for other properties to suit your search needs. Once you apply all required properties, near the bottom of the filter panel, click **Apply**, as shown below.

![Filter options for exporting consent data, including status and date fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_8.png)

Securiti builds a query based on your selected properties and displays the filtered results.
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![Export consent data interface showing completed statuses and date ranges for exports.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_export_consent_data_9.png)
