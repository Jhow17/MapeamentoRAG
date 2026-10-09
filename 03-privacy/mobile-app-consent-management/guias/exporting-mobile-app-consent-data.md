---
title: "Exporting mobile app consent data"
slug: "exporting-mobile-app-consent-data"
updated: 2026-08-31T15:52:25Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/exporting-mobile-app-consent-data"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Exporting mobile app consent data

**Scenario**

As a Data Privacy Officer, you receive a regulatory request to provide mobile app consent records for data subjects for a specific reporting period. Pulling this data manually is slow and increases the risk of missing or incomplete records. With Securiti's Export Consent Data functionality, you can select a custom date range and extract mobile app consent data specific to that period. This helps you respond quickly to audits, demonstrate compliance with confidence, and avoid delays caused by manual data collection.

Securiti lets you export mobile app consent data directly from the management portal using a selected date range. This capability simplifies data extraction for reporting, compliance, and operational use while improving reliability and reducing manual effort.

> [!NOTE]
> Note
> 
> Only Super Admins can initiate mobile app consent data exports, and each export includes data from all organizational units by default.

Use the following table to understand the available export capabilities:

| Capability | Description |
| --- | --- |
| Date range selection | Exports mobile app consent data for any selected historical date range. |
| Large data handling | Splits large datasets into multiple `CSV` files and bundles them into a single `ZIP` file. |
| Email delivery | Processes the export in the background and sends an email notification when the export completes. The email includes a secure download link to the exported data or notifies you if no data is available for the selected date range. > [!NOTE] > Note > > Securiti retains exported data for **30 days** and then automatically deletes it. |
| Job status tracking | Tracks export status as “In Progress”, “Completed”, or “Failed”. |

## Procedure

To export mobile app consent data:

1. In Securiti, open **Mobile App Consent Management**, and choose **Explorers > Export Consent Data**.
2. On the Export Consent Data page, from the upper right corner, click **Export**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export-button(1).png)
3. On the **Export** popup, set the date range using the date picker, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Set-Date-Range-Export.png)
4. Once done, near the bottom of the popup, click **Export**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export-Consent-Data.png)

> [!NOTE]
> Note
> 
> If you stay on the **Export Consent Data** page after starting an export, click **Refresh Dashboard** to update the table and view the latest status, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Refresh-Dashboard.png)
5. Once the export completes, check your email for a notification from Securiti. The email includes secure download links or notifies you if no data is available for the selected date range, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Email-Exported-Mobile-Consent-Data.png)

## Exporting consent data from completed jobs

To export consent records from the existing completed jobs:

1. In Securiti, open **Mobile App Consent Management**, and choose the **Explorers > Export Consent Data**.
2. To the right of the jobs table, next to the **Updated On** column, click **Download**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download-Icon.png)

Securiti processes the export of consent records again and sends you via email.

> [!NOTE]
> Note
> 
> Securiti updates the **Updated On** column after you initiate the re-export.

### Consent data fields

Use the following table to understand the columns shown on the Export Consent Data page:

| Column | Description |
| --- | --- |
| Date Range | Shows the date range selected for the export job. |
| Created By | Shows the user who initiated the export job. |
| Status | Shows the job status as In Progress, Completed, or Failed. |
| Created On | Shows the date the export job was created. |
| Updated On | Shows the date the export job was last updated. For instance, when a re-export is initiated. |

## Using the top-level filter

The top-level filter lets you combine different properties of the export jobs and apply filters accordingly. It works from the top down and determines the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the **Export Consent Data** dashboard, click **+**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filters-Icon(1).png)
2. From the filters panel apply one or more filters using the following properties, as shown below: ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filters-Panel.png)

| Property | Description |
| --- | --- |
| Created On | Filters export jobs by date range. Use **between** to select a date range. |
| Created By | Filters export jobs by the user who created them. Use **is one of** to select one or more users from the provided list, or use the search option. |
| Status | Filters export jobs by job status, such as In Progress, Completed, or Failed. Use **is one of** to select one or more statuses, or use the search option. |
| Updated On | Filters export jobs by the export job's last updated time. For instance, when you initiate a re-export job, the Updated On date changes to the current date. Use **between** to select a date range. |
3. Once you set all required properties, from the bottom of the filter panel, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results.
4. (Optional) To clear the filter, from the upper right corner, click **Clear Search**.
