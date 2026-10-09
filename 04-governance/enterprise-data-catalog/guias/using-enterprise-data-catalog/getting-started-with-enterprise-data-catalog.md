---
title: "Getting Started with Enterprise Data Catalog"
slug: "getting-started-with-enterprise-data-catalog"
updated: 2026-07-21T12:56:52Z
published: 2026-07-21T12:56:52Z
canonical: "helpcenter.securiti.ai/getting-started-with-enterprise-data-catalog"
stale: true
area: governance
modulo: enterprise-data-catalo
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Enterprise Data Catalog

Enterprise Data Catalog is a centralized data explorer that lets you register datasets manually and automatically. This includes all relevant metadata, and organizing them for easy navigation, search, and updates. The solution also lets you enhance datasets with tags, glossaries, and other annotations, enabling quick and efficient retrieval of any registered dataset and its associated information. With this complete picture of your data, EDC supports your data governance, privacy, and security efforts.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Enterprise%20Data%20Catalog-Page-3.drawio(1).svg)

### Step 1 - Define your Enterprise Data Catalog objective

Identify the primary goals for your Enterprise Data Catalog, such as improving data accessibility, enhancing governance, and supporting analytics. Engage with stakeholders to understand their needs, assess current challenges, and set measurable outcomes to guide the catalog’s development, effectively.

[Learn more](/v1/docs/objective-of-enterprise-data-catalog).

### Step 2 - Define your Enterprise Data Catalog scope

After refining the objective, define the scope of your Enterprise Data Catalog by identifying key data sources, systems, and stakeholders. Prioritize critical data assets, determine necessary integrations, and clarify roles for data owners, stewards, and end users. Start with a pilot phase focusing on high-value datasets, then expand as adoption grows. Regularly review and update the catalog to meet evolving needs.

[Learn more](/v1/docs/scope-of-the-enterprise-data-catalog).

### Step 3 - Identity and catalog data sources

Compile a comprehensive inventory of all data sources to be included in the Enterprise Data Catalog, such as databases, data lakes, cloud storage, and more. It is essential to capture and document data from all relevant systems, applications, and platforms to ensure easy discovery for users. This step is crucial for achieving full data visibility across the enterprise.

> [!NOTE]
> **Note**
> 
> Securiti offers out-of-the-box integration for over 300 SaaS and self-hosted platforms.
> 
> [Learn more](/latest/docs/managing-data-system-connectors).

### Step 4 - Establish data governance and ownership

Establish a framework for effective data management by defining ownership roles, implementing strong governance policies, and creating a data domain hierarchy to ensure data integrity, accountability, and high quality across your organization.

| ![Ownership.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-064f893b-ef66-5235-b7a1-642b3a2161e3.png) | **Define ownership roles** Customize ownership relationships in the Enterprise Data Catalog to better align with your organization's terminology. Adjust the predefined ownership types to suit stakeholder needs, ensuring accurate data asset management. For example, a **Compliance Officer** - An individual tasked with ensuring that data handling practices adhere to legal and regulatory standards. [Learn more](/latest/docs/edcownership). |
| --- | --- |
| ![domain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aeff890f-4b0d-52fa-94ac-1278621cfd37.png) | **Create a data domain hierarchy** Create domains and subdomains to logically categorize and organize data based on business areas. Domain categorizes data assets by broad business areas, while subdomains refine these categories into more specific topics. For example, the **Engineering** domain covers all engineering functions, and the **Software** subdomain under **Engineering** focuses on software development and management. [Learn more](/v1/docs/domains). |

### Step 5 - Curate the business metadata

Establish comprehensive business metadata and glossaries to ensure all stakeholders share a common understanding of data terms. Collaborate with business users and subject matter experts to identify key terms and concepts. Define clear, consistent definitions, and assign data stewards to manage the glossary. Standardize naming conventions for uniformity, promote adoption through training and support, and regularly maintain the glossary to ensure accuracy and relevance. This foundational work enhances data quality, communication, and effective governance across the organization.

### Step 6 - Access and harvest technical metadata

