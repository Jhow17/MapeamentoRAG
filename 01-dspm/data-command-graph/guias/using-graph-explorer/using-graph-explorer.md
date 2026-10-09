---
title: "Using Graph Explorer"
slug: "using-graph-explorer"
status: "update"
updated: 2025-12-10T05:46:29Z
published: 2025-12-10T05:46:29Z
canonical: "helpcenter.securiti.ai/using-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using Graph Explorer

Securiti's Graph Explorer is a fundamental component of Data Command Graph and provides a graphical representation of data across all Securiti modules. It adopts a graph database relationship model to ingest, store, and query data from various sources within Securiti. Graph Explorer lets you create custom and complex queries to analyze your data and their relationship with different entities.

Moreover, Graph Explorer offers the flexibility to share your customized views and filters in the form of a JSON query or export them as a CSV file.

> [!NOTE]
> **Important**
> 
> The Graph Explorer does a depth-first search and returns paginated data. You may not see complete results directly in the Graph Explorer due to pagination. To view complete results, export the results as a CSV file.

To access the Graph Explorer.

- In the **New Navigation** left sidebar, click the jewel icon and choose **Graph Explorer**, as shown below.

![The interface shows the Graph Explorer option highlighted in the navigation menu.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using_graph_explorer.png)

The following are some example use cases for Securiti's Graph Explorer:

- What data systems containing sensitive data does a compromised user have access to?
- What data systems contain objects past their retention period?
- What specific DynamoDB tables have sensitive data?
- What high-risk processing activities need a DPIA?

For more information, see the topics below:

- [Getting Started with Graph Explorer](/v1/docs/getting-started-with-data-command-graph#getting-started-with-graph-explorer), to learn about Graph Explorer module.
- [Understanding Graph Explorer](/v1/docs/understanding-graph-explorer) , to learn about supported features and entities in the Graph Explorer.
- [Managing queries in the Graph Explorer](/v1/docs/managing-queries-in-the-graph-explorer), to learn about creating queries and using the Graph Explorer.

## Related

- [Understanding Graph Explorer](/understanding-graph-explorer.md)
- [Managing queries in the Graph Explorer](/managing-queries-in-the-graph-explorer.md)
- [Using JSON expression for queries](/using-json-expression-for-queries.md)
- [Creating widgets in Graph Explorer](/creating-widgets-in-graph-explorer.md)
