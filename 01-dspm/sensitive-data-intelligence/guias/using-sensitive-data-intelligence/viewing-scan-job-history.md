---
title: "Viewing scan job history"
slug: "viewing-scan-job-history"
updated: 2026-09-29T11:12:38Z
published: 2026-09-29T11:12:38Z
canonical: "helpcenter.securiti.ai/viewing-scan-job-history"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing scan job history

The **Scan Job History** page lets you track the progress and outcomes of all past and ongoing discovery scan jobs across your data systems. For each scan job, you can view key metrics such as Files Count, Files Scanned, Skipped Files, and Data Skipped. Use this page to monitor scan performance, identify anomalies, and review job-level details such as start and end times, active scan duration, and average file processing rates.

To access this page, open the **Scan Definitions** page and choose **Scan Job History**, as shown below.

![Overview of scan job history with job IDs, statuses, and data system types listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanjobhistory_scandefinitions.png)

On this page, you can find information such as **Files Count**, **Files Scanned**, **Skipped Files**, **Data Skipped**, **Throttling Status**, and more.

- The **Throttling Status** column shows a red label when the scan job's throttling percentage (the greater of the percentage of API calls rate-limited and the percentage of the last hour spent throttled) exceeds 10%. Otherwise, the column shows `--`.

- You can use the **Data System Type** filter to find relevant scans, as shown below.

![Overview of scan definitions, job history, and data system types in a dashboard interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystemtype_scanjobhistory.png)

- To view the details identified in the scan job, such as data elements, content profiles, and exact data profiles, click the **View Metadata** icon for the respective scan job, as shown below.

![Scan job history details showing job status, duration, and processed objects statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/statsofascanjob_scanjobhistory.png)

> [!NOTE]
> **Note**
> 
> - Total scan duration shows total elapsed time from scan start to scan end, including any paused time.
> - Active scan duration shows the cumulative time during which the scan was actively running, excluding paused intervals.
> - The following metrics show lifetime averages for the entire active scan duration, excluding scan pauses:
>   - Average Files Processed
>   - Average Files Skipped
>   - Average Files Errored
>   - Average Data Processed
>   - Average Data Skipped
>   - Average Data Errored
>   - Average Files Scan Time

- You can view these metrics from the **Column Selector** as well, as shown below.

![Scan definitions interface showing job history, filters, and completed jobs statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnselector_scandefinitions.png)

- Click the **More Options** (three dots icon) at the end of each entry, as shown below. This lets you perform the following operations:
  - View logs
  - Copy Export Report Link

![Overview of scan definitions and job history with options to view logs and reports.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanjoboptions_scandefinitions.png)

> [!NOTE]
> **Note**
> 
> Content profile match results and data element breakdowns for unstructured data systems such as GCS, S3, and Microsoft 365 SharePoint Online do not appear in the **Job Run Stats** panel during the scan. Results populate incrementally as individual files finish scanning, with full results available once the scan completes. To view discovered content profiles and data elements while a scan is in progress, see the [Unstructured Data Scan](/latest/docs/using-the-unstructured-data-discovery) and [Structured Data Discovery](/latest/docs/structured-data-discovery-new-experience) dashboards.

For more information, see [Viewing scan logs](/latest/docs/viewing-discovery-scan-logs-1).
