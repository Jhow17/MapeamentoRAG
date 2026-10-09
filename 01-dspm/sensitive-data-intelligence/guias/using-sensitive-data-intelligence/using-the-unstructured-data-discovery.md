---
title: "Using the Unstructured Data Scans dashboard"
slug: "using-the-unstructured-data-discovery"
status: "update"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/using-the-unstructured-data-discovery"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using the Unstructured Data Scans dashboard

## Overview

The Unstructured Data Scans dashboard provides a scan-by-scan view of classification results for your unstructured data systems. It lets you analyze scan results from your discovery scan, understand where sensitive data resides, and assess its volume, type, and distribution across your data systems and locations.

The dashboard includes the following components:

- Total number of files that were scanned, skipped, or errored.
- Total data volume that was scanned, skipped, or errored.
- Total number of data elements discovered, data element types detected, and unique data elements identified.
- Tree Map chart showing data distribution across the following dimensions:
  - Content Profiles
  - Data Element Types
  - Data Systems
  - File Categories
  - File Types
  - File Formats
  - Resource Paths
- Sankey chart showing the distribution of classified files across the following dimensions:
  - Locations
  - Data Systems
  - File Types
  - File Formats
- A list of files identified after running discovery scan or connector scan, including:
  - File types
  - File formats
  - Content profiles
  - Data elements
  - Data element types
  - Data system locations
- A geographic (world map) view showing the global distribution of unstructured data.
- Tables displaying aggregated statistics grouped by the following dimensions:
  - Content profiles
  - File formats
  - Data systems
  - Data element types
  - Exact data profiles

To open the Unstructured Data Scans dashboard, from the left panel, choose **Sensitive Data Intelligence** > **Unstructured Data Scans**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-29 at 12.57.03 PM(1).png)

### Using the Unstructured Data Scans dashboard

1. On the Unstructured Data Scans dashboard, near the upper left corner, click the **Scan** menu to select any discovery scan or a connector scan, as shown below.

![Overview of unstructured data scans with highlighted Google Drive automation options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectingdiscoveryscan_unstructureddatascans.png)

> [!NOTE]
> Note
> 
> - By default, the dashboard displays data from the most recently run discovery or connector scan selected in the scan dropdown.
> - If no scans have been run for the tenant, the dashboard appears empty and provides a button to redirect you to the discovery scan page to initiate a scan.

1. Use the top Filter to narrow down the scope of a discovery scan or a connector scan by the following properties:

| Properties | Description |
| --- | --- |
| Data System Type | Displays the type of data system where the file resides. For example, `Confluence Cloud`. |
| Data Systems | Displays the name of the data system instance associated with the resource. For example, `Finance-Drive`. |
| Data System Location | Displays the geographical or logical location of the data system. For example, `United Stated of America`. |
| Data System Owner | Displays the owner or administrator of the data system. For example, `John`. |
| File Name | Displays the name of the file discovered during the scan. For example, `medical-records.docx`. |
| File Owner | Displays the name of the owner of the file. For example, `System`. |
| Resource Path | Displays the full path of the resource within the data system. For example, `/finance/payroll/2026/`. |
| File Size | Displays the size of the file, in bytes. For example, `5.2MiB`. |
| File Cluster Name | Displays the cluster or logical grouping associated with the file. For example, `Finance Cluster`. |
| File Scope | Displays the scope or accessibility level of the file. For example, `Files with sensitive information`. |
| Data Element Category | Displays the category of data elements detected in the file. For example, `Government Identifiers`. |
| Data Element Types | Displays the types of data elements identified. For example, `Email Address`. |
| Content Profiles | Displays the content profiling results derived from file analysis. For example, `AU PA Unstructured`. |
| File Type Category | Displays the high-level classification of the file type. For example, `Legal`. |
| File Type | Displays the specific file type detected. For example, `Invoice`. |
| File Format | Displays the format of the file. For example, `PDF`. |
| Exact Data Profiles | Displays the exact data profiles matched during content inspection. For example, `Credit Card Number(Exact Match).`. |
| Files with Evidence | Indicates whether evidence files are available for detected data elements. |
| Skip Reason | Displays the reason why a file was skipped during scanning, if applicable. For example, `Unsupported File Type`. |
| Discovery Scan Job ID | Displays the unique identifier of the scan job that processed the file. For example, `scan-7890-abcd-4567`. |
| File Created Time | Displays the timestamp when the file was created. For example, `May 02 2024, 09:45 am`. |
| File Modified Time | Displays the timestamp when the file was last modified. For example, `Jun 01 2024, 03:10 pm`. |
| First Scan Time | Displays the timestamp when the file was scanned for the first time. For example, `Jun 05 2024, 11:20 am`. |
| Last Scan Time | Displays the timestamp when the file was most recently scanned. For example, `Jun 11 2024, 07:20 pm`. |

