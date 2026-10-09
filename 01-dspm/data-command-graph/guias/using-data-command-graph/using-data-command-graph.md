---
title: "Using Data Command Graph"
slug: "using-data-command-graph"
status: "update"
updated: 2026-09-17T16:22:34Z
published: 2026-09-17T16:22:34Z
canonical: "helpcenter.securiti.ai/using-data-command-graph"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using Data Command Graph

Securiti’s Data Command Graph is a graph database model technology that captures all the key metadata and relationships between entities across all Securiti modules. With the Data Command Graph, you can explore all entities and relationships in your environment and apply filters on them based on their properties. The technology works as an effective tool to search or query any relationship within the multidimensional graph model in minimal time. With the Data Command Graph, you can run platform-wide queries or filters to retrieve metadata and save those queries as JSON expressions, CSV files, or widgets into your custom dashboards.

> [!WARNING]
> Important
> 
> This module is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

For more information, see the prerequisites section below.

> [!CAUTION]
> **Warning**
> 
> The following regions do not have Disaster Recovery (DR) for the Data Command Graph functionalities. While backups can be stored, Data Command Graph functionalities are not available if a restore is needed in these regions due to a hard failure.
> 
> - [Montreal](https://app3.securiti.ai)
> - [Mumbai](https://app6.securiti.ai)

Data Command Graph serves as the foundation for **Graph Explorer** and **Inventory** and lets you run your custom searches. Moreover, Data Command Graph is also integrated across Securiti’s modules with a Circular Graph view and limited entities according to an app’s scope.

To learn more about the graph pages, see [Getting Started with Data Command Graph](/v1/docs/getting-started-with-data-command-graph).

![Data_Command_GraphV3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e1882433-bd8b-e3f1-be36-bb2cac05ec88.png)

For more information, see the following topics:

- [Using Graph Explorer](/v1/docs/using-graph-explorer)
- [Using Inventory](/v1/docs/using-inventory)
- [Using the app-specific inventories](/v1/docs/using-the-app-specific-inventories)
- [Data Command Graph API reference](/v1/docs/data-command-graph-api-reference)

### Prerequisites for using Data Command Graph

To use the Data Command Graph, you must have access to Securiti's **Data Command Graph** module.

Once you have access to Securiti's **Data Command Graph** module, ensure that you connect your relevant data sources with Securiti for data ingestion, such as data systems, cloud accounts, third-party applications, AI models, or platforms.
