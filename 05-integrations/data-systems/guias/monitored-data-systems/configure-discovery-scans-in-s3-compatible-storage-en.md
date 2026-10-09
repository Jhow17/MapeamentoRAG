---
title: "Configure discovery scans in S3 Compatible Storage"
slug: "configure-discovery-scans-in-s3-compatible-storage-en"
updated: 2025-10-31T14:29:07Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-s3-compatible-storage-en"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in S3 Compatible Storage

This section describes creating a discovery scan for S3 Compatible Storage. See [Understanding discovery scans](/v1/docs/discovery-scans) for more information about Securiti discovery scans.

To configure a discovery scan in S3 Compatible Storage:

1. On the **Create Discovery Scan** page under the **Scan Details** section, enter a convenient name and description for the scan job.
2. In the **Scope** section, apply the following settings:

| \| Parameter \| Description \| \| --- \| --- \| \| Select Target \| Choose **S3 Compatible Storage**. \| \| Select Bucket \| Choose the specific bucket(s) you want to scan. The Select Buckets dialog shows you the list of buckets with columns for Bucket Name, Approximate Size of the bucket, and its Account ID. \| \| Select Primary Scan \| Specify any of your older scans as primary or the current one. Selecting the data system and its instance(es) enables the **Select Primary Scan** field. Click the **View Scans** link to view the specified scan on the **Discovery Scans List** page. \| |
| --- |
| Parameter | Description |
| Select Target | Choose **S3 Compatible Storage**. |
| Select Bucket | Choose the specific bucket(s) you want to scan. The Select Buckets dialog shows you the list of buckets with columns for Bucket Name, Approximate Size of the bucket, and its Account ID. |
| Select Primary Scan | Specify any of your older scans as primary or the current one. Selecting the data system and its instance(es) enables the **Select Primary Scan** field. Click the **View Scans** link to view the specified scan on the **Discovery Scans List** page. |
3. Under the **Scan Conditions** section, select your desired inclusion or exclusion attribute:
  - **Object Extension Category**
  - **Object Prefix**
  - **Object Name**
  - **Object Tags**
  - **Object Extensions**
  - **Object Size**
  - **Last Modified**
4. In the **Advanced Settings**, use the following settings for your structured data systems. The settings available vary by data system type.
  1. Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.

In case of S3 Compatible Storage, it processes only the new files, objects in S3 buckets in the next scan. The last sync time is compared with the last scan start time.
  2. Under the **Sampling** section, perform the following settings:

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
  3. (Optional) If you have [private cloud storage configured](/v1/docs/system-settings-configuring-private-cloud-storage), mark the Collect Evidence checkbox. Enabling this option collects your scan results for each file in a separate evidence file, which can be viewed and downloaded from the Unstructured Data Discovery dashboard. For more information, see [viewing and downloading the classification evidence file](https://helpcenter.securiti.ai/docs/using-the-unstructured-data-discovery#viewing-and-downloading-the-classification-evidence-file)

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
  4. Under the **Image Text Extraction** section, mark the **Extract text from images using** OCR checkbox to include images in OCR scanning.

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
  5. Under the **File Text Extraction** section, mark the checkbox for **Extract text from compressed and archived files**. Enabling this option lets Securiti scan data from all the supported compressed file types.

> [!NOTE]
> **Note**
> 
> - Embedded file types include **PDF**, **Word** (doc, docx, docm, doct), **Excel** (xls, xlsx, xlsm), **PowerPoint** (ppt, pptx, pptm), and **Email** (EML) documents.
> - Archived and compressed files are scanned only when the **Archive** file type is included in the **Scan Conditions** and **Extract text from compressed and archived files** is enabled in the **Advanced Settings**. If the Archive file type is included in the conditions but extraction is disabled, the file is downloaded and sent to the content classifier, then skipped without being scanned. If the Archive file type is excluded from the Scan Conditions, the file is skipped by policy regardless of the extraction setting.
  6. Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically, or you can initiate it manually from [Configuring the file cluster analysis](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files). For more information, see [Using the cluster analysis dashboard](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
  7. Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, then you can see this
> 
> **Breach Impact Analysis** toggle on the data system's **Permissions** tab.
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data** , you can configure another scan for the same data system instance and disable the Breach Impact Analysis from that scan.
5. In the **Sensitive Data** section, choose the locality enabled for your tenant. Securiti shows the data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
6. In the **Sensitive Data** section, apply the following settings:
  1. Choose the **Locality** enabled for your tenant. Securiti shows the data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  2. In the **Sensitive Data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configure-discovery-scans-in-s3-compatible-storage-en-image-t4ta4zqm.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configure-discovery-scans-in-s3-compatible-storage-en-image-1kll8402.png)
7. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below: ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configure-discovery-scans-in-s3-compatible-storage-en-image-sg1sh64h.png)
  - **Running manual scans**
    - You can activate and deactivate the scans manually at any time, and you can also start and cancel the scan at any time you want.
  - **Running scans on a periodic basis**
    - The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval, only when you do not want to run them at specific intervals. The minimum pause interval that you can specify is one hour.
    - If a scan job runs for more than a day (e.g, for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configure-discovery-scans-in-s3-compatible-storage-en-image-ok37hz8o.png)
8. (Optional) In the **Responses**, choose what responses Securiti take when the scan completes. You can specify one or more emails with a relevant email template.
  1. Enable the **Send an email notification** toggle. Choose what response Securiti to take when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
  2. Enable the **Trigger Workflow** toggle to specify a workflow. Then, click **Add Workflows**. To do this, configure a [discovery scan trigger node](/document/preview/164118#UUID-b3c1e53a-86c2-6dd4-d001-c122818a1441).
9. (Optional) In the Responses area, scroll down to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** option to add a new table/topic or update all table/topic selections, or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.
  - You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - (Optional) In the Responses area, to extract your unstructured schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register schema** checkbox.

1. Near the top right side of the page, click **Finish and Activate**. To view discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
