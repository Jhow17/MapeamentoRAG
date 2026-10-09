---
title: "Using the scan definitions page"
slug: "using-the-scan-definitions-page"
updated: 2026-09-29T10:46:03Z
published: 2026-09-29T11:09:43Z
canonical: "helpcenter.securiti.ai/using-the-scan-definitions-page"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using the scan definitions page

This section covers the details of all the options available on the **Scan Definitions** page.

To access this page, from the sidebar, choose **Scan Definitions**.

![Securiti dashboard displaying sensitive data intelligence and discovery scan options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/navigatingtoscandefinitions.png)

The **Scan Definitions** page displays all existing scans with their status, such as completed, in progress, or scheduled. It also shows a **Throttling Status** column for each scan:

- If the scan is heavily throttled, this column shows a red label.
- For all other scans, this column shows `--`.

> [!NOTE]
> Note
> 
> - Throttling reflects rate limits enforced by the connector's SaaS provider, not a limit imposed by Securiti.
> - Securiti marks a scan as heavily throttled when the throttling percentage (the greater of the percentage of API calls that were rate-limited and the percentage of the last hour spent throttled) exceeds 10%. Hover over the label to view more details.

![Overview of scan definitions with job statuses and data system types displayed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/lastjobrun_scandefinitions.png)

Use the **Options** (three dots) at the end of each entry to perform the following operations:

![Overview of scan definitions with active and inactive scans listed in a table format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/morescanoptions_scandefinitions.png)

