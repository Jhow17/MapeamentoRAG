---
title: "Datasets"
slug: "datasets"
updated: 2026-09-08T21:00:16Z
published: 2026-09-08T21:00:16Z
canonical: "helpcenter.securiti.ai/datasets"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Datasets

**Scenario**

As a data engineer, you need to track and manage datasets across databases, streams, and data lakes. Manually mapping tables, views, and file paths slows integration efforts and risks inconsistency. With EDC’s dataset entity model, you can register and represent all types of data, like tables in Snowflake or files in S3, in one place. This ensures consistent metadata and simplifies data onboarding.

### Prerequisites

To work with datasets, you must have the **Manage Datasets** permission enabled for your account. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

### Structured datasets

Datasets are organized in separate folders based on the data systems. The folders and subfolders take you to a specific table and its details within a dataset.

> [!NOTE]
> **Note**
> 
> You can also include special characters, like “/”, in dataset names, database names, data system names.

Structured data refers to data that is typically stored in well-defined, tabular, or hierarchical structures, such as databases, spreadsheets, or data tables. Examples of structured data include customer information in a CRM database, financial records in an accounting system, product catalog data in the Securiti platform, and so on.

Currently, the following structured data systems are supported in the Enterprise Data Catalog:

- Amazon Athena
- Amazon Aurora for PostgreSQL
- Amazon DynamoDB
- Amazon MSK
- Amazon RDS MariaDB
- Amazon RDS for MySQL
- Amazon RDS for PostgreSQL
- Amazon Redshift
- Apache HBase
- Apache Hive
- Apache Presto
- Apache Trino
- Azure Blob Storage
- Azure Cosmos DB
- Azure Cosmos DB for MongoDB
- Azure Synapse
- Braze
- Cassandra
- Cloudera Impala
- Databricks
- Domo
- Google BigQuery
- Google Cloud SQL for MySQL
- Google Cloud SQL for PostgreSQL
- Google Cloud SQL for SQL Server
- Greenplum
- HP NonStopSQL
- IBM Db2
- IBM Db2 zOS
- IBM Netezza
- InterSystems Cache
- JIRA
- MariaDB
- Microsoft Dynamics 365 CRM (Suite)
- MongoDB
- MySQL
- Oracle
- Oracle Autonomous Data Warehouse
- Oracle Autonomous Transactional
- PostgreSQL
- Power BI Service
- SAP HANA
- SAP SuccessFactors
- SQL Server
- Salesforce
- ServiceNow Tables
- Snowflake
- Starburst
- Teradata
- Zendesk

![Datasets_Main_Page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a12cfd8b-aa97-16dd-db4c-7898367717b6.png)

To explore the dataset:

1. Open **Enterprise Data Catalog**, then choose **Datasets**.
2. Enter a keyword in the search bar to find all the datasets related to that keyword.
3. Click on the data system folder and subfolders to see all the tables inside that folder.

The default preview card of a particular table shows you:
  - Table name
  - Table description
  - Domains
  - Glossary terms
  - Tags
  - Owners
4. Click on a table to see the detailed information.

| Tab Name | Description | Details |
| --- | --- | --- |
| Schema | Schema of the dataset | Field | The data field in the table. The dataset fields are sorted alphabetically. |
| Description | The description of the specific field. You can add **description** directly from the options available at the column level. To add a description, click **+Add Description** and start adding the description for the column. |
| Tags | The tags associated with the data. You can associate **tags** directly from the options available at the column level. To add a tag, click **+ Add Tags** and start associating the tag for the column. |
| Glossary Terms | The glossary terms associated with the data. You can associate **glossary terms** directly from the options available at the column level. To add a glossary term, click **+ Add Terms** and start associating the tag for the column. |
| Governance Flags | The governance flags associated with the data. You can associate **governance flags** directly from the options available at the column level. To add a governance flag, click **+ Add Flag** and start associating the governance flag for the column. |
| Domain | The domain associated with the data. You can associate **domain** directly from the options available at the column level. To add a domain, click **+ Set Domain** and start associating the domain for the column. |
| Properties | Properties extracted from the data source. You can add custom properties to the datasets as well. > [!NOTE] > Note > > The **Properties** tab for datasets ingested via EDC ingestion displays important metadata such as the **Job Name, Database Name,** and I**ngestion Run ID**. These details enhance transparency and make it easier to trace each dataset back to its original source. > > You can search for datasets ingested through EDC using a custom query. In the search bar, enter: > > **/q customProperties:"ingestion_job_name=<your_ingestion_job_name>"** > > Replace **<your_ingestion_job_name>** with the specific ingestion job name, for example, mysql-db. | Name | Name of the property. |
| Value | Data or value of the property. |
| Documentation | Detailed documentation of the dataset, and related links. |
| Lineage | Information about the provenance and consumption of data. |
| Queries | Queries are run against the dataset, and a comprehensive audit trail of these operations is available in the Query tab under the Change Log section. For more details, refer to the dataset audit trails. |
| Stats | Statistics for the dataset including basic statistics for the table and for each column in the table. |
| Validation | Successful and failed assertions for the data quality in the dataset. |
| Retention and disposal | Helps you understand relevant metadata in datasets while searching the catalog. |
| Privacy | Contains the same metadata information of the dataset stored in the data store information in the Data Mapping module. |

![Dataset_with_updated_glossary_term.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b16c40a2-4324-338a-45c6-12c750c65819.png)

#### Managing entity associations

The right panel on the Entity page lets you update the following associations for the entity:

- About
  - Documentation
  - Links

To update the documentation and links for the entity, see the documentation details. The same process can be done through this **About** section.
- Owners

To attach owners to the entity:
  1. From the **Owners** section on the right panel, click **+ Add Owners**.
  2. On the **Add Owners** popup, select the owner from the **Owner** menu and the owner type from the **Type** menu. See [ownership](/latest/docs/edcownership) for more details.
  3. Click **Done**.

You can view the user's email address alongside their name when you hover over the user badge.
- Tags
  1. From the **Tags** section on the right panel, click **+ Add Tags**.
  2. On the **Add Tags** popup, choose tags.
  3. Click **Done**.
- Glossary terms

Once the glossary terms are added, you have to hover over terms in the **Glossary Terms** section to view context. This required additional actions and made comparing terms difficult. To remove this difficulty, a new tab, **Glossary Terms**, is added on the left panel where entity details are given.

The glossary terms tab contains a grid with the following columns:

**Linking the glossary term**

To link a glossary term:

**Searching the glossary term**

The following menus let you filter and search for specific glossary terms:

**Removing glossary term from the entity**

You can also delete a glossary term’s relationship with an entity on individual rows or in bulk.The **Remove Relationship** option lets you detach a glossary term from an entity without deleting the term itself. This action removes the association between the term and the entity while keeping the glossary term available in the system for future use.

To remove a single glossary term from the entity:

To remove glossaries in bulk from the entity:
  1. From the **Glossary Terms** section on the right panel, click **+ Add Term**.
  2. On the **Add Glossary Terms** popup, search for the glossary term.
  3. Click **Done**.
  - Term name
  - SubType
  - Domain
  - Data product
  - Owner of the glossary term
  - Applied governance status
  - Browse path
  - Description
  - Applied PII flag
  - Applied CDE flag
  1. At the top right corner of the glossary terms grid, click **+ Add Terms**.
  2. On the **Add Glossary Terms** popup, search for the glossary term.
  3. Click **Done**.

> [!NOTE]
> **Note**
> 
> Any changes made to a glossary term also appear in the **Glossary Terms** tab.
  - SubType
  - Domain
  - Data product
  - Owner
  1. Click **Options** (three dots) located next to the term.
  2. Select **Remove Relationship** from the dropdown menu.
  3. On the confirmation popup, click **Yes**.
  1. Mark the checkbox next to each glossary term you want to remove.
  2. At the bottom of the page, click **Remove Relationship**.
  3. On the confirmation popup, click **Yes**.
