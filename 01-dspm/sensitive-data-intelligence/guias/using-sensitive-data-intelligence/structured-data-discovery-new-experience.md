---
title: "Structured Data Discovery New Experience dashboard"
slug: "structured-data-discovery-new-experience"
updated: 2026-09-09T08:29:45Z
published: 2026-09-09T08:29:45Z
canonical: "helpcenter.securiti.ai/structured-data-discovery-new-experience"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Structured Data Discovery New Experience dashboard

Securiti's Structured Data Discovery dashboard offers a unified view to review and edit classifications results across structured data systems such as MySQL, SQL Server, and Snowflake. It features an enhanced interface and a streamlined validation process for efficient management of sensitive data and classifications.

In the new dashboard:

- You can use a single view to explore structured data systems, including their columns, tables, schemas, and databases, with additional context such as regions and data element nodes to support deeper insights and analysis.
- For each resource type, you can view key information such as identified data element counts, asset types, content profile counts, and more, all associated with different structured data system tables.
- You can review classifications and view sample data to verify the accuracy of detected data elements and ensure proper classification within your structured data systems.
- You can view and download evidence files to examine the data that triggered classifications, helping validate classifications.
- You can apply or associate content profiles to the columns of tables to classify and manage sensitive data more effectively within your structured data systems.
- You can view the relationships between columns, tables, schemas, and databases and other entities such as data systems and cloud systems, providing a comprehensive understanding of your data's structure and lineage.

> [!NOTE]
> Note
> 
> It’s a premium feature that is available on a subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.

To open the Structured Data Discovery dashboard, in Securiti's **Sensitive Data Intelligence** module, choose **Data Explorers** > **Structured Data Discovery**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(309).png)

To switch to the new dashboard, click **New Experience**.

Choose an entity from the left panel to view its details in the table on the right side.

![Overview of structured data discovery with database and column statistics displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-01 at 3.52.56 PM(1).png)

| Data | Column | The **Column** entity shows the column counts as well as the result of column classification. > [!NOTE] > Note > > The **Data Elements** column displayed under the **Columns** entity may show `0` even when **Data Element Types** are detected for the same column. > > It is because **Data Element Types** are detected based on the column name and metadata, so they can appear even when no rows were scanned. Whereas, the **Data Elements** count reflects detections found during row sampling and it displays `0` if no rows were scanned for a column. |
| --- | --- | --- |
| Table | The **Table** entity shows the table count as well as the result of tables scanned during the discovery scan jobs. |
| Database Schema | The **Database** Schema entity shows the database schemas' counts as well as the results of the database schemas scanned during the discovery scan jobs. |
| Database | The **Database** entity shows the database counts as well as the results of the databases scanned during the discovery scan jobs. |
| Structured | This **Structured** entity shows the assets associated with structured data systems, security posture findings, the volume of data records, objects, and PD attributes (data elements), and so on. |
| Management | Region | The **Region** entity shows the regions where your data systems and database schemas, and tables are stored, with their counts. |
| Data Classification | Data Elements | The **Data Classification** category provides data elements and content profiles detected during the discovery scan jobs. |

To learn more, refer to the following table.

