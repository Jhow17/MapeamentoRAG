---
title: "Using File Cluster Analysis dashboard"
slug: "detecting-and-reducing-duplicate-and-near-duplicate-data"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/detecting-and-reducing-duplicate-and-near-duplicate-data"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using File Cluster Analysis dashboard

It is important to manage Redundant, Obsolete, and Trivial (ROT) data, which at times may become potentially risky and costly. In such a case, you need to establish clear policies and methodologies for data retention and deletion to improve efficiency, save cost and storage, mitigate risks, and improve data quality. Securiti's file cluster analysis feature helps you identify duplicate and near-duplicate data (files or documents).

The clustering process identifies and groups such files or documents that are exactly similar or nearly similar after a complete discovery scan job. In the Securiti platform, clustering is performed to identify such duplicate or nearly duplicate files or documents during the discovery scan jobs for unstructured data systems such as Amazon S3, Azure files, Microsoft 365 SharePoint Online, and so on. When the discovery scans are complete, the results appear on the File Cluster Analysis dashboard.

> [!NOTE]
> Note
> 
> Securiti supports cluster analysis for unstructured connectors and for unstructured data in hybrid connectors.

To learn how to use the file clustering dashboard, see [Using the file cluster analysis dashboard](https://helpcenter.securiti.ai/v1/docs/detecting-and-reducing-duplicate-and-near-duplicate-data).

### Detect Duplicate Files

For your ROT data management, it is important that you regularly review your data across your data systems and have retention policies in place. You may require adjustments to your policies as your organization's data evolves, and your ROT data management requirement may also change. Retention policies are helpful in managing ROT data to ensure data is retained only for as long as it serves a legitimate business purpose and should comply with global regulatory standards. For example, financial data can be retrieved for a certain period of up to several years, while non-critical email data can have a shorter retention period. Similarly, you can get rid of duplicate files from your data system if you have configured the retention policies.

At Securiti, you can [configure file insights policies](/v1/docs/configuring-file-insights-policies) to handle ROT data as well as find sensitive information present in files placed in your data system storage.

Securiti allows duplicate detection by calculating checksums for the scanned files during the classification scan. A discovery scan can detect duplicate files as its basic functionality and applies checksums to files when the files are included in the discovery scan's scope. If you find more than one identical checksum value, those are duplicate files.

### Detect Near-Duplicate Files

Securiti can detect near-duplicate files by using the first 3,000 characters (~3KB) of a file’s parsed text content, and for that, you must enable the cluster analysis while configuring a discovery scan for your unstructured data. Changes to cluster analysis settings will require scanning of your data system before the settings take effect.

To identify near-duplicate files in your data systems, see the [Viewing duplicate and near-duplicate documents](https://helpcenter.securiti.ai/docs/using-the-unstructured-data-discovery#viewing-duplicates-and-nearduplicate-documents).

To learn more about file clustering, its configuration, and how to view results, follow the sections below:

1. File cluster analysis prerequisites
2. Configure File Clustering Analysis
3. Review the file clustering results to view duplicate files in your unstructured data systems
  - Using the Universal Data Explorer to View Duplicate Files
  - Using the Graph Explorer to view Duplicate Files
  - Viewing document clusters in the Graph Explorer
  - Viewing near duplicate documents in the Unstructured Data Discovery
4. Using the File Cluster Analysis Dashboard

### 1. File clustering analysis

This section provides instructions to configure file clustering analysis and review its results.

#### Prerequisites

To enable the file clustering analysis feature:

1. In the case of self-hosted data systems, you must deploy a [Pod or elastic Pod](/v1/docs/securiti-pods-and-elastic-pods).
2. Configure and [activate the connector for the data system](/v1/docs/managing-data-system-connectors).
3. In the **Advanced Settings** of the discovery scan, mark the **Enable Similar Document Cluster Analysis** checkbox when you are about to create a discovery scan for any unstructured data system.

![Settings for enabling document cluster analysis and data subject requests in a software interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/enableclusteranalysis_clusteranalysissettings.png)

For more information, see [Discovery scans for unstructured data systems](/v1/docs/discovery-scans).

> [!NOTE]
> **Note**
> 
> When you enable this checkbox for cluster analysis, it applies to new scans. For an existing scan, if you want to detect near-duplicate files, and enable this option, then rescanning is required.

### 2. Configuring file clustering analysis

After manually triggering the clustering job for the first time, Securiti triggers cluster analysis automatically each time new scan data is received. You can also manually trigger it from the **File Cluster Analysis** configuration page at any time.

> [!WARNING]
> Important
> 
> Consider the following when configuring cluster analysis:
> 
> - You must have at least one discovery scan configured with document clustering enabled before you can manually trigger the clustering job.
> - The first clustering run must always be triggered manually. After that, Securiti triggers it automatically each time new scan data is received within 7 days.
> - If no new scan data arrives for more than 7 days, the automatic schedule resets and you must manually trigger the job again before automatic triggering resumes.
> - Clustering is performed only on data that has already been scanned.

1. From the main menu, choose **Sensitive Data Intelligence** > **Discovery Scans** > **Cluster Analysis Settings**.

![Dashboard displaying sensitive data intelligence and cluster analysis settings options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.18.19 PM.png)

It opens the **Cluster Analysis Settings** page.
2. From the **Organization** menu, choose an organization for which you want to configure the cluster analysis.

![Cluster Analysis Settings interface showing organization selection and job completion status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.19.36 PM.png)

On the **Cluster Analysis Settings** page, you can view three tabs:
  - The **Cluster Jobs** tab shows the status of clustering jobs successfully completed, in progress, or failed. On this tab, you can see the following job statuses:
    - **Not Started**: The clustering job has not started yet
    - **Scheduled**: The clustering job is scheduled to run on a periodic basis
    - **In Progress**: The clustering job is in progress. For in progress clustering jobs, you can see the completion progress in percentage as shown below:

![Cluster Analysis Settings showing scheduled job details and options for analysis initiation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.21.27 PM.png)
    - **Completed**: The clustering job has been completed.
    - **Partially Completed**: The clustering job has been partially completed due to an error.
    - **Failed**: The clustering job has failed.
  - In the **Advanced Configuration** tab, set the parameters as described in the table below.

| Parameter | Description |
| --- | --- |
| Similarity Level Threshold | To configure the percentage of similarity threshold, set this value in percentage, while the default value is set at 70%. When set as 70%, the system evaluates the documents for your unstructured data systems and flags two or more documents as similar if their similarity score meets or exceeds 70%. You can choose to adjust this threshold based on your specific needs to capture potential matches. - Increase this number, for example, 80% or 90%, to enforce the stricter criteria for similarity of documents to be exactly similar. This lowers the file count in a cluster. - Decrease this number, for example, 40% or 50%, to relax the similarity of documents. This increases the file count in a cluster. |
| Minimum Documents Per Cluster | The minimum number of documents required per cluster can be set to a value between 5 and 100. It lets you control the granularity of the clustering process. By default, the system is set to a minimum of 5 documents per cluster, ensuring that even small groups of similar documents are captured. Adjusting this threshold up to 100 may be useful for you if you are dealing with larger data sets or looking to focus on more substantial groupings of documents. |

![Settings for cluster analysis including similarity threshold and minimum files per cluster.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.20.17 PM.png)
  - The **Audit Trail** tab lets you view the activities related to file clusters that include automatic or manual job runs and any changes made by users.

### 3. Reviewing file clustering analysis results to view duplicate files in your unstructured data systems

You can review the duplicate files and cluster analysis results on

- Universal Data Explorer
- Graph Explorer
- Unstructured Data Discovery
- File Cluster Analysis dashboard

Duplicate files can be identified by comparing checksum values. Identical files will have identical checksums.

#### Using the SDI Universal Data Explorer to view duplicate files

You can view duplicate files using SDI's Universal Data Explorer by comparing the Checksum values. If there is more than one identical Checksum value, that means these files are duplicates. For more information, see [Discovery scans for unstructured data systems](/v1/docs/discovery-scans).

1. From the main menu, choose **Sensitive Data Intelligence** > **Data Explorers** > **Universal Data Explorer.**
2. Click the plus sign (**+**) and choose the **Files** entity and a relevant data system for which you want to find the duplicate files, and click **Apply**.
3. Click **Column Selector** at the end of the **Files** entity grid, as shown below:

![dcgcolumnSelectorIcon.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c947dcc1-93c4-a6b6-45cc-d411d5cd0843.png)

Choose the **Checksum** option and other relevant columns, and click **Apply**.

![dcgchecksumColumSelection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70417ff9-eedc-dfb9-1062-eba4d67f3749.png)
4. Securiti shows the **Checksum** column entries if there are duplicate files for your data system.

> [!NOTE]
> **Note**
> 
> To view the duplicate files together, use the up or down arrow in the **Checksum** column to sort the column in ascending order or descending order.
> 
> ![ChecksumColumnSort.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-adc0c8d9-0a93-e410-6b57-394bfc0e3f5c.png)

You can see the duplicate documents identified during discovery scans, as shown below:

![dcgDuplicateDocResults.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-272aabb6-3e85-216d-332b-11f5b07b0e8f.png)

#### Using Graph Explorer to view duplicate files

You can view duplicate files once the discovery job is complete. For more information, see [Discovery scans for unstructured data systems](/v1/docs/discovery-scans).

1. From the main menu, choose **Graph Explorer**.

![GENav2_0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3381d782-722c-6f98-1f6a-352e61cf675f.png)
2. Click the plus sign (**+**) and choose the Files node.

![Graph Explorer interface showing data system type filter options for cloud storage.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filterdatasystem_graphexplorer.png)
3. Click the **Column Selector** at the end of the **Files** entity grid.

![Graph Explorer interface displaying data system types and file details for Google Cloud Storage.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnselector_graphexplorer.png)

Choose the **Checksum** option and other relevant columns, and click **Apply**.

![Graph Explorer interface displaying data system types and selected columns for query.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/checksumfield_graphexplorer.png)

Securiti shows the **Checksum** column entries if there are duplicate files available in your data system.

![geDuplicateDocumentsResults.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fe537b5d-4658-7dcc-2bbd-d59051ee3496.png)

#### 

#### Viewing document clusters in the Graph Explorer

You can see the files associated with file clusters in the Graph Explorer with overall document counts and duplicate counts.

To view duplicate documents:

1. From the main menu, choose **Graph Explorer**.

![GENav2_0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3381d782-722c-6f98-1f6a-352e61cf675f.png)
2. Click the plus sign (**+**) and choose the **Files** property.
3. Choose the **File Cluster** property to view the available list of clusters. You can see the duplicate document counts under the **Duplicate Count** column as shown below:

![Graph Explorer interface displaying file clusters and their respective counts and duplicates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/duplicatecount_graphexplorer.png)
4. To view the relationship between different nodes, click **Instance Inspector**, as shown below:

![Graph Explorer interface displaying file clusters and their respective counts and details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/instanceinspector_graphexplorer.png)

Alternatively, click **Show Metadata** and choose **Explore**.

![Graph Explorer interface displaying file clusters and their details for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/metadataexploreroption_graphexplorer.png)

This opens the relationship among different nodes, such as files, data systems, content profiles, and so on, as shown below:

![Overview of file cluster with related components like location, account, and data system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/instanceexplorer_graphexplorer.png)

#### Viewing duplicates and near-duplicate documents

In the Unstructured Data Explorer dashboard, you can see a list of duplicate documents identified from a data system folder.

1. In Securiti, open **Sensitive Data Intelligence**, and choose **Data Explorers** > **Unstructured Data Discovery**.
2. Scroll down to the **Documents** grid and click an entry to expand.
3. Scroll down to the **DUPLICATES AND NEAR-DUPLICATES** area. You can see a list of nearly duplicate and exact duplicate documents.

To view the document clusters, in the **File Cluster Analysis** dashboard, scroll down to the **Cluster List** grid, click **Options** (three dots), and choose **View Files.**

![Cluster list displaying active data clusters with file details and actions available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewfilesoption_fileclusteranalysis.png)

> [!NOTE]
> **Note**
> 
> Securiti includes the duplicate and near duplicate document counts in the CSV export only if the records count is less than 100 K.

> [!NOTE]
> **Note**
> 
> To download the duplicates and near-duplicate documents, click **Download** as a CSV file. Securiti sends you an email when the file is available to download.
> 
> ![ude-2Duplicate_and_Near_Duplicates.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-613d9f2c-1c8b-03a7-28cd-5e980505e134.png)
> 
> You can also download it from Securiti's [my-downloads](/v1/docs/securiti-pods-and-elastic-pods) page.
> 
> ![ude_export.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d99ec90-11c7-aeca-9487-d762e8954b95.png)
> 
> This PDF export file is compressed, and you can choose its format depending on your environment, such as .ZIP or .GZ.
> 
> You can choose the relevant option according to your environment from **System Settings** > **Organizational** > **General** , and from the **Default Export Settings** > **Compressed CSV Format** menu, choose a relevant option.
> 
> ![Settings menu showing default export options for compressed CSV formats in an organization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/downloadformatselection_settings.png)

### 4. Using the File Cluster Analysis dashboard

You can create document clusters to identify similar or near-duplicate documents. You can label a similar set of documents having similar information as public, internal, confidential, restricted, and so on, and call them document clusters, as they can have the same combination of data elements. Another reason for creating document clusters is to identify duplicate documents from the same data source to apply ROT management policies. In this case, you can remove unwanted copies of documents to save storage space.

On Securiti's File Cluster Analysis dashboard, you can see information about different clusters identified after completing discovery scan jobs only if you enable the **Enable Similar Document Cluster Analysis** option while creating the discovery scan jobs.

> [!NOTE]
> **Note**
> 
> Near the upper right side of the dashboard, the **File Cluster Analysis** link appears disabled if the discovery scan job is not complete. You must run a discovery scan job and enable similar document cluster detection functionality. For more information, see [Discovery scan for unstructured data systems](/v1/docs/discovery-scans).

1. From the main menu, choose **Sensitive Data Intelligence** > **Data Explorers** > **File Cluster Analysis**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fileClusterAnalysisMenu.png)
2. At the dashboard, a top row of widgets gives you a numerical snapshot of clusters:
  - Total Clusters
  - Documents
  - Data System
  - Duplicate Files
  - Data Element Types

For larger counts for data elements, there is a count on each dashboard according to the standard units (SI) as below:

- Symbols for thousand, million, billion, and trillion are in lowercase (m, b, t), respectively.
- Symbols for greater numbers peta, exa, and zetta are in UPPERCASE (P, E, Z), respectively.

**Using filters**

1. Click the plus (**+**) button to see filter options.
2. On the popup, choose one of the relevant options, such as Document Cluster Name, Cluster State, Contains Duplicates, and so on.

![File Cluster Analysis interface showing filter options and data element types overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filterforfilecluster_fileclusteranalysis.png)
3. Click **Apply** to see the updated stats in each area of the dashboard.

> [!NOTE]
> **Note**
> 
> From the **Cluster Distribution** widget, if you click a yellow box, that applies to the top filters in addition to the filters you applied already.
  - View updated stats in top widgets such as total clusters, total files, duplicate file counts, and data element counts
  - View the cluster distribution according to file count and resource size

![Analysis of file clusters showing total files, data systems, and document types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filecountandresourcesize_fileclusteranalysis.png)
  - View the list of active and inactive clusters identified in discovery scans under the **Cluster List** widget.
4. To save the custom filters applied, click **Save View**. Choose one of the options from **Save as a New View** to save the filters or **Revert Changes** to revert your changes.

![File cluster analysis showing total clusters, files, and data element types statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveaview_fileclusteranalysis.png)
  1. You can save the customer filter under an existing group or save it in a new group. When you click **Save View**, you can see a popup to add a group, press **Enter** to add a new group, followed by adding its name, filter name, and then click **Save View**.
  2. To view filters that have already been saved, click **Saved Views**. You can see the system and custom-created filter tabs on the left side, as shown below.

![Overview of data systems, duplicate files, and content profiles in a management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/openingasavedview_fileclusteranalysis.png)

To clear your applied filters, click **Clear Search**.

![File cluster analysis showing total clusters, files, and data element types distribution.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/clearsearch_fileclusteranalysis.png)

In the **Cluster Distribution** widget, select the top 10, 20, or 50 clusters based on **File Count** or **Resource** **Size** conditions.

![File cluster analysis showing total clusters, files, and data element types distribution.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/resourcesizeandfilecount_fileclusteranalysis.png)

Next is a row of panels that shows:

- Top Data Element Types
- Top Content Profiles
- Top Document Types

![Overview of data element types, content profiles, and document types in a data management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/topdatacontentprofileanddocumenttypes_fileclusteranalysis.png)

In the **Cluster List** grid, you can search for clusters using the search bar, as shown below.

![Overview of data element types, content profiles, and document types in a cluster list.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/searchclusterlist_fileclusteranalysis.png)

The **Cluster List** grid shows the list of available clusters identified after a complete discovery scan job for clustering, and the information associated with all the clusters regarding:

- Cluster Name
- Number of documents
- Number of duplicates
- Size on disk
- Data element type
- Data element
- Document types
- Data systems
- Tag

Securiti retains 10000 clusters, and you can now save the important ones that you want to keep, as per your choice, based on the following conditions:

- Saved priority (or priority saving)
- Maximum number of documents per cluster
- Most recently saved clusters

You can delete the extra clusters that are out of the limit of 10000, based on the following conditions:

- Unsaved clusters
- Dismissed/Archived clusters
- Oldest saved clusters
- Minimum number of documents per cluster

> [!NOTE]
> **Note**
> 
> Unsaved clusters have a higher priority for deletion over dismissed clusters since dismissed clusters also fall within the saved clusters.

**Viewing files in clusters**

In the **Clusters List** panel, near the left side of the page, click **Options** (three dots) > **View Files**.

![Overview of data clusters with file details and actions available for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewfiles_clusterlist.png)

The Graph Explorer dashboard with the applied query opens, as shown below.

![Graph Explorer interface displaying file data and search options for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graphexplorerviewfromviewfiles.png)

**Renaming and saving clusters**

You can save the important clusters to avoid reaching the limit of 10K. If the 10K limit is reached, and there are clusters beyond the limit, Securiti now automatically deletes the clusters by retaining the first 10K clusters based on the following precedence:

- Securiti deletes the unsaved clusters
- Securiti checks if the clusters' count is still above 10K, then deletes the next dismissed/archived clusters.
- Securiti checks if the clusters' count is still above 10K, then deletes clusters with the least number of documents

> [!NOTE]
> **Note**
> 
> Unsaved clusters have a higher priority for deletion over dismissed clusters since dismissed clusters also fall within the saved clusters.

In the **Clusters List** panel, near the left side of the page, click **Options** (three dots) > **Rename** to rename the cluster. Similarly, click **Options** (three dots) > **Save** to save it.

![Overview of cluster data including names, sizes, and document types for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/renameorsavethecluster_clusterlist.png)

**Exporting document clusters**

1. In the **Clusters List** panel, click **Export All Clusters** to export all the clusters available in the current list to a CSV file.

![Data cluster overview with export option and various file statistics displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exportallcluster_clusterlist.png)
2. On the popup, click **Export**. To export a cluster from the **Clusters List** panel, near the left side of the page, click **Options** (three dots) > **Export as a CSV file**. On the popup, click **Export**.

![Data management interface displaying cluster details and export options for files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exportaspecificcluster_clusterlist.png)

> [!NOTE]
> **Note**
> 
> The document cluster sizes on the dashboard appear in rounded numbers, whereas in the exported CSV files, you can see the exact cluster size.

**Adding or removing tags**

1. In the **Clusters List** panel, near the left side of the page, click **Options** (three dots) > **Tags**.

![Overview of data clusters with file sizes and document types for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/accesstags_clusterlist.png)
2. Add or remove the desired tag, press **ENTER**, and click **Save**.

**Understanding cluster states**

Each cluster in the **Cluster List** grid has a state that indicates its current status. You can apply a filter to view clusters by their state.

Use the following table to understand the available cluster states:

| Cluster State | Representation | Description |
| --- | --- | --- |
| **Active** | Displays an **Active** label next to the cluster name. | The default state for all clusters created by Securiti. New documents from subsequent scans are added to these clusters. |
| **Dismissed** | Displays a **Dismissed** label next to the cluster name. | Indicates a cluster that has been archived by a user. Dismissed clusters are excluded from future cluster analysis runs and do not receive new documents from subsequent scans. You can restore a dismissed cluster to **Active** at any time using the **Restore** option. |
| **New** | Displays a **New Cluster** (green dot) icon alongside the **Active** label next to the cluster name. | Indicates a cluster that Securiti has freshly created and that has not been modified by a user. A cluster changes its state to **Active** once you perform any action on it, such as renaming, dismissing, or saving it. |

**Dismissing and restoring clusters**

1. In the **Clusters List** panel, near the left side of the page, click **Options** (three dots) > **Dismiss**.

![Overview of data clusters with file sizes and document types listed in a table.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dismissacluster_clusterlist.png)
2. To dismiss all the clusters from the current list, near the left side of the page, click **Options** (three dots) > **Dismiss** from the **Cluster Actions** list.
3. Similarly, to bring the dismissed clusters back, select the desired cluster from the list and click **Restore** from the **Cluster Actions** list.

![Cluster management interface showing dismissed clusters and restore option for selected items.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/restorecluster_clusterlist.png)

You can use the **Show Dismissed Clusters** option from filters to see the dismissed clusters.

![File Cluster Analysis interface showing filter options for cluster state selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filtertoviewdismissedclusters.png)

## Related

- [Using the Unstructured Data Scans dashboard](/using-the-unstructured-data-discovery.md)
- [Discovery scans](/discovery-scans.md)