- Domain
  1. From the **Domain** section on the right panel, click **Set Domain**.
  2. On the **Set Domain** popup, search for the domain.
  3. Click **Done**.
- Data product
  1. From the **Data Product** section on the right panel, click **Set Data Product**.
  2. On the **Set Data Product** popup, search for the data product.
  3. Click **Done**.

#### URN for structured dataset

You can uniquely identify any dataset in the Enterprise Data Catalog with a URN. URN stands for Uniform Resource Name. The sample URN is as follows:

urn:li:dataset:(urn:li:dataPlatform:snowflake,snowflake-1688.RAW.ANALYTICS.CUSTOMERS,PROD)

#### Dataset usage details

You get more details on the dataset usage while searching the datasets. These details help you understand how the dataset is used, who are the top users and the unique users that you can contact.

The metadata required to populate this is captured by the Access Intelligence (AI) capabilities implemented in the Data Access Governance module.

> [!NOTE]
> **Note**
> 
> Currently, you can get the dataset usage details for the Snowflake data system only.

After registering a dataset, you can get the following details on the dataset usage:

- Unique user count
- Single user's usage counts for a given resource
  - Count: Number of times the dataset has been used
  - User: URN of the user
  - User email: Email of the user, resolved using the user's URN upon dataset ingestion
- Field-level usage stats
  - Name of the field
  - Number of times the dataset field has been used
- Monthly executed queries

Monthly count of executed queries per table while searching the Snowflake datasets.

![Usage___Unique_users_-_EDC_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-715ea904-6a4e-5ed6-d28c-41421dfe095f.png)

![Queries_-_Dataset_Usage_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c31dcf77-d701-70dc-fce3-a8b539886eb2.png)

> [!NOTE]
> **Note**
> 
> To get the above details ingested, running the access intelligence scan is a prerequisite. Once you get the data after running the access intelligence scan then you are able to ingest the above details.

> [!NOTE]
> **Important**
> 
> The **Stats** tab is enabled when the **datasetProfile** or **datasetUsageStatistics** aspects of a dataset are populated. Typically, these aspects are populated when a user executes an ingestion plugin (via [EDC Ingestion](/latest/docs/edc-ingestion) or CLI) that captures this type of information.

#### Documentation details

You can update the dataset with relevant documentation and links.

**To update documentation**

**To attach links**

#### Sharing datasets

To share datasets:
  1. Click the edit icon to open the **Documentation** tab of the table.
  2. Enter the documentation details, then click **Save**.
  1. Click **+ Add Link**.
  2. On the **Add Link** popup, add a valid **URL** and **Label**.
  3. Click **Add** to save the link.
  1. Click on the data system folder and subfolders to see all the datasets inside that folder.
  2. Click on a dataset you want to share.
  3. At the right side of the page, click **Share** menu to view the following three options.

| Option | Description |
| --- | --- |
| Copy link | Copies a shareable link of the dataset. |
| Copy URN | Copies the URN of the dataset. URN uniquely identifies an entity on the EDC. |
| Email | You can share the dataset via email. |

![Share_button-_updated.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-123a4f49-b11a-3f99-fbe7-db2cb19d388b.png)

#### Containers for the structured datasets

When you register any dataset through a discovery scan or manual registration process, Securiti creates three containers in the Enterprise Data Catalog module. These are platform instance container, database container and schema container. The platform instance container contains a database container inside it. And the database container contains a scheme container inside it. This hierarchy provides you with more context on the containers of a dataset like Schemas, Databases, Metastores, Buckets, etc.

To explore containers for structured dataset:

1. Near the search bar, click the **Explore all** button to open the search result page where all the discovered assets are listed.
2. Apply the **Containers** filter from the filters sidebar to fetch the containers.

![Screenshot_2023-07-10_at_2_02_59_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cb0a45ff-25e6-22b8-ac59-6dbc35f8035c.png)![Screenshot_2023-07-10_at_1_56_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-410c9230-e4e3-4643-add8-1edb3fd6e290.png)![Screenshot_2023-07-10_at_1_58_24_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f8e8583-1028-47c8-2054-05c33ae054f4.png)

Open any container and use the right panel to add, edit or delete associations for the container. Read [managing associations](/v1/docs/datasets) for more information.

#### Structured dataset container URN

You can uniquely identify any structured dataset container in the Enterprise Data Catalog with a URN. URN stands for Uniform Resource Name. The sample URNs are as follows:

| URN type | Example |
| --- | --- |
| Platform instance container | urn:li:container:snowflake,snowflake-1618. |
| Database container | urn:li:container:snowflake,snowflake-1618,SNOWFLAKE_SAMPLE_DATA. |
| Schema container | urn:li:container:snowflake,snowflake-1618,SNOWFLAKE_SAMPLE_DATA,TPCDS_SF10TCL. |

#### Adding properties to containers

You can perform CRUD (Create, Read, Update, Delete) operations on the container properties. You can create new properties for containers, edit their values, and even delete them. This functionality streamlines data management processes and empowers you to tailor containers according to your requirements.

#### Adding container properties

Add container properties:

1. Click on a container you want to add properties for.
2. On the containers details page, click **Properties** tab.
3. At the top right cover of the page, click **+ Add New Property**.
4. On the **Add a new Property** popup, enter the property name and value.
5. Click **Add**.

#### Editing container properties

Edit container property:

1. Click the **Edit** button located on the right side of the property row that you want to edit.
2. On the **Edit a new Property** popup, update the value.

> [!NOTE]
> **Note**
> 
> You cannot edit the name of the property.
3. Click **Save**.

#### Deleting container properties:

Delete container property:

1. Click the **Delete** icon located on the right side of the property row that you want to delete.
2. On the **Delete Property** popup, click **Delete**.

> [!NOTE]
> **Note**
> 
> Be careful before deleting the property, as this action is irreversible and cannot be undone.

### Unstructured datasets

Securiti organizes unstructured data sets in separate folders based on the data systems.

> [!NOTE]
> **Note**
> 
> You can also include special characters, like “/”, in dataset names, database names, data system names.

Unstructured data refers to information that doesn’t conform to a specific data model or format, making it more challenging to organize, process, and analyze using traditional data management techniques. Common examples of unstructured data include text files, email messages, documents, videos, images, webpages, blogs, audio files, and so on.

Currently, the following unstructured data systems are supported in the Enterprise Data Catalog:

- Amazon S3
- Azure Blob Storage
- Elasticsearch
- NFS
- Office 365 OneDrive
- SMB
- Sharepoint

> [!NOTE]
> **Note**
> 
> Currently, we support file schema extraction from CSV, TSV, and JSON file formats for the data systems mentioned above. Additionally, you can ingest unstructured files such as images, videos, PDFs, and text files into the EDC for these systems.

To explore unstructured datasets:

1. Open **Enterprise Data Catalog**, then choose **Datasets**.
2. Enter a keyword in the search bar to find all the datasets related to that keyword.

The folders and subfolders take you to a specific dataset file or folder. The default preview card of the file or folder shows you:
  - Table name
  - Description
  - Domains
  - Glossary terms
  - Tags
  - Owners
3. Click on a folder or file to view its details.

| Tab Name | Description |
| --- | --- |
| Schema | Schema of the dataset. |
| Documentation | Detailed documentation of the dataset, and related links. |
| Properties | Extracted properties. You can add custom properties to the datasets as well. > [!NOTE] > Note > > The **Properties** tab for datasets ingested via EDC ingestion displays important metadata such as the **Job Name**, **Database Name**, and **Ingestion Run ID**. These details enhance transparency and make it easier to trace each dataset back to its original source. > > You can search for datasets ingested through EDC using a custom query. In the search bar, enter: > > **/q customProperties:"ingestion_job_name=<your_ingestion_job_name>"** > > Replace **<your_ingestion_job_name>** with the specific ingestion job name, for example, mysql-db. |
| Stats | Number of columns. |
| Lineage | See the structured datasets section for details. |
| Queries | See the structured datasets section for details. |
4. Use the right panel to add, edit or delete associations for the dataset. Read [managing associations](/v1/docs/datasets) for more information.

