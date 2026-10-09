---
title: "Discovery scans for unstructured connectors"
slug: "discovery-scans-for-unstructured-connectors"
updated: 2026-09-29T09:53:42Z
published: 2026-09-29T11:19:31Z
canonical: "helpcenter.securiti.ai/discovery-scans-for-unstructured-connectors"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Discovery scans for unstructured connectors

Unstructured data systems store information in files, folders, email messages, videos, webpages, audio files, and more. Configure the discovery scans for unstructured connectors to let Securiti identify all the sensitive data elements and content profiles that exist on your data system.

> [!NOTE]
> **Note**
> 
> Securiti supports scanning files that are embedded within other documents, including up to four levels of nesting. For example, Microsoft Office files such as Word, PowerPoint, and Excel are automatically scanned along with any embedded documents they contain.

To create a discovery scan for unstructured data systems such as Amazon S3, Alfresco, and Microsoft 365 SharePoint Online, follow the steps below:

## Specifying the scan details and scope

To specify the scan details and scope:

1. From the sidebar, hover over **Sensitive Data Intelligence** and choose **Discovery Scans > Scan Definitions.**
2. Near the upper-right corner of the **Scan Definitions** page, click **+ Create Discovery Scan**, as shown below.

![Overview of scan definitions with active and completed job statuses displayed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creatediscoveryscanoption_scandefinitions.png)
3. In the **Scan Details** area, enter a name and description for the scan.

![Creating an unstructured discovery scan for Amazon S3 with job details and scope.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scandetails_creatediscoveryscan.png)
4. In the **Scope** area, choose the data system type and relevant data system instance.

![Select buckets for unstructured discovery scan with active bucket details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scopedefinitions_discoveryscans.png)

> [!NOTE]
> Note
> 
> - If you do not specify a scope, Securiti scans all available data in the system by default.
> - Securiti limits the number of records displayed for scopes. We recommend using the case-insensitive search feature to accurately find and choose the scope for your data system.

### Scope settings for data systems

Scope settings vary across the data systems. Use the following table to understand the possible scope settings based on the data system:

| Data System | Scope Settings |
| --- | --- |
| Amazon S3 | When configuring scans for your Amazon S3 data system, you can choose multiple instances to scan specific buckets of your choice. In this case, Securiti only scans the buckets you have selected, ensuring a targeted and efficient scan. ![Interface for selecting Amazon S3 buckets with details on size and accounts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectingbuckets_creatingdiscoveryscans(1).png) |
| Box | When configuring scans for your Box data system, if you do not specify a selection in the **Scope** settings, Securiti scans all groups within your Box environment. ![boxScanScope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e6b2bd0-f813-773f-da0f-3792b3e648a9.png) |
| Microsoft 365 SharePoint Online | Similarly, when configuring scans for the Microsoft 365 SharePoint Online data system, if no selection is made in **Data System Scope**, Securiti scans all available data in your SharePoint system. ![spSitesScope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-055277b7-42f9-ec0c-bbfb-9e7bf8e2d1c3.png) |
5. The **Scan Conditions** of your discovery scan let you further refine and limit your scans. Choose the required scan conditions from the following options:

![Configuration options for Amazon S3 discovery job with various scan conditions listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanconditions_discoveryscans.png)

> [!WARNING]
> **Important**
> 
> - Discovery scans can automatically detect duplicate documents existing on your data system or cloud storage.
> - Securiti first fetches metadata for all documents within the defined data system scope and then evaluates the scan conditions for each document. Only the documents that meet these conditions are downloaded and sent for content classification, ensuring efficient and targeted scanning.

**Limiting the scan scope**

When you define a discovery scan scope and choose specific item(s) from the scopes list, the scan conditions only apply to those selected items. For example, in Microsoft 365 SharePoint Online, you can choose specific sites and libraries to include or exclude in your scan scope, and scan conditions evaluate only within that defined selection.

![sharePointSitesScope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2575b99-6afe-b6ce-003c-8219617b2361.png)

