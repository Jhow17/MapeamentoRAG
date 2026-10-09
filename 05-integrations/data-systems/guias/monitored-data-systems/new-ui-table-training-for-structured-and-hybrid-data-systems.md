---
title: "Table training for structured and hybrid data systems"
slug: "new-ui-table-training-for-structured-and-hybrid-data-systems"
updated: 2026-04-06T10:28:32Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/new-ui-table-training-for-structured-and-hybrid-data-systems"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Table training for structured and hybrid data systems

> [!WARNING]
> **Important**
> 
> - We do not recommend you skip **Table Training** for accurate data classification and compliance. However, you can advance the connector directly to the scanning state.
> - If the new UI is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Table Training is a post-connector authentication process for structured and hybrid data systems that enable efficient identification and classification of data elements, particularly personal data. Table training shows you a representative sample of rows from the tables and uses machine learning to make initial guesses that help you visualize and understand what personal data you have and where. You can evaluate and refine the guesses by editing the data element types to ensure accurate data classification.

### View Table Training

1. If you have not already done so, authenticate the connector for the [structured or hybrid](/latest/docs/supported-data-system-connectors-in-securiti) data system.

After the data system connector activation, Securiti scans the data system to learn its schemas and tables.
2. On the left sidebar of your data system instance, under the **Configuration**, click **Table Training**.

> [!NOTE]
> **Note**
> 
> - If the **Table Training** is disabled, it indicates that the connector has not finished learning schemas yet. Wait for a minute or two, refresh your browser, and try again.
> - The Table Training option appears when you successfully activate the structured or hybrid data system instance for both Self-hosted and Securiti Cloud connectors.

![Overview of integration settings with highlighted Table Training option and feature permissions status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/click-TT.png)

### View schemas, tables, rows, and columns

> [!NOTE]
> **Important**
> 
> Securiti does not support scanning `EXTERNAL TABLE` types, except for the Amazon Athena data system connector. As a result, the row and column counts for `EXTERNAL TABLES` appear as 0 on the Table Training page.

1. Initially, you see the zero number of counts for rows and columns.

![Salesforce integration settings showing no data available in the table training section.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/0-row-column.png)

Post authentication, the **Table Training** page shows the list of tables without row and column count. You can see the rows and columns when the data system completes the learning phase or discovery scan, depending on the connector type.
  - For Self-hosted connectors, you must complete a discovery scan to see the rows and columns count as learning is performed through discovery scans.
  - For Securiti Cloud connectors, the data system must complete the learning phase.

When the data system learns or discovers the data, the **Table Training** page shows the number of rows and columns. See the example below for one of the Microsoft Dataverse instances.
2. On top of the Table Training page, click the **v** (down arrow) icon to see the **Schemas, Tables, and Views.**
  1. Click **Tables and Views** to see the list of tables attached to their Schemas.
    - Tables are linked to their respective Schemas. In this case, the data system does not contain any schema. You see **public** schema as a parent to all the tables in the list.

![Overview of Microsoft Dataverse settings with highlighted schemas and columns information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/public-schema.png)
    - If schemas exist in the data system, you can see the tables attached to the respective Schemas as shown below.

> [!NOTE]
> **Note**
> 
> The schema name generation varies in different data system instances.

![Database integration interface showing table training and column details for ai_classification_test.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tt-table-r-c.png)
3. See the number of rows and columns under each table.

> [!NOTE]
> **Note**
> 
> Row counting for a few data systems is not supported either due to the data system's inability to provide this data or the performance impact Securiti would cause on the data system by counting rows. See the list of connectors that don't support row counting:
> 
> - NetSuite (Self-Hosted)
> - Azure Synapse (Self-Hosted)
> - Apache Hive
> - Zendesk (Self-Hosted)
> - Microsoft Dynamics 365 CRM (Suite) (Self-Hosted)
> - Cassandra (Self-Hosted)
> - Google Bigtable
> 
> ![Overview of Google BigTable integration with highlighted table training options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/NA-rows.png)
4. On the right side under the **Column Name**, see the list of columns that exist in the single table.
  1. To view a list of columns in each table, click any table on the top under **Tables & Views**, as shown below.