> [!NOTE]
> **Note**
> 
> Now you can populate external URLs of the registered dataset. The DatasetProperties aspect of a dataset allows storing an external URL. External URLs help to access the dataset if you are correctly authenticated with the data system.
> 
> Currently, you can only populate external URLs for the following data systems:
> 
> - AWS S3
> - Snowflake
> 
> ![User_for_View_in_snowflake_and_sorted_fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b964810-1356-34fc-ea88-52d4913157c5.png)

#### URN for unstructured dataset

You can uniquely identify any dataset in the Enterprise Data Catalog with a URN. URN stands for Uniform Resource Name. The sample URN is as follows:

urn:li:dataset:(urn:li:dataPlatform:s3,s3-10741.securiti-qa-tmp-s3-inventory-src/schema-classification/Research-and-development-survey-2021-CSV-notes.csv,PROD)

In the above example, **securiti-qa-tmp-s3-inventory-src** is the bucket name. However, **/schema-classification** is the folder route to the specific table.

#### Documentation details

You can update the dataset with relevant documentation and links.

**To update documentation**

1. Click the edit icon to open the **Documentation** tab of the table.
2. Enter the documentation details, then click **Save**.

**To attach links**

1. Click **+ Add Link**.
2. On the **Add Link** popup, add a valid **URL** and **Label**.
3. Click **Add** to save the link.

#### Containers for unstructured data systems

When you register any dataset through a discovery scan or manual registration process, Securiti creates platform instance containers in the Enterprise Data Catalog module. The platform instance containers provide you with more context on the containers of a dataset like Schemas, Databases, Metastores, Buckets, etc.

To explore unstructured dataset container:

1. Near the search bar, click the **Explore all** button to open the search result page where all the discovered assets are listed.
2. Apply the **Containers** filter from the filters sidebar to fetch the containers.

![Screenshot_2023-08-07_at_2_06_29_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-02202a3a-14ae-4747-3a1a-7571189fa8a9.png)

Open any container and use the right panel to add, edit or delete associations for the container. Read [managing associations](/v1/docs/datasets) for more information.

#### Unstructured dataset container URN

You can uniquely identify any unstructured container in the Enterprise Data Catalog with a URN. URN stands for Uniform Resource Name. The sample URN is as follows:

urn:li:container:onedrive,https://dsrtestautomation-my.sharepoint.com/personal/admin_dsrtestautomation_onmicrosoft_com/Documents/

#### Adding properties to containers

You can perform CRUD (Create, Read, Update, Delete) operations on the container properties. You can create new properties for containers, edit their values, and even delete them. This functionality streamlines data management processes and empowers you to tailor containers according to your requirements.

#### Adding container properties

Add container properties:

1. Click on a container you want to add properties for.
2. On the containers details page, click **Properties** tab.
3. At the top right cover of the page, click **+ Add New Property**.
4. On the **Add a new Property** popup, enter the property name and value.
5. Click **Add**.

#### Editing container properties

Edit container property:

1. Click the **Edit** button located on the right side of the property row that you want to edit.
2. On the **Edit a new Property** popup, update the value.

> [!NOTE]
> **Note**
> 
> You cannot edit the name of the property.
3. Click **Save**.

#### Deleting container properties:

Delete container property:

1. Click the **Delete** icon located on the right side of the property row that you want to delete.
2. On the **Delete Property** popup, click **Delete**.

> [!NOTE]
> **Note**
> 
> Be careful before deleting the property, as this action is irreversible and cannot be undone.

### Streaming datasets

Streaming datasets are organized in separate folders based on the data systems. The folders and subfolders take you to a specific table and its details within a dataset.

Currently, the following streaming data systems are supported in the Enterprise Data Catalog:

- Amazon MSK
- Confluent Kafka
- Kafka

> [!NOTE]
> **Note**
> 
> Use the right panel to add, edit or delete associations for the dataset. Read [managing associations](/v1/docs/datasets) for more information.

### Audit trail for datasets

You can view comprehensive insights about how a dataset has changed over time. This can help you make informed decisions and better manage your assets.

To view the audit trail:

1. Open **Enterprise Data Catalog**, then choose **Datasets**.
2. Click on the data system folder and subfolders to open the specific dataset details page that you want to see an audit trail of.
3. On the upper right corner of the page, click **Change Log** to view the following audit trail details:

| Value | Description |
| --- | --- |
| Time | The time when each change occurred. |
| Activity | Nature of the modification (for example, add, edit, delete). |
| Attribute | Specific aspects of the asset that changed. |
| Old value | Previous state for a complete historical perspective. |
| New value | Updated information. |
| Message | Additional context through accompanying messages. |
| User | Name of the user responsible for the change. |
| Metadata explorer | Provides additional details regarding the entity. |

### Updating dataset metadata in bulk using CSV file

You can update dataset metadata in bulk to ensure productive management of your dataset metadata. To update:

1. Open **Enterprise Data Catalog**, then choose **Datasets**.
2. On the **Datasets** page, click the **Bulk Update**.
3. On the **Bulk Import Dataset** popup, from the CSV type menu, choose one of the following options:
  - Dataset (to update the dataset metadata)
  - Dataset schema (to update the schema of the dataset)
4. Click anywhere on the file import section, and choose the file from your device to import.

> [!NOTE]
> **Note**
> 
> For a smooth upload, make sure your CSV file follows a specific format. If it doesn't, you might face issues uploading it. To make sure everything works well, download the CSV template and use it as a guide for how to set up your file.
> 
> - On the bottom left of the file import section, click **Download Sample CSV** from the UI to download the sample.
5. Mark the **Override** option to generate new data and remove existing entries. Leave it unchecked to merge the new metadata with the existing entries.
6. Click **Import**.

Once the import is completed, you can open the dataset that you added in the CSV file to see the updated metadata.

> [!NOTE]
> **Note**
> 
> - You must configure [private cloud storage](/latest/docs/private-cloud-storage) for successfully loading datasets in bulk into EDC.
> - Discovery scans take precedence over dataset import and EDC Ingestion. Re-running a discovery scan resets a dataset's metadata to what the scan detects, removing anything added through dataset import or EDC Ingestion.
> 
>   
> 
> For example, a discovery scan registers a dataset with two lineage relationships. You add one through dataset import and one through EDC Ingestion, giving the dataset four. Re-running the discovery scan leaves only the original two.
> 
>   
> 
> After re-running a discovery scan, re-run the dataset import and EDC Ingestion in their original order to restore the overwritten metadata.

### Creating and updating datasets metadata in bulk using Excel file

You can create and update datasets in the EDC with all the aspects. You can do so by just uploading .xlsx file.

> [!NOTE]
> **Note**
> 
> - You must configure [private cloud storage](/latest/docs/private-cloud-storage) for successfully loading datasets in bulk into EDC.
> - Discovery scans take precedence over dataset import and EDC Ingestion. Re-running a discovery scan resets a dataset's metadata to what the scan detects, removing anything added through dataset import or EDC Ingestion.
> 
>   
> 
> For example, a discovery scan registers a dataset with two lineage relationships. You add one through dataset import and one through EDC Ingestion, giving the dataset four. Re-running the discovery scan leaves only the original two.
> 
>   
> 
> After re-running a discovery scan, re-run the dataset import and EDC Ingestion in their original order to restore the overwritten metadata.

To create and update datasets into EDC:

