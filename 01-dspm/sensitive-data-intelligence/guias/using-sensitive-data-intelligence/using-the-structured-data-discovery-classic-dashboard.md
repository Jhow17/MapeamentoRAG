---
title: "Using the Structured Data Discovery dashboard"
slug: "using-the-structured-data-discovery-classic-dashboard"
updated: 2026-09-09T08:30:21Z
published: 2026-09-09T08:30:21Z
canonical: "helpcenter.securiti.ai/using-the-structured-data-discovery-classic-dashboard"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using the Structured Data Discovery dashboard

### Prerequisites

In this dashboard, you can view the scan results and stats for complete discovery scans for structured data systems.

> [!NOTE]
> **Note**
> 
> - You might experience a delay in structured discovery results appearing in the Structured Data Discovery dashboard because a back-end asynchronous worker processes and formats the results before displaying them.
> - Downloading the evidence file is only possible if you have configured Private Cloud Storage (PCS) and have the appropriate permissions to view the evidence file. For more information, see [Managing evidence files and downloads](/latest/docs/managing-evidence-files-and-downloads).
> - You can configure multiple PCS instances in Securiti. Each data system is linked with its own PCS instance, and Securiti automatically uses the correct PCS instance when processing cases.

### Summary of Structured Data Discovery dashboard features

The summary of important elements that the Securiti platform identifies after completing discovery scan jobs includes:

- Databases, schemas, tables, and columns scanned during discovery scan jobs, with the data element identified, as well as relevant content profiles
- Counts for data element types and categories identified from structured data systems, as well as owners with their trend lines on a monthly, quarterly, and yearly basis
- Geographical view of structured data centers located on various global sites, with the count for different stats
- A few grids show the counts for data element types existing in different databases and schemas of different tables distributed across various global locations

### Using the Structured Data Discovery dashboard

To open the Structured Data Discovery dashboard, choose **Sensitive Data Intelligence** > **Structured Data Discovery**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(309).png)

At the top of the dashboards, use the rows of tiles for a quick view of metrics and trends, as shown below. The default view shows only the top row. Click **Expand More** below the tiles to view the second row.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(310).png)

For larger counts for data elements, there is a count on each dashboard according to the standard units (SI) as below:

- Symbols for millions, billions, and trillions are in lowercase (m, b, t), respectively.
- Symbols for greater numbers peta, exa, and zetta are in UPPERCASE (P, E, Z), respectively.

Below the tiles is a Sankey chart that disaggregates the available data bounded by the current filters.

![RN_SDI_strux_sankey.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e74695a-d586-a774-89ed-875571c13229.png)

Below the Sankey chart, you can use the tabs to view tabular structured data in:

- Columns
- Tables
- Schemas
- Databases

![stru_tab_view.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2cf5cc07-6792-97c6-476a-5597ae53b7e9.png)

You can search for structured data using the search bar, as shown below.

![stru_tab_view_search.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c01ea4b2-f635-2b1a-7f12-25a9cf4f6877.png)

The following table describes each entity of the **Columns** tab.

| Entity | Description |
| --- | --- |
| Data Element Type Data Element Category | It shows the data elements detected after discovery scans with their respective data element category. |
| Column Name Data Type | It shows the column names scanned during the discovery scans with their respective data type. |
| % Content Confidence % Header Confidence | It shows the content confidence level as well as the header confidence level calculated based on different criteria that you defined while configuring the system data elements. |
| Data Elements | It shows the counts for data elements detected in the discovery scans. |
| Schema Table | It shows the schema and tables scanned in the discovery scans. |
| Data System Instance | It shows the data system and its relevant instance that you used in the discovery scan. |
| Database Name | It shows the database(s) scanned in the discovery scan. |
| Data System Location | It shows the data system's location. |
| Unique ID | Unique ID represents if the column is marked as a primary identifier. In the Structured Data Discovery dashboard, the unique ID represents the Personal Identifier (PI) column on the Table Training page. ![struUniqId.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ffc77c2f-f706-d260-faf7-3abe74fc427d.png) |
| Masked | It shows whether Securiti masks the column, because a Data Access Control policy applies to it. For more information, see [Using Data Access Control Policies](/latest/docs/access-control-policies). |
| Owner | It shows the owner who initiated the discovery scans. |