| [Filtering data in grid](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#filtering-data-in-the-grid) | [Using trendlines and changing metrics](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#using-trendlines-and-changing-metrics) | [Customizing the visible columns](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#customizing-the-visible-columns) |
| --- | --- | --- |
| [Viewing Relationships in Graph Explorer](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#viewing-relationships-in-the-graph-explorer) | [Reviewing and editing classification (previously Table Training)](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#reviewing-and-editing-classifications) | [Registering Tables, Schemas, and Databases to EDC](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#registering-tables-schemas-and-databases-to-the-enterprise-data-catalog-edc) |
| [Viewing and downloading Evidence Files](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#viewing-and-downloading-evidence-files) | [Viewing and editing CLOB and Encrypted column properties](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#viewing-and-editing-clob-and-encrypted-column-properties) | [Enabling and disabling extensive graph queries](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#enabling-and-disabling-expensive-graph-queries) |
| [View reviewed and validated columns in Validation Workbench sessions](https://helpcenter.securiti.ai/docs/structured-data-discovery-new-experience#viewing-reviewed-and-validated-columns-of-a-validation-workbench-session) |  |  |

#### Using the Structured Data Discovery dashboard

This section provides instructions for filtering, trendlines, and customizing the visible columns.

#### Enabling and disabling expensive graph queries

The Structured Data Discovery New Experience features an **Activate Graph Metrics** toggle to optimize page load performance. With this control, Securiti disables automated graph metric calculations by default for tenants with large volumes of metadata. You can load this detailed data on-demand for your current session by enabling the **Activate Graph Metrics** toggle, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(284).png)

> [!NOTE]
> Note
> 
> - The **Activate Graph Metrics** toggle is designed as a performance optimization for tenants with very large data volumes. For all other tenants, the toggle is hidden, and graph metrics remain enabled by default.
> - Enabling this toggle for tenants with very large data volumes can result in slower page load times.

Once activated, these additional columns become available in the **Column Selector.** A purple vertical indicator next to these metrics highlights them as on-demand graph metrics.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(285).png)

#### Filtering data in the grid

Securiti lets you view a fixed number of entities in the form of nodes on the Structured Data Discovery dashboard that best represent the underlying data.

1. Click the plus sign (**+**) to create a new quick filter.
2. On the popup, choose an entity to view properties associated with it. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(286).png)
3. Next, choose the relevant operator to choose the right criteria, then click **Apply**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(287).png)

For example, if you want to choose **Table** for **MySQL** data system, you can choose **Table** > **Data Systems** > **MySQL** and click **Apply**. You can see the list of tables scanned for the MySQL data system with counts (6k) and relevant attributes in the form of a table on the right side. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(288).png)

> [!NOTE]
> **Note**
> 
> - When you choose **Data Systems**, choose **Asset Type** or **Asset Name** to view your relevant data system.
> - You can choose the **Discovery Scan** and the **Discovery Scan Job** entities, alongwith their relevant properties, to view results of various discovery scans.
> - You can choose the **Discovery Scan** and the **Discovery Scan Job** entities, alongwith their relevant properties, to view results of various discovery scans.
> - You can choose the **Discovery Scan** and the **Discovery Scan Job** entities, alongwith their relevant properties, to view results of various discovery scans.
> - You can choose the **Discovery Scan** and the **Discovery Scan Job** entities, alongwith their relevant properties, to view results of various discovery scans.

You can see the tables scanned for the MySQL data system with counts (6k) and relevant attributes in the form of a table on the right side.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(289).png)

From the top left side, you can click the plus sign (+) to use actively available filters, such as types of data elements, data systems, tables, schemas, and columns. Different operators are available for each filter type.

- is one of or is not one of
- is equal to or is not equal to
- between
- greater than or less than
- less than or equal to
- greater or equal to
- contains or does not contain
- starts with or does not start with
- empty or is not empty, and so on

Some of these filters show a list of options, such as data systems or data elements available in the system.

**Example 1**

To view classified tables between 5 and 10, see below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(290).png)

**Example 2**

To view tables with columns less than or equal to 100, see below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(291).png)

To save the custom filters applied, click **Save View**.

1. 
  1. You can save the customer filter under an existing group or save it in a new group. When you click **Save View**, you can see a popup to add a group, press **Enter** to add a new group, followed by adding its name, filter name, and then click **Save View**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(292).png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(293).png)
  2. To view already created filters, click **Saved Views**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(294).png)
2. To clear applied filters, click **Clear Search**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(298).png)

#### Using trendlines and changing metrics

On the very top of the dashboard, you can see a few trendline widgets that you can use to view stats on a trendline for the past 30 days to 12 months.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(297).png)

You can choose an option to view the relevant trendline.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(299).png)

On the left panel, view the entities for structured data. These include:

| Entity Group | Entity Name |
| --- | --- |
| Data | Table |
| Database Schema |
| Structured Database |
| Discovery Scan |
| Discovery Scan Jobs |
| Structured |
| Management | Region |
| Data Classification | Data Element |
| Content Profile |
| Exact Data Profile |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(300).png)

Expand each category to view entities and their details in the table on the left side.

#### Customizing the visible columns

You can include or exclude the columns from the **Column Selector** on the right side of the table.

1. To include or exclude columns from the dashboard table, click the **Column Selector** entity grid.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(301).png)

If additional columns are available, scroll left or right to view them. Examples of available columns include:

> [!NOTE]
> Note
> 
> Securiti shows a column as **Masked** if a Data Access Control policy applies to it. For more information, see [Using Data Access Control Policies](/latest/docs/access-control-policies).
  - Data Type
  - Data Element Type
  - Column Name
  - Data Element
  - Data System Type
  - Database
2. Choose your relevant column to include or exclude and click **Apply**.

#### Using the Last Scan and Last Modified At filters and column properties

You can use the **Last Scan** and **Last Modified At** filters to view column data relevant to specific scans.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(302).png)

#### Viewing reviewed and validated columns of a Validation Workbench session

If you have reviewed columns from your database tables in Validation Workbench, Securiti lets you see them in the Structured Data Discovery dashboard.

To view reviewed and validated columns, apply the **Session ID** filter from the **Columns** quick filters on the upper-left side of the page. This displays column data along with the associated **Session ID** and **Session Name** from the relevant Validation Workbench session.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(303).png)

For more information, see [Using the Validation Workbench to review and validate classifications](http://using-the-validation-workbench-to-validate-classificationsprivate-preview.html).

#### Viewing and editing CLOB and Encrypted column properties

If you have selected the CLOB scan option from the **Advanced Settings** in the discovery scan configuration, you can see the **CLOB** column and its data on the Structured Data Discovery dashboard New Experience under the **Column** entity grid. It also shows the **Encrypted** column on the Structured Data Discovery New Experience under the **Column** entity grid. If these columns are not displayed on the dashboard, you can choose them from the **Column Selector**. This helps you identify **CLOB** and **Encrypted** data elements discovered during discovery scans. You can also use quick filters to set **CLOB** and **Encrypted** properties to `True` to view these columns.

To enable the CLOB scanning:

- In Discovery Scans, see the [Discovery Scans for Structured Data Systems](/v1/docs/discovery-scans).
- Alternatively, in the Table Training page, see the [Table Training for Structured and Hybrid data systems](/v1/docs/table-training-for-structured-and-hybrid-data-systems).

You can also use filters to set **CLOB** and **Encrypted** properties to `true` to view these columns.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(304).png)

The following is a sample of **CLOB** and **Encrypted** column data that you may see on the Structured Data Discovery dashboard.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(305).png)

#### Editing the CLOB and Encrypted column properties

To edit these properties:

> [!NOTE]
> **Note**
> 
> - To manually edit the **CLOB** and **Encrypted** column properties in the Structured Data Discovery New Experience, make sure you have enabled the Universal Data Explorer for your Securiti tenant.
> - For Sovereign deployments, you can edit these properties in the **Table Training** for your relevant data system.

1. From the **Column** entity, choose one or multiple columns, and click **Review Classification**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(306).png)

It opens the **Review Classification** popup as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(307).png)
2. On the above popup, you can see some of the column entries are already marked. To edit the **CLOB** and **Encrypted** column entries, you can manually mark or unmark the required column entries.

#### Reviewing and editing classifications

For the entity you have selected, click an entry from the list.

> [!WARNING]
> Important
> 
> - Securiti fetches sample data in the Review Classification modal, using pre-signed URLs for enhanced security.
> - A maximum of 30 sample rows per column is available for review to provide an high-level overview of the sample data.

Click ​**Review Classification**​​ (previously Table Training) from the popup.

![sdev2revieClassificationExplore.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e4f1e22-b6d9-a1c0-e4dc-2b0d1bbb9823.png)