1. Open **Enterprise Data Catalog**, then choose Datasets.
2. On the **Dataset** page, click the **Bulk Update**.
3. On the **Bulk Import Dataset** popup, from the CSV type menu, choose one of the following options:
  - Dataset (to update the dataset metadata)
  - Dataset schema (to update the schema of the dataset)
4. Click anywhere on the file import section, and choose the file from your device to import.

> [!NOTE]
> **Note**
> 
> For a smooth upload, make sure your .xlsx file follows a specific format. If it doesn't, you might face issues uploading it. To make sure everything works well, download the sample excel template and use it as a guide for how to set up your file and read the instructions carefully.
> 
> - On the bottom left of the file import section, click **Download Sample Excel** from UI to download the sample.
5. Mark the **Override** option to generate new data and remove existing entries. Leave it unchecked to merge the new metadata with the existing entries.
6. Click **Import**.

> [!NOTE]
> **Note**
> 
> If there is an error in the file, the XLSX file validation fails. In that case:
> 
> - Click **View Error Log** to view a list of error logs.
> - Click **Retry** to upload the right file again.

Once the import is completed, you can open the dataset that you added in the .xlsx file to see the updated metadata.

> [!NOTE]
> **Note**
> 
> - You can view the audit trials of the dataset bulk import activities in the [Audit logs](/v1/docs/securiti-platform-viewing-the-securiti-audit-log) section.
> - You can also view the dataset bulk import activities in the [Messages & Notifications](/latest/docs/securiti-platform-using-the-securiti-messages-notifications-panel) section.

### Instructions for importing metadata using an Excel file

#### Main tab

**To add a new dataset:**

- In the **Dataset URN** column, you must enter the dataset URN in the right format.

The generic format is as follows:

> [!NOTE]
> urn:li:dataset:(urn:li:dataPlatform:<platformName>,<qualifiedDatasetName>,<environment>)

In the above format:

> [!NOTE]
> **Note**
> 
> There are a few restrictions when creating an URN. Column names are encoded if they contain any of the following reserved characters. To prevent this, it is advisable to avoid using these characters.
> 
> - Commas "," are reserved characters in URN fields.
> - Parentheses "( , )" are reserved characters in URN fields.
> 
> For example, **urn:li:dashboard:(looker,dashboards.thelook)** is a valid urn, but **urn:li:dashboard:(looker,dashboards.the, look)** is invalid.

**Dataset format**

urn:li:dataset:(urn:li:dataPlatform:mysql,mydb.company.employee,PROD)
  - <platformName> is the data platform (for example, Snowflake, MySQL, Kafka).
  - <qualifiedDatasetName> is the full name of the dataset including account, database, schema, and table (or topic, etc).
  - <environment> is the deployment environment (For example, PROD, DEV)

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
- You must enter the right values to the **Subtype** and **Name** columns to create the new dataset successfully.
- Enter the values of the following aspects, if you want then to update the new dataset:
  - Description
  - Domain URN
  - Domain name
  - Governance status
  - PII flag
  - CDE flag
  - Data product URN
  - Data product name

> [!NOTE]
> **Note**
> 
> To link the domain and/or data product to the new dataset, enter their URNs. Including their names is optional.

**To update the existing dataset, you must:**

- Enter the correct URN. Open the dataset details page, and at the right side of the page, click **Share > Copy URN**.The instructions for the other columns are the same.

#### Properties

You can add and update properties to the dataset. To do so:

- In the **Dataset URN** column, enter the URN of the dataset. To get the right URN of the dataset, open the dataset details page, and at the right side of the page, click **Share > Copy URN**. The **Dataset** **URN** column is a mandatory field.
- In the **Dataset** **Name** column, enter the name of the dataset (optional).
- Enter property name and value. Both columns are mandatory.

> [!NOTE]
> **Note**
> 
> To add multiple properties to a single dataset, create a separate row for each property while using the same dataset URN and dataset name.

#### Structured properties

To add and update the structured properties for the datasets, fill out the structured properties tab, which includes the following columns:

| Column | Required? | Description |
| --- | --- | --- |
| Dataset URN | Yes | - Enter the URN of the dataset. To get the right URN, open the dataset details page, and at the right side of the page, click **Share > Copy URN**. |
| Dataset Name | No | - Add the name of the dataset. |
| Property URN | Yes | - Enter the structured property URN. **Example**: urn:li:structuredProperty:54a6a00b-bdf7-4ba8-9f00-8b93d180bc2d \| urn:li:structuredProperty: \| This is the constant component consisting of urn (This is the prefix indicating that the string is a URN), li (This is a namespace identifier), and structuredProperty (This specifies the type of resource being identified). \| \| --- \| --- \| \| 54a6a00b-bdf7-4ba8-9f00-8b93d180bc2d \| A randomly generated UUID, assigned to this specific structured property. \| |
| urn:li:structuredProperty: | This is the constant component consisting of urn (This is the prefix indicating that the string is a URN), li (This is a namespace identifier), and structuredProperty (This specifies the type of resource being identified). |
| 54a6a00b-bdf7-4ba8-9f00-8b93d180bc2d | A randomly generated UUID, assigned to this specific structured property. |
| Property Name | No | - Enter the structured property name. **Example**: Created Time |
| Property Cardinality | Yes | - Set the cardinality for the structured property as either SINGLE or MULTIPLE. Cardinality is the number of values that can be assigned to a specific structured property. - **Single Cardinality** - Assigns only one value of the structured property to an entity. - **Multiple Cardinality** - Assigns multiple values of the structured property to an entity. |
| Property Value Type | Yes | - Enter the value type of the structured property. The value type specifies the format of data that can be assigned to a property, such as Number, Date, String, or URN. **Example**: STRING |
| Property Value | Yes | - Enter the structured property value. It refers to the specific data assigned to a property based on its value type. **Example**: 2021-01-15 |

#### Ownership

You can add and update ownership to the dataset. To do so:

- In the **Dataset URN** column, enter the URN of the dataset. To get the right URN of the dataset, open the dataset details page, and at the right side of the page, click **Share > Copy URN**. It is a mandatory column.
- In the **Dataset Name** column, enter the name of the dataset (optional).
- In the **Owner** column, enter the owner's email address (for example, JohnDoe@securiti.net). This field is mandatory, and the ownership details for the dataset will be updated only if the email address is valid.
- In the **Ownership Type URN** column, add the URN of the ownership type. To get the right URN, refer to the [custom ownership URN](/latest/docs/edcownership).
- In the **Ownership Type Name** column, enter the ownership type name.

> [!NOTE]
> **Note**
> 
> - If you want to add a custom ownership type, then the **Ownership Type URN** field and the **Owner** columns are mandatory where you have to add the ownership type urn and the owner email, respectively.
> - If you want to add a legacy ownership type, add any one of the following options in the **Ownership Type Name** column:
> 
> In this case, both the **Ownership Type Name** and **Owner** columns are mandatory. You must enter the correct names and emails for the action to be successful.
>   - TECHNICAL_OWNER
>   - BUSINESS_OWNER
>   - DATA_STEWARD
>   - NONE

#### Lineage

You can define field-level lineage between a source (upstream) dataset and a target (downstream) dataset. For example, consider a case where the **film_list** view is created using data from the **inventory** table.

- In the **Dataset** **URN** add the URN of the downstream dataset receiving the data. it is a mandatory column. **Example**: `urn:li:dataset:(urn:li:data:postgres,public.film_list,PROD).`
- In the **Dataset** **Name** column, add the human-readable name of the downstream dataset. It is an optional column. Example: **film_list**.
- In the **Dataset** **Field** **URN**, add the URN of the specific field in the downstream dataset receiving the data. It is a required column. **Example**: `urn:li:schemaField:(urn:li:dataset:(urn:li:data:postgres,public.film_list,PROD),film_id).`
- In the **Upstream** **Dataset** **Field** **URN**, add URN of the field in the upstream dataset (inventory table) from which the data originates. it is a mandatory column. Example: `urn:li:schemaField:(urn:li:dataset:(urn:li:data:postgres,public.inventory,PROD),film_id). `