![Overview of Microsoft Dataverse showing table columns and data elements for configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/column-list.png)
  2. Repeat the same step for each table to see the number of columns.

### Error rectification

- Check for errors marked by red dots or triangles, and hover over the errors for details. If necessary, address the errors in your tables and schemas, then start table training.
- In some cases, you may see a Learn Failed error as shown below. Click **Relearn Table with Discovery Scan** to re-learn just that table without having to re-learn the entire database.

> [!NOTE]
> **Note**
> 
> Securiti relearns only failed tables and not the ones which were successfully learned in previous scans.

### Verification and manual classifications

Table Training lets you verify and classify the column's attributes for effective data classification.

#### 1. Verifying Primary Keys

For each table, identify the Primary Key(s) used in table join operations. Securiti uses this information to correctly query the table and any related tables for personal data when it collects information to fulfill DSR requests.

When Securiti does its initial scanning, it makes a guess at which column (if any) is a primary key and marks its checkbox. During table training, you verify or correct this guess.

Although tables can have multiple Primary Keys, they usually have only one, and it is most often the first column in the table.

Once you have identified the Primary Key column (if any) for the table, mark its **PK** checkbox as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(605).png)

#### 2. Verifying primary identifiers

For each table, identify the primary identifiers that uniquely identify a data subject. When Securiti does its initial scanning, it guesses which column (if any) is a primary identifier and marks its checkbox. During table training, you verify or correct this guess.

Once you have identified the primary identifier column (if any) for the table, mark its Primary Identifier (**PI**) checkbox as shown below.

When configuring joins for multiple tables in Data Subject Rights (DSR), ensure one table contains the Primary Identifier (**PI**) to retrieve data from all the tables.

> [!NOTE]
> **Important**
> 
> When configuring joins for multiple tables in [Data Subject Rights (DSR)](/v1/docs/using-data-subject-rights-1), ensure one table contains the Primary Identifier (PI) to retrieve data from all the tables.

#### 3. Matching clob and encrypted column property

If you enabled the **CLOB** scan option from the **Advanced Settings** in the discovery scan configuration, or if the field classification during the discovery scan identified a column with an encrypted type property, then the following column properties are marked in the Table Training section:

- Clob
- Encrypted

These columns are automatically marked on table training page if identified as column property during field classification in discovery scan. If you don't see any column as marked correctly, mark the clob or encrypted column by editing the columns.

#### 4. Matching and classifying data element type

When Securiti scans your database tables, it uses machine learning to make guesses about which columns contain data element types such as first names, last names, phone numbers, etc. Before you use Securiti to process DSR requests for the data source, you must check, and where necessary correct, the guesses.

For each table, match and manually classify the data element types by following these steps:

1. Under the **Data Element Type**, match the column names with the data element types.

For exact matching of column names with the data element types, consider the following:

> [!NOTE]
> **Note**
> 
> If the Data Element Type column is empty, it probably means that Securiti has not finished classifying the table contents. Wait a minute or two, then refresh your browser and try again.
  - If the Securiti column name matches with the data element type field that it should not match, this is classified as overmatch. Look for the correct data element from the data element type field for exact matching.
  - If the Securiti column name does not match with the data element type field that it should have, this is classified as undermatch. Look for the correct data element from the data element type field for exact matching.
2. In case columns don’t match, you can change the data elements to match correctly. For manual classification, enable the edit mode, and click the plus sign (+) to choose the relevant data element from the list.
3. On the **Add Data element | Data Elements** popup:
  1. Select the **Data Element type** from the menu that matches the column name.
  2. Click Add **Data Elemetns | Data Elements** to save the manual classification.