![Overview of unstructured data scans with highlighted Google Drive automation options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectingdiscoveryscan_unstructureddatascans(1).png)

> [!NOTE]
> **Note**
> 
> - You can use case-insensitive keywords to search for the **File Owners** from the quick filters.
> - For a filter property, the values in the filters list are limited to a maximum of 1000, and only the top 1000 values associated with the most files appear in the list. These values are dynamically updated based on the currently applied filters.

1. To save the custom filter(s) applied, click on **three dots (option) > Save View**, as shown below.

![Overview of unstructured data scans with statistics and content profiles displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveview_unstructuredatascans.png)
  1. You can save the custom filter under an existing group or in a new group. When you click **Save View**, you can see a popup to add a group, followed by adding its name, and then click **Save View**, as shown below.

![Overview of unstructured data scans with file statistics and save view options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveviewfields_unstructuredatascans.png)
  2. To view already saved filters, click on **three dots (option) > Saved Views**, as shown below.

![Overview of unstructured data scans with statistics and content profiles displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/savedview_unstructuredatascans.png)

You can also **View,** **Edit** and **Delete** your **Saved Views**, as shown below.

![User interface displaying saved views with options to view, edit, or delete items.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/savedviewoptions_unstructuredatascans.png)
  3. To clear your applied filters, click **Clear Search**, as shown below.

![Overview of unstructured data scans with detailed statistics and content profiles displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clearsearch_unstructuredatascans.png)

### Understanding the dashboard

The Unstructured Data Scans dashboard displays different tiles and widgets to display discovery scan results. Use sections below to understand what each tile and widget represents in the dashboard.

#### Dashboard Tiles

At the top of the dashboard, rows of tiles provide a quick overview of key metrics for the selected Unstructured Data Scan.

| Tiles | Description |
| --- | --- |
| Files | Displays the total number of scanned, skipped, and errored files across the data system(s) scanned by the selected unstructured data scan. |
| Volume | Displays the total data volume scanned, skipped, and errored across the data system(s) scanned by the selected unstructured data scan. |
| Data Elements | Displays the total number of data elements discovered, the number of data element types detected, and the number of unique data elements identified across the data system(s) scanned by the selected unstructured data scan. For large data element counts, values are displayed using standard SI units: - Symbols for millions, billions, and trillions are shown in lowercase (m, b, t), respectively - Symbols for larger units such as peta, exa, and zetta are shown in UPPERCASE (P, E, Z), respectively. |

![Overview of unstructured data scans showing scanned files, volume, and data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filestats_unstructuredatascans.png)

> [!NOTE]
> **Note**
> 
> - Securiti shows these counts based on scans, not data systems. When the same scan is run multiple times, the counts are incremented as resource size increases. Skip reasons based on discovery scan conditions or system rules are also reflected. When you apply quick filters, the counts update automatically.
> - If only one row of tiles is visible, click **Expand** below the tiles to view the second row.
> 
> ![Overview of unstructured data scans showing scanned files and content profiles statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/expandfilestats_unstructuredatascans.png)

