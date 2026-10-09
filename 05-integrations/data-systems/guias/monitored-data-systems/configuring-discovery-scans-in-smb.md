---
title: "Configuring discovery scans in SMB"
slug: "configuring-discovery-scans-in-smb"
updated: 2026-06-02T11:10:00Z
published: 2026-06-02T11:10:00Z
canonical: "helpcenter.securiti.ai/configuring-discovery-scans-in-smb"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring discovery scans in SMB

This section describes creating a Discovery scan for SMB. See [Understanding discovery scans](/v1/docs/discovery-scans) for more information about Securiti discovery scans.

> [!NOTE]
> **Note**
> 
> - For connectors activated on pod versions 1.140.0 and above, Securiti collects Last Access Date and Time for the SMB connector.
> - To include the `created_date` in your files, see the [Troubleshooting for SMB connector](/v1/docs/troubleshooting-for-smb-connector).

1. On the **Create Discovery scan** page under the **Scan Details** section, enter a convenient **Name** and **Description** for the scan job.
2. In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **SMB**. |
| Select Data Systems | Choose the specific Data system instances to scan. |
3. Selecting a Data system and its Instance(s) enables the **Select Primary Scan** field.

Primary scans make it easier to see one scan result for each Data system on the Unstructured Data Explorer at a time. You can run multiple scans on the same Data system and can choose anyone to show up in the Unstructured Data Explorer.

The very first scan you create becomes the primary scan, and its results automatically show up in the dashboard. In case of multiple scans for the same Data system, you can mark any scan as a primary scan and hence, you can view the results of your primary scan on Unstructured Data Explorer.

While configuring a scan, you can choose not to make it a Primary scan if you only want it for specific purposes, like Breach Analysis, and don't want the results shown on the dashboard.

Each Data system can only have one Primary scan at a time.

Choose a scan to set it as a primary scan from the **Primary Scan Selection** menu.

![smbPrimaryScan.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-610412de-38d0-7b65-2991-82e46103d129.png)

Click the **View Scans** link to view the specified scan on the **Discovery Scans** page.

> [!NOTE]
> **Note**
> 
> - Securiti displays a warning message when you remove or leave a primary scan blank, preventing the Data system from appearing in the Unstructured Data Explorer when the primary scan filter is applied.
> - When you select an unstructured Data system, multiple scans might exist for that Data system. You can mark the same scan that you are about to create as a primary or mark any of the older scans related to the same unstructured Data system.

On the Unstructured Data Explorer, to view the primary scan results, the primary scan filter is already applied by default, as shown below: ![ude_primary_scanfilter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d704a7c-db4f-cb8f-889a-2b9e0c4a1174(1).png)
4. In the **Data system Scope** section, select SMB shares you want to include or exclude from the scan.

> [!NOTE]
> **Note**
> 
> - When configuring the SMB Connector for Discovery scan, you can either activate it with a root path "/" to scan all available shares on the specified host or specify a particular share name.
> - To limit the scope of scan, we recommend you activate the Connector with a specific share name. Securiti only discovers metadata for that single share, excluding any additional shares on the same host.
5. The **Scan Conditions** of your Discovery scan let you further refine and limit your scans, regardless of whether you have specified a **Data system Scope** or not. Securiti uses them to validate the data being processed. **Scan Conditions** and **Advanced Settings** work together to define the scan scope, as you can choose scan conditions to include or exclude different options such as file extension, size, and so on.

> [!WARNING]
> **Important**
> 
> - Discovery scans can automatically detect duplicate documents existing on your Data system or Cloud storage.

> [!NOTE]
> **Note**
> 
> - **Scoped Scans**: Data fetching is restricted to the defined scope (e.g., selected groups). In this case, the **Scan Conditions** apply only to the data within the specified scope.
> - **Unscoped Scans**: All available data is fetched first, and then the Scan Conditions are applied to validate or limit that data.

To use the relevant options appropriately, use the following Table:

| Scan Condition | Description |
| --- | --- |
| File Extension Category | Securiti lets you include or exclude files or objects during scanning, enhancing overall scan performance. You can add or remove exclusions based on your specific requirements. To include or exclude a **File Extension Category** or **Object Extension Category** in your scan, choose one of the options from the categories listed below. **File Extension Categories** - **Archive** If you want to exclude all types of compressed files from scanning, choose the **Archive** option. ![scanConditionsArchive.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-33d1e326-bbbb-2988-7f75-261794108ecb(2).png) - **Configuration** - **Binary** - **Audio** - **Video** - **Source Code** - **Temporary Files** and so on **Object Extension Categories** - Archive If you want to include or exclude all types of compressed files from scanning, choose the **Archive** option. ![scanConditionExtentionCategory.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae9b9e98-d779-cfab-c793-fd1a9e328bae(1).png) - **Word Processing** - **Spreadsheet** - **Presentation** - **Desktop Publishing** - **Binary** - **Audio** - **Video** - **Email** - **Temporary Files** and so on > [!NOTE] > **Note** > > You can add multiple options based on your specific requirements. |
| Folder Path | Securiti lets you choose from the available options to include or exclude the necessary folder(s) based on your scanning requirements. ![folderPathUntructuredOptions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ec6d8d7-5f42-a80e-314f-a667eb968fb2(2).png) Select a relevant option to include or exclude files from a specific folder, ensuring Securiti scans only the files within that folder. - **Match prefix** (is Condition): Includes files that start with the specified prefix. Securiti evaluates each document to check if it meets the customer-defined criteria before downloading its content. - **does not Match prefix** (is not Condition): Excludes files that start with the specified prefix. > [!NOTE] > **Note** > > These options Match the beginning of the folder path, unlike regex, which can Match anywhere in the path. **Example for matching prefix** **Assume the following folder structure**: 1. Projects/2024/Reports 2. Projects/2023/Reports 3. Archives/2024/Reports 4. Projects/2024/Logs 5. Archives/2023/Logs **Using the prefix Match such as "Projects/"** - The Match includes options 1, 2, and 4 because they start with Projects/. - The Match excludes options 3 and 5 because they start with Archives/. Similarly, using "Projects/" with does not Match prefix excludes options 1, 2, and 4 while including options 3 and 5. This method is useful for scanning or excluding entire folder structures based on their starting path. - **Match regex**: Includes files that Match the exact prefix based on the provided regex pattern. - **does not Match regex**: Excludes files that Match the exact prefix based on the provided regex pattern. Choosing the Match regex option lets Securiti include files that Match based on the provided regex pattern. **Example for matching regex** **Assume the following folder structure**: 1. Projects/2024/Reports 2. Projects/2023/Reports 3. Archives/2024/Reports 4. Projects/2024/Logs 5. Archives/2023/Logs Using the regex .*2024/Reports.*, the Match will include options 1 and 3 but excludes 2, 4, and 5. This logic follows the same behavior as the prefix Match / does not Match prefix functionality, but allows for more flexible pattern matching with regex. |
| File Name | Securiti lets you specify a file or object name using a regex pattern to Match desired files or objects for inclusion or exclusion in the scan. ![smbFileName.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc9803b9-752b-5b22-6795-bb58738cfbce.png) Choosing the **contains** option lets Securiti include the files and objects based on the specified regex pattern Choosing the **does not contain** option lets Securiti exclude the files and objects based on the specified regex pattern |
| File Owner | Lets you include or exclude the file owner in the scan condition using regex patterns to let Securiti detect and scan documents based on the file owner You must use shortnames for files on Microsoft Windows. For more information, see [Troubleshooting for SMB connector](/v1/docs/troubleshooting-for-smb-connector). |
| File Extensions | If the file extension is in common video formats (see image), then such files are not downloaded and are not shown in the Unstructured Data Explorer. Securiti lets you choose the relevant option if you want to include or exclude the File Extension or Object Extension in your scan, such as: - docx - xlsx - con - conf - con - tmp and so on If you want to exclude compressed files (zip, gzip, lzip, and so on) from scanning, choose these options. ![scanConditionExtentions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2a3d713-ed76-95eb-5fd4-656461bbcb0e(2).png) If a file does not fall into the above three categories (zip, gzip, lzip, and so on), it is downloaded and passed on for classification, where it is again classified based on its content. Hence, some of the VOB files or .AAX files were classified as they were below 10GB in size and not part of video file extensions, as shown below: ![video_formats.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0306a29b-b6ad-80fd-eadb-6050d770881d(26).png) |
| File Size | Securiti lets you specify the file size to include or exclude files in or from the scan, ensuring that only files within the defined size range are processed. ![smbFileSize.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-235299e6-f111-1921-e31b-e7933594bcce.png) - If the file size is 0 bytes, the file is not downloaded, irrespective of extension, but does show in the Unstructured Data Explorer as part of the skip policy. - If the file size is 10GB, the file is not downloaded irrespective of extension, but does show in the Unstructured Data Explorer as part of the skip policy. - If the file extension is in common video formats, then such files are not downloaded and are not shown in the Unstructured Data Explorer. |
| Date Created | Securiti lets you specify the creation date before or after a selected date to include or exclude files based on their creation timestamp. ![dsScanConditionDateCreatedBeforeAfter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97950b5c-de5f-f861-af59-e794022e69bf(2).png) |
| Last Modified | Securiti lets you specify the last modified date before or after a selected date to include or exclude files and objects based on their modification timestamp. ![dsBeforeAfterLastModifiedDate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12ee281d-ac65-6e0b-da58-b98f7d67649f(2).png) |
6. In the **Advanced Settings**, use the following settings for your data systems. The settings available vary by Data system type.
  1. Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.