Alternatively, select multiple checkboxes to perform a bulk edit. This enables the **Review Classification** option. Click **Review Classification**.![Overview of structured data discovery with highlighted review classification option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-09 at 3.20.01 PM.png)

On the **Review Classification** popup, you can see the classification results with the data elements identified after classification.

![Database columns overview with highlighted access time and content profiles for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reviewclassification_structureddatadiscovery.png)

You can also see **No match found** entries for some of the **Column Names** under the **Data Element Type** column. To perform the reclassification, choose a relevant data element from the **Data Element Type** column, then click **Apply & Save Selection**.

![Data management interface displaying columns, search options, and authentication settings for databases.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assigndataelement_reviewclassification.png)

For CLOB columns, you can also manage content profiles directly from the **Review Classification** modal. Select or update the content profile from the **Content Profile** column against the relevant CLOB column and click **Apply & Save Selection**. Any changes to the content profile at the column level are automatically reflected at the table level.

![Database column selection interface showing various content profiles and options for filtering.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assigncontentprofiles_reviewclassifications.png)

You can also apply content profiles on a table level:

![Database column overview with highlighted access time and content profiles for selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/assigncontentprofilesontable_reviewclassifications.png)

To review sample data, click **View Sample Data** (previously **Preview Sample Data** on the Table Training page). From the **Review Classification** page, you can view sample data in line with the column that you are reviewing.

> [!WARNING]
> **Important**
> 
> You are authorized to view sample data for column(s) under the following conditions:
> 
> - You must have Data System Owner permissions for the data system that contains the column(s) you are viewing. This ensures you have the required access to manage or review those columns.
> - The data system must belong to one of the organizations you have selected, ensuring access is limited to authorized organizational contexts.

For more information, see [Private Cloud Storage documentation](/v1/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> **Note**
> 
> Any updates to the content profiles or data element type attributes are automatically reflected in the Enterprise Data Catalog (EDC), ensuring consistency and up-to-date metadata across the platform.

You can also apply filters by selecting multiple data elements. Click **Add** (plus icon) next to a data element to add it to the filter. Then click **Apply Filter** to filter columns for the selected data elements only.

#### Understanding and using content profile filters

Securiti lets you identify which columns directly contributed to a table's content profile classification. You can filter columns and tables by content profile using the **Columns Content Profile** and **Content Profile** filters:

- The **Columns Content Profile** filter shows only the columns where that content profile is directly assigned at the column level.
- The **Content Profile** filter operates at the table level and returns all tables with that content profile enabled, including only the columns that directly contributed to that table's overall content profile.

> [!WARNING]
> Important
> 
> - This behavior applies only to data scanned in Securiti release 1.149 or later. For the previously scanned data, the **Content Profile** filter continues to show all the columns in the table.

Use the following examples to understand when to use each filter:

- If you want to view all the columns in a table, apply the **Table Name** filter without any reference to content profiles.

![Overview of student records database with highlighted columns and data classification details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/nocontentprofilefitlerenabled_structureddatadiscovery.png)
- If you want to find all the tables with that content profile enabled, apply the **Content Profile** filter.

![Overview of structured data discovery with selected content profiles and table details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tablesreturnedbycontentprofile_sdev2.png)

It also returns all the columns that directly contributed to that table's overall content profile

![Data discovery interface showing columns, data types, and classifications for sensitive information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnsreturnedbycontentprofile_sdev2.png)

> [!NOTE]
> Note
> 
> - Column(s) may appear under the **Content Profile** filter even if that content profile is not directly assigned to it, as shown below. This means the column contributed to the table's overall content profile classification in combination with other columns in the same table. The content profile is evaluated at the table level, not the individual column level.
> 
> ![Overview of structured data discovery with highlighted columns and classifications for student records.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/indirectlycontributingcontentprofiles.png)
> 
> - For CLOB columns, only natively assigned content profiles are visible at the column level. If a CLOB column appears under a table-level content profile filter without that profile listed natively, the column contributed to the table's content profile in combination with non-CLOB columns.
- If you want to view columns with a content profile natively assigned, use the **Columns Content Profile** filter for a precise, column-level view of content profile assignments.

![Data discovery interface showing selected columns and their classifications for student records.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/columnscontentprofilefilter.png)

#### Viewing metadata and sample data

To view metadata and sample data:

1. In the Review Classification popup, from an entry of your choice, click **Show Metadata**.

![Database column names and data types displayed in a user interface for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(281)(2).png)
2. Choose the **Metadata** or **Sample** **Data** tab as per your choice.

![Database column details including names, types, and data systems for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(279)(2).png)

In the **Metadata** tab, you can see the discovery scan metadata, while in the Sample Data tab, you can see the classification sample data.

> [!NOTE]
> **Note**
> 
> To view sample data, you must be the Data Owner.

#### Viewing and downloading evidence files

You can download evidence files directly from the Structured Data Discovery dashboard to verify the accuracy of discovery scans for each data element displayed in the dashboard pop-up.

> [!WARNING]
> Important
> 
> You must meet certain prerequisites to view and download evidence files. For more information, see [Accessing evidence files in Securiti](/latest/docs/managing-evidence-files-and-downloads).

> [!NOTE]
> Note
> 
> You can configure multiple PCS instances in Securiti. Each data system is linked with its own PCS instance, and Securiti automatically uses the correct PCS instance when processing cases.

Choose the **Column** entity and click the **Download Evidence** icon with the down arrow key.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sddv2EvidenceDownloadIcon.png)