In the second row of tiles, you can see **Exact Data** profiles and records counts across your configured unstructured data scan.

![Data scan results showing profiles, records, and data elements for Google Drive.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exactdatastats_unstructuredatascans.png)

#### Tree Map Chart

Below the tiles, a tree map chart shows how unstructured data is distributed across the following dimensions:

- Content Profiles
- Data Element Types
- Data Systems
- Document Categories
- Document Types
- File Formats

Tabs at the top of the chart let you switch between dimensions. Clicking on any tile applies a filter that updates the entire dashboard.

A metric displayed above the tree map chart reflects the selected dimension.

![Overview of unstructured data scans with detailed content profiles and data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/chartoptions_unstructuredatascans.png)

#### Sankey Chart

Below the tree map, a sankey chart displays the distribution of classified files across the following dimensions:

- Locations
- Data Systems
- Document Types
- File Formats

![File distribution overview showing document types and formats for various data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sankeychart_unstructuredatascans.png)

#### Files grid

Below the Sankey chart, the **Files** grid displays one row per scanned file. Selecting a row shows detailed information for that file.

For self-hosted data systems, after a complete scan job, the **Files** grid allows you to sort by counts of unique or total data elements. Securiti calculates unique identity counts (unique data elements) and stores them in the database after the scan completes.

![List of files with details like owner, data elements, and document categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dataelementsalla_unique_uds.png)

> [!NOTE]
> **Note**
> 
> - If the **File Owner** field is empty, it is typically due to permission-related issues. We recommend that you must review the connector documentation and ensure the connector account has the required permissions.
> - All detected data elements are shown with their unique counts, with unique values displayed in brackets. To enable unique count collection, turn on the **Collect Evidence** toggle in the **Advanced Settings** section when you [configure a discovery scan](/v1/docs/discovery-scans).
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-26 at 1.05.18 PM.png)

Expanding a file in the **Files** grid displays additional details about that file.

| Data System Type | Displays the type of data system where the file resides. For example, `Microsoft 365 OneDrive`. |
| --- | --- |
| Data System | Displays the name of the data system instance associated with the file. For example, `OneDrive Discovery Scan`. |
| File Format | Displays the format of the file. For example, `Mail`. |
| File Size | Displays the size of the file. For example, `11.2 MB`. |
| File Cluster | Displays the cluster or logical grouping associated with the file, if applicable. |
| Resource Path | Displays the full path of the file within the data system. |
| Resource URL | Displays the direct URL to the file in the source data system. |
| File Created Time | Displays the timestamp when the file was created. |
| File Modified Time | Displays the timestamp when the file was last modified. |
| First Scan Time | Displays the timestamp when the file was scanned for the first time. |
| Last Scan Time | Displays the timestamp when the file was most recently scanned. |
| Content Profiles | Displays the content profiles matched for the file. Hover over a content profile tag to view the following: - **Dictionary Keyphrases**, which specifies the dictionary keyphrases that triggered the detection. For example, the screenshot below shows that `Thomas` keyphrase, along with others, triggered the `Custom Naming` content profile. - **Data Element Types**, which specifies the data element types associated with that content profile. For example, the `First Name` and `Last Name` data elements triggered the `Custom Naming` content profile. ![Overview of data profiles and duplicates in a discovery scan interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dataelementsanddictionaty_uds.png) |
| Data Elements – All (Unique) | Displays the data elements detected in the file, grouped by category. For example, **Contact Info**, **Location**, **Name**, **Social**, and **Profession**. Each category shows the total count of detections, and each data element type within it shows the total and unique occurrence counts. For example, `Email Address x 10 (10)`. |
| Data Element Types | Displays the detected data element type of the file. |
| Document Type | Displays the detected document type of a file. You can edit a document type using the following steps: 1. Click the **Edit document type** (pencil) icon adjacent to the file name. ![List of documents with various statuses and a highlighted medical entry.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/editdocumenttypeclassification_uds.png) 2. Select the new document type from the dropdown. 3. Click **Apply & Save Selection**. ![A list of documents with a search option and selection filters for academic records.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/selectingnewdocumenttype_uds.png) This applies the new document type to the selected file. 1. (Optional) Click the **Revert classification** icon to revert the classification back to the system classification. ![List of documents with highlighted dissertation entry and associated metadata details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/revertmanualclassification_uds.png) > [!WARNING] > Important > > Securiti does not retain manual document type changes across discovery scan runs. The rescan of the file replaces your change with the system classification. > > To correct a document type so that the change persists, use [AI Tuning](/latest/docs/classifying-document-types-using-ai-tuning). |
| Document Category | Displays the detected document category of a file. |
| Exact Data Profiles | Displays the exact data profiles matched for the file. |
| Duplicates and Near-Duplicates | Displays a list of exact duplicate and near-duplicate files identified for the file, along with the data system, resource path, and similarity level for each. Click **Download** to export this list. |