#### Glossary terms

You can add and update glossary terms to the dataset. To do so:

- In the **Dataset** **URN** column, enter the URN of the dataset. To get the right URN of the dataset, open the dataset details page, and at the right side of the page, click **Share > Copy URN**. It is a mandatory column.
- In the **Dataset** **Name** column, enter the name of the dataset (optional).
- In the **Term** **URN** column, add the URN of the term.
- In the **Term Name** column, add the name of the term.

> [!NOTE]
> **Note**
> 
> To successfully add the glossary term with the dataset, you must enter the glossary **Term** **URN**. It is the mandatory field, the **Term Name** is optional.

#### Tags

You can add and update tags to the dataset. To do so:

- In the **Dataset** **URN** column, enter the URN of the dataset. To get the right URN of the dataset, open the dataset details page, and at the right side of the page, click **Share > Copy** **URN**. It is a mandatory column.
- In the **Dataset** **Name** column, enter the name of the dataset (optional).
- In the **Tag** **URN** column, add the URN of the term.
- In the **Tag Name** column, add the name of the term.

> [!NOTE]
> **Note**
> 
> To successfully link the tag to the dataset, you must enter the **Tag** **URN**. It is the mandatory field, the **Tag Name** is optional.

#### Schema Field

You can add and update the schema fields of the datasets. To do so:

- In the **Dataset** **Field URN** column, add the dataset field URN.

> [!NOTE]
> **Note**
> 
> You can copy the dataset field URN by clicking the **Options (three dots)** menu at the right end of the dataset schema field.

**Schema Field Format**

urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:<platformName>,<qualifiedDatasetName>, <environment>),<fieldPath>)

**Components**

> [!NOTE]
> **Note**
> 
> There are a few restrictions when creating an URN. Column names are encoded if they contain any of the following reserved characters. To prevent this, it is advisable to avoid using these characters.
> 
> - Commas "," are reserved characters in URN fields.
> - Parentheses "( , )" are reserved characters in URN fields.
> 
> For example, **urn:li:dashboard:(looker,dashboards.thelook)** is a valid urn, but **urn:li:dashboard:(looker,dashboards.the, look)** is invalid.

**Example**

urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:snowflake,mydb.analytics.sales,PROD),sales_region)

**Breakdown:**
  - urn:li:schemaField:

It indicates that this URN represents a schema field within a dataset. It uniquely identifies a specific field, including nested fields, in the schema of a dataset.
  - urn:li:dataset:

It refers to the dataset to which the schema field belongs. This is specified using a nested URN.
  - urn:li:dataPlatform:<platformName>

It identifies the platform where the dataset resides (e.g., mysql, hive, snowflake, etc.).
  - <qualifiedDatasetName>

It is the fully qualified name of the dataset, typically including:

Example: mydb.sales.transactions.
    - Database name (e.g., mydb)
    - Schema name (e.g., sales)
    - Table name (e.g., transactions)
  - <environment>

It specifies the environment in which the dataset resides (e.g., PROD for production, DEV for development, or TEST for testing).
  - <fieldPath>

It represents the path of the schema field being referenced (e.g., transaction_id)
  - urn:li:schemaField:

This identifies the URN as a schema field.
  - urn:li:dataset:

It specifies the dataset where this schema field belongs.
  - urn:li:dataPlatform:snowflake

It indicates the dataset is hosted on the Snowflake platform.
  - mydb.analytics.sales

The fully qualified name of the dataset, where:
    - mydb is the database
    - analytics is the schema
    - sales is the table
  - PROD

It refers to the production environment.
  - sales_region

It is the schema field being referenced, which is a top-level field in this dataset.

This URN uniquely identifies the **sales_region** field within the **mydb.analytics.sales** dataset hosted on the Snowflake platform in the production environment.
- In the **Dataset** **Name** column, add the dataset name.
- In the **Field Name** column, add the field name you want to create or update.
- In the **Data Type** column, add a value for the data type. The allowed values are as follows:
  - Int
  - Int4
  - Int8
  - Int16
  - Int32
  - Int64
  - Int identity
  - Bigint
  - Smallint
  - Numeric
  - Decimal
  - Float
  - Integer
  - Clob
  - Interval
  - Null
  - Time
  - Datetime
  - Timestamp
  - Date_time
  - Byte
  - Binary
  - Varbinary
  - Array
  - Bytea
  - Char
  - Nvarchar
  - Varchar
  - String
  - Text
  - Mediumtext
  - Longtext
  - Bool
  - Boolean
  - Json
  - Jsonb
  - Date
  - Enum
- In the **Primary Key** column, add the value as **True** or **False**. The foreign key parameter lets you specify which fields should be used as unique identifiers, ensuring correct database relationships.
- In the **Description** column, add the description.
- In the **PII** **Flag** column, set the flag as true or false.
- In the **CDE Flag** column, set the flag as true or false.

> [!NOTE]
> **Note**
> 
> - The **Field Name**, and **Dataset** **Field** **URN** are mandatory columns to update or add a dataset schema field. The **Data Type** column along with **Field Name** and **Dataset** **Field URN** are mandatory for creating the dataset schema field. If you leave this empty, the corresponding schema field will be ignored.
> - To create new schema fields for the dataset, the field name in the **Dataset Field URN** column (at the end of the dataset URN) must match the name entered in the **Field Name** column.

Schema field foreign keys

You can create or update the foreign keys of the scheme fields. To do so:

- In the **Source** **Dataset** **Field URN** column, add the URN of the source dataset field. This URN identifies the field in the source dataset that acts as a foreign key. It links it to a corresponding field in another dataset. It is a mandatory field.

**Example**:
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),actor_id,withcomma)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),first_name,,twocomma)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),last_name,#/\withSpecialChar)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),last_update,"withqoute)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),columnname(withbrackets)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),columnname)withbrackets)
- In the **Source Field Name** column, add the name of the source field. It is a mandatory column.

**Example:**
  - actor_id,withcomma
  - first_name,,twocomma
  - last_name,#/\withSpecialChar
  - last_update,"withqoute
  - columnname(withbrackets
  - columnname)withbrackets
- In the **Foreign** **Dataset** **Field URN** column, add the URN of the referenced field in the foreign dataset. This field is the target of the foreign key relationship. It is a mandatory column.

**Example**:
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),first_name,,twocomma)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),last_name,#/\withSpecialChar)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),last_update,"withqoute)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),columnname(withbrackets)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),columnname)withbrackets)
  - urn:li:schemaField:(urn:li:dataset:(urn:li:dataPlatform:postgres,postgres-1.dvdrental.public.category,PROD),actor_id,withcomma)
- In the **Foreign Field Name** column, add the names of the foreign fields. It is a mandatory field.

Example:
  - first_name,,twocomma
  - last_name,#/\withSpecialChar
  - last_update,"withqoute
  - columnname(withbrackets
  - columnname)withbrackets
  - actor_id,withcomma
- In the **Foreign Key Name** column, add the name of the foreign key constraint or relationship. This identifier aids in managing and identifying the linkage between the source and target dataset fields.

**Example**:
  - FK_Comma_To_DoubleComma
  - FK_DoubleComma_To_SpecialChars
  - FK_SpecialChars_To_Quote
  - FK_Quote_To_OpenBracket
  - FK_OpenBracket_To_CloseBracket
  - FK_CloseBracket_To_Comma

> [!NOTE]
> **Note**
> 
> The **Source** **Dataset** **Field URN**, **Foreign** **Dataset** **Field URN, Source Field Name,** and **Foreign Field Name** are mandatory columns to add or update foreign key relationships in the dataset schema fields.

#### Schema field glossary terms

You can add and update the schema field glossary terms of the datasets. To do so:

