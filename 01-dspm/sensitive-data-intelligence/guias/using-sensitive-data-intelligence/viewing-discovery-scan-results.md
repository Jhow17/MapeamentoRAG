---
title: "Viewing scan results"
slug: "viewing-discovery-scan-results"
updated: 2026-09-29T11:10:47Z
published: 2026-09-29T11:10:47Z
canonical: "helpcenter.securiti.ai/viewing-discovery-scan-results"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Viewing scan results

Discovery scans let you identify, manage, and protect sensitive data across your data estate to support compliance and security requirements.

When you run a discovery scan, you can identify data elements across your environment, including structured, unstructured, and streaming data systems. You can configure these scans to locate sensitive and personal data that may be subject to privacy regulations such as GDPR, CCPA, and HIPAA. Identifying sensitive data is the first step in protecting it and ensuring compliance.

Discovery scans surface all data, including shadow data that is unknown or unmanaged. Securiti provides a dedicated risk explorer dashboard for insights into risks associated with your data systems. For more information, see [Viewing risks associated with data systems](/v1/docs/using-the-data-risk-explorer).

> [!NOTE]
> **Note**
> 
> Securiti shows the discovery scan results only for completed scans.

## Viewing discovery scan results on the Scan Definitions page

On the **Scan Definitions** page, click **View Results** from any scan job entry. Securiti takes you to the respective structured, unstructured, or streaming dashboard based on the data system type.

![Overview of scan definitions, including active and inactive scans with job statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewresults_scandefinitions.png)

The page displays scan times, data elements, content profiles, documents scanned, and exact data indexes, along with their counts.

## Viewing discovery scan results for unstructured data systems

Use this section to view discovery scan results for unstructured data systems such as **Amazon S3**, **Microsoft 365 SharePoint Online**, and **Alfresco**.

- On the **Scan Definitions** page, from any scan job entry, click **View Results**. Securiti takes you to the **Unstructured Data Scans** dashboard, where you can view counts for data elements, content profiles, documents scanned, exact data profiles, and more.
- Alternatively, from the **Scan Job History**, copy the **Scan Job ID**.

![Scan job history table displaying completed and error statuses for various scans.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/copyscanjobid_scandefinitions.png)
- On the **Unstructured Data Scans** dashboard, open the filters from the top-left side and use the **Discovery** **Scan Job ID** filter to view the discovery scan results.
- You can see a list of documents scanned during this discovery scan job under the **Files** grid.

![Overview of files and data distribution in Sweden, including employee information and locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filesgrid_unstructureddatascans.png)

> [!NOTE]
> **Note**
> 
> When searching for files using the search bar, keep the following in mind. For instance, consider a file named **NZ_CC_Automation**:
> 
> - Search is token-based, not an exact file name match. Results may include files that contain the same keywords. For instance, searching **NZ_CC** returns all files that contain this keyword.
> - Special characters are supported.
> - Search is case-insensitive in most cases. Use consistent casing for best results. For instance, searching **NZ_CC_Automation** and **nz_cc_automation** returns the same results.
> - Partial word matches may not be supported. For instance, searching **NZ_CC_Auto** might not return results.

When you expand a file entry, you can view the folder path and the time the scan started. You can also view the data elements, content profiles, and their counts identified in the specific discovery scan job.

![Details of a file scan including data elements and timestamps for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filesgridmetrics_unstructureddatascans.png)

Below the **Files** grid, additional distribution grids display counts by location, document type, content profile, file format, data system, data element type, and exact data profile.

![Overview of content distribution by document types, file formats, and data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/contentdistribution_unstructureddatascans.png)

### Viewing evidence for specific documents

You can view the evidence for specific documents in the **Unstructured Data Scans** dashboard after the discovery scan is complete.

