---
title: "Graph module comparison and use cases"
slug: "graph-module-comparison-and-use-cases"
updated: 2026-05-11T07:39:20Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/graph-module-comparison-and-use-cases"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Graph module comparison and use cases

The Data Command Graph (DCG) serves as the cornerstone technology in Securiti's Knowledge graph, utilizing graph database modeling to access metadata for modules across the platform. It represents relationships and properties for entities through an optimized approach, as you apply filters and explore relationships in both graphical and tabular forms.

Securiti utilizes Data Command Graph through different graph modules, each serving its unique functionality. The table below compares graph modules and their functionalities.

| Graph module | Description | Use case example |
| --- | --- | --- |
| Graph Explorer | Lets you create custom filters and complex queries as you access entities across all modules in Securiti platform. Visualize your data in graph and grid views and save them. You can export your results as CSV and also save them as JSON format. For more information, see [Using Graph Explorer](/v1/docs/using-graph-explorer). | How many data systems are related to a particular user? Also fetch the assessments for that data system. To do so, you can select the **Data System** node from the filter panel and add relationship to it by adding **Securiti User** node. Filter the **Securiti User** by **Name** property and select the appropriate user. Next, add relationship to the parent node by selecting the **Assessment** node. ![graphexplorer_usecases.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-386f2655-9902-7f4d-b023-508c71eb255b.png) |
| Inventory | Browse and navigate through all the nodes across Securiti platform. Apply filters to entities and their attributes. The inventory page offers a complete view of each collected data system, cloud service, File, Table, Column and any other supported object type which has been ingested into the Data Command Graph. Inventory lets you have a quick look at nodes and their data without having to access the individual module. For more information, see [Using Inventory](/v1/docs/using-inventory). | How many cloud services have a particular asset type? To do so, simply select the **Cloud Service** entity from the menu and filter it by the **Asset Type** property. Visualize the required data on the grid panel. ![inventory_usecase.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2717228d-6538-cd55-c66c-0d7a090f149f.png) |
| Circular (DCG) Graph View | The Circular (DCG) Graph View is a pre-defined graph with curated node selections for exploring graph. This view is available for some of the modules currently, including Sensitive Data Intelligence, Data Access Governance, and Enterprise Data Catalog. These app-specific inventories provide a granular view into your module's data and let you view the data in a circular graph view as well as a grid view on the bottom of the page. Apply filters based on properties of your selected entities for precise results. This view automatically traverses every relationship between the nodes in the circular graph when you apply node property filters. You can also save and export your views. For more information, see [Using the app-specific inventories](/v1/docs/using-the-app-specific-inventories). | - **Universal Data Explorer in SDI** Which data system instances have specific number of PD attributes? To do so, select the **Data System** entity and apply filters for **Volume of PD Attributes**. ![Data relationship graph showing various data systems and their connections in a circular layout.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Universal Data Explorer_SDI.png) - **Data Command Graph in DAG** See all Identity Sources with Microsoft 365 Provider. To do so, select the **Identity Source** entity and choose your O365 provider in the **Provider Name** entity. ![dagdcg_usecase.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6a2e8076-2860-beb0-91d8-7cc245d3106f.png) - **Data Command Graph in EDC** See Data domains for a particular data catalog entity. To do so, select the **Data Domain** entity and set the **Data Catalog URN** property to your entity's URN. ![edcdcg_usecase.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eeb2b921-f8d5-b5ab-2acb-48b77023dabe.png) |

## Related

- [Using Graph Explorer](/using-graph-explorer.md)
- [Using Inventory](/using-inventory.md)
- [Using the app-specific inventories](/using-the-app-specific-inventories.md)