- In the **Dataset** **Field URN** column, add the dataset field URN.

> [!NOTE]
> **Note**
> 
> You can copy the dataset field URN by clicking the **Options (three dots)** menu at the right end of the dataset schema field.
- In the **Dataset** **Name** column, add the dataset name.
- In the **Field Name** column, add the field name you want to create or update.
- In the **Term URN** column, add the URN of the term.
- In the **Term Name** column, add the name of the term.

> [!NOTE]
> **Note**
> 
> To successfully add or update the schema field glossary term, **Dataset** **Field URN**, **Field Name**, and **Term URN** columns are required.

> [!NOTE]
> **Important**
> 
> To successfully update or add schema field glossary terms, make sure to enter the updated **Dataset** **Field URN** in the **Schema Field Glossary Terms** tab after modifying the schema field name in the **Schema Field** tab.

#### Schema field tags

You can add and update the schema field tags of the datasets. To do so:

- In the **Dataset** **Field URN** column, add the dataset field URN.

> [!NOTE]
> **Note**
> 
> You can copy the dataset field URN by clicking the **Options (three dots)** menu at the right end of the dataset schema field.
- In the **Dataset** **Name** column, add the dataset name.
- In the **Field Name** column, add the field name you want to create or update.
- In the **Tag URN** column, add the URN of the term.
- In the **Tag Name** column, add the name of the term.

> [!NOTE]
> **Note**
> 
> To successfully add or update the schema field tags, **Dataset** **Field URN**, **Field Name**, and **Tag URN** columns are required.

> [!NOTE]
> **Important**
> 
> To successfully update or add schema field tags, make sure to enter the updated **Dataset** **Field URN** in the **Schema Field Tags** tab after modifying the schema field name in the **Schema Field** tab.

#### Schema field domains

You can add and update the schema field domains of the datasets. To do so:

- In the **Dataset** **Field URN** column, add the dataset field URN.

> [!NOTE]
> **Note**
> 
> You can copy the dataset field URN by clicking the **Options (three dots)** menu at the right end of the dataset schema field.
- In the **Dataset** **Name** column, add the dataset name.
- In the **Field Name** column, add the field name you want to create or update.
- In the **Domain URN** column, add the URN of the domain.
- In the **Domain Name** column, add the name of the domain.

> [!NOTE]
> Note
> 
> To successfully add or update the schema field domains, **Dataset Field URN**, **Field Name**, and **Domain URN** columns are required.

#### Sample data

The sample data tab provides example entries for each section to help you understand the correct format. It includes sample data for every tab in the template, letting you reference the examples when populating your sheet.

### Log files for monitoring the dataset bulk load activities

Securiti generates a log file whenever you bulk import datasets using an Excel file. This log file provides a detailed overview of the process, including the number of new entries created and any failures encountered during the bulk upload.

To access the log file:

1. Open the **Messages & Notifications** section, where you will receive two messages—one indicating that the bulk upload has started and another confirming its completion. The completion message includes details on any failed rows along with the log file name.
2. Copy the log file name from this message.
3. Click your avatar at the bottom of the left navigation bar and select **My Downloads**.
4. Use the copied log file name to search for the file, then download and open it to review the log details.

The log file typically provides a summary of the bulk import process, highlighting both successful entries and failures.![Log_files_-_Datasets.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-15b6b28b-d981-b124-a6a7-2658c3c3f767.png)

### Exporting dataset aspects

You can export datasets, including schema metadata and and various detailed attributes. This provides more comprehensive data insights and improved governance. The aspects you can export are listed below.

| Aspect |
| --- |
| Main tab | - Dataset URN - Subtype - Name - Description - Domain URN - Domain name - Governance status - PII flag - CDE flag - Data product URN - Data product name |
| Properties | - Dataset URN - Dataset name - Property name - Property value |
| Ownership | - Dataset URN - Dataset name - Owner - Ownership type URN - Ownership type Name |
| Glossary term | - Dataset URN - Dataset name - Term URN - Term name |
| Tags | - Dataset URN - Dataset name - Tag URN - Tag name |
| Schema field | - Dataset field URN - Dataset name - Field name - Description - PII flag - CDE flag |
| Schema field glossary term | - Dataset field URN - Dataset name - Field name - Term URN - Term name |
| Schema field tags | - Dataset field URN - Dataset name - Field name - Tag URN - Tag name |

To export dataset aspects:

- Open the datasets page and select the datasets you want to export by marking the checkboxes.
- Click **Export** from the popup menu that appears at the bottom of the page.

> [!NOTE]
> **Note**
> 
> - The export option is also available under the **Actions** button, located on the top right side of the page.
> - Datasets export honor your [RBAC permissions](/latest/docs/edc-rbac-permissions-and-roles). The export file includes only the entities you have permission to view. Entities you do not have access to are automatically excluded from the export.
- If the export results contain fewer than 1000 records, the file will start downloading. Once the download is complete, you can view the .xlxs file on your local device.
- When your search results exceed 1000 records, you will receive a message on the screen that says, “Export Started, Once file is ready, we'll email you the link”.
- Check your registered email address for a message containing the requested .xlxs file as an attachment.

> [!NOTE]
> **Important**
> 
> Ensure that your registered email address is up to date to receive the files.

### Linking dataset fields to domains

You can relate dataset fields to the domains and subdomains. This lets you achieve more precise and meaningful classifications.

To assign a domain to a dataset field:

1. Locate the specific field you want to update.
2. Click **+ Set Domain** found in the **Domain** column of that field’s row.
3. On the pop-up that appears, select the appropriate domain.
4. Click **Done** it to complete the assignment.

![domain_linking.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84b78075-2b2f-22f9-bd8f-c15d54de41cc.png)

For example, consider an order record that fuses customer account data and order data. This record contains a set of fields belonging to a customer data-specific domain. It also has fields belonging to the orders management domain. Using this feature, you can assign the appropriate domain to each field, ensuring accurate categorization and domain alignment.

Additionally, you can search schema fields by their linked domain. The related fields can be viewed in the **Related Entities** tab of the domain.

### Deleting data systems and discovered assets

To delete discovered assets:

1. Open **Enterprise Data Catalog**, then choose **Datasets**.
2. On the **Datasets** page, mark the checkbox(s) for the data system(s) you want to delete.
3. Click **Delete** from the popup menu that appears at the bottom of the page.

> [!NOTE]
> **Note**
> 
> Alternatively, on the right side of the page, click **Actions > Delete Datasets** to delete the datasets.
4. A warning popup appears on the page. Click **Delete** to confirm deletion.
5. Likewise, you can also delete the specific asset. Click on the data system folder, subfolders to access the specific table you want to delete. Near the Share button choose **Options** (three dots) > **Delete Dataset**.

![EDC_-_Delete_tables_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5249736b-f655-aad3-41da-edeaac716969.png)

### Data lineage

**Scenario**

As a data engineer, you must trace how personal data flows across systems to meet regulatory requirements. Manually mapping data sources and transformations is tedious and often incomplete, risking non-compliance. With Securiti's data lineage feature, you automatically visualize data journeys across different data systems such as Snowflake and BigQuery. You quickly identify data origins and downstream impacts, ensuring full transparency and simplifying audits.

In today’s data-driven organizations, understanding data's journey from its origin to its final destination is crucial. Data Lineage plays a pivotal role in data governance by ensuring accountability, enhancing data quality, and supporting compliance efforts. By providing a clear view of how data flows and transforms within your organization, it establishes a foundation for trust, transparency, and effective data management.

**Defining data lineage**

Data lineage provides a detailed view of the path that data takes through your organization. It tracks data flow, transformations, and dependencies, ensuring transparency and fostering trust. Think of it as a map, showing where data comes from, where it has been, and where it is going.

**Key purposes of data lineage**

- Trust and understanding