**Choosing ALL in the scan scope**

When the scope is set to `ALL`, Securiti fetches all available data from the selected data system and includes it in the scan. For example, if you choose `ALL` as the scope for a SharePoint discovery scan, Securiti includes all SharePoint sites (and their respective libraries) in that scan.

> [!NOTE]
> **Tip**
> 
> To select or clear a range of items in the scan scope faster, click one item to set it as the starting point, then hold **Shift** and click another item. Every item between the two takes the state of the one you just clicked. **Shift-click** again to extend or shrink the range from the same starting point. **All** and **None** are not included in the range.
  1. Object Extension Category
  2. Object Extensions
  3. Object Name
  4. Object Prefix
  5. Object Size
  6. Object Tags

![sharePointSitesScopeALL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ac0758b-52a2-c188-b77f-589cfff63cac.png)

For more information, see [Scan Conditions in discovery scans for unstructured data systems](/latest/docs/scan-conditions-for-unstructured-data-systems).

## Configuring Advanced Settings for a scan

After specifying the scan scope, expand the **Advanced Settings** section to configure the additional settings for your unstructured data systems, as shown below:

![Advanced settings for data scanning, including options for incremental scans and document analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/advancedsettings_discoveryscans(1).png)

1. Mark the **Incremental Scan** checkbox to let Securiti scan only new files and objects in subsequent scans.
2. Under the **Sampling** section, configure the following settings:

| Option | Related Options | Description |
| --- | --- | --- |
| Unstructured Data > [!NOTE] > Note > > If you don’t mark the checkbox for Unstructured data, Securiti scans 100% of the files with a limit of 10 GB, which are part of this discovery scan scope. | Scan | Enter the percentage of unstructured files to include in the scan. Securiti uses a probability approach to select files based on the specified percentage. > [!NOTE] > Note > > Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > > > > As a result, the actual number of scanned files can vary from the configured sampling percentage. For example, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan up to | Set the maximum file size to include in the scan. Securiti scans only up to this limit per file. For example, if you set the unstructured sampling to 1MB, but a file is 3MB and contains personal or sensitive data, Securiti scans only 1MB of that file. |
| Semi-Structured Data > [!NOTE] > Note > > If you don’t enable the Semi-structured data checkbox, Securiti scans 100% of these file types with no size or record limit. | Scan | Enter the percentage of semi-structured files to include. Supported file types are as follows: - `AVRO` - `PARQUET` - `XLSX` - `CSV` - `TSV` - `ORC` > [!NOTE] > Note > > Securiti evaluates each file independently and randomly determines whether to include it in the scan based on the configured sampling percentage. > > > > As a result, the actual number of scanned files can vary from the configured sampling percentage. For example, if you configure a 20% sampling rate for 100 files, Securiti might scan 10, 17, or 25 files instead of exactly 20. |
| Scan up to | Specify the maximum number of records from semi-structured data to include. For example, if you specify a sample of 100 records in a discovery scan, Securiti shows 100 rows were detected for data elements under the discovery scan results. > [!NOTE] > Note > > There is a limit of 100,000 records. |
3. (Optional) If you have [Private Cloud Storage configured](/latest/docs/system-settings-configuring-private-cloud-storage), mark the **Collect Evidence** checkbox to collect scan results for each file in a separate evidence file. You can view and download this file from the Unstructured Data Discovery dashboard.

For more information, see [Viewing and downloading the classification evidence file](/v1/docs/using-the-unstructured-data-discovery).

> [!NOTE]
> Note
> 
> - If you have multiple Private Cloud Storage configurations, evidence files are stored in the one selected during connector configuration.
> 
> - If no detections are found during a scan, individual evidence files are not generated; however, Securiti generates that scan’s evidence. When detections are present, Securiti creates merged evidence files until it reaches the limit of 4GB. If the evidence exceeds this threshold, evidence files are not generated further to maintain performance and system stability.
> 
> This customization is especially helpful for cost-conscious teams that want to manage storage usage by limiting the volume or scope of evidence collected.

