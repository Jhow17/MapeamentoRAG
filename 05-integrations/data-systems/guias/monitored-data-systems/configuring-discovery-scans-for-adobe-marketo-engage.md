---
title: "Configuring discovery scans for Adobe Marketo Engage (Self-hosted)"
slug: "configuring-discovery-scans-for-adobe-marketo-engage"
updated: 2026-08-28T11:37:04Z
published: 2026-08-28T11:37:04Z
canonical: "helpcenter.securiti.ai/configuring-discovery-scans-for-adobe-marketo-engage"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring discovery scans for Adobe Marketo Engage (Self-hosted)

This section describes creating a discovery scan for Adobe Marketo Engage (Self-hosted) connector.

For more information about Securiti discovery scans, see [Understanding discovery scans](/latest/docs/discovery-scans).

## Scope settings

Perform the following steps to configure scan details and scope settings for Adobe Marketo Engage (Self-hosted) connectors:

- On the **Create Discovery Scan** page, under the **Scan details**, enter a convenient name and description for the scan job.
- In **Scope**, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Adobe Marketo Engage** |
| Select Data System(s) | Choose the specific data system instances to scan. |
- In the **Data System Scope**, use the Data System tools to choose which databases, schemas, tables, and views to include or exclude from the scan. The exact tools vary by data system type.

## Advanced settings

In the **Advanced Settings,** under the **Structured Data** section, use the following settings for your data systems.

- Mark the checkbox for **Store Sample Data** to store your sample files at your desired location configured during the connector activation process. When disabled, Securiti does not store any sample files on the appliance or cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page.

> [!NOTE]
> **Note**
> 
> - For Standard Pod deployments, you can enable this option without restrictions.
> - For EPod V2 deployments, Securiti checks whether PCS is configured:
>   - If PCS is not configured, you cannot enable this option and an error is displayed.
>   - If PCS is configured, you can enable the option and store sample files in PCS.

- Mark the checkbox for **Scan of string data type (CLOB) columns** to Scan every field of a string data type column for every data element type. The string data types include VARCHAR, JSON, TINYTEXT etc. These data types vary for each data system.

- In the **Classification preferences for successive scans** section, mark or clear the checkbox for **Perform classification on columns and tables previously learned** .

The setting performs field classification on previously learned columns and leverages any newly found evidence in those columns. When enabled, Securiti performs field classification on columns previously learned and identifies any new entries. If the columns have no data, Securiti classifies them as 'Unknown', and if the columns have new data, that will automatically be classified in the new scan.

In the **Advanced Settings** section, use the following settings **For Unstructured Data**. The settings available vary by Data system type.

- Mark **Enable Data Subject Requests (DSR) Automation** checkbox to let Securiti index the scanned data elements for use when processing the DSR request.
- Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.
- In the **Sampling** section, use the following settings:

1. Mark the checkbox for **Unstructured data** to select the sample of unstructured data using the percentage and size of the dataset.

> [!NOTE]
> **Note**
> 
> If you don’t mark the checkbox for Unstructured data, Securiti scans 100% of the files with a limit of 10 GB, which are part of this discovery scan scope. Marking the **Unstructured** **data** checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Scan | Add the percentage of unstructured files that you want to include in the scan. Securiti uses probability approach to select files based on the specified percentage and scans only the selected files. > [!NOTE] > Note > > - Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > - The actual number of scanned files can vary from the configured sampling percentage. For instance, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan up to | Add the size of each file that you want to include in the scan. For instance, if you set the unstructured sampling to 1MB, but a file is 3MB and contains personal or sensitive data, Securiti scans only 1MB of that file. |
2. Mark the **Semi-structured** data checkbox and specify the percentage of files and the maximum number of records to include in this scan.