Data lineage builds trust and understanding. By tracking data origins and transformations, it gains your confidence in the data they use. This clarity is essential for effective decision-making and data-driven strategies.
- Compliance

Lineage supports compliance efforts. Regulatory requirements often demand organizations to trace sensitive data. With data lineage, you can demonstrate adherence to regulations, ensuring accountability and avoiding penalties.
- Debugging and root cause analysis

Data lineage is also invaluable for debugging and root cause analysis. When issues arise in data workflows, lineage lets you pinpoint the source of the problem quickly, minimizing downtime and ensuring data integrity.
- Impact analysis

Data lineage enables impact analysis. It helps evaluate the effects of changes to downstream systems or processes. For instance, if a data system is modified, lineage lets you understand how it impacts connected systems, reducing the risk of unintended consequences.

Lineage lets you track the inputs from which a data asset is derived, along with the data assets that depend on it downstream. Types of lineage connections supported in the Enterprise Data Catalog are:

- Dataset-to-dataset
- Column-to-column

The data lineage feature is supported for the following data systems:

- Amazon Redshift
- Amazon RDS for PostgreSQL
- Google BigQuery
- IBM DB2
- MySQL
- Oracle
- PostgreSQL
- Snowflake
- SQL Server

#### Capturing lineage

You can capture lineage in either of the following two ways:

- **SQL parser**

In this method, besides having a subscription for SQL Lineage, you must have the required subscription to Securiti’s Sensitive Data Intelligence module to configure discovery scans and run scan job.

In Sensitive Data Intelligence, on the **Discovery Scan** page, mark the **Extract Lineage from the SQL** checkbox. This option extracts the lineage from SQL objects included inside schemas or databases in scope.

> [!NOTE]
> **Note**
> 
> While configuring discovery scans, make sure you have selected the databases, schemas and views for which lineage needs to be viewed. By default, “All” is selected for all these options. In this case, if you mark the **Extract Lineage from the SQL** checkbox then lineage gets included from SQL objects for all the databases, schemas and tables and views.
> 
> However, if you have selected specific databases for lineage and select some specific databases, schemas, and views. In this case, if you mark the **Extract Lineage from the SQL** checkbox then lineage gets included from SQL objects included inside the selected databases only.

- **DataHub plugins**

You can capture lineage through DataHub plugin support such as through [EDC ingestion](/latest/docs/edc-ingestion).

While configuring the ingestion recipe, mark the Include Lineage checkbox from the Advanced Settings to include the table and view the lineage in your ingestion.

![EDC_-_HCHA_-_Include_Lineage_from_ingestion_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce404cd4-ffa6-1046-b480-693ba5c33845.png)

> [!NOTE]
> **Note**
> 
> - You can also register lineage using DataHub CLI directly. Note that EDC is compatible with DataHub.
> - When data lineage is ingested through a discovery scan, a default folder is automatically created. This folder contains intermediate objects, which are useful for tracking how data transforms throughout its lifecycle. However, when lineage is ingested through EDC ingestion, this default folder is not created, and therefore intermediate objects are not generated.

#### Viewing lineage

To view lineage:

1. Open **Enterprise Data Catalog**, in the **Explore your Metadata** section, click **Datasets** as shown below.

![Datasets_access_for_Lineage_display.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52b6b6e5-97e9-69f7-2929-01687fbf9d7b.png)
2. Enter a keyword in the search bar to find all the datasets related to that keyword.
3. Click on the data system folder and subfolders to see all the tables inside that folder.
4. Click on any table you want to view lineage of.
5. Click **Lineage > Visualize Lineage.**

![Visualise_lineage_-_updated_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56672fe7-61f9-122c-b1de-61925b19f6e8.png)

Click **Visualize Lineage** to open the lineage visualization page where you can view lineage among tables linked to views, procedures, and functions.

![Lineage_screen_-_compress_lineage_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f5b6f68-ea4f-7d21-2088-60b5dccc2713.png)

On the lineage visualization page:

- Mark the **Show Full Tiles** toggle to view the complete name of the entity in the tiles.
- Mark the **Compress Lineage** toggle to collapse related entities into a single lineage node.
- Mark the **Show Columns** toggle to view column details of the datasets.

![Lineage_toggles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95d38e64-b948-5be0-bacd-db46f1a8c421.png)

#### Viewing column level lineage

Column level lineage lets you perform column level impact analysis by viewing the full end-to-end list of column dependencies. To view column level lineage unmark the **Compress Lineage** toggle and mark the **Show Columns** toggle as shown below.

![Screenshot_2023-06-26_at_11_50_28_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae39e64e-6f1d-1874-281c-a51619642372.png)

#### Views, functions and procedures logic

You can view logic or definition of the views, procedures, and functions of the dataset tables.

1. Open Enterprise Data Catalog, then choose any dataset, for example, Snowflake.
2. Click folders, and subfolders to view all the tables. Select a view, function, or procedure to see the detailed information.
3. On the bottom right of the page, click **View Definition** to view the logic code.

![view_definition_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7158caa7-525a-a75e-8cf2-ba354799238d.png)![logic_definition.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0bc9c1ad-c6f5-4979-85a6-87662bded65b.png)

#### 

#### Applying filters to visualize lineage

To filter lineage:

1. Under **Lineage** tab, near the upper left corner of the page, click **Filter** to open the filters panel.
2. Mark the checkboxes for the options you want to view in the lineage visualization page among the entities.

![Filter_panel_selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-96c03242-d70c-0790-867c-eeca1eadbef2.png)

#### Filtering time-based lineage

To filter time-based lineage:

1. Click on the data system folder and subfolders to see all the tables inside that folder.
2. Click on any table you want to edit the lineage of.
3. Click **Lineage**.
4. At the right side of the lineage section, click **Last 14 days** menu.
5. Apply the filter to view the lineage edges by the observed date.
6. Click the **Visualize Lineage** to view the updated lineage.

![time_window_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08b358c1-4b2a-f23d-c2ca-84681a4ca107.png)

#### Adding new filter to visualize lineage

To add new filter to visualize lineage:

1. Under the Lineage tab, click **Advanced**.

![Advanced.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-72f1f64c-3694-94a7-7c69-911010fea0a3.png)
2. Click **+ Add Filter** menu and select the appropriate option.

![Filter_dropdown_-_lineage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2da6eec-122e-e363-eab9-d2c8473d2390.png)
3. When you select any option from the menu, a popup opens. On the popup, select the required option from the menu and click **Done** to add your desired filter.

![adding_filter_to_lineage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56f852dd-7633-04ad-a233-b70c1ca8ec43.png)

#### Editing lineage