Configure the following evidence settings:

![Settings for evidence collection in a data scanning application interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/collectevidence_discoveryscans.png)

| Setting | Description |
| --- | --- |
| Evidence collected per Scan Job | Securiti generates and merges evidence files up to a cap of 4 GB. You can limit collection to a specific number based on storage capacity. > [!NOTE] > Note > > By default, it is set to unlimited per discovery scan job. |
| Evidence collected per Document | Set between 1 and 500,000 evidence per document detections. |
| Evidence collected per Data Element | Set between 1 and 100,000 evidence per data element detection. |
| Value | Mark to store the actual detected values. |
| Metadata | Mark to include metadata such as page number, sheet name, or column name where the detection was found. |
| Context | Mark to include 150 characters before and after the detected value. Supports up to 500,000 detections per scan job, 100,000 per document, and 20,000 per data element per document. |

**Example use cases**
  1. To locate specific information with a limited number of data elements, configure the Evidence collected per Scan Job setting accordingly.
  2. If you are looking for more information, for example, 100 detections per document and 10 data elements per document, Securiti generates ten evidence files per document.
4. (Optional) If you have selected **SMB** as the data system, mark the **Use SMB Server Replica For Scanning** checkbox to use the read replica server for scanning instead of the primary server.

> [!WARNING]
> Important
> 
> This option is only available for SMB connectors configured with read replica credentials. If not, Securiti displays a message prompting you to update the connector configuration before proceeding.
5. (Optional) Mark **Include document metadata in classification scope,** if you want to include file name and header information in the classification scope.
6. If you have selected **Microsoft Outlook** as the data system, mark the **Scan Attachments** and **Scan Mail Content** checkboxes to include attachments and email body content in the scan scope.

> [!WARNING]
> Important
> 
> - You must upgrade to pod versions 1.148.0 and above to use this feature.
> - Both checkboxes are marked by default on existing scans after upgrading to pod versions 1.148.0 and above.
> - At least one checkbox must be marked to run a scan. Securiti does not allow you to run a scan if both checkboxes are cleared.
> - These options are only available for the Microsoft Outlook (self-hosted) connector.
7. Under the **Image Text Extraction** section, mark the **Extract text from images using OCR** checkbox to include images in OCR scanning.

Common image types include JPG, PNG, BMP, JPEG, and so on.

> [!NOTE]
> Note
> 
> Text extraction from images using OCR is available only in environments where pods have been deployed. Securiti uses the extracted text for data classification.

Configure the following additional settings for **Extract text from images using OCR**:

![Settings for image text extraction using OCR, including megapixels and aspect ratio recommendations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/imagetextextraction_discoveryscans.png)

> [!WARNING]
> Important
> 
> For data systems configured using EPod V2, OCR processes up to 20 images per file by default. To change this limit, contact your Customer Success Manager or Account Representative.