> [!NOTE]
> **Note**
> 
> If you don’t enable the **Semi-structured data** checkbox, Securiti scans 100% of these file types with no size or record limit. Marking the **Semi-structured** data checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Scan | Add the percentage of semi-structured files that you want to include in the scan. These file types include: - AVRO - PARQUET - XLSX - CSV - TSV - ORC > [!NOTE] > Note > > - Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > - The actual number of semi-structured scanned files can vary from the configured sampling percentage. For instance, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan upto | Specify the sample of records from semi-structured data that you want to include in the discovery scan. For example, if you specify a sample of 100 records in a discovery scan, Securiti shows 100 rows were detected for data elements under the discovery scan results. > [!NOTE] > **Note** > > There is a limit to scanning 100,000 records in the case of semi-structured data. |

- (Optional) If you have [private cloud storage configured](/latest/docs/private-cloud-storage), mark the **Collect Evidence** checkbox. Enabling this option collects your scan results for each file in a separate evidence file, which can be viewed and downloaded from the Unstructured Data Discovery dashboard. For more information, see [viewing and downloading the classification evidence file](/latest/docs/using-the-unstructured-data-discovery#using-the-unstructured-data-scans-dashboard).

Here, Securiti lets you configure additional options to define the volume of the evidence to be collected.

| Setting | Description |
| --- | --- |
| Evidence collected per Scan Job | - The default is set to unlimited per discovery scan job. - Securiti generates unlimited evidence files and merges them into a single merged evidence file until it reaches a cap of 4 GB. Alternatively, you can limit evidence collection to a specific number (e.g., up to 2.5 million) based on your storage capacity. |
| Evidence collected per File | You can set this between 1 and 100,000 evidence per File detections. |
| Evidence collected per Data Element | You can set this between 1 and 20,000 evidence per data element detection. |
| Value | If you want to store the actual detections, mark the **Value** checkbox. |
| Context | Specify how many detections this scan must store after performing the discovery scan. You have the option to set the default limit and a higher context limit: |
| Metadata | If you want to see where this detection was found in the metadata, such as page number, sheet name, or column name. To use this option, mark the **Metadata** checkbox. |
  - If no detections are found during a scan, individual evidence files are not generated; however, Securiti generates that scan’s evidence. When detections are present, Securiti creates unlimited merged evidence files until it reaches the limit of 4GB. If the evidence exceeds this threshold, evidence files are not generated further to maintain performance and system stability.
  - This customization is especially helpful for cost-conscious teams that want to manage storage usage by limiting the volume or scope of evidence collected.
- Mark the **Include document metadata in classification scope** checkbox to include file name and header information in the classification scope.
- Under the **Image Text Extraction** section, mark the **Extract text from images using** OCR checkbox to include images in OCR scanning.

Common image types include JPG, PNG, BMP, JPEG, and so on.

> [!NOTE]
> **Note**
> 
> Text extraction from images using OCR is available only in environments where pods have been deployed. Securiti, then utilizes the extracted text for data classification.

Marking the **Extract text from images using OCR** checkbox shows you the following settings:

| Setting | Description |
| --- | --- |
| Min/Max megapixels | Set the minimum and maximum megapixels between 0.1 to 50, as Securiti skips images that exceed this limit, while the minimum default value is set to 0.01 and the maximum default value is set to 8. |
| Min / Max Aspect Ratio | Set the minimum and maximum aspect ratios between 0.2 (e.g., 1' × 5') and 10, as Securiti skips images that are too thin or shallow, making them unsuitable for scanning. The minimum default value is set to 0.2, and the maximum default value is set to 5. **Example** For an image with dimensions of 1000×748 (where 1000 is the width and 748 is the height, the aspect ratio is calculated by dividing the width by the height, which in this case becomes 1.33. We can adjust it according to the recommended setting to achieve the recommended aspect ratio between 0.2 to 5. > [!NOTE] > **Tip** > > For a better understanding of image dimensions and > > aspect ratios, visit the following: > > [Common aspect ratio for images and videos](https://marketing.istockphoto.com/blog/aspect-ratio/) > > [A guide to common aspect ratio, and image sizes](https://www.shutterstock.com/blog/common-aspect-ratios-photo-image-sizes) To use OCR settings for efficient scanning > > performance, see [Use case examples of text extraction from images](/latest/docs/scan-conditions-to-use-ocr-settings). |
| Number of pdf pages | Set the number of PDF pages between 1 and 100 in the PDF document that should be scanned by our OCR engine. |

Under the **File Text Extraction** section, mark the checkbox for **Extract text from compressed and archived files**. Enabling this option lets Securiti scan data from all the supported compressed file types.

> [!NOTE]
> **Note**
> 
> - Embedded file types include **PDF**, **Word** (doc, docx, docm, doct), **Excel** (xls, xlsx, xlsm), **PowerPoint** (ppt, pptx, pptm), and **Email** (EML) documents.
> - Archived and compressed files are scanned only when the **Archive** file type is included in the **Scan Conditions** and **Extract text from compressed and archived files** is enabled in the **Advanced Settings**. If the Archive file type is included in the conditions but extraction is disabled, the file is downloaded and sent to the content classifier, then skipped without being scanned. If the Archive file type is excluded from the Scan Conditions, the file is skipped by policy regardless of the extraction setting.

> [!NOTE]
> **Note** After a discovery scan completes, the resource URL for most asset types opens the asset in Adobe Marketo Engage. For file and image asset types, the resource URL instead opens the asset directly in a new browser tab.
> 
> This happens because the resource URL for file and image assets comes directly from the API response, so Securiti opens the asset itself instead of redirecting to Adobe Marketo Engage.

- Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically or you can initiate it manually from [Configuring the file cluster analysis](/latest/docs/detecting-and-reducing-duplicate-and-near-duplicate-data).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
- Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

## Sensitive Data settings

Perform the following steps to configure Sensitive Data settings for Adobe Marketo Engage (Self-hosted) connector:

- In the **Sensitive data** section, apply the following settings:
  - Choose the locality enabled for your tenant. Securiti shows the data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  - Choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_structured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b626f22e-f77f-cdbc-adef-0eff29445609(17).png)

## Schedule settings

Perform the following steps to configure Schedule settings for Adobe Marketo Engage (Self-hosted):

- In the **Schedule**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(25).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(24).png)

## Responses settings

Perform the following steps to configure Responses settings for Adobe Marketo Engage (Self-hosted):

(Optional) In the **Responses**, choose what responses Securiti takes when the scan completes. You can choose the following available response actions.

- **Send an Email Notification**: Notify about the scan job through emails. You can specify one or more emails with a relevant email template. Enter the email address(es) and select an email template from the menu.
- **Trigger Workflow**: Notify about the scan job by triggering a Workflow. To do this configure a [Discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).
- **Register data assets into the Data Catalog**: Mark **Add or Update all selections** option to add a new Table/topic or update all Table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - Mark the **Extract Lineage from SQL** checkbox to enable or disable the field data assets lineage to the data catalog. Enabling this option extracts the lineage from SQL objects included inside schemas or databases in scope.
  - Mark the **Add Dataset in lower case** checkbox to add the structured or Streaming datasets to the data catalog in lowercase Uniform Resource Names (URNs).

> [!NOTE]
> Note
> 
> If you want to convert your data system (that has a unique set of names (tables, views, functions, topics, or columns) to lowercase Uniform Resource Names (URNs) in the data catalog, you can mark the **Register Dataset in the lower case** option for your current data system from the structured or streaming data dashboard.

For more information about structured data dashboard, see [Using the Structured Data Discovery dashboard](/latest/docs/using-the-structured-data-discovery-classic-dashboard).
  - Mark the **Always Execute Response** checkbox to ingest the datasets to the Enterprise Data Catalog regardless of whether it has already been registered before. This feature lets you stay on top of dynamic data changes, ensuring your catalog remains accurate and reliable.
- Near the top right side of the page, click **Finish and Activate**. To view discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).

## Caveats

Review the following caveats before running a classification scan on Adobe Marketo Engage (Self-hosted) with Securiti:

- If a discovery scan reaches the Adobe Marketo Engage daily export limit and uses up all its retry attempts, Securiti automatically restarts the export when the quota resets daily at 12:00 AM CST. The scan continues without user intervention, though it may take a little longer to finish. For more information, see [Marketo Integration Best Practices](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/marketo-integration-best-practices#api-limits).