In the case of SMB, an incremental scan includes only new or modified files in SMB shares.
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
  4. Gets the file owner information that is available for the SMB Data system only.

> [!NOTE]
> **Note**
> 
> This **File Owner** information is supported for SMB shared hosts on Windows servers only.
  5. Mark the **Use Read Replica** checkbox to can data from a read-only Replica server instead of the primary server in **SMB** data system. This works with any read-only Replica, such as a disaster recovery (DR) replica or a secondary site replica. Enabling this checkbox scan your Replica SMB servers during business hours due to the load of scanning potentially competing with user and application access to data if very large pods put additional strain on their devices.

> [!NOTE]
> Note
> 
> - You must authenticate your SMB data system using Replica server credentials in addition to the primary one.
> - To use this feature, you must upgrade your pod version to release 1.145 and higher.
  6. Mark the **Get MIP Labels Information** checkbox to extract MIP labels for your shares. See [Microsoft Information Protection (MIP) label extraction for data systems](/v1/docs/microsoft-information-protection-mip-label-extraction-for-data-systems), for more information.

> [!NOTE]
> Note
> 
> Securiti supports MIP label extraction for `ONENOTE` and `ONENOTE_TOC2` files with size lesser than 50MB.
  7. Under the **Image Text Extraction** section, mark the **Extract text from images using** OCR checkbox to include images in OCR scanning.

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
  8. Under the **File Text Extraction** section, mark the checkbox for **Extract text from compressed and archived files**. Enabling this option lets Securiti scan data from all the supported compressed file types.

> [!NOTE]
> **Note**
> 
> - Embedded file types include **PDF**, **Word** (doc, docx, docm, doct), **Excel** (xls, xlsx, xlsm), **PowerPoint** (ppt, pptx, pptm), and **Email** (EML) documents.
> - Archived and compressed files are scanned only when the **Archive** file type is included in the **Scan Conditions** and **Extract text from compressed and archived files** is enabled in the **Advanced Settings**. If the Archive file type is included in the conditions but extraction is disabled, the file is downloaded and sent to the content classifier, then skipped without being scanned. If the Archive file type is excluded from the Scan Conditions, the file is skipped by policy regardless of the extraction setting.
  9. Mark the checkbox for **File Type Classification Only** to let Securiti perform the scan purely on document file types.
  10. Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically, or you can initiate it manually from [Configuring the file cluster analysis](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files). For more information, see [Using the cluster analysis dashboard](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
  11. Mark the **Enable Data Subject Requests (DSR) Automation** on this datacheckbox to let Securiti index the scanned data elements for use when processing the DSR request. Securiti builds an index of all primary Data Element types, which includes:

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
  12. Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, then you can see this
> 
> **Breach Impact Analysis** toggle on the data system's **Permissions** tab.
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data** , you can configure another scan for the same data system instance and disable the Breach Impact Analysis from that scan.
7. In the **Sensitive data** section, apply the following settings:
  1. Choose the **Locality** enabled for your tenant. Securiti shows the Data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  2. In the **Sensitive data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(40).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(40).png)
8. (Optional) If you have enabled private Cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

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
9. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(94).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval, only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(87).png)
10. (Optional) In the **Responses** section, apply the following settings:
  1. Enable the **Send an email notification** toggle. choose what responses Securiti takes when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
  2. (Optional) In the **Responses** area, enable the **Trigger Workflow** toggle, and click **Add Workflow**.

![dsAddWorkflows.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-250c6c63-917f-b02c-766f-64d2e195c9e1(31).png)

On the **Add Trigger Workflow** popup, choose the Discovery scan Trigger. Click **Add Workflow**. ![dsTriggerWorkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c2169c-3832-611e-d139-2f9d3e03365e(31).png)

For more information, see [Discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
  3. Enable the **Register data assets into the Data Catalog** toggle to add your assets to a catalog. Mark **Add or Update all selections** option to add a new Table/topic or update all Table/topic selections or mark **Add sections if not present** to add a new topic.
    - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
    - (Optional) In the Responses area, to extract your unstructured Schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register Schema** checkbox.
    - In the **Set Environment** field, select the environment that you want this scan to be associated with such as Production.
11. Near the top right side of the page, click **Finish and Activate**.

Discovery scan takes time to complete the process depending on the data available in Data system Instance.
12. Refer to the matching procedure to view the Discovery scan results.

The live stats are refreshed and updated after periodic intervals until the scan is complete.
  1. On the **Discovery Scans** page at the specific scan job Row, choose More Actions (**three dots**) icon > **View Scan Scope**.
  2. On the Scan Scope Popup, click the scan job Row you want to view.

It expands the Scan Scope popup by showing the **Job Run Stats**.