The following table describes each entity of the **Tables** tab.

| Entity | Description |
| --- | --- |
| Table Name | It shows the tables scanned during the discovery scan. |
| Cataloged | It shows whether this table has been registered to the Enterprise Data Catalog if configured in the discovery scans. |
| Content Profiles | It shows the content profile associated with this table. There can be more than one content profile associated with a table. |
| Exact Data Profile | It shows the exact data profile associated with this table. |
| Data System Instance | It shows the data system and its relevant instance that you used in the discovery scan. |
| Database Name | It shows the database that you used for scanning in the discovery scan. |
| Data Elements | It shows the data elements count calculated in the discovery scan. |
| Schema | It shows the schema that you used for scanning in the discovery scan. |
| Columns with Classification | It shows the counts for classified columns from tables. |
| Data System Location | It shows the data system's location. |
| Owner | It shows the owner who initiated the discovery scans. |

The following table describes each entity of the **Schemas** tab.

| Entity | Description |
| --- | --- |
| Schema Name | It shows the schema that you used for scanning in the discovery scan. |
| Data System Instance | It shows the data system and its relevant instance that you used in the discovery scan. |
| Database Name | It shows the database that you used for scanning in the discovery scan. |
| Data Elements | It shows the data elements count calculated in the discovery scan. |
| Tables with Classification | It shows the counts for classified tables in the discovery scan. |
| Columns with Classification | It shows the counts for classified columns from tables. |
| Data System Location | It shows the data system's location. |
| Owner | It shows the owner who initiated the discovery scans. |

The following table describes each entity of the **Databases** tab.

| Entity | Description |
| --- | --- |
| Database Name | It shows the database that you used for scanning in the discovery scan. |
| Data Elements | It shows the data elements count calculated in the discovery scan. |
| Data System Instance | It shows the data system and its relevant instance that you used in the discovery scan. |
| Schemas with Classifications | It shows the counts for classified schemas in the discovery scan. |
| Tables with Classifications | It shows the counts for classified tables in the discovery scan. |
| Columns with Classifications | It shows the counts for classified columns from tables. |
| Data System Location | It shows the data system's location. |
| Owner | It shows the owner who initiated the discovery scans. |

You can filter the view of your data with the **Filters** panel on the right side of the page.

![Database table displaying marital status data elements and content profiles for filtering.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filterforclassicstructureddatadiscovery.png)

#### Using content profile filters

You can filter columns and tables by content profile using the **Columns Content Profile** and **Content Profile** filters. These two filters operate at different levels and return different results:

- The **Columns Content Profile** filter shows only the columns where that content profile is directly assigned, giving you a precise, column-level view.
- The **Content Profile** filter operates at the table level and returns all tables with that content profile enabled, including only the columns that directly contribute to that table's overall content profile.

> [!WARNING]
> Important
> 
> This behavior applies only to data scanned in Securiti release 1.149 or later. For the previously scanned data, the **Content Profile** filter continues to show all the columns in the table.

You can resize the width of columns under each tab of the **Columns**, **Tables**, **Schemas**, and **Databases** tab. Move the cursor to the edge of the column, then click and hold the left mouse button. Further, drag the cursor to the left or right to adjust the width of the column and release the mouse button.

![stru_tav_view_filters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-24e31e80-b839-afee-53a8-465b333593fa.png)

To download your structured data dashboard' content, click **Export as CSV**, as shown below.

![stru_tab_view_export.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b68d3b9-f71d-b193-08d2-04c8eb762a8b.png)

