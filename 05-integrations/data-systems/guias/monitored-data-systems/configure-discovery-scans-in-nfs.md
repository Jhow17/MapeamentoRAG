---
title: "Configure discovery scans in NFS"
slug: "configure-discovery-scans-in-nfs"
updated: 2026-07-22T19:50:55Z
published: 2026-07-22T19:50:55Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-nfs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in NFS

This section describes creating a Discovery scan for NFS. See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

## Scope settings

Perform the following steps to configure scan details and scope settings for NFS connectors:

- On the Create Discovery scan page **Scan Details** area, enter a convenient name and description for the scan job.
- In the Scope area, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **NFS.** |
| Select Data Systems | Choose the specific NFS Data system instances to scan. |
- Selecting the Data system and its Instance(es) enables the **Select Primary Scan** field. Specify any of your older scans as primary or the current one.

> [!NOTE]
> **Note**
> 
> When you select an unstructured Data system, multiple scans might exist for that Data system. You can mark the same scan that you are going to create as a primary or mark any of the older scans related to the same unstructured Data system.

![nfs_primaryscan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a9b8c3d5-a474-7ef8-3f7d-53ffdddca75a.png)

Click the **View Scans** link to view the specified scan on the Discovery Scans List page.
- In the **Scan Conditions** area, select your desired file object category to include or exclude from the scan for your selected unstructured Data system. This list of excluded file objects skips the processing of less important files and improves overall scan performance. You may add or remove additional exclusions based on your requirements.

![ds_scan_conditions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04cd7e51-25ff-97e9-1277-642a8e6d6af7(10).png)

Securiti includes or excludes the files according to the following conditions:
  - If the file size is 0 bytes, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file size is 10GB, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file extension is in common video formats(see image) then such files are not downloaded and are not shown as part of the dashboard.
  - If a file does not fall into the above 3 categories, it is downloaded and passed on for classification where it is again classified based on its content. Hence Some of the VOB files or .aax files were classified as they were below 10GB in size and not part of video file extensions as shown below:

![video_formats.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0306a29b-b6ad-80fd-eadb-6050d770881d(17).png)

You can include or exclude the File Owner field from the scan conditions to scan files for specific users only.

## Advanced Settings

In the **Advanced Settings**, use the following settings for your Structured data systems:

- Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.
- 1. Mark the checkbox for **Unstructured data** to select the sample of unstructured data using the percentage and size of the dataset.

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
- Mark the checkbox for **Get MIP Labels Information** to extract MIP labels for your document. For more information, see [Microsoft Information Protection (MIP) label extraction for data systems](/latest/docs/microsoft-information-protection-mip-label-extraction-for-data-systems).
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
- Under the **File Text Extraction** section, mark the checkbox for **Extract text from compressed and archived files**. Enabling this option lets Securiti scan data from all the supported compressed file types.

> [!NOTE]
> **Note**
> 
> - Embedded file types include **PDF**, **Word** (doc, docx, docm, doct), **Excel** (xls, xlsx, xlsm), **PowerPoint** (ppt, pptx, pptm), and **Email** (EML) documents.
> - Archived and compressed files are scanned only when the **Archive** file type is included in the **Scan Conditions** and **Extract text from compressed and archived files** is enabled in the **Advanced Settings**. If the Archive file type is included in the conditions but extraction is disabled, the file is downloaded and sent to the content classifier, then skipped without being scanned. If the Archive file type is excluded from the Scan Conditions, the file is skipped by policy regardless of the extraction setting.
- Mark the checkbox for **File Type Classification Only** to let Securiti perform the scan purely on document file types.
- Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically, or you can initiate it manually from [Configuring the file cluster analysis](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files). For more information, see [Using the cluster analysis dashboard](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
- Mark the **Enable Data Subject Requests (DSR) Automation** on this datacheckbox to let Securiti index the scanned data elements for use when processing the DSR request. Securiti builds an index of all primary Data Element types, which includes:

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
- Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, then you can see this
> 
> **Breach Impact Analysis** toggle on the data system's **Permissions** tab.
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data** , you can configure another scan for the same data system instance and disable the Breach Impact Analysis from that scan.

## Sensitive Data settings

Perform the following steps to configure Sensitive Data settings for NFS:

- In the **Sensitive data** area, choose the locality enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  - In the **Sensitive data** area, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(27).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(27).png)

> [!NOTE]
> **Note**
> 
> - If you have enabled the data subject requests automation on the data, some of the data elements are disabled for customization. You can see the message ‘Personally Identifiable Data element that helps with DSR Automation’ when you hover over those data elements.
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

Perform the following steps to configure Schedule settings for NFS:

- In the **Schedule area**, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(72).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(66).png)
  - **Custom Cron**

For custom cron jobs, use the [expression builder](https://crontab.guru/). It has the minute, hour, day of the week, and day of the month settings. When you are done, use that expression in the Enter Cron field.![cronjob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc9b8076-799b-9c0f-c533-8c0a42fe28c8(6).png)

You can also exclude the times when you don't want the scan to run and specify multiple times weekly, or monthly. Select the hour block(s) in the 24x7 matrix where scanning should be executed. The scan is automatically paused at the beginning of each execution block and resumed at the end.

![exclude_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bfe17ec-ae09-821a-76a3-fca2d7d68e46(6).png)

## Responses settings

Perform the following steps to configure Responses settings for NFS:

(Optional) In the **Responses** area, choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template.

- (Optional) In the **Responses** area, enable the **Trigger Workflow** toggle, and click **Add Workflow**.

![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(10).png)
  - On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**.

![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(10).png)

For more information, see [Discovery scan trigger node](https://helpcenter.securiti.ai/docs/discovery-scan-trigger-node).
- (Optional) In the Responses area, scroll down to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** option to add a new Table/topic or update all Table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:
    - | Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - (Optional) In the Responses area, to extract your unstructured Schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register Schema** checkbox.

Near the top right side of the page, click **Finish and Activate**. To view Discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).