#### Viewing files and folders in Explorer Mode

**Explorer Mode** lets you view files and folders in a hierarchical structure.

> [!WARNING]
> Important
> 
> **Explorer Mode** is only available for tenants with Securiti release 1.110 or later. If **Explorer Mode** is not available in your tenant, contact your Customer Success Manager or Account Representative to enable it.

You can perform the following actions directly within the view:

- Drill down through folder hierarchies.
- Sort results.
- Apply filters by data system, folder, or file name.

> [!NOTE]
> Note
> 
> The filters apply across the entire **Unstructured Data Scans** page.

To access this view, enable the **Explorer Mode** toggle, as shown below.

![Overview of file organization and data distribution in a workspace interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/explorermode_unstructureddatascans.png)

> [!NOTE]
> Note
> 
> - **Explorer Mode** is available only for data system types that support folder hierarchy, such as Amazon S3, Google Cloud Storage, and SharePoint.
> - Exporting as CSV always exports the flat list of files regardless of whether **Explorer Mode** is enabled.

#### Geographic and tabular views

The dashboard also includes a world map that shows the geographic distribution of unstructured data.

![Map showing data distribution locations and document types for various content profiles.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/contentdistributionbylocation_unstructuredatascans.png)

Below the world map, there are tables that display aggregated content distribution statistics grouped by the following dimensions:

- Document types
- Content profiles
- File formats
- Data systems
- Data element types
- Exact data profiles

![Content distribution overview by document types and file formats in a data management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/contentdistributionfilters_unstructuredatascans(2).png)

### Viewing and downloading the classification evidence file

You can download classification evidence files directly from the Unstructured Data Scans dashboard using a secure, time-limited signed URL. These evidence files help verify the accuracy of discovery scans by displaying the first 20 occurrences of each detected data element in the dashboard Highlights pop-up. The complete list of occurrences is available in the downloaded evidence file.

