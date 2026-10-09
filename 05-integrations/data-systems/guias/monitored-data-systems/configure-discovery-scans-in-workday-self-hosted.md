---
title: "Configure discovery scans in Workday (Self-hosted)"
slug: "configure-discovery-scans-in-workday-self-hosted"
updated: 2026-07-01T10:13:04Z
published: 2026-07-01T10:13:04Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-workday-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Workday (Self-hosted)

This section describes creating a Discovery scan for Workday (Self-hosted). See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

> [!NOTE]
> Note
> 
> Securiti lets you create only one discovery scan for structured and hybrid connectors at a time, such as Salesforce CRM and Jira Cloud. This limitation does not apply to Databricks.

## Scope settings

Perform the following steps to configure scan details and scope settings for Workday connectors:

- On the **Create Discovery scan** page under the **Scan Details** section, enter a convenient **Name** and **Description** for the scan job.
- In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Workday.** |
| Select Data Systems | Choose the specific Data system instances to scan. |
| Select Primary Scan | Specify any of your older scans as primary or the current one. Selecting the Data system and its Instance(es) enables the **Select Primary Scan** field. > [!NOTE] > **Note** > > When you select an unstructured Data system, multiple scans might exist for that Data system. You can mark the same scan that you are going to create as a primary or mark any of the older scans related to the same unstructured Data system. Click the **View Scans** link to view the specified scan on the **Discovery Scans List** page. |
- In the **Data system Scope** section, select Workday objects you want to include or exclude from the scan.
- In the **Scan Conditions** section, select your desired inclusion or exclusion attribute:
  - **File Extension Category**
  - **File Name**
  - **File Extensions**
  - **File Size**

This inclusion or exclusion skips the processing of less important files and improves overall scan performance. You may add or remove additional exclusions based on your requirements.

Securiti includes or excludes the files according to the following conditions:
  - If the file size is 0 bytes, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file size is 10GB, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file extension is in common video formats(see image) then such files are not downloaded and are not shown as part of the dashboard.

> [!NOTE]
> **Note**
> 
> If a file does not fall into the above 3 categories, it is downloaded and passed on for classification where it is again classified based on its content. Hence Some of the VOB files or .aax files were classified as they were below 10GB in size and not part of video file extensions as shown below:
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(616).png)

## Advanced settings

In the **Advanced Settings** under the **Structured Data** section, use the following settings for your data systems.

- Mark the checkbox for **Store Sample Data** to store your sample files at your desired location configured during the connector activation process. When disabled, Securiti does not store any sample files on the appliance or cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page.

> [!NOTE]
> **Note**
> 
> - For Standard Pod deployments, you can enable this option without restrictions.
> - For EPod V2 deployments, Securiti checks whether PCS is configured:
>   - If PCS is not configured, you cannot enable this option and an error is displayed.
>   - If PCS is configured, you can enable the option and store sample files in PCS.

- Mark the checkbox for **Include evidence file for CLOB scanning in discovery scan job** to Include the evidence file for the scan option, private cloud storage to be turned on.

Marking this checkbox enables the **Max Detections to Store** field, where you can specify the limit per discovery scan, per column, and per data element type.

These limits influence the number of data elements that are collected in evidence files for a discovery scan job. The maximum limits for each control are as follows:
  - Per Discovery Scan Job: 2.5M
  - Per Column: 500K
  - Per Data Element Type: 100K

- Mark the checkbox for **Scan of string data type (CLOB) columns** to Scan every field of a string data type column for every data element type. The string data types include VARCHAR, JSON, TINYTEXT etc. These data types vary for each data system.

- In the **Classification preferences for successive scans** section, mark or clear the checkbox for **Perform classification on columns and tables previously learned** .

The setting performs field classification on previously learned columns and leverages any newly found evidence in those columns. When enabled, Securiti performs field classification on columns previously learned and identifies any new entries. If the columns have no data, Securiti classifies them as 'Unknown', and if the columns have new data, that will automatically be classified in the new scan.

In the **Advanced Settings** under the **Unstructured Data** section, use the following settings for your data systems.

1. Mark the checkbox for **Unstructured data** to select the sample of unstructured data using the percentage and size of the dataset.

> [!NOTE]
> **Note**
> 
> If you don’t mark the checkbox for Unstructured data, Securiti scans 100% of the files with a limit of 10 GB, which are part of this discovery scan scope.

Marking the **Unstructured data** checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Scan | Add the percentage of unstructured files that you want to include in the scan. Securiti uses probability approach to select files based on the specified percentage and scans only the selected files. > [!NOTE] > Note > > - Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > - The actual number of scanned files can vary from the configured sampling percentage. For instance, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan up to | Add the size of each file that you want to include in the scan. For instance, if you set the unstructured sampling to 1MB, but a file is 3MB and contains personal or sensitive data, Securiti scans only 1MB of that file. |

Mark the **Semi-structured data** checkbox and specify the percentage of files and the maximum number of records to include in this scan.

> [!NOTE]
> **Note**
> 
> If you don’t enable the **Semi-structured data** checkbox, Securiti scans 100% of these file types with no size or record limit.