#### Step 6 A- Ingest metadata

Gather and manage information about your data systems by accessing technical metadata, which includes details like file formats, data types, and relationships. Choose an appropriate method to ingest metadata and data lineage, ensuring consistency by matching URNs if using multiple methods. This ensures data accuracy, traceability, and availability across your organization.

Register your metadata into the EDC using any of the following methods. Method 1 uses Sensitive Data Intelligence (SDI) for metadata ingestion. SDI scans data sources to discover assets, classify sensitive data, and capture lineage information. EDC then uses this metadata to catalog and organize assets, making them searchable, traceable, and easier to govern across the organization. Method 2 involves third-party connectors developed by the DataHub community.

| Method 1 |
| --- |
| **Automatic registration** Bulk push structured, unstructured, and streaming datasets into the Enterprise Data Catalog. Automatic registration uses a discovery scan to search and analyze data sources, automatically registering and cataloging the discovered data without extra steps. This method efficiently catalogs large and diverse datasets. [Learn more](/v1/docs/registering-metadata-into-the-enterprise-data-catalog). | [Embedded content](https://player.vimeo.com/video/901758979) |
| **Manual registration** Manual registration involves selecting specific datasets to add to the Enterprise Data Catalog. This method is suitable for selective and precise cataloging of specific datasets, especially when detailed review and validation are required. [Learn more](/v1/docs/registering-metadata-into-the-enterprise-data-catalog). | [Embedded content](https://player.vimeo.com/video/901758979) |

| Method 2 |
| --- |
| [Embedded content](https://player.vimeo.com/video/901772356) | **EDC ingestion** This ingestion method enhances the connector support provided by the Sensitive Data Intelligence module. The EDC ingestion capability lets you configure and execute additional connectors that support data sources not covered by the SDI module. This includes sources such as ETL tools (e.g., DBT) and data models from platforms like Looker. [Learn more](/v1/docs/edc-ingestion). |

#### Step 6B - Register data lineage

Register lineage to capture and track the flow of data through various systems, documenting transformations and dependencies. This visibility enhances understanding of data origins, ensures compliance, and supports effective data governance.

| **Document data lineage** With data lineage, you can map the flow of data through your organization, detailing its origins, movements, and endpoints. Column-level lineage tracks changes and movements for each specific data column, while table-level lineage tracks at the table level. [Learn more](/v1/docs/datasets). | [Embedded content](https://player.vimeo.com/video/901773979) |
| --- | --- |

### Step 7 - Metadata collection and curation

Systematically gather and manage metadata from your data sources to enhance data discovery, governance, and usability across the organization. Focus on capturing essential details about each data asset, including definitions, classifications, and relationships. Utilize automation tools for data lineage, classification, and transformation during ingestion to streamline the curation process. This ensures all relevant information is organized and maintained, making data assets more searchable, understandable, and valuable for users in their decision-making processes.

### Step 8 - Create a training strategy

Develop a comprehensive training strategy to equip users with the skills to access, search, and utilize the data catalog effectively. Tailor training programs for different user groups, offer hands-on workshops, and create clear documentation and video tutorials. Communicate the catalog's value, promote best practices, and provide ongoing support to ensure users can maximize its benefits. Collect feedback regularly to refine training resources as the catalog evolves.

### Step 9 - Core offerings

Enterprise Data Catalog offers essential tools to enhance data management and usability. From ensuring data quality to facilitating collaboration, our core offerings empower users to analyze data, monitor changes, and visualize relationships, optimizing access and usage for informed decision-making.

Explore how these capabilities can transform your data ecosystem and drive informed decision-making.

| [Embedded content](https://player.vimeo.com/video/901768470) | **Analyze data quality** With the data quality framework, perform data quality assessments to ensure data meets specific standards, expectations, and criteria, thereby improving data reliability. **Example** **Value range checks**: This validation confirms that data falls within expected ranges, flagging negative numbers in **Sales Quantity** to identify input errors that could skew analysis. [Learn more](/v1/docs/data-quality-framework). |
| --- | --- |
| ![WF.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66b67933-9c52-d043-c4ac-f7afd412456f.png) | **Trigger workflow on metadata change** With the **Data Catalog Trigger** node, create triggers that monitor and respond to changes in metadata within the EDC. This node initiates workflows when assets are added, modified, permanently deleted, or soft deleted, ensuring efficient management of data assets. [Learn more](/v1/docs/trigger-nodes-data-catalog). |
| ![WF.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66b67933-9c52-d043-c4ac-f7afd412456f.png) | **Update EDC metadata** With **Data Catalog** node, update the EDC by incorporating metadata collected throughout the workflow. This node lets you perform Upsert operations on catalog entities, including Containers, Datasets, and Glossary terms, ensuring that your data catalog remains accurate and current throughout the workflow. [Learn more](/v1/docs/data-catalog). |
| ![DCG.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f585637-60f7-da71-4812-6ddeab867f6b.png) | **Visualize data relationships** Use the **Data Command Graph** to map and visualize the interactions among various data elements. The Data Command Graph provides insights into how data points connect, helping you understand the structure of your data ecosystem and facilitating better data management and analysis. [Learn more](/v1/docs/edc-specific-data-command-graph-dashboard). |
| ![Messaging_Center.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-79bc0732-b767-352d-6a85-b8bfa1753a82.png) | **Collaborate in EDC** Utilize the **Messaging Center** to enhance collaboration within the Enterprise Data Catalog. Users can comment, ask questions, and provide feedback on data assets. This feature captures and shares tribal knowledge, ensuring that everyone involved has a clear understanding of the available data assets and their contexts. [Learn more](/v1/docs/messaging-center). |
| ![Search.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e563853d-1711-e692-bc66-3353b65d5b5e.png) | **Search data assets** Utilize the search capability to quickly locate data assets in the catalog using the search functionality. Apply **basic filters** like platform, environment, and type to narrow results. For **advanced queries**, use specific attributes and logical expressions. Exclude terms with a minus sign and initiate complex queries with the **/q** operator for better results. [Learn more](/v1/docs/edc-dashboard). |
| ![Usage_Analytics.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f78edb8b-e699-2787-a50f-5091439b578c.png) | **Monitor catalog usage** Monitor catalog usage effectively with **Usage Analytics**. It provides valuable insights into how metadata in the catalog is accessed and utilized across your organization. [Learn more](/v1/docs/usage-analytics). |

### Step 10 - EDC API documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The EDC API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without setting up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-catalog/apidocs/index.html). | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **GraphQL APIs** EDC offers a powerful GraphQL API for programmatic interaction with your organization’s Metadata Graph, enabling efficient access to entities and relationships. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-catalog/apidocs/index.html). | ![GraphQL_APIs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8029da09-5817-8110-d1d2-c96e753769b1.png) |
| **Download the postman collection** We also provide postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-catalog/apidocs/index.html). | ![postman_collection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a001929b-c959-5d47-8ff9-9279f6ed1cae.png) |

An Enterprise Data Catalog (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.

Domain is a logical or thematic grouping of related data assets. Domains are used to categorize and organize data assets based on their subject matter or the business context they belong to. For example, you might have a Finance domain that includes data related to financial transactions, reports, and analysis, or a Human Resources domain that encompasses data related to employee information, payroll, and HR processes.

A URN, or Uniform Resource Name, is a Uniform Resource Identifier (URI) that is used to uniquely identify a resource, but without specifying its location or how to access it.

Containers are structures or repositories that hold and organize related data assets. These assets could include datasets, tables, files, or other data-related items. Containers for those assets can be folders, schemas, and databases. Containers help categorize and manage data assets, making it easier for you to discover, access, and understand the data within them.

A dataset is a structured collection of consumable data with associated metadata and features for managing, discovering, and governing data assets within an organization. Tables and files are common examples of datasets.

A glossary term is a collection or repository of terms and their definitions that are relevant to the organization. This glossary serves as a reference guide for users to understand the common terminology used within the organization.
