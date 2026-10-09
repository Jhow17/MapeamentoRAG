---
title: "Configure discovery scans in Microsoft 365 SharePoint Online"
slug: "configure-discovery-scans-in-microsoft-365-sharepoint-online"
status: "update"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-microsoft-365-sharepoint-online"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Microsoft 365 SharePoint Online

This article describes creating a discovery scan for Microsoft 365 SharePoint Online. For more information, see [Understanding discovery scans](/v1/docs/discovery-scans).

> [!NOTE]
> **Note**
> 
> - Discovery scan for SharePoint Online retrieves sensitivity labels that you apply to files within your Microsoft 365 environment. You can view the retrieved sensitivity labels in the [Graph Explorer](/latest/docs/using-graph-explorer).
> - You can also retrieve sensitivity labels for SharePoint Online using [data inventory sync](/latest/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted).
> 
> To learn more about sensitivity labels extraction, see [Microsoft Information Protection (MIP) label extraction for data systems](/latest/docs/microsoft-information-protection-mip-label-extraction-for-data-systems).

To configure a discovery scan in Microsoft 365 SharePoint Online, perform the following steps:

> [!WARNING]
> **Important**
> 
> - You can't run a discovery scan from the Permissions tab in your activated data system connector if the Data Inventory and Entitlement Sync Scope section is empty.
> - We recommend you do not retry running scans in case of "access denied errors" such as that for an inaccessible SharePoint site or library.

On the **Create Discovery Scan** page under the **Scan Details** section, enter a convenient name and description for the scan job.

In the **Scope** section, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Microsoft 365 SharePoint Online**. |
| Select Data Systems | Choose the specific data system instances to scan. |

In the **Data System Scope** section for your selected **Data System**, configure the following settings:

In the **SharePoint Site Collection / Site** section, choose one of the following methods to specify the SharePoint sites to include in the scan. To help you decide which method fits your use case, refer to the table below before configuring your scan scope.

1. The **Scan Conditions** of your discovery scan let you further refine and limit your scans, regardless of whether you have specified a **Data System Scope** or not. Securiti uses them to validate the data being processed. **Scan Conditions** and **Advanced Settings** work together to define the scan scope, as you can choose scan conditions to include or exclude different options such as file extension, size, and so on.

> [!WARNING]
> **Important**
> 
> Discovery scans can automatically detect duplicate documents existing on your data system or cloud storage.

> [!NOTE]
> **Note**
> 
> - **Scoped Scans**: Data fetching is restricted to the defined scope (e.g., selected groups). In this case, the **Scan Conditions** apply only to the data within the specified scope.
> - **Unscoped Scans**: All available data is fetched first, and then the Scan Condi tions are applied to validate or limit that data.

To use the relevant options appropriately, use the following table:

| Scan Condition | Description |
| --- | --- |
| File Extension Category | Securiti lets you include or exclude files or objects during scanning, enhancing overall scan performance. You can add or remove exclusions based on your specific requirements. To include or exclude a **File Extension Category** in your scan, choose one of the options from the categories listed below. **File Extension Categories** - **Archive** If you want to exclude all types of compressed files from scanning, choose the **Archive** option. ![scanConditionsArchive.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-33d1e326-bbbb-2988-7f75-261794108ecb(1).png) - **Configuration** - **Binary** - **Audio** - **Video** - **Source Code** - **Temporary Files** and so on > [!NOTE] > Note > > You can add multiple options based on your specific requirements. |
| Folder Path | Securiti lets you choose from the available options to include or exclude the necessary folder(s) based on your scanning requirements. ![folderPathUntructuredOptions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ec6d8d7-5f42-a80e-314f-a667eb968fb2(1).png) Select a relevant option to include or exclude files from a specific folder, ensuring Securiti scans only the files within that folder. - **match prefix** (is Condition): Includes files that start with the specified prefix. Securiti evaluates each document to check if it meets the customer-defined criteria before downloading its content. - **does not match prefix** (is not Condition): Excludes files that start with the specified prefix. > [!NOTE] > **Note** > > These options match the beginning of the folder path, unlike regex, which can match anywhere in the path. **Example for matching prefix** **Assume the following folder structure**: 1. Projects/2024/Reports 2. Projects/2023/Reports 3. Archives/2024/Reports 4. Projects/2024/Logs 5. Archives/2023/Logs **Using the prefix match such as "Projects/"** - The match includes options 1, 2, and 4 because they start with Projects/. - The match excludes options 3 and 5 because they start with Archives/. Similarly, using "Projects/" with does not match prefix excludes options 1, 2, and 4 while including options 3 and 5. This method is useful for scanning or excluding entire folder structures based on their starting path. - **match regex**: Includes files that match the exact prefix based on the provided regex pattern. - **does not match regex**: Excludes files that match the exact prefix based on the provided regex pattern. Choosing the match regex option lets Securiti include files that match based on the provided regex pattern. **Example for matching regex** **Assume the following folder structure**: 1. Projects/2024/Reports 2. Projects/2023/Reports 3. Archives/2024/Reports 4. Projects/2024/Logs 5. Archives/2023/Logs Using the regex .*2024/Reports.*, the match will include options 1 and 3 but excludes 2, 4, and 5. This logic follows the same behavior as the prefix match / does not match prefix functionality but allows for more flexible pattern matching with regex. |
| Object Tags | Securiti lets you specify object tags that are relevant to your requirements to refine the selection and classification of objects during scanning. You can enter the tags in **key: value** format as shown below: ![dsObjectTags.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6910645b-d345-4ee6-5694-de7557bfd463(1).png) |
| File Name | Securiti lets you specify a file or object name using a regex pattern to match desired files or objects for inclusion or exclusion in the scan. ![dsObjectName.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-154c5cfa-ff6a-dcd8-acdd-306572d7a764(1).png) Choosing the **contains** option lets Securiti include the files and objects based on the specified regex pattern Choosing the **does not contain** option lets Securiti exclude the files and objects based on the specified regex pattern |
| File Extensions | If the file extension is in common video formats (see image), then such files are not downloaded and are not shown in the Unstructured Data Explorer. Securiti lets you choose the relevant option if you want to include or exclude the **File Extension** or **Object Extension** in your scan, such as: - docx - xlsx - con - conf - con - tmp and so on If you want to exclude compressed files (zip, gzip, lzip, and so on) from scanning, choose these options. ![scanConditionExtentions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2a3d713-ed76-95eb-5fd4-656461bbcb0e(1).png) If a file does not fall into the above three categories (zip, gzip, lzip, and so on), it is downloaded and passed on for classification, where it is again classified based on its content. Hence, some of the VOB files or .AAX files were classified as they were below 10GB in size and not part of video file extensions, as shown below: ![video_formats.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0306a29b-b6ad-80fd-eadb-6050d770881d(16).png) |
| Object Size | Securiti lets you specify the file size to include or exclude files in or from the scan, ensuring that only files within the defined size range are processed. ![dsObjectSize.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fefc74d-c83d-8091-df4d-c8ecf9019e50(1).png) - If the file size is 0 bytes, the file is not downloaded irrespective of extension, but does show in the Unstructured Data Explorer as part of the skip policy. - If the file size is 10GB, the file is not downloaded irrespective of extension, but does show in the Unstructured Data Explorer as part of the skip policy. - If the file extension is in common video formats, then such files are not downloaded and are not shown in the Unstructured Data Explorer. |
| File Owner | Securiti lets you include or exclude documents scanning based on the file owner. Provide the file owner's email in the form of a regex pattern. ![discoveryScanFileOwnerSP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae8e9b85-b23d-477f-00e0-be6d291b2d47.png) > [!NOTE] > **Note** > > If file doesn't contain owner's email, Securiti scans such files because scan condition doesn't apply in case of missing owner email. |
| Date Created | Securiti lets you specify the creation date before or after a selected date to include or exclude files based on their creation timestamp. ![dsScanConditionDateCreatedBeforeAfter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97950b5c-de5f-f861-af59-e794022e69bf(1).png) |
| Last Modified | Securiti lets you specify the last modified date before or after a selected date to include or exclude files and objects based on their modification timestamp. ![dsBeforeAfterLastModifiedDate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12ee281d-ac65-6e0b-da58-b98f7d67649f(1).png) |

In the **Advanced Settings** section, use the following settings for your unstructured data systems. The settings available vary by data system type.
  1. | Method | Use Case |