For more information, see the [Prerequisites for downloading evidence files](/latest/docs/managing-evidence-files-and-downloads#prerequisites-for-evidence-file-downloads).

To view and download evidence files:

1. In the **Files** grid, expand a file and click **View Evidence**, as shown below. The highlights pop-up appears, displaying the evidence content.

![Overview of Azure Files data system with highlighted content profiles and scan details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/View Evidence button_UDS.png)
2. On the **Evidence Viewer** popup, click the **Download** button in the **Summary** tab to download the evidence file to your system. The download uses a signed, time-limited URL.
3. Hover over the icon before the data element name to identify whether the classification is manual or system classified, as shown below.

![Evidence viewer displaying bank statement data elements and their respective locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/systemclassifiedicon_uds(1).png)
4. Click the **Sample Data** tab to view the sample data collected from the file during the discovery scan, as shown below.

![Bank statement details including account number, postal code, and personal information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sampledatatab_evidenceviewer_uds(1).png)

For files that do not contain sample data, such as files scanned before Securiti release 1.151, the **Sample Data** tab displays **Sample data not available**.

> [!NOTE]
> Note
> 
> Securiti collects sample data when you mark the **Collect Evidence** checkbox in the discovery scan configuration. For more information, see [Discovery scans for unstructured connectors](/latest/docs/discovery-scans).
5. Expand a data element to view the anchor term associated with the detection, as shown below. Anchor terms give additional context about the detection.

![Summary of evidence viewer showing data elements and their categories for a document.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bestpositiveanchor_evidenceviewer_uds(1).png)

> [!NOTE]
> Note
> 
> - If encryption is enabled in your **Private Cloud Storage** configuration, the evidence file is downloaded in encrypted (`.sef`) format. For more information on decrypting the file, see [Configuring Private Cloud Storage encryption and decryption](/v1/docs/system-settings-configuring-private-cloud-storage).
> - Securiti displays only the first 20 occurrences of evidence for each data element detection. To view all occurrences, download the full evidence file.

The following is a sample evidence file.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-26 at 1.22.20 PM.png)

### Understanding skip reasons for files skipped from discovery scans

This section explains the reasons why files or tables are skipped during discovery scans. You can view these skip reasons in the Unstructured Data Scans dashboard under the **Files** grid.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2N6090PK.png)

> [!NOTE]
> **Note**
> 
> - Securiti tracks the number of files marked as **Skipped by Policy**, but does not store detailed metadata for all such files. As a result, these files may not appear in the **Unstructured Data Scans** dashboard. A file is marked as **Skipped by Policy** when the discovery scan configuration excludes it from the scan scope.
> - If a file appears in the Unstructured Data Scans dashboard, it means that Securiti saved its metadata. If the file was skipped, the corresponding skip reason is displayed.
> 
> If the skip reason is **Objects skipped by policy**, the file was excluded from the scan based on the discovery scan configuration.
> - To view all skipped files or filter by specific skip reasons, use the File Skip Reason filter in the Unstructured Data Scans dashboard. This filter displays both partially skipped and fully skipped files.
>   - **Partially Skipped Files**: These files may contain detections but are partially skipped due to classification or scan policies. They are counted in the “Objects Scanned” and “Data Scanned” statistics.
>   - **Fully Skipped Files**: These files have no detections and are fully skipped.They are counted in the “Objects Skipped By System” and “Data Skipped” statistics.
> 
> Some dynamic skip reasons may not be ingested into the Unstructured Data Scans dashboard. As a result, differences may occur between **Discovery Scan** statistics and file-level metadata.

The table below lists the possible skip reason messages, who triggered the skip, and how the skipped files are counted in the dashboard statistics. You might not see all of them listed in the Unstructured Data Scans dashboard under the **Files** grid because your scans were run with different configurations and requirements.

