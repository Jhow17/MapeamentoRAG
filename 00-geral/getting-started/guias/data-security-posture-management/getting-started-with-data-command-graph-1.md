---
title: "Getting Started with Data Command Graph"
slug: "getting-started-with-data-command-graph-1"
updated: 2026-08-11T07:04:40Z
published: 2026-08-11T07:04:40Z
canonical: "helpcenter.securiti.ai/getting-started-with-data-command-graph-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Data Command Graph

Securiti's Data Command Graph unifies metadata relationships across all modules, replacing siloed approaches to manage data discovery, privacy, security, and compliance. It provides a comprehensive view of data and relationships, enabling you to visualize and act on insights. With its graph database model, use **Graph Explorer** to create custom queries, **Inventory** to browse and filter data, and app-specific graphs in **Sensitive Data Intelligence**, **Data Access Governance**, and **Enterprise Data Catalog** to view metadata for those modules.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data%20Command%20Graph.drawio(2).svg)

### Prerequisite

To use the Data Command Graph effectively, make sure your modules are enabled for data ingestion. This includes connecting data systems, third-party applications, AI platforms or models, IaaS cloud accounts, and other relevant data sources to the Securiti platform. Once connected, your data is available for exploration and analysis.

### Choose your data exploration objective

After your data is available, choose the graph module you wish to explore your data in. This varies based on the use case as explained in the table below.

[Learn more](/v1/docs/graph-module-comparison-and-use-cases).

