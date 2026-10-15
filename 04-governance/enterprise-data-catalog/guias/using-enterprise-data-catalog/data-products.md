---
title: "Data products"
slug: "data-products"
updated: 2026-08-04T09:07:14Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/data-products"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Data products

Data products are structured and managed sets of data designed to meet specific business needs or use cases within an organization. Curated and maintained by domain experts, these products ensure accuracy, reliability, and relevance.

Each data product is an independent unit managed by a specific domain team. This team is responsible for defining, publishing, and maintaining their data assets, ensuring high-quality data that meets customer needs.

#### Prerequisites

- Manage data product: It is the metadata privilege for domains to create/delete data products at the entity level. If you have this privilege for a given domain, you can create and delete data products underneath it.
- Edit data product: It is the metadata privilege to add or remove the data product for a given entity.
- You must have **Manage Data Products** permission enabled for your account. For details, refer to [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

#### Creating data products

To create a data product, you must first navigate to the domain that will contain this data product.

1. Open Enterprise Data Catalog, then **Govern > Domains**.
2. On the domains page, click any domain containing this data product.
3. Navigate to the **Data Products** tab and click **+ New Data Product**.
4. On the **Create new Data Product** popup, add name and description.
5. Click **Create**.

#### Viewing data products

You can search for the created data products in any of the following two ways:

- Navigate to the Enterprise Data Catalog dashboard and click the **Data Products** widget.

OR

- Navigate to the entity details page.
- Scroll down the page and click Data Products located at the bottom of the right sidebar.

OR

- Click any domain that has data products linked.
- Click **Data Products** tab to view the list of data products linked to the domain.

#### Editing data products

1. On the top right side of the data product, click the **Edit icon**.
2. On the **Edit Data Product** popup, update the name and/or description.
3. Click **Update**.

#### Deleting data products

- On the top right side of the data product, click **Options (three dots) > Delete**.

#### Marking data products as read only

You can mark data products as read-only. To do so:

1. Open any data product.
2. From the data product's details page, click **Options** (three dots) > **Mark as read only**.

Once marked as read-only, none of the data product's attributes can be edited, helping you maintain data integrity and ensure consistent governance across your data catalog.

To make a read-only data product editable again:

1. From the data product's details page, click **Options** (three dots) > **Mark as Editable**.

> [!NOTE]
> - To use this feature, your role requires the **Edit Data Product Read Only Status** permission. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

#### Linking data products to data entities

1. On an entity's detail page, navigate to the right panel to locate the Data Product section.
2. Click **Set Data Product**.
3. On the **Set Data Product** popup, search for the data product you'd like to add this asset to.
4. When you are done, click **Add**.

![EDC_-_Data_products.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad6ca8d8-1254-58e0-abe3-ff7bc26b8543.png)

> [!NOTE]
> **Note**
> 
> To remove an asset from a data product, click the **x** icon on the data product label. For adding, editing, or deleting other associations for the data products, read [managing associations](/v1/docs/datasets).

#### Audit trails for data products

You can view comprehensive insights about how a data product has changed over time. This can help you make informed decisions and better manage your assets.

To view the audit trail:

1. Open **Enterprise Data Catalog**, from the top right corner of the page, and click **Govern > Domains**.
2. Open the domain for which you want to see an audit trail.
3. Click the **Data Products** tab and open any data product.
4. On the upper right corner of the page, click **Change Log** to view the following audit trail details:

| Value | Description |
| --- | --- |
| Time | The time when each change occurred. |
| User | Name of the user responsible for the change. |
| Activity | Nature of the modification (for example, add, edit, delete). |
| Attribute | Specific aspects of the asset that changed. |
| New value | Updated information. |
| Old value | Previous state for a complete historical perspective. |
| Message | Additional context through accompanying messages. |

## Data products dashboard

Enterprise Data Catalog has a Data Products dashboard, designed to help you easily manage and organize your data products.

With this dashboard, you can:

- View all data products you have created.
- See associated domains, glossary terms, tags, asset counts, and owners.

To access the data products dashboard:

- Open Enterprise Data Catalog, and click **Data Products** from the EDC dashboard.

### Exploring data products dashboard

This page lets you easily manage and organize your data products.

At the top center, you can find a universal search bar. Use it to quickly locate ingested tables, existing dashboards, EDC users, and more.

Directly beneath, a secondary search field lets you filter your created data products by name or description.

To further filter the data products, you can use the following filters located below the search bar:

- Data product
- Domain
- Glossary terms
- Tags
- Owner

### Creating a data product

To create a data product:

1. On the right side of the secondary search bar, click **+ Add Data Product**.
2. On the **Create new Data Product** popup, add:
  - Name of the data product (mandatory).
  - Description of the data product.
  - Associated domain (mandatory).
3. Click **Create**.

Once the data product is created, you can see it in the data products listing page.

### Exploring data products

Below the filtering options, the table presents a list of created data products. For each created data product, you can view the following details:

- Name
- Description
- Associated glossary terms
- Associated tags
- Owners

### Linking data products with EDC entities

Once a data product is created, you can link it to any of the available EDC entities.

- Glossary term
  1. In the data-product list, locate the row for the product you want to edit and click the **Options** (three dots).
  2. Select **Update Terms** from the menu.
  3. In the **Edit Glossary Terms** popup, search for the desired glossary terms, select them, and click **Save**.
- Tags
  1. In the data-product list, locate the row for the product you want to edit and click the **Options** (three dots).
  2. Select **Update Tags** from the menu.
  3. In the **Edit Tags** popup, search for the desired tags, select them, and click **Save**.
- Owners
  1. In the data-product list, locate the row for the product you want to edit and click the **Options** (three dots).
  2. Select **Update Owners** from the menu.
  3. For each owner you have added, choose the appropriate ownership type and click **Save**.
- Domain
  1. In the data-product list, locate the row for the product you want to edit and click the **Options** (three dots).
  2. Select **Update Domain** from the menu.
  3. In the **Edit Domain** popup, search for the desired domains, select them, and click **Save**.

> [!NOTE]
> **Note**
> 
> To perform the above actions in bulk, simply select the checkboxes next to the data products you want to configure, then choose the desired action.

### Deleting data products

To delete a data product:

1. In the data-product list, locate the row for the product you want to delete and click the **Options** (three dots).
2. Select **Delete** from the menu.
3. On the confirmation popup, click **Yes, Delete**.

> [!NOTE]
> **Note**
> 
> To perform the above action in bulk, simply select the checkboxes next to the data products you want to delete, then choose the desired action.

### Bulk load capabilities for data products

You can efficiently bulk load assets into the Enterprise Data Catalog to create new data products using an Excel file.

#### Prerequisites

You must configure private cloud storage to successfully load glossaries in bulk into EDC.

#### Scope

- You can upload an xlsx file of any size.
- Bulk load capability does minimum file checks on the file format, number of columns, rows, and before starting the ingestion job.

#### Creating and updating data products using an Excel file

To upload the data product in bulk:

1. In Securiti, open **Enterprise Data Catalog > Govern > Data Products**.
2. On the data products listing page, in the middle right corner of the page, click **+ Import**.
3. On the **Bulk Import Data Product** popup, choose the .xlsx file to import.

> [!NOTE]
> **Note**
> 
> For a smooth upload, make sure your .xlsx file follows a specific format. If it does not, you might face issues uploading it. To make sure everything works well, download the sample excel template and use it as a guide for how to set up your file and read the instructions carefully.
> 
> - On the bottom left of the file import section, click **Download Sample Excel** to download the sample Excel file.

- Click **Import**.

> [!NOTE]
> **Note**
> 
> If there is an error in the file, the .xlsx file validation fails. In that case:
> 
> - Click **View Error Log** to view a list of error logs.
> - Click **Retry** to upload the right file again.

Once the import is completed, you can open the data products that you added in the .xlsx file to see the updated metadata.

- You can view the audit trails of the data products bulk import activities in the [Audit logs](/v1/docs/audit-logs-for-enterprise-data-catalog) section.
- You can also view the data products bulk import activities in the [Messages & Notifications](/v1/docs/messaging-center) section.

> [!NOTE]
> **Note**
> 
> When you upload an excel file, you receive notifications about the import process's status (started, failed, completed) in both the audit trail and the messages & notifications section. If a process is in the started state, you cannot initiate another process simultaneously.
- Securiti generates a log file whenever you bulk import data products using an Excel file. See log files for more details.

#### Instructions for importing data products using an Excel file

> [!NOTE]
> **Note**
> 
> If any mandatory field in any tab is missing or if any column contains an incorrect format, the corresponding data product cannot be created or updated. Therefore, ensure the Excel sheet is populated carefully.

#### Data product

To add or update a data product, fill out the Data Product tab, which includes the following columns:

> [!NOTE]
> **Note**
> 
> To successfully create a new data product, the **Data Product Name** and **Domain URN** fields are mandatory. If you are updating an existing data product, you must also include the **Data Product URN**. Leaving the URN blank will result in a new data product being created.

| Column | Required? | Description |
| --- | --- | --- |
| Data product URN | No | - Add the URN for the data product. Leave blank if you want the system to auto-generate a new data product. To update an existing data product, this URN must be provided. Example urn:li:dataProduct:7b8fc9d6-23a1-4fa4-967d-2874a5643cg12 |
| Data product name | Yes | - Enter the name for the data product. This is mandatory for both creation and updates. Example Sales Analytics |
| Data product description | No | - Enter a description for the data product. Example Sales data analytics product |
| Domain URN | Yes | - Enter the URN of the domain to which this data product belongs. Example urn:li:domain:fbb19274-3a99-4b5e-9c22-9h6709c45143 |
| Domain hierarchy | No | - Provide the full domain hierarchy URN if available. Example boeing.com > Aircraft Components > B737-HydraulicSystem-June2025 |
| Domain name | No | - Enter the readable name of the domain. Example B737-HydraulicSystem-June2025 |
| Governance status | No | - Specify the governance status for the data product. This is an enum field and only accepts the following values: - Under Review - Draft - Certified |

#### Properties

To add properties to a data product, fill out the Properties tab, which includes the following columns:

> [!NOTE]
> **Note**
> 
> The **Data Product URN**, **Property Type**, **Property Name**, and **Property Value** fields are all mandatory for each row.

| Column | Required? | Description |
| --- | --- | --- |
| Data product URN | Yes | - Enter the URN of the data product to which the property belongs. Example urn:li:dataProduct:7b8fc9d6-23a1-4fa4-967d-2874a5643cg12 |
| Data product name | No | - Add the name of the data product. Example Sales Analytics |
| Property type | Yes | - Specify the type of property. Example Custom |
| Property name | Yes | - Enter the name of the property. Example Business Unit |
| Property value | Yes | - Enter the value for the property. Example Sales |

#### Ownership

To assign ownership to a data product, fill out the Ownership tab, which includes the following columns:

> [!NOTE]
> **Note**
> 
> The **Data Product URN**, **Owner**, and **Ownership Type URN** fields are mandatory.

| Column | Required? | Description |
| --- | --- | --- |
| Data product URN | Yes | - Enter the URN of the data product to which the owner is being assigned. Example urn:li:dataProduct:7b8fc9d6-23a1-4fa4-967d-2874a5643cg12 |
| Data product name | No | - Add the name of the data product. Example - Glossary > Server Logs - Sales Data |
| Owner | Yes | - Enter the identifier of the owner. Example - jane.doe@insight-analytics.net - User Behavior |
| Ownership type URN | Yes | - Enter the URN of the ownership type (for example, Technical Owner, Business Owner). Example - urn:li:ownershipType:357d193f-9812-4c43-bff2-a522524c4219 - cto@nextgen-solutions.net |
| Ownership type name | No | - Enter the name of the ownership type. Example - Manager - urn:li:ownershipType:a5a2091e-f2bb-45d8-9744-08992283a3b0 |

#### Assets

To associate assets with a data product, fill out the Assets tab, which includes the following columns:

> [!NOTE]
> **Note**
> 
> The **Data Product URN**, **Asset Type**, and **Asset URN** fields are mandatory for successful association.

| Column | Required? | Description |
| --- | --- | --- |
| Data product URN | Yes | - Enter the URN of the data product to which the asset is being assigned. Example - urn:li:dataProduct:7b8fc9d6-23a1-4fa4-967d-2874a5643cg12 |
| Data product name | No | - Add the name of the data product. Example - Sales Analytics |
| Asset type | Yes | - Enter the type of asset. Example - Dataset |
| Asset URN | Yes | - Enter the URN of the asset to be associated. Example - urn:li:dataset:(urn:li:dataPlatform:mysql,sales-db,PROD) |
| Asset name | No | - Add the name of the asset. Example - Sales DB |

#### Glossary Terms

To associate glossary terms with a data product, fill out the Glossary Terms tab, which includes the following columns:

> [!NOTE]
> **Note**
> 
> To successfully associate a glossary term, the Data Product URN and Term URN fields are mandatory.

| Column | Required? | Description |
| --- | --- | --- |
| Data product URN | Yes | - Enter the URN of the data product to which the glossary term is being assigned. Example - urn:li:dataProduct:7b8fc9d6-23a1-4fa4-967d-2874a5643cg12 |
| Data product name | No | - Add the name of the data product. Example - Sales Analytics |
| Term hierarchy | No | - Add the full hierarchy of the term. Example - Glossary > Server Logs |
| Term URN | Yes | - Enter the URN of the glossary term to associate. Example - urn:li:glossaryTerm:revenue |
| Term name | No | - Add the name of the glossary term. Example - Revenue |

#### Tags

To tag a data product, fill out the Tags tab, which includes the following columns:

> [!NOTE]
> **Note**
> 
> The **Data Product URN** and **Tag URN** fields are mandatory.

| Column | Required? | Description |
| --- | --- | --- |
| Data product URN | Yes | - Enter the URN of the data product to which the tag is being assigned. Example - urn:li:dataProduct:7b8fc9d6-23a1-4fa4-967d-2874a5643cg12 |
| Data product name | No | - Add the name of the data product. Example - Sales Analytics |
| Tag URN | Yes | - Enter the URN of the tag you want to assign. Example - urn:li:tag:real-time |
| Tag name | No | - Add the name of the tag. Example - urn:li:tag:real-time |

#### Sample data

The sample data tab provides example entries for each section to help you understand the correct format. It includes sample data for every tab in the template, letting you reference the examples when populating your sheet.

#### Log files for monitoring the data products load activities

Securiti generates a log file whenever you bulk import data products using an Excel file. This log file provides a detailed overview of the process, including the number of new entries created and any failures encountered during the bulk upload.

To access the log file:

1. Open the **Messages & Notifications** section, where you will receive two messages—one indicating that the bulk upload has started and another confirming its completion. The completion message includes details on any failed rows along with the log file name.
2. Copy the log file name from this message.
3. Click your avatar at the bottom of the left navigation bar and select **My Downloads**.
4. Use the copied log file name to search for the file, then download and open it to review the log details.

The log file typically provides a summary of the bulk import process, highlighting both successful entries and failures.

![Data_products_-_log_files.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-29f41b9e-9400-bdf7-16ee-8416d2c538a4.png)

In the above example, the error indicates that the **Data Product Name** is a mandatory field, was left blank in row 2 of the **Data Product** tab in the Excel file. Since the name is required for creating a new data product, the system rejected the entry and logged it as a failure.

### Exporting data product aspects

You can export data products including schema metadata and and various detailed attributes. This capability ensures that the exported data is more useful and actionable for analysis, reporting, or further processing.

The data product aspects that you can export are listed below.

| Aspects |
| --- |
| Data product | - Data product URN - Data product name - Data product description - Domain URN - Domain hierarchy - Domain name - Governance status |
| Data product properties | - Data product URN - Data product name - Property type - Property name - Property value |
| Structured properties | - Data product URN - Data product name - Property URN - Property name - Property cardinality - Property value type - Property value |
| Data product ownership | - Data product URN - Data product name - Owner - Ownership type URN - Ownership type name |
| Data product assets | - Data product URN - Data product name - Asset type - Asset URN - Asset name |
| Data product glossary terms | - Data product URN - Data product name - Term hierarchy - Term URN - Term name |
| Data product tags | - Data product URN - Data product name - Tag URN - Tag name |

To export data product aspects:

1. Open the data products page and select the data product you want to export by marking the checkboxes.
2. Click **Export** from the popup menu that appears at the bottom of the page.

> [!NOTE]
> **Note**
> 
> - The export option is also available under the **Actions** button, located on the top right side of the page.
> - The export action honors your [RBAC permissions](/latest/docs/edc-rbac-permissions-and-roles). It includes only the entities you have permission to view. Entities you do not have access to are automatically excluded from the export.

- If the export results contain fewer than 1000 records, the .xlsx file downloads directly to your device.
- When your search results exceed 1000 records, you receives a message on the screen that says, “Export Started, Once file is ready, we'll email you the link”.
- Check your registered email address for a message containing the requested .xlxs file as an attachment.

An Enterprise Data Catalog (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.

Domain is a logical or thematic grouping of related data assets. Domains are used to categorize and organize data assets based on their subject matter or the business context they belong to. For example, you might have a Finance domain that includes data related to financial transactions, reports, and analysis, or a Human Resources domain that encompasses data related to employee information, payroll, and HR processes.

A glossary term is a collection or repository of terms and their definitions that are relevant to the organization. This glossary serves as a reference guide for users to understand the common terminology used within the organization.

Refer to loosely defined terms that can be applied to data assets and other catalog entities. These tags make it easier to organize and search for specific assets within the Enterprise Data Catalog.

The Owner is the owner of your assessment; you can also have a Co-owner for that assessment. You can only assign the Owner role to a user accessing the current assessment organization. No Guest User (internal or external) can assume the role of an Owner.

Platform represents the array of supported data systems that encompass structured, unstructured, and streaming data. These systems are compatible with Enterprise Data Catalog capabilities, allowing it to effectively catalog, manage, and analyze data from a diverse range of sources. Examples of such platforms include popular data storage and processing solutions like Snowflake and MySQL.

A URN, or Uniform Resource Name, is a Uniform Resource Identifier (URI) that is used to uniquely identify a resource, but without specifying its location or how to access it.

Aspect refers to a collection of attributes that describes a particular facet of an entity. It is a way to look at and understand the various characteristics or sets of attributes of data objects. To put it simply, an aspect in Enterprise Data Catalog is a way of describing a particular aspect of your data, such as its quality, lineage, usage, or metadata.

## Related

- [Domains](/domains.md)
