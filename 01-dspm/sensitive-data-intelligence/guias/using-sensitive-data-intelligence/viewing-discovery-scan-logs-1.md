---
title: "Viewing scan logs"
slug: "viewing-discovery-scan-logs-1"
updated: 2026-09-29T11:13:27Z
published: 2026-09-29T11:13:27Z
canonical: "helpcenter.securiti.ai/viewing-discovery-scan-logs-1"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing scan logs

Securiti lets you track lags, errors, and issues in your discovery scans using detailed scan logs.

> [!NOTE]
> **Note**
> 
> Logs are supported for all structured and unstructured discovery scans.

To view discovery scan logs:

1. From the side panel, hover over **Sensitive Data Intelligence** and choose **Discovery Scans > Scan Definitions**.
2. From any discovery scan entry, choose **Options** (three dots icon) > **View Logs**, as shown below.

![Scan Definitions interface displaying active, inactive scans, and options for managing scans.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewlogsforadiscoveryscan_scandefinitions.png)

Securiti redirects you to the **Scan Job Logs** page, as shown below.

![Scan job logs display job IDs, statuses, and timestamps for data scanning activities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewinglogsofascanjob_scandefinitions.png)

> [!NOTE]
> **Note**
> 
> Once the scan job is complete, Securiti sends you an email notification with a summary for each data system scanned. You receive this email only if you enabled the **Send an Email Notification** option during discovery scan creation.

## Exporting discovery scan logs

You can export all discovery scan logs to a CSV file to analyze and troubleshoot issues. To export, click **Export**, as shown below.

![Scan definitions and job logs with export option highlighted for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exportingdiscoveryscanlogs_scandefinitions.png)

Securiti exports all stats from the **Scan Definitions** and **Scan Job History** pages, including scan metadata, regardless of filters applied. Securiti sends an email notification when the CSV file is ready to download. You can also download it from the **My Downloads** page.

## Common discovery scan errors

Use the following table to understand common errors in discovery scans. Click the error to navigate to the audit logs for the specific discovery scan error.

| Error | Description |
| --- | --- |
| Failed to Classify | Occurs due to any issue encountered during content classification. Securiti increments this error sub-category in such cases. |
| Failed to Download | Occurs due to an internal issue that prevents file download. It might result from a failed download task, a missing file, or repeated retry failures due to network or system-related problems. |
| System Error | Indicates an internal connector error due to system-related issues within the platform. |
| API Error | Occurs when the system encounters issues such as hitting the rate limit, exhausting the API quota, or failing to retry a task targeting an API. |
| Credentials Expired | Occurs when OAuth 2.0 credentials have been revoked, preventing the system from retrieving data. |

## Using filters on the discovery scan logs page

On the **Scan Job Logs** page, use quick filters to find logs for specific scans. For example, to view discovery scan logs for Microsoft 365 SharePoint Online, use the **Data System Type** filter.

To apply filters:

1. Click the **Apply Filters** (plus icon) button to see filter options.
2. On the popup, choose an option such as **Scan name**, **Scan ID**, or **Data System Type**.
3. Click **Apply**, as shown below.

![User interface displaying scan definitions and filter options for data system types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfilters_scandefinitions.png)
4. To save applied filters, click **Save View** and choose an option from the menu, as shown below. These include:

![Interface showing scan job logs with options to save views and job details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveviewdropdown_scandefinitions.png)
  - **Save with Changes** to save the changes in the selected saved view
  - **Save as a New View** to save the current view as a new one
  - **Revert Changes** to cancel the latest changes
5. If you choose **Save as a New View**, fill the required fields, as shown below.

![Interface showing scan job logs and options to save views for Amazon RDS.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveviewfieldsforscanjoblogs_scandefinitions.png)
6. To access the saved views, click **Saved Views**, as shown below.

![Scan job logs showing completed and in-progress jobs for Amazon RDS for MySQL.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/savedviewsoption_scanjoblogs.png)

System and custom-created views appear on the left side, as shown below.

![Overview of saved views and scan jobs for Amazon RDS for MySQL.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/accessingsavedviews_scandefinitions.png)
7. To clear applied filters, click **Clear Search**, as shown below.

![Scan job logs showing completed and in-progress jobs for Amazon RDS for MySQL.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clearsearch_scanjoblogs.png)

For more information, see [Creating discovery scans](/latest/docs/creating-discovery-scans).