| **Graph Explorer** Use Graph Explorer to create custom queries and explore data and relationships across all entities of Securiti’s modules. Graph Explorer also lets you use JSON Expression for queries. [Learn more](/latest/docs/using-graph-explorer). | [Embedded content](https://app.storylane.io/demo/hrndx8v0o1q5?embed=inline) |
| --- | --- |
| **Inventory** Use Inventory to browse and filter properties for data across all entities of Securiti's modules. [Learn more](/v1/docs/using-inventory). | ![Inventory management interface displaying cloud hosting options and data services available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventorydashboard.png) |
| **App-specific inventories** Use the app-specific inventories or Data Command graph pages to explore and filter entities specific to your Sensitive Data Intelligence, Data Access Governance and Enterprise Data Catalog modules only. See the rows below for each app-specific inventory. [Learn more](/latest/docs/using-the-app-specific-inventories). | ![Data command graph illustrating relationships between various data elements and policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datacommandgraph.png) |
| **Universal Data Explorer in SDI** Use Universal Data Explorer in Sensitive Data Intelligence to browse and filter entities relevant to Sensitive Data Intelligence module only. Apply filters by properties and view results for your sensitive data, scans, and classifications in grid and circular graph. [Learn more](/latest/docs/using-the-universal-data-explorer). | ![Visual representation of data systems and their relationships in a data exploration tool.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/universaldataexplorer.png) |
| **Data Command Graph in DAG** Use Data Governance Command Graph to browse and filter entities relevant to the Data Access Governance module only. Apply filters by properties and view access intelligence results in grid and circular graph. [Learn more](/latest/docs/data-access-governance-data-command-graph). | ![Data Command Graph interface displaying identity provider information and user principal counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datacommandgraph_identityproviderquery.png) |
| **Data Command Graph in EDC** Use the Data Command Graph page in Enterprise Data Catalog to browse and filter data catalog entities only. Apply filters by properties and view results for datasets in grid and circular graph. [Learn more](/latest/docs/edc-specific-data-command-graph-dashboard). | ![Data Command Graph interface displaying hosting options and scanned data statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/enterprisedatacatalog_dashboard.png) |

### Getting Started with Graph Explorer

In Graph Explorer, you are presented with a blank page to start building your custom queries with entities across Securiti platform. Apply filters by adding properties and relationships to your entities and explore various options to manage results including widget creation, instance exploration or saving your views.

#### Step 1 - Choose a mode to build query

| ![Graph Explorer interface showing options to add filters and begin search.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add Query button_Graph Explorer(1).png) | **Query builder** In Graph Explorer, you can build queries in **Query builder** mode by selecting entities and applying filters from the filter panel. You can select your entities by clicking on the **+** on the Graph Explorer page and selecting an Entity from the available groups. Each Group contains entities representing to a domain in the Securiti module. For example, **Data** group contains all entities related to data management and data systems. Click **Run Query**. [Learn more.](/v1/docs/managing-queries-in-the-graph-explorer) |
| --- | --- |
| ![Graph Explorer interface displaying query filters and options for data exploration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Running JSON query_DCG(1).png) | **JSON View** You can also build queries in **JSON View** mode if you already have a JSON query. Simply upload or paste your JSON query in the code window. Click **Run Query**. [Learn more.](/v1/docs/using-json-expression-for-queries) |

#### Step 2 - View query results

After creating your query, you can view and analyze your filters in the following supported views.

| **Table View** Lets you view your query results in form of a grid where rows represent instances of an entity with applied filters and columns represent the properties for that entity. This the default view and provides insights into properties for an entity or individual instances. [Learn more.](/v1/docs/using-table-view-in-graph-explorer) | ![Graph Explorer interface displaying AI Agents and their associated account details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/AI Agent with account query_Graph Explorer(1).png) |
| --- | --- |
| **Relationship View** Lets you analyze relationships applied to entities in a segmented and easy to understand view. Use the view if you want to understand the relationships between entities instead of being more focused on properties and graphical representation. [Learn more.](/v1/docs/using-relationship-view-in-graph-explorer) | ![Graph Explorer displaying security posture findings related to GCP Pub Sub subscriptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filtered query result_Graph Explorer(1).png) |

#### Step 3 - Explore results at instance level

In Graph Explorer and Inventory pages, you can explore instances with the following options to view granular details and insights.

| ![Graph Explorer displaying data system and asset details for Amazon S3 resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/metadataexplorer_graphexplorer.png) | **Metadata explorer** Click on any instance to view its metadata and details such as file path, owner and properties. The metadata explorer provides details about an instance. The metadata explorer also contains **Explore** and **View JSON** options explained below. [Learn more.](/v1/docs/inspecting-instances-in-graph-explorer) |
| --- | --- |
| ![Overview of AWS Cloud components including policies, data systems, and storage details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/instanceviewpopup_reportingdashboard(2).png) | **Instance explorer** As one of the most powerful tools of the Data Command Graph, instance explorer provides graphical and tabular view for an instance's relationships, entity counts and properties. Click **Explore** on the metadata explorer to open Instance explorer. [Learn more.](/v1/docs/inspecting-instances-in-graph-explorer) |
| ![JSON expression displayed in Graph Explorer for filtering AWS data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Copy and download JSON_DCG(1).png) | **View JSON** Click **View JSON** on the metadata explorer to view, copy, and download the JSON code for your instance's query. Use the JSON value to create queries, share with others or for creating widgets. This option is not available for Inventory and module-specific inventories. [Learn more.](/v1/docs/inspecting-instances-in-graph-explorer) |

#### Step 4 - Manage query results

After creating views or filters, you can save your views, create widgets, share your queries or export CSV.

| **Create widgets** You can create grid or metric widgets for your data if you want to analyze them in a dashboard or use them for data analysis and reporting purposes. Click **Create Widget** and specify widget details on the modal. Your widget is saved in your selected dashboard. The created widgets can be explored in the Reporting Dashboard module. [Learn more.](/v1/docs/creating-widgets-in-graph-explorer) | [Embedded content](https://app.storylane.io/demo/msy6mxl21ewv?embed=inline) |
| --- | --- |
| **Save View** Save your queries or views to use later or share them with other users. [Learn more.](/v1/docs/managing-queries-in-the-graph-explorer) | ![Data command graph displaying compliance view with various data systems and relationships.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_savingview(1).png) |
| **Share JSON queries** In JSON View, you can copy or download the JSON code for your query which can be used for various purposes such as sharing a JSON query with other users. [Learn more.](/v1/docs/using-json-expression-for-queries) | ![Graph Explorer interface displaying data system and hosting asset details with query options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/shareanddownloadjsoncode_graphexplorer.png) |
| **Export CSV for grids** In **Table View** you can export the results in form of a CSV file. The CSV file can be used for sharing or analysis purposes. [Learn more.](/v1/docs/using-table-view-in-graph-explorer) | ![Graph Explorer displaying data system and security posture findings with asset details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export CSV option_Graph Explorer(1).png) |

### Getting Started with Inventory

In Inventory, you can browse and filter through entities across all modules in Securiti platform. The graph module is used to view entities, their data and properties on one page without having to shift between various modules. Unlike Graph Explorer, you can view results in tabular or grid view only.

#### Step 1 - Search or select entities

| ![Cloud hosting options displayed with various data services and their respective counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventorydashboard_filters.png) | **Apply filters** On the left menu for entities, select an entity you want to explore data for. Clicking on an entity displays all instances in the grid on right side of the menu. [Learn more.](/v1/docs/using-inventory) |
| --- | --- |

#### Step 2 - Filter by properties

| **Apply properties** After selecting an entity, you can start applying filters by properties. Unlike graph explorer, relationships cannot be added. Entities can only be filtered by their properties. [Learn more.](/v1/docs/using-the-inventory-dashboard) | ![Inventory interface displaying cloud hosting options and filter selections for data properties.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventoryproperties.png) |
| --- | --- |

#### Step 3 - View filtered results

After creating views or filters, you view the filtered results in grid.

| ![Inventory view showing Azure Cloud hosting details and associated data counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewfilteredresults_inventorydashboard.png) | **View filters** After selecting entities and their properties, you can view the filtered results on the grid along with the entity count metric on the top row of the grid. [Learn more.](/v1/docs/using-inventory) |
| --- | --- |

#### Step 4 - Explore results at instance level

In Inventory pages, you can explore instances by using the Instance Explorer or viewing their metadata.

| **Metadata explorer** Click on any instance to view its metadata and details such as file path, owner and properties. The metadata explorer provides details about an instance. The metadata explorer also contains **Explore** option explained below. [Learn more.](/v1/docs/using-instance-explorer-in-inventory) | ![Inventory interface displaying cloud hosting options and Azure Cloud details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/metadataexplorer_inventorydashboard.png) |
| --- | --- |
| **Instance explorer** As one of the most powerful tools of the Data Command Graph, instance explorer provides graphical and tabular view for an instance's relationships, entity counts and properties. Click **Explore** on the metadata explorer to open Instance explorer. [Learn more.](/v1/docs/using-instance-explorer-in-inventory) | ![Overview of Azure Cloud hosting, data systems, files, and related properties.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/instanceexplorer_inventorydashboard.png) |

#### Step 5 - Manage filtered results

In Inventory pages, you can create widgets for your filtered results in the Reporting Dashboard or save views.

| ![Inventory interface displaying Azure Cloud hosting options and filter settings for compliance.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveview_inventory.png) | **Save View** Save your filters or views to use later or share them with other users. [Learn more.](/v1/docs/using-the-inventory-dashboard) |
| --- | --- |

### Getting Started with app-specific inventories

In module-specific inventories or Data Command Graph pages, you can browse and filter through entities for your module only. The functionality is similar to that in Inventory with an additional feature of a circular graph.

| **Universal Data Explorer in SDI** On this page, you can view entities for Sensitive Data Intelligence only and explore data such as scan results, data systems, etc. [Learn more.](/v1/docs/using-the-app-specific-inventories) | ![Overview of data systems, scanned tables, and documents in a relationship graph.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/universaldataexplorer(1).png) |
| --- | --- |
| **Data Command Graph in DAG** On this page, you can view entities for Data Access Governance only and explore data such as IAM roles and policies, access management, users, etc. [Learn more.](/v1/docs/using-the-app-specific-inventories) | ![Data command graph illustrating relationships between various data elements and policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datacommandgraph(1).png) |
| **Data Command Graph in EDC** On this page, you can view entities for Enterprise Data Catalog only and explore data such as data, glossary, domains, etc. [Learn more.](/v1/docs/using-the-app-specific-inventories) | ![Data Command Graph displaying various data systems and their relationships in a circular layout.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/enterprisedatacatalog_dcg.png) |

#### Step 1 - Search or select entities

| ![User interface displaying hosting options and data categories for cloud services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyingfilters_dcg.png) | **Apply filters** On the bottom of the page below the circular graph, from the left menu for entities, select an entity you want to explore data for. Clicking on an entity displays all instances in the grid on right side of the menu. [Learn more.](/v1/docs/using-the-app-specific-inventories) |
| --- | --- |

#### Step 2 - Filter by properties

| **Apply properties** On the top of the page, after selecting an entity you can start applying filters by properties. Unlike graph explorer, relationships cannot be added. Entities can only be filtered by their properties. [Learn more.](/v1/docs/using-the-app-specific-inventories) | ![Data Command Graph displaying hosting options including AWS Cloud and other entities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfitlers_dcg.png) |
| --- | --- |

#### Step 3 - View filtered results

After creating views or filters, you can view filtered results on the circular graph on top of the page as well as on the grid.

| ![Overview of cloud hosting details including AWS Cloud and data system counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewfilteredresults_dcg.png) | **View filters** After selecting entities and their properties, you can view the filtered results on the grid along with the entity count metric on the top row of the grid. [Learn more.](/v1/docs/using-the-app-specific-inventories) |
| --- | --- |

#### Step 4 - Explore results at instance level

In Inventory pages, you can explore instances by using the Instance Explorer or viewing their metadata.

| **Metadata explorer** Click on any instance to view its metadata and details such as file path, owner and properties. The metadata explorer provides details about an instance. The metadata explorer also contains **Explore** option explained below. [Learn more.](/v1/docs/using-instance-explorer-in-the-app-specific-inventories-dcg) | ![Interface showing AWS Cloud hosting details and data system statistics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/metadataexplorer_dcg.png) |
| --- | --- |
| **Instance explorer** As one of the most powerful tools of the Data Command Graph, instance explorer provides graphical and tabular view for an instance's relationships, entity counts and properties. Click **Explore** on the metadata explorer to open Instance explorer. [Learn more.](/v1/docs/using-instance-explorer-in-the-app-specific-inventories-dcg) | ![Overview of AWS Cloud services, including data systems, files, and account details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/instancexplorer_dcg.png) |

#### Step 5 - Manage filtered results

In Inventory pages, you can create widgets for your filtered results in the Reporting Dashboard, save views or export CSV of your results from the grid.

| ![Data Command Graph showing AWS Cloud assets and their relationships in a visual format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveview_dcg.png) | **Save View** Save your filters or views to use later or share them with other users. [Learn more.](/v1/docs/using-the-inventory-dashboard) |
| --- | --- |

### Using circular graph

| **Circular graph** The circular graph in app-specific inventories represent your module's entities, their counts and connections with other entities. It provides a source of visualizing connections in one place. You can hover over the graph to explore connections for an entity of your choice. [Learn more.](/v1/docs/using-the-app-specific-inventories) | ![Data Command Graph displaying various data systems and their relationships visually represented.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/circularview_dcg.png) |
| --- | --- |

### Using Identity Graph Explorer

> [!NOTE]
> **Important**
> 
> This page is for Data Access Governance queries only.

| ![Overview of data systems with various asset types and scanned table statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/savedviews_dcg.png) | **Identity Graph Explorer** Near the top right corner of the **Data Governance Command Graph** page, you can select **Identity Graph Explorer** to create custom queries and explore relationships for identity and access management only. The Identity Graph Explorer offers same functionalities and implementation as Graph Explorer but for **Data Access Governance** module only. You can access system views from the page to explore predefined queries. See [Getting Started with Graph Explorer](/v1/docs/getting-started-with-data-command-graph#getting-started-with-graph-explorer), for more information. |
| --- | --- |

### Data Command Graph API documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Data Command Graph API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the docs** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without setting up a separate environment. [Learn more](https://securiti-doc-router.securiti.xyz/modules/data-command-graph/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://docs.securiti.ai/modules/data-command-graph/apidocs/index.html#section/Authentication) | ![gs_dcg_postman.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b760ebd0-0123-492d-383c-874f52f188c5.png) |

A JSON code, which is generated for an applied filter. The JSON expression can be used as a query to fetch information about the nodes specified in the filter. The expression is typically formatted in JSON (JavaScript Object Notation), and serves as a structured representation of the specified conditions for querying or modifying graph database content.

A graph modeling term. A distinct and identifiable object or unit within the Securiti system, represented as a node or a subnode in the graph database. Entities are a part of Securiti's modules such as **Data Element** from Sensitive Data Intelligence, or **User** in Securiti. Entities can have properties and relationships with other entities.

A collection of units belonging to the same product area in Securiti.