| Skip reason message (Files Grid) | Skipped by | Counts fetched under the Unstructured Data Scans dashboard | Reason |
| --- | --- | --- | --- |
| All encapsulated files were skipped | Objects skipped by the system | - Objects Skipped by Data System - Data Skipped | Securiti generates this message when a compressed or container file, such as `ZIP` or `TAR` , is processed but all files extracted from it are skipped. Triggered by: - Discovery scan - Data scan |
| An internal error occurred | Objects skipped by the system | - Objects Skipped by Data System | Securiti generates this message when a compressed file, such as `ZIP` or `TAR` is sent to the Content Classifier and it runs into a failure. In such a case, the connector does not retry scanning the compressed file and instead skips the file altogether. Triggered by: - Discovery scan - Data scan |
| Authorization Error Accessing File | Objects skipped by the system | - Objects Errors - Data Error | Securiti is unable to scan the file due to insufficient permissions. |
| Failed To Classify File | Objects skipped by the system | - Objects Errors - Data Error | Securiti is not able to classify the file to identify sensitive data due to an internal error. |
| File contains non-sensitive data | Objects skipped by the system | - Objects Errors - Data Error | Securiti generates this message when it identifies that the file does not contain any sensitive information and should not be processed further. Specifically, this skip reason is used when: - The file falls under the **Publications** category, containing specific phrases indicative of non-sensitive content, such as a book. - The file is publicly available published material, including papers, articles, or similar unstructured content. These cases represent the scope in which unstructured files are classified as non-sensitive publications and skipped accordingly. Triggered by: - Discovery scan - Data scan |
| File partially scanned | Objects skipped by the system | - Objects Scanned - Data Scanned | Securiti generates this message when one or more components within the file cannot be scanned. This might occur in the following scenarios: - Unsupported or corrupted files extracted from compressed files, such as `ZIP` or `TAR`. - Embedded images or thumbnails that do not meet the OCR criteria. - Empty sheets within spreadsheets, documents, or presentations. - Embedded files, such as model weights or audio files, that do not meet scan conditions. Triggered by: - Discovery scan - Data scan |
| OCR policy | Objects skipped by policy | - Objects Skipped by System - Data Skipped | Securiti generates this generic message when a file violates an OCR Policy. This mostly occurs when a scan is not configured to perform OCR, and there are image files found during the scan, which will then be skipped. > [!NOTE] > **Note** > > These files are shown on Unstructured Data Scans dashboard after you apply the **File Skip Reason** > **OCR Policy** filter. > > ![Data scan interface showing skip reasons and data elements summary for unstructured data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/skipreasons_unstructuredatascans.png) > > It also applies to instant classification scans. |
| Scan Policy | Objects skipped by policy | - Objects Skipped by System - Data Skipped | Securiti generates this generic message when a Content Scan Policy violation occurs, but it cannot be attributed to any of the specific Scan Policy skip reasons. |
| Scan policy: file age | Objects skipped by policy | - Objects Skipped by System - Data Skipped | Securiti generates this message when a file does not fall within the period defined in the Content Scan Policy, for example, a file created between 2010 and 2015. |
| Scan policy: file extension | Objects skipped by policy | - Objects Skipped by System - Data Skipped | Securiti generates this message when an excluded file extension is found in the scan. This is defined under Content Scan Policy. For example, an excluded file extension could be `.conf` files, which are skipped during the scan. |
| Scan policy: file format | Objects skipped by the policy | - Objects Skipped by System - Data Skipped | Securiti generates this message when an excluded file format is found in the scan. This is defined under Content Scan Policy and Scan Condition. For example, an excluded file format could be `EPUB` files, which are skipped during the scan. |
| Scan policy: file name pattern | Objects skipped by policy | - Objects Skipped by System - Data Skipped | Securiti generates this message when a file’s name matches a certain pattern that should be excluded or if it does not match a pattern for files that should be included, based on the configured Content Scan Policy. |
| Scan policy: file size | Objects skipped by the policy | - Objects Skipped by System - Data Skipped | Securiti generates this message when the file size does not fall within the file size limits defined under the Content Scan Policy. For example, users can configure files greater than 500MB to be skipped in the scan. |
| Table contains non-sensitive data | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when a table or database is analyzed and is deemed not to contain any sensitive information, so it is not processed any further. Triggered by: - Discovery scan - Data scan |
| Unable to parse | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when Securiti is unable to parse a file due to any reason not attributed to the file’s encryption or password protection or other blacklist reasons, such as there being no parser for it. |
| Unable to parse: encrypted | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when Securiti is unable to process a file because it was encrypted. |
| Unable to parse: File is empty | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when the file contains no data and is empty. Triggered by: - Discovery scan - Data scan |
| Unable to parse: File is greater than 10GB | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when the file size is larger than 10 GB. Triggered by: - Discovery scan - Data scan |
| Unable to parse: File is not present on source | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when the file is deleted from the data system before it can be downloaded. Triggered by: - Discovery scan - Data scan |
| Unable to parse: incomplete dataset | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when a file/object ID is missing, so the file is not downloaded and skipped. Triggered by: - Discovery scan - Data scan |
| Unable to parse: password protected | Objects skipped by the system | - Objects Skipped by System - Data Skipped | Securiti generates this message when Securiti is unable to process a file because it is password-protected. Triggered by: - Discovery scan - Data scan |
| Unknown Scan Error | Objects skipped by the system | - Objects Errors - Data Error | Securiti is not able to determine the cause of the error, due to which the file was skipped from classification. |