Marking the **Semi-structured data** checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Scan | Add the percentage of semi-structured files that you want to include in the scan. These file types include: - AVRO - PARQUET - XLSX - CSV - TSV - ORC > [!NOTE] > Note > > - Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > - The actual number of semi-structured scanned files can vary from the configured sampling percentage. For instance, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan upto | Specify the sample of records from semi-structured data that you want to include in the discovery scan. For example, if you specify a sample of 100 records in a discovery scan, Securiti shows 100 rows were detected for data elements under the discovery scan results. > [!NOTE] > **Note** > > There is a limit to scanning 100,000 records in the case of semi-structured data. |

- (Optional) If you have [private cloud storage configured](/v1/docs/system-settings-configuring-private-cloud-storage), mark the Collect Evidence checkbox. Enabling this option collects your scan results for each file in a separate evidence file, which can be viewed and downloaded from the Unstructured Data Discovery dashboard. For more information, see [viewing and downloading the classification evidence file](https://helpcenter.securiti.ai/docs/using-the-unstructured-data-discovery#viewing-and-downloading-the-classification-evidence-file)

Here, Securiti lets you configure additional options to define the volume of the evidence to be collected.

  - If no detections are found during a scan, individual evidence files are not generated; however, Securiti generates that scan’s evidence. When detections are present, Securiti creates unlimited merged evidence files until it reaches the limit of 4GB. If the evidence exceeds this threshold, evidence files are not generated further to maintain performance and system stability.
  - This customization is especially helpful for cost-conscious teams that want to manage storage usage by limiting the volume or scope of evidence collected.

| Setting | Description |
| --- | --- |
| Evidence collected per Scan Job | - The default is set to unlimited per discovery scan job. - Securiti generates unlimited evidence files and merges them into a single merged evidence file until it reaches a cap of 4 GB. Alternatively, you can limit evidence collection to a specific number (e.g., up to 2.5 million) based on your storage capacity. |
| Evidence collected per Document | You can set this between 1 and 500,000 evidence per document detections. |
| Evidence collected per Data Element | You can set this between 1 and 100,000 evidence per data element detection. |
| Value | If you want to store the actual detections, mark the **Value** checkbox. |
| Metadata | If you want to see where this detection was found in the metadata, such as page number, sheet name, or column name. To use this option, mark the **Metadata** checkbox. |
| Context | Specify how many detections this scan must store after performing the discovery scan. You have the option to set the default limit and a higher context limit: |
| Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per data element type in each document (up to 100,000) |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per data element type in each document (up to 20,000) |

### Example use cases

  - To locate specific information with a limited number of data elements, configure the Evidence collected per Scan Job setting accordingly.
  - If you are looking for more information, for example, 100 detections per document and 10 data elements per document, Securiti generates ten evidence per document.
- Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically or you can initiate it manually from [Configuring the file cluster analysis](/latest/docs/detecting-and-reducing-duplicate-and-near-duplicate-data).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
- Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

## Sensitive Data settings

- In the **Sensitive data** section, choose the **Locality** enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  - In the **Sensitive data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(42).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(42).png)
- (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

Doing so lets you view evidence as described in Viewing evidence for specific documents.
  - To save your detections to a file, mark the **Save detections from scan results into a file** checkbox.
  - To detect metadata such as location and type, mark the **Metadata such as Location, Type** checkbox.
  - Enable the **Context** checkbox. Specify the number of detections that this scan can store after performing the Discovery scan. You have the option to set the default limit and higher context limit:

Securiti still captures the actual scan results even if you deselect the **Context** checkbox.

**Example Use Cases**:
    - | Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per Data element type in each document (up to 100,000) |
| --- | --- |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per Data element type in each document (up to 20,000) |
    - If you are looking for a piece of specific information with a small number of data elements, you can set the detections per scan job as described above.
    - If you are looking for more information for example 100 detections per document and 10 data elements per document, Securiti gives 10 evidences per document - as you have specified 10 data elements detection per document in the Discovery scan job.

## Schedule settings

Perform the following steps to configure Schedule settings for Workday:

- In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(100).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day. ![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(93).png)

## Responses settings

Perform the following steps to configure Responses settings for Workday:

(Optional) In the **Responses** section, apply the following settings:

- Enable the **Send an email notification** toggle. choose what responses Securiti takes when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
- (Optional) In the **Responses** area, enable the **Trigger Workflow** toggle, and click **Add Workflow**.![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(36).png)
  - On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**.![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(36).png)

For more information, see [Discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).
- Near the top right side of the page, click **Finish and Activate**.

The Discovery scan takes time to complete the process depending on the data available in the Data system Instance.
- Refer to the matching procedure to view the Discovery scan results.
  - On the **Discovery Scans** page at the specific scan job Row, choose the More Actions (**three dots**) icon > **View Scan Scope**.
  - On the Scan Scope Popup, click the scan job Row you want to view.

It expands the Scan Scope popup by showing the **Job Run Stats**.

The live stats are refreshed and updated after periodic intervals until the scan is complete. To view Discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).
