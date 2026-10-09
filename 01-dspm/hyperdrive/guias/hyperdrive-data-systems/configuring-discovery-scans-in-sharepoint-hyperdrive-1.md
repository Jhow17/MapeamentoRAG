---
title: "Configuring Discovery scans in Outlook (Hyperdrive)"
slug: "configuring-discovery-scans-in-sharepoint-hyperdrive-1"
updated: 2026-07-18T06:57:48Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/configuring-discovery-scans-in-sharepoint-hyperdrive-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Discovery scans in Outlook (Hyperdrive)

> [!NOTE]
> Note
> 
> - The Outlook Discovery Scan includes all emails within mailbox content for the scoped users or groups, regardless of whether the emails are from internal or external senders.
> - To include all mailboxes and nested folders in the scanning, you must upgrade the Outpost version to release 1.146 or higher.

This section describes creating a Discovery scan for Microsoft 365 Outlook. See [Understanding discovery scans](/v1/docs/discovery-scans) for more information about Securiti discovery scans.

Once you have completed the Microsoft 365 Outlook connector authentication and scoping inventory sync is complete, you can create discovery scans for the Microsoft 365 Outlook you used in the connector authentication.

1. On the **Create Discovery scan** page Scan details area, enter a convenient name and description for the scan job.
2. In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose one of the following connectors. - **Microsoft 365 Outlook**. |
| Select Data Systems | Choose the specific Data system instances to scan. |
3. In the **Data system Scope**, specify the following scopes in case of Connector type you selected.

> [!NOTE]
> **Note**
> 
> The Outlook Discovery Scan now includes all emails within mailbox content for the scoped users or groups, regardless of whether the emails are from internal or external senders.

| Connector type | Data Sytem Scopes |
| --- | --- |
| Microsoft 365 Outlook | Select groups or users from the **Specify Discovery scan Scope(s)** menu to include in the scan. You can select single and multiple groups or users. Securiti scans all the folders and child folders for the selected scope. |
4. Under the **Scan Conditions** section, select your desired inclusion or exclusion attribute:

Securiti includes or excludes the files according to the following conditions:
  - **File Extension Category**
  - **File Name**
  - **File Owner**
  - **File Extensions**
  - **File Size**
  - **Created Date**
  - **Last Modified**
  - If the file size is 0 bytes, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file size is 10GB, the file is not downloaded irrespective of extension but does show in the Dashboard as part of the skip policy.
  - If the file extension is in common video formats(see image) then such files are not downloaded and are not shown as part of the dashboard.

> [!NOTE]
> **Note**
> 
> If a file does not fall into the above 3 categories, it is downloaded and passed on for classification where it is again classified based on its content. Hence Some of the VOB files or .aax files were classified as they were below 10GB in size and not part of video file extensions as shown below:
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(634).png)
5. In the **Advanced Settings**, use the following settings for your Unstructured data systems. The settings available vary by Data system type.
  1. Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.

In case of Outlook, the incremental scan processes only the updated messages and attachments and skips them in the next scan. The last sync time is compared with the last scan start time
  2. 1. Mark the checkbox for **Unstructured data** to select the sample of unstructured data using the percentage and size of the dataset.

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
  4. Mark the **Include newly discovered tables and schemas** **into the scan scope** to consider all new tables and schemas automatically for scanning while maintaining the configurations done in the scope section. Selecting this option lets Securiti automatically include newly discovered tables and schemas in the scope of the scan.
  5. For Microsoft 365 Outlook (Self-hosted), mark the **Scan Attachments** and **Scan Mail Content** checkboxes to include attachments and message body content in the scan scope.

These options let you independently control whether email attachments and email body content are included in the scan, giving you greater flexibility to tailor scan scope based on your requirements.

> [!NOTE]
> Note
> 
> - Both checkboxes are marked by default on existing and new scans. No Outpost upgrade is required if both checkboxes remain selected.
> - At least one checkbox must be marked to run a scan. Securiti does not let you run a discovery scan if both checkboxes are cleared.
> - If you clear either checkbox, you must upgrade your Outpost versions to release 1.148.0 and above.
  6. Under the **Image Text Extraction** section, mark the **Extract text from images using** OCR checkbox to include images in OCR scanning.

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
  7. Under the **File Text Extraction** section, mark the checkbox for **Extract text from compressed and archived files**. Enabling this option lets Securiti scan data from all the supported compressed file types.

> [!NOTE]
> **Note**
> 
> - Embedded file types include **PDF**, **Word** (doc, docx, docm, doct), **Excel** (xls, xlsx, xlsm), **PowerPoint** (ppt, pptx, pptm), and **Email** (EML) documents.
> - Archived and compressed files are scanned only when the **Archive** file type is included in the **Scan Conditions** and **Extract text from compressed and archived files** is enabled in the **Advanced Settings**. If the Archive file type is included in the conditions but extraction is disabled, the file is downloaded and sent to the content classifier, then skipped without being scanned. If the Archive file type is excluded from the Scan Conditions, the file is skipped by policy regardless of the extraction setting.
  8. Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically or you can initiate it manually from [Configuring the file cluster analysis](/latest/docs/detecting-and-reducing-duplicate-and-near-duplicate-data).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
  9. Mark the **Enable Data Subject Requests (DSR) Automation** on this datacheckbox to let Securiti index the scanned data elements for use when processing the DSR request. Securiti builds an index of all primary Data Element types, which includes:

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
  10. Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, then you can see this
> 
> **Breach Impact Analysis** toggle on the data system's **Permissions** tab.
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data** , you can configure another scan for the same data system instance and disable the Breach Impact Analysis from that scan.
6. In the **Sensitive data** section, apply the following settings:
  1. Choose the **Locality** enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  2. In the **Sensitive data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(24).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(24).png)
7. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(65).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(59).png)
8. (Optional) In the **Responses** section, apply the following settings:
  1. Enable the **Send an email notification** toggle. choose what responses Securiti takes when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
  2. Enable the **Trigger Workflow** toggle to specify a specified Workflow. Then, click **Add Workflows**. To do this configure a [discovery scan trigger node](/v1/docs/discovery-scan).
9. Refer to the matching procedure to view the Discovery scan results.

The live stats are refreshed and updated after periodic intervals until the scan is complete. To view Discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).
  1. On the **Discovery Scans** page at the specific scan job Row, choose the More Actions (**three dots**) icon > **View Scan Scope**.
  2. On the Scan Scope Popup, click the scan job Row you want to view.

It expands the Scan Scope popup by showing the **Job Run Stats**.

#### Key considerations for scope configuration

- Externally linked inline attachments are not scanned, i.e. images linked in the email’s HTML.
- Discovery scan includes the following items multiple times:
  - Messages copied to other folders
  - A Message sent by external users to multiple internal users (can be via a group).
  - Emails “Sent As” another user, where copies are saved to multiple mailboxes.
- Messages not scanned:
  - Messages sent by users that are not scoped