> [!NOTE]
> **Note**
> 
> The Content Classifier skips files after download, as it only processes files received from connectors.

### Exporting the dashboard as a CSV file

This section describes how to export the Unstructured Data Scans dashboard as a CSV file. The exported CSV file includes all data based on the selections made in the scans and filter panel, including the file size in bytes, KB, MB, GB, and so on.

> [!NOTE]
> **Note**
> 
> Securiti includes duplicate and near-duplicate file counts in the CSV export only if the record count is less than 100K.

To export data from your the Unstructured Data Scans dashboard to a CSV file:

1. From the **Files** grid, click **Export as CSV**, as shown below. To limit the exported content, apply the relevant filters.

![Overview of data system files, including sensitive files and content distribution locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exportcsv_unstructureddatascans(1).png)
2. Securiti sends an email notification when the file is ready to download. The email with the download link may take a few minutes, depending on the number of records. You can also download the CSV file from [My Downloads](https://qa.securiti.xyz/#/my-downloads) page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PXO0I0GF.png)

> [!NOTE]
> **Note**
> 
> You can export up to a maximum of 15 million records in a single CSV export from the Unstructured Data Scans dashboard.

### Exporting the dashboard as a PDF file

This section describes how to export the Unstructured Data Scans dashboard as a PDF file. The exported PDF file includes all data based on the selections made in the scans and filter panel. Any filters applied on the dashboard are also considered on the Report’s page and are reflected in the exported PDF.

1. To export the entire dashboard, click **Export PDF** in the upper-right corner of the Unstructured Data Scans page, as shown below.

![Overview of unstructured data scans showing scanned files and data elements statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exportpdf_unstructuredatascans.png)

2. Securiti sends you an email notification when the PDF is ready. You can also download the PDF file from [My Downloads](https://qa.securiti.xyz/#/my-downloads) page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KR8UVM70.png)

The following is a sample PDF export.

> [!NOTE]
> Note
> 
> The exported report shows limited data for grid sections. For detailed information, click **“For detailed information on this dashboard, click here**” on the report’s cover page to access the live dashboard in the Securiti Portal.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-29 at 12.32.26 PM.png)

### Viewing duplicate and near-duplicate files

In the Unstructured Data Scans dashboard, you can view a list of duplicate and near-duplicate files identified from a data system folder. You can also see the similarity percentage for each file.

1. Scroll down to the **Files** grid and click an entry to expand it.
2. Scroll down to the **duplicates and near-duplicates** section. Here, you can view a list of exact duplicate and near-duplicate files, as shown below.

![List of duplicate files with their data system types and resource paths displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/duplicateandnearduplicate_uds.png)

3. To view the file clusters, in the **File Cluster Analysis** dashboard, scroll down to the **Cluster List** grid, click **o****ptions** **(three dots)**, and select **View Files**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZLAXRVBH.png)

For more information, see [Detecting and reducing duplicate and near-duplicate data](/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data).

> [!WARNING]
> **Important**
> 
> Securiti includes duplicate and near-duplicate file counts in the CSV export only if the record count is less than 100K.

4. To download the duplicate and near-duplicate files, click **Download**, as shown below. Securiti sends an email notification when the file is ready.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Z90B1P13.png)

5. You can also download it from [My Downloads](https://qa.securiti.xyz/#/my-downloads) page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MP0C5RH8.png)

## Related

- [Viewing scan results](/viewing-discovery-scan-results.md)