You can edit lineage for entities manually through the user interface. In order to edit lineage through the user interface, you must have **Edit Dataset Lineage** permission enabled for your account. For more details, refer to [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

> [!NOTE]
> **Note**
> 
> It is important to know that the Edit Lineage privilege is required for all entities whose lineage is affected by the changes. For example, in order to add **Dataset X** as an upstream dependency of **Dataset Y**, you must have Edit Lineage privilege for both **Dataset X** and **Dataset Y**.

To edit lineage:

1. Click on the data system folder and subfolders to see all the tables inside that folder.
2. Click on any table you want to edit the lineage of.
3. Click **Lineage**.
4. Click **Edit** menu to edit upstream and downstream.

![Edit_dropdown_-_lineage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70cc3e69-ca9f-76b8-548b-ff94d0cad63b.png)
5. If you select edit upstream, **Manage Upstream lineage** popup opens.
6. In the **Add Upstream** field, add the desired dataset, and click **Save Changes**.

![Manage upstream lineage for datasets, including SQL Server and Oracle tables.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/210749 - dataset with complete path.png)
7. Click the **Visualize Lineage** to view the updated lineage.

You can also edit the lineage from the lineage diagram.

1. Open the lineage diagram for the table of interest.
2. Click **Options** (three dots) and choose either **Edit Upstream** or **Edit Downstream**.

![EDC_-_Lineage_edit_from_diagram.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c0f051c-0cfb-3516-91d8-b6699c44ca77.png)

> [!NOTE]
> **Note**
> 
> Lineage added by hand and automatically may conflict with one another to cause unwanted overwrites. It is strongly recommended that lineage is edited manually in cases where lineage information is not also extracted in an automated fashion that is through [discovery scan](/latest/docs/discovery-scan-regular-node) and [EDC ingestion](/latest/docs/edc-ingestion).

#### Exporting lineage

You can export lineage from the lineage diagram. With this export feature, you can have greater control over the data lineage visualization, fostering improved collaboration, analysis, and compatibility with different tools or platforms.

To export lineage:

1. Open the lineage visualization screen for the dataset for which you want to export lineage.
2. On the top right corner of the lineage diagram, click **Export** menu.
3. Click **as CSV**, or **as Image** or **as SVG** to export the lineage in the preferred format.

![EDC_-_Export_lineage_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04f964c1-3b2c-3581-56af-885974b9bc72.png)

If you select **as SVG**, or as **Image**, then you can view the lineage diagram snapshot in the downloaded SVG and PNG.

![LineageRelations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e8c9c757-3385-fd1f-a620-72d30d1375c8.png)

If you select **as CSV**, then the lineage gets exported in the CSV format with the following column details:

- Upstream URN
- Downstream URN
- Upstream type
- Downstream type
- Upstream description
- Downstream description
- Upstream owners
- Downstream owners
- Upstream tags
- Downstream tags
- Upstream terms
- Downstream terms
- Upstream domain
- Downstream domain
- Upstream platform
- Downstream platform
- Upstream container
- Downstream container
- Upstream entity URL
- Downstream entity URL
- Upstream host/IP
- Downstream host/IP
- Upstream name
- Downstream name
- Upstream field
- Downstream field

### Adding properties to datasets

You can perform CRUD (Create, Read, Update, Delete) operations on the dataset properties. You can create new properties, modify their values, and remove them as needed. This functionality streamlines data management processes and empowers you to tailor datasets according to your requirements.

#### Adding dataset properties

Add dataset property:

1. Click on the data system folder and subfolders to see all the datasets inside that folder.
2. Click on a dataset you want to add properties for.
3. On the dataset details page, click **Properties** tab.
4. At the top right cover of the page, click **+ Add New Property**.
5. On the **Add a new Property** popup, enter the property name and value.
6. Click **Add**.

#### Editing dataset properties

Edit dataset property:

1. Click the **Edit** button located on the right side of the property row that you want to edit.
2. On the **Edit a new Property** popup, update the value.

> [!NOTE]
> **Note**
> 
> You cannot edit the name of the property.
3. Click **Save**.

#### Deleting dataset properties

Delete dataset property:

1. Click the **Delete** icon located on the right side of the property row that you want to delete.
2. On the **Delete Property** popup, click **Delete**.

> [!NOTE]
> **Note**
> 
> Think carefully before deleting the property, as this action is irreversible and cannot be undone.

### Syncing all attributes from data mapping into the EDC

You can sync all **Basic Information**, **Retention and Disposal**, and **Security Measures** attributes from the [Data Mapping Automation module](/v1/docs/using-data-mapping-automation) into the EDC.

To view these attributes:

- Open the dataset details page in the EDC and click on the Asset Map Properties.

> [!NOTE]
> **Note**
> 
> Any updates to these attributes in the Data Mapping module will be reflected in the EDC.

![EDC_-_Attributes_syncing_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-348ad93d-8a1f-86ab-6504-51b5a8b7432b.png)

### Deprecation and deletion specific assets

You can delete or deprecate the specific asset at any point in time.

For Deprecation or deletion of an asset:

1. Click on the data system folder and subfolders to see all the tables inside that folder.
2. Click on a table you want to delete or deprecate.
3. Click Options (three dots)

![EDC_-_Deleting_Assets.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c61b3d1-5838-fa83-13ff-597aa53a2faa.png)
  - To deprecate the asset, select **Mark as deprecated** option.
  - To delete the asset, select **Delete Asset** option.

### Automatic registration of content profiles in the datasets

You can automatically add content classifications to datasets. For example, when Securiti classifies content with the **Confidential** profile and then ingests that table into Enterprise Data Catalog, you see that dataset mapped to the glossary term **Confidential** content profile.

> [!NOTE]
> **Note**
> 
> The content profile registration is supported for all structured sources as well as supported unstructured file formats.

### Dataset read-only protection

You can mark datasets as read-only, providing stronger control over dataset integrity. When a dataset is set to read-only, it is protected from modifications, ensuring its contents remain unchanged unless explicitly updated by an authorized user.

To mark a dataset as read-only:

1. Open the desired dataset and click **Options** (three dots) located to the left of the **Share** button.
2. Select **Mark as read-only** to make the dataset non-editable.
3. To make the dataset editable again, select **Mark as editable** from the same menu.

**Key features**

| Feature | Description |
| --- | --- |
| Controlled unmarking with permissions | Only users with the **Edit dataset read-only** permission can add or remove the read-only status when updates are required. |
| Change log visibility | All actions related to marking or unmarking a dataset as read-only are automatically recorded in the change log, providing full auditability and transparency. |
| Improved search and discovery | You can now filter and search for datasets marked as read-only, making it easy to identify and manage protected datasets across your environment. |

## FAQs

#### The lineage tab is grayed out - why can’t I click on it?

If the lineage tab is grayed out and you can't click on it, there are several possible reasons for this behavior:

- Insufficient permissions

You may not have the necessary permissions or access rights to view the data lineage.
- Data lineage is not enabled

The data lineage feature may not be enabled or configured in your EDC instance. Administrators or data governance personnel can enable and configure data lineage features. Verify with your system administrator or consult the platform documentation for guidance on enabling data lineage.
- No lineage information is available

If there is no data lineage information available for the specific data asset or dataset you are looking at, the lineage tab may be greyed out. Ensure that the data asset has associated lineage information.

#### Does Securiti require any third-party technologies to provide data lineage? Can I replace my existing data lineage tool with Securiti? Can I enrich Securiti with lineage data from my existing tool?

It depends on how data is moved (tools used) within your organization because the lineage is generated by those tools. We will then need a way to extract that lineage metadata to populate it in our Enterprise Data Catalog. However, you can capture lineage using:

- SQL parser: Securiti has its own SQL parser to extract lineage (not just ANSI SQL, but from most SQL dialects).
- DataHub community plugins: Given that the EDC supports DataHub APIs, we can ingest lineage using the [plugins](/v1/docs/interacting-with-the-enterprise-data-catalog) supplied by the DH community.

If you require to capture lineage from a source not supported by the EDC, please submit a feature request for our evaluation.

An entity is a specific and distinguishable object in the Enterprise Data Catalog. It could represent various things like datasets or glossary terms.

Platform represents the array of supported data systems that encompass structured, unstructured, and streaming data. These systems are compatible with Enterprise Data Catalog capabilities, allowing it to effectively catalog, manage, and analyze data from a diverse range of sources. Examples of such platforms include popular data storage and processing solutions like Snowflake and MySQL.

A dataset is a structured collection of consumable data with associated metadata and features for managing, discovering, and governing data assets within an organization. Tables and files are common examples of datasets.

A URN, or Uniform Resource Name, is a Uniform Resource Identifier (URI) that is used to uniquely identify a resource, but without specifying its location or how to access it.

An Enterprise Data Catalog (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.

A process or practice where certain data assets, metadata, or data-related resources within an organization's data catalog are marked as outdated, obsolete, or no longer recommended for use.

## Related

- [Registering metadata into the Enterprise Data Catalog](/registering-metadata-into-the-enterprise-data-catalog.md)