Securiti downloads the evidence file in JSON format to your system's **Downloads** folder.

> [!NOTE]
> **Note**
> 
> To view the evidence summary of structured data classification, see Evidence summary for structured data classification.

The following table provides information to view the evidence file path in Structured Data Discovery dashboard, Graph Explorer, and Inventory dashboards.

| Dashboard | Description |
| --- | --- |
| Structured Data Discovery dashboard | 1. In the Structured Data Discovery dashboard, click the plus sign (+) and choose **Evidence File Path** with the operator is not empty. 2. From the **Column Selector**, include the **Evidence file path** property. This shows the evidence file path, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sddv2EvidenceFilePath.png) |
| Graph Explorer | 1. In the Graph Explorer, click the plus sign (+) and choose **Column**. 2. From the **Column Selector**, include the **Evidence File Path** property. 3. From the **Evidence File Path** column, choose the is not empty option. This shows the evidence file path, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(277).png) |
| Inventory | 1. In the Inventory dashboard, click the plus sign (+) and choose **Evidence File Path** with the operator is not empty. 1. From the **Column Selector**, include the **Evidence File Path** property. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(276).png) |

#### Viewing relationships in the Graph Explorer

For the entity you have selected, click an entry from the list. A popup appears with **Review Classification** and **Explore** buttons.

![sdev2revieClassificationExplore.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e4f1e22-b6d9-a1c0-e4dc-2b0d1bbb9823.png)

Click **Explore** to view the relationship between the entities such as Data Element, Column, Table, Schema, Database, Data System, Account, User, Location, Cloud Type, and so on.

![sdev2relationships.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bb09bd90-0f01-b23a-47e3-d3a132edbc05.png)

#### Registering tables, schemas, and databases to the enterprise data catalog (EDC)

Registering for the enterprise data catalog option is available only for tables, schemas, and databases.

Choose an entry from the list of Tables, Schemas, or Databases entities and click **Register to EDC** from the popup. Securiti registers them to the Enterprise Data Catalog (EDC) module.

> [!NOTE]
> **Note**
> 
> Any updates to the content profiles or data element type attributes will automatically be reflected in the EDC.

For more information, see [Discovery scans for structured data systems](/v1/docs/discovery-scans).

## Related

- [Viewing scan results](/viewing-discovery-scan-results.md)
- [Using the Structured Data Discovery dashboard](/using-the-structured-data-discovery-classic-dashboard.md)