#### 5. Verifying and configuring joins

For all tables, identify the joins (foreign key links) that relate the table to any other tables. Securiti uses this information to correctly query the table and any related tables for personal data when it collects information to fulfill DSR requests. When Securiti does its initial scanning, it reads the joins from the metadata for each table.

It helps Securiti correctly parses the relationships between the personal data systems in different tables. For more information, see [Verify its joins, and configure any additional joins](/v1/docs/verifying-and-configuring-joins).

### Reviewing sample data from tables

On the table training page, you can preview the sample data from the database tables that you used for classification. This is to make sure that your classification produces accurate results.

To preview sample data:

1. From the top row of options, click **Preview Sample Data**.

> [!NOTE]
> **Note**
> 
> If the **Preview Sample Data** button is disabled, it can be due to the following reasons:
> 
> - You don’t have either `View Data Evidence` or `View Evidence for Owned Connectors` permissions under the SDI module. For more information, see [Sensitive Data Intelligence RBAC permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).
> - Data system learning is still in progress.
> - Store Sample Data option is disabled in the Discovery scan.

If **Preview Sample Data** button is disabled due to Store Sample Data option, perform the following steps to enable it:

> [!NOTE]
> **Note**
> 
> To view the discovery scan related to the current database tables, click **View Corresponding Discovery Scan**. Securiti takes you to the relevant discovery scan configuration page.
  1. On the top right, click **View Corresponding Discovery Scan**.
  2. From the **Discovery scan details** page, mark the checkbox for **Store Sample Data.**
  3. Save the discovery scan configuration.
  4. You can navigate back to the data system **Table Training** page to see the enabled **Preview Sample Data** option.
2. On the **Preview Data Sample** popup, you can see the path or sample data depending on the storage.
  - Securiti normally stores sample files data in pods. On the **Preview Data Sample** popup, you see the path of pod node where sample file is stored, as shown below.

> [!NOTE]
> **Important**
> 
> Securiti doesn't support Preview Data Sample if you have configured EPod V2 for your structured or hybrid data system. For EPod V2 deployments, Preview Data Sample support is only available if PCS is configured in your tenant.
  - In the case of files stored on private cloud storage, Securiti encrypts the Data Sample and decrypts it to show the **Data Sample Preview** popup, as shown below.

> [!NOTE]
> **Note**
> 
> Securiti now excludes evidences from the sample file data if you have excluded it from Data Elements in Sensitive Data Intelligence.
    - You can also download the sample data from **Data Sample Preview** popup using Signed URLs if you have enabled the **Evidence Download** and disabled **Enforce Signed Headers for Evidence Validation** option in General tenant-level settings. For more information, see [Configuring General Settings](/latest/docs/system-settings-configuring-securiti-general-settings).
      - To download the sample data, on the top right of the **Data Sample Preview** Popup, click **Download**. it downloads the entire table selected for sample in structured data systems.
  - In case of any validation error, Securiti still shows you an encrypted file that can be downloaded.

### Viewing the percentage of scanned rows

To view your desired level of scanned data count (percentage of scanned rows), use the **Data Count Percentage** from the filter panel.

See the **Data Count** column for rows scanned out of total rows, that show the percentage of scanned rows.

### Post Table Training steps

After you do the table training, click **Initiate data scan** for Securiti cloud connectors. Securiti then scans all rows of the tables of interest and builds an inventory of identities that helps you visualize and understand what personal data you have and where.

As a result, the **Data Elements** column in Sensitive Data Intelligence’s **Structured Data Explorer** also shows an estimated count for these connectors as it is a product of the estimated row count and the number of data elements discovered in a column.

(Optional) For Securiti Cloud data systems, you can use the **Scan Statistics** tab to view additional data. It shows you the table training status and displays a progress bar for the following:

- Rows Classified
- Total Data Classified

![scan-stat.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2bfc96ba-734b-0c93-060a-604ffdb4f957.png)