Securiti emails you a link you can use to download the file.

You can choose the relevant option according to your environment from **System Settings** > **Organizational** > **General**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/SettingsZipFromats.png)

### Registering Assets with the Data Catalog

You can register Tables, Schemas, and Databases with the Data Catalog to make them discoverable and governed within Enterprise Data Catalog.

1. Select one or more Tables, Schemas or Databases that you want to register, and click **Register with Data Catalog**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1RR0V1JC.png)
2. In the **Register with Data Catalog** popup, choose how selected entities should be handled:

| Options | Description |
| --- | --- |
| Add and Update all selection | Registers new entities and updates existing ones in the Data Catalog. |
| Add selections if not present | Registers only entities that do not already exist in the Data Catalog. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NJQY4NX8.png)
3. Enable **Add Dataset in lower case** to register all entities using lowercase URNs in the Enterprise Data Catalog, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9J5B2PSY.png)
4. Select a **Default Governance Status** to apply to all metadata ingested during this scan, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-J2N3WVMA.png)
5. Select the **Environment** that you want this scan to be associated with, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-99LURKS1.png)
6. Add metadata such as **Description**, **Links**, **Tags**, **Glossary Terms**, **Owners**, **Domain**, as shown below.

| Tabs | Description |
| --- | --- |
| Description | Add a textual description for the asset |
| Links | Add URLs with optional labels |
| Tags | Assign tags for classification and discovery |
| Glossary Terms | Associate business glossary terms |
| Owners | Assign owner(s) and owner types |
| Domain | Assign the asset to a business domain |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CQUY5U32.png)
7. Click **Save and Register with Data Catalog** to complete the registration process, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8V2CDX9N.png)

### Viewing CLOB and Encrypted column properties

If you have selected the CLOB scan option from the **Advanced Settings** in the discovery scan configuration, you can see the **CLOB** column and choose it from the **Column Selector**. You can also see the **Encrypted** column in the **Column** entity grid. You can also use filters to set **CLOB** and **Encrypted** properties to `Yes` to view these columns.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(311).png)

The following is a sample of CLOB and Encrypted column data that you may see on the Structured Data Discovery dashboard.

![sdev1CLOBEncryptedData.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ca9158c-02e3-8e8a-7941-4ea8070bec01.png)

> [!NOTE]
> **Note**
> 
> - You can manually edit the **CLOB** and **Encrypted** column properties in the [Structured Data Discovery New Experience](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience), make sure you have enabled the Data Command Graph for your Securiti tenant.
> - For Sovereign deployments, you can edit these properties in the **Table Training** for your relevant data system. For more information, see the [Table Training for Structured and Hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).

### Exporting the Structured Data Discovery dashboard to a CSV file

This section describes how to export the structured dashboard to a CSV file. This file includes everything that you select from the filter panel. To do so:

1. From the **Columns**, **Tables**, **Schemas**, or **Databases** tab, click **Export as CSV** to export the dashboard content to a CSV file.

![stru_tab_view_export.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b68d3b9-f71d-b193-08d2-04c8eb762a8b.png)
2. To limit the export content, use the filter panel. Securiti sends you an email when the file is available to download. The email with the download link may take a few minutes, depending on the number of records.

> [!NOTE]
> **Note**
> 
> - There is a limit to export up to a maximum of 15 million records in each CSV export of the structured data dashboard.
> - This CSV export limit applies to all CSVs, Columns, Tables, Schemas, and Databases.

### Navigating to the data system's Table Training tab

When you click an entry from the Columns, Tables, Schemas, or Databases tab, Securiti redirects you to the relevant data system's **Table Traning** tab. To learn more about Table Training, see [Table training for structured data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).

### Geographical locations

You can view all structured data centers located on various global sites with the count of different stats.

> [!NOTE]
> **Note**
> 
> You can resize the width of columns under the **Data Elements Distribution By Data Locations** grids. Move the cursor to the edge of the column, then click and hold the left mouse button. Further, drag the cursor to the left or right to adjust the width of the column and release the mouse button.