| --- | --- |
| Selecting SharePoint Sites | Ideal for smaller site lists or quick, ad hoc scans. To include or exclude specific sites in the scan choose the applicable sites. To scan all sites in the tenant, select “All”. You can select or exclude sites directly in the UI without additional preparation. Use this option for smaller site lists or quick scans. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-23 at 9.44.02 AM.png) |
| Uploading a CSV file | To scan up to 10,000 SharePoint sites, upload a CSV file that lists the sites to include or exclude. Use the provided sample format or a CSV file exported. For more information, see [Fetching multiple SharePoint Site IDs](/latest/docs/fetching-multiple-sharepoint-site-ids). Use this option when scanning a large or existing list of sites that requires precise control over the scan scope. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-23 at 9.44.31 AM.png) |

> [!CAUTION]
> Warning
> 
> Securiti does not scan sites configured as the quarantine destination. If the SharePoint Online site specified in the Quarantine Site URL field is also included in the scan scope, it is automatically skipped during the scanning process. To scan files in that site, remove the site URL from the Quarantine Site URL field during the connector configuration.

****Method 1****: Selecting SharePoint Sites****

In the **SharePoint Site Collection / Site** section, click **Select sites** in the **Inclusion** tab to select the scan specific sites to be included or run a tenant-wide scan by selecting “All”. To exclude any specific sites from the scan, you can specify the sites in the **Exclusion** tab.

****Method 2 Uploading a CSV file****

    - In the **SharePoint Site Collection / Site** section, click **Upload CSV** in the **Inclusion** tab add the increased scope of SharePoint sites, you can select up to 10,000 SharePoint sites for scanning through a CSV file. Once you upload the CSV file, you can see the sites selected with the count. To exclude any specific sites from the scan, you can upload the CSV of sites in the **Exclusion** tab.

To learn how to fetch multiple SharePoint site IDs, see [Fetch multiple SharePoint Site IDs](/v1/docs/fetching-multiple-sharepoint-site-ids).
    - To see the CSV file format supported by Securiti, click **View Sample**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-23 at 9.44.59 AM.png)
    - A sample CSV file that includes the SharePoint site ID is downloaded to your system’s **Downloads** folder. You can create your CSV files using the sample that you have downloaded.

> [!NOTE]
> Note
> 
> Each site follows the following format in the single column CSV. Each site contains three elements separated by commas.
> 
> hostname, site Globally Unique Identifier, web Globally Unique Identifier
> 
> See the examples below.
> 
> `example.sharepoint.com, 111aa11a-2ab2-3c3c-4d4d-555501a55555, 66bbb666-7ba7-8a1b-92aa-000000000000`

Once you have selected the sites, you will see the list as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-23 at 9.46.43 AM.png)

In the **Select Library** section, under **Inclusion** tab, choose a library name for that site. For example, **Documents** or **All** to include in the scan, as shown below. You can use the **Exclusion** tab to exclude the library from the scan.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-23 at 9.48.23 AM.png)

In the **Select Folder Path** section, under the **Inclusion** tab, enter the folder path for the SharePoint library. It will be set to all by default, as shown below. You can use the **Exclusion** tab to exclude any folder from the scan.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-23 at 9.51.21 AM.png)