To configure Private Cloud Storage, see [Configuring Private Cloud Storage](/v1/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> **Note**
> 
> - You must enable the **Collect Evidence** toggle under **Advanced Settings** when configuring the discovery scan for your unstructured data systems, such as Microsoft 365 SharePoint Online and Amazon S3.
> 
> ![Settings for evidence collection in a data scanning application interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/collectevidence_discoveryscancreation.png)
> - Enabling the **Collect Evidence** toggle saves the scan results to your private cloud storage. For more information, see [Configuring Private Cloud Storage](/v1/docs/system-settings-configuring-private-cloud-storage).
> - When Securiti processes a large number of evidence files (for instance, 10,000 batches), it uploads them to a folder dedicated to the evidence summary. Securiti deletes that folder automatically once it generates the summary. For more information, see [Discovery scans for unstructured connectors](/latest/docs/discovery-scans-for-unstructured-connectors).
> - If no detections are found during a scan, individual evidence files are not generated; however, Securiti generates that scan's evidence. When detections are present, Securiti creates unlimited merged evidence files until it reaches the limit of 4GB. If the evidence exceeds this threshold, evidence files are not generated further to maintain performance and system stability.

#### Viewing evidence on the Unstructured Data Scans dashboard

The evidence displays the exact data scanned for a file from the **Files** grid of the **Unstructured Data Scans** dashboard. You can verify detections and identify matched data along with its offset in the file, including metadata such as file number, offset, and record number, on a per-file basis.

Securiti generates evidence files only if you have configured Private Cloud Storage (PCS) and enabled the **Collect Evidence** toggle under **Advanced Settings** when configuring a discovery scan.

#### Viewing evidence on the Scan Definitions page

Click the **View Metadata** icon from any entry to view the data elements, content profiles, and exact data profiles identified in the scan job.

- To download the evidence file, click **Download Link** in the Collect Evidence field. This copies the URL to your clipboard, which you can paste into a browser to download the file from your cloud storage.

> [!NOTE]
> **Note**
> 
> - You can see the Collect Evidence option only for complete discovery scan jobs.
> 
> ![Overview of scan definitions, including active and completed scans with detailed job statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/downloadevidencefile_scandefinitions.png)
> - These evidence summary files are in compressed format. To view these files, you must decompress them using the **gunzip** tool.
> - The number of file records in the downloaded evidence file may be fewer than the number of files displaying detections in the UI. If this occurs, contact your Customer Success Manager or Account Representative to confirm whether your tenant meets the eligibility requirements for evidence file configuration.

## Viewing discovery scan results for structured data systems

Use this section to view discovery scan results for structured data systems such as **MySQL**, **Snowflake**, and **PostgreSQL**.

- On the **Discovery Scans** page, from an entry, click **View Results**.

![Overview of scan definitions with statuses and details for various data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewresults_structureddatascans.png)
- Securiti takes you to the **Structured Data Discovery** dashboard, where you can view the counts in the top tiles and Columns, Table, Database Schema, Data Systems, and Data Element entities in the left panel. These entities show counts for how many columns, tables, schemas, and databases have been scanned for your selected data system.

![Overview of a data discovery scan with details on scan name and status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/structureddatadiscovery_dashboard.png)
- From the top-left side, click the **Apply Filters** (plus icon) to use available filters such as types of data elements, data systems, tables, schemas, and columns. Some filters display a list of available data systems or data elements that you can choose from.
- To view the column classification results, choose one or more entries from the list and click **Review Classification**.

For more information, see [Classification validation and fine-tuning discovery scans](/v1/docs/classification-validation-and-fine-tuning-discovery-scans) and [Using Validation Workbench for structured data](/v1/docs/using-the-validation-workbench-to-review-and-validate-classifications).

## Viewing discovery scan results for streaming data systems

Use this section to view discovery scan results for streaming data systems such as **Kafka**, **Confluent Kafka**, and **Amazon MSK**.

- On the **Discovery Scans** page, from an entry, click **View Results**.

![Scan definitions overview showing active and completed scans for Kafka data system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewresults_streamingdashboard.png)
- Securiti takes you to the **Streaming Data Discovery** dashboard, where you can view the counts in the top tiles for data elements, topics, schemas, and content profiles identified in discovery scans.
- The dashboard also includes tabs for fields, topics, and schemas with their counts, which you can expand for further details.

Additional grids display counts for data elements by category and the associated data systems.

## Viewing discovered assets in Graph Explorer

1. From the sidebar, click **Graph Explorer**.
2. Click the Apply Filters (plus icon) on the upper-left side of the dashboard.

![Graph Explorer interface showing options to add filters and begin a search.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfilters_graphexplorer.png)
3. Choose the **Discovery Scan** entity to view the list of discovery scans.

![Search bar displaying 'discovery' with related data options in Graph Explorer interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/discoveryscanentity_graphexplorer.png)

The list displays discovery scan jobs with their active or inactive status, the time of the last scan, and whether it was marked as a primary scan.
4. Add a relationship by following the steps below:
  1. Click **More Actions** (three dots icon) to open a menu.
  2. Select **Add Relationship**.
  3. Choose the **Data System** entity.

This displays the data system instance activated for your Securiti tenant.

![Graph Explorer interface showing options to add properties and relationships for data visualization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/addrelationship_graphexplorer.png)
5. From the **Data System**, click the **More Actions** (three dots icon) to add another relationship, and choose the **Content Profile** entity. This displays the content profiles identified in the discovery scan jobs for the selected data systems.

![Graph Explorer interface displaying various content profiles and their data types.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/contentprofilefilter_graphexplorer.png)

Click **Explore** to view relationships between different entities, such as data elements identified, data systems, and files.

![Graph Explorer interface displaying content profiles and their details for data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/explore option_graphexplorer.png)

This opens the Explore view popup as shown below:

![Overview of PII content profile with various data categories and user groups displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exploreview_graphexplorer.png)

> [!NOTE]
> **Note**
> 
> You can also use **Graph Explorer** to create additional widgets. For more information, see [Using Graph Explorer](/v1/docs/using-graph-explorer).

#### Viewing discovery scan statistics in Universal Data Explorer

The **Universal Data Explorer** also displays multiple metrics for discovery scan jobs, such as Scan Job ID, Scan Initiator, Scan Start Time, Scan Status, and more.

![Overview of discovery scan jobs with detailed properties and data elements displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/exploreview_ude.png)

For more information, see [Viewing scan job history](/latest/docs/viewing-scan-job-history).

## Related

- [Discovery scans](/discovery-scans.md)
- [Using the Unstructured Data Scans dashboard](/using-the-unstructured-data-discovery.md)
- [Structured Data Discovery New Experience dashboard](/structured-data-discovery-new-experience.md)
- [Using the Streaming Data Discovery dashboard](/using-the-streaming-data-discovery-dashboard.md)