| Action | Description |
| --- | --- |
| Scan Details | Lets you view the current scan's configuration. Available for all discovery scan types including Running, Paused, Canceled, Completed, and Scheduled. |
| View Scan Scope | Displays all data systems involved in the scan along with their individual statuses and statistics, and the pod configuration used for the scan. Available for all discovery scan types. For more information, see [Viewing the scan scope](/latest/docs/using-the-scan-definitions-page#viewing-the-scan-scope). |
| View Job Run History | Lets you view the scan job history, including the scan job ID with objects, tables, and documents scanned and skipped, along with start and end times. For more information, see [Viewing the scan job history](/latest/docs/viewing-scan-job-history). |
| Pause Scan | Pauses a running or in-progress scan. For more information, see [Managing scan definitions](/latest/docs/managing-scan-definitions). |
| Resume Scan | Resumes a paused scan. |
| Scan Now | Runs the scan manually. Securiti starts scanning instantly only if the pod is activated. |
| Clone Scan | Uses the same configuration of an existing scan. You cannot clone a completed scan. |
| Delete Scan | Deletes an existing scan. For more information, see [Managing scan definitions](/latest/docs/managing-scan-definitions). |
| View Logs | Lets you view logs of a completed scan. For more information, see [Viewing the discovery scan logs](/latest/docs/viewing-discovery-scan-logs-1). |
| Cancel | Cancels a running or in-progress scan. On the popup, click **Cancel**. |
| EDC Refresh | Automatically updates datasets in the Enterprise Data Catalog. Available for structured data systems only. |

## Viewing discovery scan results

Click **View Results** from any entry to view the scan results on the [structured](/latest/docs/structured-data-discovery-new-experience), [unstructured](/latest/docs/using-the-unstructured-data-discovery), or [streaming](/latest/docs/using-the-streaming-data-discovery-dashboard) data dashboards.

![Overview of scan definitions, including active and inactive scans with job statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewresults_scandefinitions.png)

## Viewing discovery scan metadata

Click the **View Metadata** icon from any entry to view the data elements, content profiles, and exact data profiles identified in the scan job.

![Overview of scan definitions with active and inactive scans listed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewmetadataicon_scandefinitions.png)

To expand the metadata explorer view, click the expand icon.

![Overview of scan definitions, including Google Drive Discovery Scan and job statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/expandmetadataview_scandefinitions.png)

## Viewing the classification evidence

Collecting evidence lets you validate detections after scan jobs complete. You can access evidence files for your unstructured scans if you have configured [Private Cloud Storage (PCS).](/latest/docs/system-settings-configuring-private-cloud-storage)

Securiti generates evidence files only when detections are found during a scan. When detections are present, Securiti creates merged evidence files up to a cap of 4 GB. If the evidence exceeds this threshold, Securiti stops generating evidence files to maintain performance and system stability.

> [!NOTE]
> Note
> 
> If no detections are found, Securiti still generates the scan's evidence summary file.

To view the evidence file for AWS, Azure, GCP, and OCI Private Cloud Storage:

1. In the Collect Evidence field, click **Download Link**. This action copies the file's URL to your clipboard.

![Overview of scan definitions, including active and inactive scans with download link option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/downloadlink_scandefinitions.png)
2. Paste the URL into your browser to download the evidence file directly from your cloud storage.

> [!WARNING]
> Important
> 
> If you have configured Azure in Private Cloud Storage, the download link may not open the exact evidence file directly. After logging in to the Azure cloud, you may need to manually navigate to the file location.

For more information, see [Evidence summary for structured data classification](/latest/docs/summary-of-classification-evidence-for-structured-data).

> [!NOTE]
> **Note**
> 
> These downloaded evidence files are in compressed format. To view these files, you must decompress them using the **gunzip** tool.

## Creating and applying quick filters

You can create quick filters to find a specific scan job and save them for future use.

> [!NOTE]
> **Note**
> 
> Quick filters apply to the **Scan Definitions** and **Scan Job History** pages, whereas grid filters apply to individual pages only.

To use quick filters:

1. Under the **Scan Definitions** heading, click the **Add** (plus icon).
2. Choose an option from:
  1. Scan name
  2. Scan ID
  3. Data System Type
3. Select the operator and value for the filter.

![User interface displaying scan definitions and filter options for data system types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfilters_scandefinitions.png)
4. Click **Apply**.
5. To save the filter, click **Save Views**.

![Scan Definitions interface showing Kafka data system type and scan details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveafilterview_scandefinitions.png)
6. On the **Save View** popup, choose an existing filter group or click **Add New** to create one.
7. Enter the filter name and description.
8. Click **Save View**.

![Interface showing scan definitions and filters for Kafka data systems management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveviewfields_scandefinitions.png)

To view existing saved filters, click **Saved Views**. Your saved filter appears on the **Custom Views** tab.

![Dashboard displaying Kafka data systems and scan details for analysis and management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/openingasavedview_scandefinitions.png)

> [!NOTE]
> **Note**
> 
> Click **Clear Search** on the right side of the filter to clear it and view the full list of scans.
> 
> ![Scan definitions for Kafka with job status and details displayed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clearsearch_scandefinitions.png)

## Customizing visible columns

The **Scan Definitions** page lets you customize visible columns and apply top-level filters.

![Scan Definitions interface showing Kafka data system type and active scan details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/customizingcolumns_scandefinitions.png)

## Viewing discovery scan stats

You can view the discovery scan status under the **Job Status** column for completed, canceled, timeout, errored, or scheduled scans. Results are available on the relevant dashboard, such as [structured](/latest/docs/structured-data-discovery-new-experience), [unstructured](/latest/docs/using-the-unstructured-data-discovery), or [streaming](/latest/docs/using-the-streaming-data-discovery-dashboard) data dashboards.

![Scan definitions for Snowflake with job statuses and last run details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/lastjobstatus_scandefinitions.png)

> [!NOTE]
> **Note**
> 
> - The scan results appear on the respective dashboards only for completed scan jobs.
> - Average stats are calculated over the past 5 hours of the scan and are not based on total scan duration.

The **Average Velocity** stats in the **Job Run Stats** popup also show a **Throttling Status** value:

- This value shows the throttling percentage for the scan, calculated as the greater of the percentage of API calls that were rate-limited and the percentage of the last hour spent throttled.
- When the percentage is based on time spent throttled rather than on API calls, the tile header changes to **Throttling duration (Last hour)** and shows the percentage of the last hour spent throttled.
- A red label appears next to the percentage when the throttling percentage exceeds 10%.

> [!NOTE]
> Note
> 
> Throttling reflects rate limits enforced by the connector's SaaS provider, not a limit imposed by Securiti. Once the scan completes, the throttling fields clear and show `--`.

### Unstructured discovery scan stats

Expand **Job Run Stats** to view discovery scan stats for unstructured data.

![Overview of scan definitions and job run statistics for data processing tasks.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/unstructureddatasystemjobrunstats_scandefinitions.png)

Use the following table to understand each stat:

| Stat | Description |
| --- | --- |
| Objects processed | Total objects processed during the scan job run. This is a sum of: - Scanned: Documents successfully scanned - Skipped by system: Documents skipped by the system - Skipped by error: Documents skipped due to errors |
| Objects skipped by policy | Documents skipped due to user-defined policies out of the total document count. |
| Volume processed | Total data processed during the scan job run. This is a sum of: - Scanned: Data volume successfully scanned - Skipped by system: Data volume skipped by the system - Skipped by error: Data volume not processed due to errors |
| Volume skipped by policy | Data not processed due to user-defined policies out of the total data volume. |
| Average files processed | This includes: - Skipped: Average files skipped per hour - Errored: Average files per hour for which an error occurred - File scan time: Time in seconds for scanning or classification of a file |
| Average data processed | This includes: - Skipped: Average data volume skipped per hour - Errored: Average data volume per hour for which an error occurred |

### Structured discovery scan stats

Expand **Job Run Stats** to view discovery scan stats for structured data.

![Overview of MySQL scan job statistics including databases, tables, and classification times.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddatasystemjobrunstats_scandefinitions.png)

Use the following table to understand each stat:

| Stat | Description |
| --- | --- |
| Databases scanned | Databases successfully processed out of the total databases. |
| Schemas scanned | Schemas successfully processed out of the total schemas. |
| Tables scanned | Tables successfully processed out of the total tables. |
| Tables/Views having errors | Tables or views not processed due to errors out of the total counts. |
| Views scanned | Views successfully processed out of the total views. |
| Columns scanned | Columns successfully processed out of the total columns. |
| Average tables classified | Average number of tables classified per hour in a specific job. |
| Average query latency time | Average query latency time in seconds, such as the time taken to query a table for scanning. |
| Average classification time | Average classification processing time for a table in seconds. |

### Streaming discovery scan stats

Expand **Job Run Stats** to view discovery scan stats for streaming data.

![Overview of scan definitions and job run statistics for Kafka data system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/streamingdatasystemjobrunstats_scandefinitions.png)

Use the following table to understand each stat:

| Stat | Description |
| --- | --- |
| Schemas scanned | Schemas successfully processed out of the total schemas. |
| Topics scanned | Topics successfully processed out of the total topics. |
| Topics having errors | Count of topics for which errors occurred during a scan job. |
| Fields scanned | Fields successfully processed out of the total fields. |

## Viewing the scan scope

On the **Scan Definitions** page, you can view the scan scope to identify the pod running the scan and monitor its CPU and memory usage.

1. For a completed scan, click **Options** (three dots) and choose **View Scan Scope**.

![Overview of scan definitions for Kafka data system with job status and details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewscanscopeoption_scandefinitions.png)

This opens the **Scan Scope** popup.

![Overview of scan definitions and job statuses for data systems in a management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanscopepopup_scandefinitions.png)

Use the following table to understand the columns on the **Scan Scope** popup:

| Column | Description |
| --- | --- |
| ID | Identifier of the data system. |
| Data System | The data system instance activated from the Data Systems page and used for the discovery scan configuration. |
| Cluster Name | The pod's cluster on which this scan was running. |
| Last Updated | The time when the scan last ran. |
| Status | The current status of the scan. |
| Message | The scan job messages based on the scan type. Examples include: - `The scan job has hit the &lt;connector_type&gt; API limit. The scan job will slow down. Check the logs for more details.` - If the scan job fails, the Message column will show the corresponding error message. > [!NOTE] > Note > > Only one of Error or Message is shown at a time, with Error taking precedence. |
| Throttling Status | Refers to whether the data source's SaaS provider is currently rate-limiting it, based on the greater of the percentage of API calls rate-limited and the percentage of the last hour spent throttled. Shows a red label when this percentage exceeds 10%, and `--` otherwise. Hover over the label to view more details. |
2. Click the cluster name link from the **Cluster Name** column to navigate to the **Cluster Status** page for your pod.

![Scan scope details showing completed status for GCP-Securitide data system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clusternamelink_scanscopepopup.png)

On the **Cluster Status** page, you can view the number of nodes and their CPU and memory usage.

![Dashboard displaying CPU and RAM usage statistics for a cloud deployment system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clusterstatustab_pods.png)
3. On the **Cluster Status** page, in the **Discovery Scan** section, you can see the status of current and previous scans as shown below:

![Overview of application performance with scan statuses and insights for data processing.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/discoveryscantab_pods.png)

For more information about configuring the pod, see [Pods configuration](/v1/docs/pods-configuration).

## Viewing discovery scan statistics in Data Command Graph

The Data Command Graph also displays the following performance metrics for individual discovery scan jobs:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-S0SUDOFL.png)

| Metric | Description |
| --- | --- |
| Total Scan Duration | Displays the total elapsed time since the discovery scan started, including active and idle periods. |
| Active Scan Duration | Displays the total time the scan spent actively processing data. |
| Average File Scan Time | Displays the average time taken to scan a single file during the selected period. |
| Average Files Processed | Displays the average number of files processed in the selected time range. |
| Files Scanned | Displays the total number of files successfully scanned. |
| Data | Displays the total volume of data processed during the scan. |
| Rate Limit Usage | Displays the level of rate limit consumption during the scan. |

For more information, see [Creating discovery scans](/latest/docs/creating-discovery-scans).