### Data elements distribution

Next, are the two grids showing you the data element and data system-wise distribution of data elements with their counts from columns, schemas, tables, and databases.

> [!NOTE]
> **Note**
> 
> You can resize the width of columns under the **Data Elements Distribution By Data Element Types** and **Data Elements Distribution By Data Systems** grid. Move the cursor to the edge of the column, then click and hold the left mouse button. Further, drag the cursor to the left or right to adjust the width of the column and release the mouse button.

### Exporting the Structured Data Discovery dashboard to a PDF file

This section describes how to export the structured dashboard to a PDF file. This file includes everything that you select from the filter panel. To do so:

1. To export the entire content of the structured data dashboard, from the upper right corner, click **Export PDF**. You can apply filters from the filter panel to limit the dashboard content.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(312).png)
2. Securiti sends you an email when the PDF file is available to download.

### Registering data system names to lowercase URNs in the data catalog

You can register the data systems, datasets, tables, and columns in lowercase Uniform Resource Names (*URNs*) in the enterprise data catalog. To do so:

1. In **Sensitive Data Intelligence**, choose **Data Explorers** > **Structured Data Discovery**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(309).png)
2. Scroll down to the tabular view of streaming data and select the **Tables** tab.
3. Select the desired table(s) from the list.
4. Mark **Add or Update all selections** option to add a new table or update all table selections, or mark **Add sections if not present** to add a new table.
5. Mark the **Add Dataset in lower case** checkbox to add the structured datasets to the data catalog in lowercase Uniform Resource Names (URNs).

> [!NOTE]
> **Important**
> 
> Make sure to keep the following points in mind while registering the data systems, datasets, tables, and columns to the data catalog in lowercase URNs:
> 
> - If you want to avoid discovering duplicate URNs in the data catalog, always remember the **Add Dataset in lower case** checkbox option used in the **Responses** area of discovery scan jobs. In case you enabled it in the discovery scan, enable this option from the structured or streaming data dashboard as well.
> - If you have not enabled the **Add Dataset in lower case** checkbox option from the discovery scan job, you don't need to enable it from the structured or streaming data dashboard as well.
> - To avoid discovering duplicate URNs, you must recall the option used in the older discovery scan job for this particular dataset. In case you do not remember that, follow the steps below:
>   1. Grab the data system name from the streaming or structured dashboard.
>   2. Go to the data systems, search for that data system, and open its instance.
>   3. Click the corresponding discovery scan job to open it, check the option from the **Responses** area, and note this option to enable it from the structured or streaming data dashboard.
> - To avoid any mistakes, before running the discovery scan job, you can always enable or disable the **Add Dataset in lower case** option in the discovery scan, depending on your requirements. If you mistakenly enable or disable it in the discovery scan, you can always enable or disable it only if the job was never run.
> - If you enable the **Add Dataset in lower case** option, run the discovery scan job, and later decide to disable it, you must delete the first job and create a new job. The same is true for vice versa.

- From the **Default Governance Status** menu, select the appropriate status for the metadata being ingested.

You can select one of the following governance statuses for the metadata:

| Default governance status | Description |
| --- | --- |
| None | The dataset does not have a defined governance status. |
| Draft | The dataset is in the initial stages of creation or modification. |
| Under Review | The dataset is being assessed, evaluated, or scrutinized for accuracy, quality, and compliance. |
| Certified | The dataset has undergone a thorough evaluation, meets established standards, and is approved for broader use. |
- (Optional) In the Responses area, to extract your unstructured schema in CSV or JSON format and register it to the Enterprise Data Catalog, mark the **Extract and register schema** checkbox.

## Related

- [Structured Data Discovery New Experience dashboard](/structured-data-discovery-new-experience.md)
- [Viewing scan results](/viewing-discovery-scan-results.md)
