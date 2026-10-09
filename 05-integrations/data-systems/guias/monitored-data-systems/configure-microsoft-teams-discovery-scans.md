---
title: "Configure Microsoft Teams discovery scans"
slug: "configure-microsoft-teams-discovery-scans"
updated: 2025-11-20T12:10:40Z
published: 2025-11-20T12:10:40Z
canonical: "helpcenter.securiti.ai/configure-microsoft-teams-discovery-scans"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure Microsoft Teams discovery scans

This section describes creating a Discovery scan for Microsoft Teams. For more information about Securiti discovery scans., see [Understanding discovery scans](/v1/docs/discovery-scans).

1. On the **Create Discovery scan** page under the **Scan Details** section, enter a convenient name and description for the scan job.
2. In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Microsoft Teams**. |
| Select Data Systems | Choose the specific Data system instances to scan. |
| Select Primary Scan | Specify any of your older scans as primary or the current one. Selecting the Data system and its Instance(es) enables the **Select Primary Scan** field. Click the **View Scans** link to view the specified scan on the **Discovery Scans List** page. |
3. In the **Data system Scope** section, select All or any specific teams and channels you want to include or exclude from the scan. By default, the list has all the teams and channels marked as selected.

> [!NOTE]
> The **Scan Conditions** of your Discovery scan let you further refine and limit your scans, regardless of whether you have specified a **Data system Scope** or not. Securiti uses them to validate the data being processed. **Scan Conditions** and **Advanced Settings** work together to define the scan scope, as you can choose scan conditions to include or exclude different options such as file extension, size, and so on.

> [!NOTE]
> **Note**
> 
> - **Scoped Scans**: Data fetching is restricted to the defined scope (e.g., selected groups). In this case, the Scan Conditions apply only to the data within the specified scope
> - **Unscoped Scans**: All available data is fetched first, and then the Scan Conditions are applied to validate or limit that data.File Extension Category
  - **File Name**
  - **File Extensions**
  - **File Size**
  - **Created Date**
  - **Last Modified**
4. In the **Advanced Settings** section, use the following settings for your Structured data systems.
  1. Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.
  2. Mark the checkbox for Unstructured data to select the sample of unstructured data using the percentage and size of the dataset.

> [!NOTE]
> **Note**
> 
> If you don’t mark the checkbox for Unstructured data, Securiti scans 100% of the files with a limit of 10 GB, which are part of this discovery scan scope. Marking the Unstructured data checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Scan | Add the percentage of unstructured files that you want to include in the scan. Securiti uses probability approach to select files based on the specified percentage and scans only the selected files. > [!NOTE] > Note > > - Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > - The actual number of scanned files can vary from the configured sampling percentage. For instance, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan up to | Add the size of each file that you want to include in the scan. For instance, if you set the unstructured sampling to 1MB, but a file is 3MB and contains personal or sensitive data, Securiti scans only 1MB of that file. |
  3. Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically, or you can initiate it manually from [Configuring the file cluster analysis](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files). For more information, see [Using the cluster analysis dashboard](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
  4. Mark the **Enable Data Subject Requests (DSR) Automation** on this datacheckbox to let Securiti index the scanned data elements for use when processing the DSR request. Securiti builds an index of all primary Data Element types, which includes:

Username

    - Email
    - Passport Number
    - Driver License Number
    - US SSN
    - TSA Precheck Number
    - US Tax Payer ID
    - US DoD ID Number
    - US VISA Number
    - US Alien Registration Number
    - IN Aadhaar Card Number
    - IN PAN Number
    - BR CPF
    - AU Medicare Number
    - AU Tax File Number
    - NZ NHI

A popup appears about the data elements that are automatically enabled for DSR processing.
  5. Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, then you can see this
> 
> **Breach Impact Analysis** toggle on the data system's **Permissions** tab.
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data** , you can configure another scan for the same data system instance and disable the Breach Impact Analysis from that scan.
5. In the **Sensitive data** section, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  1. Choose the **Locality** enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  2. In the **Sensitive data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(26).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(26).png)

> [!NOTE]
> **Note**
> 
> If you have enabled the data subject requests automation on the data, some of the data elements are disabled for customization. You can see the message ‘Personally Identifiable Data element that helps with DSR Automation’ when you hover over those data elements.
6. (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

Doing so lets you view evidence as described in Viewing evidence for specific documents.

Securiti still captures the actual scan results even if you deselect the **Context** checkbox.

**Example Use Cases**:
  - To save your detections to a file, mark the **Save detections from scan results into a file** checkbox.
  - To detect metadata such as location and type, mark the **Metadata such as Location, Type** checkbox.
  - Enable the **Context** checkbox. Specify the number of detections that this scan can store after performing the Discovery scan. You have the option to set the default limit and higher context limit:

| Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per Data element type in each document (up to 100,000) |
| --- | --- |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per Data element type in each document (up to 20,000) |
  1. If you are looking for a piece of specific information with a small number of data elements, you can set the detections per scan job as described above.
  2. If you are looking for more information for example 100 detections per document and 10 data elements per document, Securiti gives 10 evidences per document - as you have specified 10 data elements detection per document in the Discovery scan job.
7. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(69).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour is followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(63).png)
8. (Optional) In the **Responses** section, apply the following settings:
  1. Enable the **Send an email notification** toggle. choose what responses Securiti takes when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
  2. Enable the **Trigger Workflow** toggle to specify a specified Workflow. Then, click **Add Workflows**. To do this configure a [discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
9. Near the top right side of the page, click **Finish and Activate**.

Discovery scan takes time to complete the process depending on the data available in the Data system Instance.
10. Refer to the matching procedure to view the Discovery scan results.

The live stats are refreshed and updated after periodic intervals until the scan is complete. To view Discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).
  1. On the **Discovery Scans** page at the specific scan job Row, choose the More Actions (**three dots**) icon > **View Scan Scope**.
  2. On the Scan Scope Popup, click the scan job Row you want to view.

It expands the Scan Scope popup by showing the **Job Run Stats**.

![SP-Scan-result.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da879457-4eef-e7d8-f0ff-e690adf35e52(1).png)