| Setting | Description |
| --- | --- |
| Min/Max megapixels | Set between 0.1 and 50. Securiti skips images outside this range. Default minimum is 0.01 and maximum is 8. |
| Min/Max aspect ratio | Set between 0.2 and 10. Securiti skips images that are too narrow or too wide. Default minimum is 0.2 and maximum is 5. > [!NOTE] > Note > > - For a better understanding of image dimensions and aspect ratios, see the following: > - [Common aspect ratio for images and videos](https://marketing.istockphoto.com/blog/aspect-ratio/) > - [A guide to common aspect ratio and image sizes](https://www.shutterstock.com/blog/common-aspect-ratios-photo-image-sizes) > - To use OCR settings for efficient scanning performance, see [Use case examples of text extraction from images](/v1/docs/use-case-examples-for-ocr-scanning-of-images). |
| Number of PDF pages | Set between 1 and 100. Specifies the number of PDF pages the OCR engine scans. |
8. Under the **File Text Extraction** section, mark the **Extract text from compressed and archived files** checkbox to scan data from supported compressed file types.

Embedded file types include the following:

| File Type | Format |
| --- | --- |
| PDF | - `pdf` |
| Word | - `doc` - `docx` - `docm` - `doct` |
| Excel | - `xls` - `xlsx` - `xlsm` |
| PowerPoint | - `ppt` - `pptx` - `pptm` |
| Email documents | - `EML` |
9. Mark the **File Type Classification Only** checkbox to perform the scan purely on document file types.
10. Mark the **Enable Similar Document Cluster Analysis** checkbox to let Securiti create clusters for duplicate and near-duplicate documents. When enabled, Securiti runs cluster analysis automatically within 24 hours. You can also start it manually. For more information, see [Using the cluster analysis dashboard](/v1/docs/using-the-cluster-analysis-dashboard).

> [!NOTE]
> Note
> 
> - Mark the **Enable Similar Document Cluster Analysis** checkbox to let Securiti identify and display:
>   - Near-duplicate files on the **Unstructured Data Scans** dashboard.
>   - Duplicate and near-duplicate clusters on the **File Cluster Analysis** dashboard.
> - Duplicate files on the **Unstructured Data Scans** dashboard are detected independently for every discovery scan and do not require this option to be enabled.
> - The discovery scan job scans only the first 3000 characters in document clustering to detect duplicate documents.
> - This option is not available for connectors with Hyperdrive mode enabled. For more information, see [Hyperdrive overview](/latest/docs/hyperdrive-overview).
11. Mark the **Enable Data Subject Requests (DSR) Automation** checkbox to let Securiti index the scanned data elements for DSR processing. Securiti builds an index of all primary Data element types, which includes:
  - Username
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
12. Mark the **Breach Impact Analysis** checkbox to integrate the scan with the data breach module. This option appears only if an existing breach is detected for that connector. Enable this option to let Securiti analyze the breach impact.

> [!NOTE]
> **Note**
> 
> - This option is available for all unstructured data system connectors. If a connector does not support the discovery scan, you can find the **Breach Impact Analysis** toggle on the data system's **Permissions** tab."
> - To enable the **Enable Data Subject Requests (DSR) Automation on this Data**, you can configure another scan for the same data system instance and disable the **Breach Impact Analysis** from that scan.

## Specifying sensitive data specifications

To specify the sensitive data specifications for a scan, follow the steps below:

1. In the **Sensitive Data** section, choose the locality enabled for your tenant.

Select **All** if you want to scan for sensitive data across all the localities.
2. Choose the specific types of data to scan. Click a category to open it and choose a specific data element, document type, content profile, and exact data profile, as shown below.

![Selection options for sensitive data categories in a document management system interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sensitivedataoptions_discoveryscans.png)

> [!NOTE]
> **Note**
> 
> If you have enabled the data subject requests automation on the data, some of the data elements are disabled for customization. You can see the message ‘Personally Identifiable Data Element that helps with DSR automation’ when you hover over those data elements.

## Configuring the scan schedule

After all the scan configurations are complete, you can schedule and specify responses for a scan. In the **Schedule** section, choose either **Run Manually** or **Run on periodic schedules**, as shown below.

![Settings for scheduling scans, including manual and periodic options with time exclusions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/discoveryscanschedule_scandefinitions.png)

Use the following table to understand the options:

| Scan Option | Specifications |
| --- | --- |
| **Run manually, admin needs to start a job for this policy** | Activate and deactivate the scans manually at any time and start or cancel the scan at any time you want. |
| Run on periodic schedule | The scheduled time starts and ends according to your local time or the time set in your device settings. Set the specific time for your scan, choose Daily, Weekly, or Monthly from the **Periodic Schedule Frequency**, and specify any time of the day, week, or month. You can also set the scan exclusion start and end time to pause your scan jobs for that particular interval, only when you do not want to run them at specific intervals. The minimum pause interval that you can specify is one hour. > [!NOTE] > Note > > - If you schedule a scan and choose a start time that has been passed, the scan starts a few minutes right after you hit **Finish and Activate**. > - Securiti skips any scheduled scans if a previously scheduled scan is still in progress. > - If you schedule a scan for any specific time, and due to some reason, it cannot start, Securiti continues to retry every ten minutes until the scan gets started. If a scan job runs for more than a day (for larger scans), and you set one hour as a pause interval, then the same pause interval of one hour will be followed every day. ![exclude_scan_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fdb1871-3b9d-9ff4-b314-dd74eb8f8db9.png) **Custom Cron** For custom cron jobs, use the [expression builder](https://crontab.guru/). It has the minute, hour, day of the week, and day of the month settings. When you are done, use that expression in the Enter Cron field. ![cronjob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc9b8076-799b-9c0f-c533-8c0a42fe28c8.png) You can also exclude the times when you don't want the scan to run and specify multiple times weekly or monthly. Choose the hour block(s) in the 24x7 matrix where scanning should be executed. The scan is automatically paused at the beginning of each execution block and resumed at the end. ![exclude_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bfe17ec-ae09-821a-76a3-fca2d7d68e46.png) > [!NOTE] > **Note** > > Securiti does not allow scans to start immediately after being timed out or errored due to performing some back-end checks or taking remediate actions. It can take up to an hour for the scan job to start automatically without any customer interaction. > > The **Scan Now** option remains disabled for an hour until the system recovers. |

## Specify responses for a scan

You can configure the **Responses** section to choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template, as shown below.

![Email notification settings with options for user selection and workflow registration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sendanemailoption_discoveryscans.png)

1. (Optional) In the **Responses** section, trigger a discovery scan workflow. To do this, configure a [discovery scan trigger node](/v1/docs/trigger-nodes-discovery-scan).
2. (Optional) In the **Responses** area, scroll down to the **Register data assets into the Data Catalog** section. Mark **Add or Update all selections** option to add a new table/topic or update all table/topic selections or mark **Add sections if not present** to add a new topic.
  - From the **Default Governance Status** menu, choose the appropriate status for the metadata being ingested.

You can choose one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
  - (Optional) In the **Responses** area, to extract your unstructured schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register schema** checkbox.
  - Mark the **Always Execute Response** checkbox to ingest the datasets to the Enterprise Data Catalog regardless of whether it has already been registered. This feature lets you stay on top of dynamic data changes, ensuring your catalog remains accurate and reliable.
3. To set the environment, configure the following:
  - From the **Set Environment** menu, choose the suitable environment.

This selection lets you choose environments for the objects to be registered in the Enterprise Data Catalog. With this capability, you can easily distinguish and manage metadata across various environments, such as Production or QA.

Below is a list of available environment variables, along with their descriptions to help you make the best selection:

| Value | Description |
| --- | --- |
| PROD | Designates production fabrics. |
| PROD-Hidden | Designates hidden production fabrics. Maintains original production behavior, displaying PROD metadata in the URN but hiding the environment in breadcrumbs. |
| DEV | Designates development fabrics. |
| TEST | Designates testing fabrics. |
| QA | Designates quality assurance fabrics. |
| UAT | Designates user acceptance testing fabrics. |
| EI | Designates early integration fabrics. |
| PRE | Designates pre-production fabrics. |
| STG | Designates staging fabrics. |
| NON_PROD | Designates non-production fabrics. |
| CORP | Designates corporation fabrics. |

## Saving and activating the scan

After completing all the scan configurations, you save and activate the scan, as shown below.

![Creating an unstructured discovery scan for Amazon S3 with job details and options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/discoveryscansaveoptions_scandefinitions.png)

Use the following table to understand the available options:

| Option | Description |
| --- | --- |
| Finish and Activate | Saves and activates the scan immediately |
| Save | Saves the configuration without activating |
| Save as Draft | Saves as a draft for later completion. |

For more information, see [Viewing discovery scan results for unstructured data systems](/v1/docs/viewing-discovery-scan-results).

An unstructured data systems refers to the systems that are used to store unstructured data. The most common examples of unstructured data include Microsoft OneDrive, Google Drive, AWS S3, and so on.