> [!NOTE]
> Tip
> 
> To get the Folder path, follow the steps below:
> 
> 1. In the SharePoint directory, select the folder of your choice to scope your scan to
> 
> ![library_name_and_folder.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7cdedca3-bef9-3d80-93fa-d738dc15c284.png)
> 2. From the right panel, click **More details** and record its folder path that would look similar to the example below.
> 
> ![more_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-beeefe4e-07f4-2df8-e535-0c3fe15163ec.png)
> 3. The **Path** would be copied in the following format:
> 
> `&lt;https://datasubjectrequest.sharepoint.com/sites/Secriti-test/Shared%20Documents/General/General%202&gt;`
> 4. Copy the section after the library name, which is `/General/General%202`
> 5. Remove the **%20** and add a space instead.
> 6. Prepend **root:/** to the above. The final path becomes `root:/General/General 2`
  1. Mark the checkbox for **Incremental Scan** to let Securiti scan only the new files and objects in the next scan and skip them in the subsequent scan.

In case of SharePoint Online, incremental scan includes only new or modified files in SharePoint sites.

> [!NOTE]
> **Note**
> 
> A 410 resyncRequired error occurs when too many changes in a drive’s files or documents cause SharePoint to revoke the delta token. When this happens, incremental sync cannot continue, and our system automatically triggers a full scan for the affected drive.
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
  3. Mark the **Get MIP Labels Information** checkbox if you want to decrypt and scan your SharePoint Online files protected by Microsoft Purview sensitivity labels. To learn more about creating sensitivity labels for applying encryption, see [Microsoft documentation.](https://learn.microsoft.com/en-us/purview/encryption-sensitivity-labels)

> [!NOTE]
> Note
> 
> - Enabling this option increases discovery scan time because the scanner must retrieve, decrypt, and process each protected file before analysis. Expect longer scan durations compared with scans of unencrypted content.
> - Securiti evaluates the file size condition before decrypting files with encrypted labels. Although encrypted files are usually compressed, their size might increase during decryption.
    - **Prerequisites for scanning MPIP-encrypted files:**
      - You must activate the Microsoft Purview Information Protection (Cloud) connector in the same Securiti tenant. For more information, see [Activate the Microsoft Purview Information Protection connector](/v1/docs/activate-the-microsoft-purview-information-protection-connector-in-securiti).

> [!CAUTION]
> Warning
> 
> If the MIP connector is activated in a different tenant, scanning doesn't include files with encryption labels.
      - You must upgrade your pod version to release 1.138 or higher.
  4. Mark the checkbox for **Include System Libraries** to scan the system-managed libraries in your SharePoint sites. These include Style Library, Master Page Gallery, and Form Templates. Unmark the checkbox to skip these libraries and scan only the business libraries.

> [!NOTE]
> Note
> 
> - To use this feature, you must upgrade to pod version 1.151.0 or later.
> - Marking Include System Libraries checkbox may increase scan volume and processing time
> - Securiti clears this checkbox by default, so a new Discovery Scans skip the system-managed libraries.
  5. Under the **Image Text Extraction** section, mark the **Extract text from images using** OCR checkbox to include images in OCR scanning.

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
  6. Under the **File Text Extraction** section, mark the checkbox for **Extract text from compressed and archived files**. Enabling this option lets Securiti scan data from all the supported compressed file types.

> [!NOTE]
> **Note**
> 
> - Embedded file types include **PDF**, **Word** (doc, docx, docm, doct), **Excel** (xls, xlsx, xlsm), **PowerPoint** (ppt, pptx, pptm), and **Email** (EML) documents.
> - Archived and compressed files are scanned only when the **Archive** file type is included in the **Scan Conditions** and **Extract text from compressed and archived files** is enabled in the **Advanced Settings**. If the Archive file type is included in the conditions but extraction is disabled, the file is downloaded and sent to the content classifier, then skipped without being scanned. If the Archive file type is excluded from the Scan Conditions, the file is skipped by policy regardless of the extraction setting.
  7. Mark the checkbox for **Enable Similar Document Cluster Analysis** to let Securiti create clusters for similar documents that you can see on the **File Cluster Analysis** dashboard.

This option enables the identification of exactly similar or nearly similar documents in clusters. When you enable this option, Securiti takes up to 24 hours for cluster analysis to run automatically, or you can initiate it manually from [Configuring the file cluster analysis](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files). For more information, see [Using the cluster analysis dashboard](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data#detect-duplicate-files).

> [!NOTE]
> **Note**
> 
> The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
  8. Mark the **Enable Data Subject Requests (DSR) Automation** on this datacheckbox to let Securiti index the scanned data elements for use when processing the DSR request. Securiti builds an index of all primary Data Element types, which includes:

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
  9. Mark the checkbox for the **Breach Impact Analysis** integrate it with the data breach module. This option shows only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, then you can see this
> 
> **Breach Impact Analysis** toggle on the data system's **Permissions** tab.
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data** , you can configure another scan for the same data system instance and disable the Breach Impact Analysis from that scan.
2. In the **Sensitive Data** section, choose the locality enabled for your tenant. Securiti shows the data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  1. Choose the **Locality** enabled for your tenant. Securiti shows the data element categories, content profiles, and exact data profiles available only for that locality for exact matching.
  2. In the **Sensitive Data** section, choose the specific types of data to scan for. Click a category to open it and select specific elements or document types as shown below.

![sensitive_data_unstructured.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4598628-9af1-a4d7-0b49-a7b2cbc2be4a(25).png)

![sensitive_data_unstructured2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-347926fd-5e5a-7344-7820-1b76e45e354e(25).png)

> [!NOTE]
> **Note**
> 
> If you have enabled the data subject requests automation on the data, some of the data elements are disabled for customization. You can see the message ‘Personally Identifiable Data Element that helps with DSR automation’ when you hover over those data elements.
3. (Optional) If you have enabled private cloud storage, use the **Collect Evidence** toggle to configure results to be saved to an evidence file.

Doing so lets you view evidence as described in Viewing evidence for specific documents.

Securiti still captures the actual scan results even if you deselect the **Context** checkbox.

**Example Use Cases**:
  - To save your detections to a file, mark the **Save detections from scan results into a file** checkbox.
  - To detect metadata such as location and type, mark the **Metadata such as Location, Type** checkbox.
  - Enable the **Context** checkbox. Specify the number of detections that this scan can store after performing the discovery scan. You have the option to set the default limit and higher context limit:

| Default - 20 characters before and after value | Choose this option for the below detection outcomes as default: - Total detections per scan job (up to 2.5 million) - Total detections per document (up to 500,000) - Detections per data element type in each document (up to 100,000) |
| --- | --- |
| Higher - 150 characters before and after value | Choose this option for the below detection outcomes for a higher content collection around detections: - Total detections per scan job (up to 500,000) - Total detections per document (up to 100,000) - Detections per data element type in each document (up to 20,000) |
  1. If you are looking for a piece of specific information with a small number of data elements, you can set the detections per scan job as described above.
  2. If you are looking for more information for example 100 detections per document and 10 data elements per document, Securiti gives 10 evidences per document - as you have specified 10 data elements detection per document in the discovery scan job.
4. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below:

![schedules_manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c071aba-bf1e-b365-c856-0897717fad35(66).png)
  - **Running manual scans**

You can activate and deactivate the scans manually at any time and you can also start and cancel the scan any time you want.
  - **Running scans on a periodic basis**

The scheduled time starts and ends as per your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval only when you do not want to run it at specific intervals. The minimum pause interval that you can specify is one hour.

If a scan job runs for more than a day (e.g. for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour is followed every day.

![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9(60).png)
5. (Optional) In the **Responses** section, apply the following settings:
  1. Enable the **Send an email notification** toggle. choose what responses Securiti takes when the scan completes. You can specify one or more **Emails** with a relevant **Email notification template**.
  2. Enable the **Trigger Workflow** toggle to specify a specified workflow. Then, click **Add Workflows**. To do this configure a [Discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
6. (Optional) In the Responses area, scroll down to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** option to add a new table/topic or update all table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - (Optional) In the Responses area, to extract your unstructured schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register schema** checkbox.
7. Near the top right side of the page, click **Finish and Activate**.

Discovery scan takes time to complete the process, depending on the data available in the data system instance.
8. Refer to the matching procedure to view the discovery scan results.

> [!NOTE]
> **Note**
> 
> You can see the document metadata **O365** and **Top-Level Directory** info under the **Documents** grid as shown below:
> 
> ![Document details including O365 ID and scan information for SharePoint file.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Configuring discovery scans - 1.png)

The live stats are refreshed and updated after periodic intervals until the scan is complete. To view discovery scan results, see [Viewing discovery scan results](/v1/docs/viewing-discovery-scan-results-en).

> [!NOTE]
> **Note**
> 
> Securiti manages displays owners' field for SharePoint Online files displayed in **Data Command Graph** and **Unstructured Data Discovery** results by following a structured fallback logic, especially when email addresses or display names are missing or incomplete.
> 
> - If the user creates a file:
>   - Securiti first uses the user’s email address.
>   - If the email is not available, it falls back to the user’s display name.
> - If the system generates a file:
>   - Securiti displays the application’s display name, since application-created files typically don't have an associated email.
> - If neither user nor application-generated details are available:
>   - Securiti uses information from the drive owner:
>   - First, it uses the drive owner’s email address.
>   - If that is not available, it falls back to the drive owner’s display name.
  1. On the **Discovery Scans** page at the specific scan job row, choose the More Actions (**three dots**) icon > **View Scan Scope**.
  2. On the **Scan Scope** Popup, click the scan job row you want to view.

It expands the **Scan Scope** popup by showing the **Job Run Stats**.

![SP-Scan-result.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da879457-4eef-e7d8-f0ff-e690adf35e52.png)

****Resolve the Redis memory issue due to Job Scan Stats storage****

The Discovery Scan process within the Sensitive Data Intelligence module leverages **Redis memory** to manage and store scan statistics. These statistics are displayed on the Discovery Scans page to provide insights into scan activities and results. This feature helps optimize performance and enables real-time visibility into scan progress and outcomes.

If you prefer not to use Redis memory for storing scan statistics, this feature can be disabled. To do so, contact the Securiti support team at [support@securiti.ai](mailto:support@securiti.ai).
