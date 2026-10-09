---
title: "Using aggregate operations in queries"
slug: "using-aggregate-operations-in-queries"
updated: 2026-05-25T16:42:46Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/using-aggregate-operations-in-queries"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using aggregate operations in queries

Securiti's Graph Explorer supports aggregate operations that let you query and analyze your data more flexibly, without writing any JSON. Aggregate operations help summarize or group information across relationships in your data. This makes it easier to summarize large datasets and monitor risk patterns.

> [!NOTE]
> **Important**
> 
> - If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> - Securiti supports aggregate operations in a query for **Graph Explorer** and **Identity Graph Explorer** pages only.

You can use them to count items, sum values, group by property, or list related data. The following aggregate operations are supported:

| Aggregate operation | Description | Compatibility |
| --- | --- | --- |
| Count | Counts the number of child entity instances per individual parent entity. Use this aggregation when you want to see how many related items exist per row or group in your results. | - Count operation is supported for all properties and works for nested relationships, such as, count of discovery scan files for a data system. - Count operation is not supported for nested entities if the root entity is one of the following: - Column - Discovery Scan Files - Files - File Findings - Folders - Resource Access - Structured Data Finding - Data Test Finding - Workflow Execution |
| Total Count | Counts the total number of entity instances that match the full query. This operation aggregates total values across all results and returns a single number for the total quantity, regardless of the grouping. | Supported for all properties and at root and mid-level entities, but aggregates only at the query endpoint. > [!NOTE] > Note > > - **Total Count** is disabled if the query contains multiple child entities at the same level. > - Securiti returns a validation error in case you attempt to add multiple entities at the same level after applying **Total Count**, or apply the operator to a query that already has multiple entities at the same level. > - You cannot add relationships to a query once **Total Count** is applied to any entity. |
| Sum | Adds up the values of numeric properties such as file size. | - Supported for numeric or integer properties only, such as **File Size**, **Sensitivity Score**. - Sum operation is not available for properties having string, enum, and date type. - Sum operation is supported at root entities of a query. |
| Map Count | Groups entities by properties and counts them. | - Supported for properties with enum and string data types, such as **Severity**, **File Type**, **Classification Label**. - Map count is not supported for numeric and date properties. |

## Caveats

You must consider the following caveats when using aggregate queries:

- Securiti lets you apply only one aggregation operation at a time for each query.
- Securiti displays the aggregate query results in the **Aggregates** tab only. They are not visible in **Graph** or **Table** views.
- The option to perform an aggregate operation is only available for supported entities and properties.
- Currently, Securiti does not support aggregate operations for the following entities:
  - Finding
  - Test Finding
  - Structured Finding
  - IAM Resource Access

## Example use cases

- This example use case demonstrates the analysis of SMB files with a file size greater than 10 MB. We apply the **Count** operation on the **File** entity in the query, as shown below.

![Data system overview showing asset names and their corresponding discovery scan counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Discovery Scan Count Filter_DCC.png)

The aggregate query returns the count of all files having a size greater than 10MB for each data system. The results help understand which files take up more storage.
- This example use case demonstrates the the calculation of the sum of data objects grouped by hosting. The query is used to calculated sum of all data objects for IaaS cloud instances. We apply **Sum** operation to the **Data Objects** property to sum up all the data objects greater than 0, as shown below.

![Graph Explorer interface displaying data system total data objects and query options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data Objects Sum Filter_DCC.png)

The aggregate query returns the summed up number in form of a metric in the **Aggregates** tab.
- This example use case demonstrates the analysis of distinct discovery scan files count according to the file formats available in the data systems. We apply **Map Count** operation on the **File Format** property to count and map all the distinct files available against a particular file format, as shown below.

![Overview of file formats and their corresponding discovery scan file counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MapCount Property_DCC.png)

The aggregate query returns the results in mapped form between the file formats and the files count against each format.
- This example use case demonstrates the calculation of total number of data system instances with an active discovery scan. We apply **Total Count** operation on the **Discovery Scan** entity, as shown below.

![Graph Explorer interface displaying Discovery Scan Total Count of 170.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Active discovery scan count_DCC.png)

The aggregate query returns the total number of data systems with an active discovery scan in the form of a metric in the **Aggregates** tab.

## Applying aggregate operations in a query

To apply aggregations in your query:

1. Open Graph Explorer and start a new query.
2. Select your root entity from the filter panel, as shown below.

![Graph Explorer interface displaying data system options and search functionality.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Entities in DCC.png)
3. Click options (three dots) and click **Add relationship** to add a related entity.
4. Click options (three dots) and click **Add properties** to add a property to your root or related entity.
5. For your selected entity or property, choose an aggregate operation from the menu, as shown below.

> [!NOTE]
> **Note**
> 
> Securiti only displays the supported aggregate operations for an entity or property. For aggregate operations and their descriptions, see the table above

![Graph Explorer interface displaying filters and options for data queries and searches.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Count Filter_DCC.png)
6. Click **Run Query** to see the aggregated results. Securiti automatically displays the aggregate results in the **Aggregates** tab, as shown below. Aggregate results cannot be viewed in **Table** or **Graph** views.

![Overview of asset names and their corresponding file counts in a data system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Aggregate tab_DCC.png)

For **Count** operation, you can view the source graph explorer query for the aggregate results in a new tab by clicking on the count, as shown below.

![File findings count for various assets displayed in a data system interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Count Property_DCC.png)

![Graph Explorer interface displaying file findings and resource paths for various assets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Table view_DCC.png)
7. (Optional) From the upper right corner of the grid, click **Create Widget** to add your results to a dashboard. Securiti lets you view these aggregate results in the form of a grid or a metric, as shown below.

![Graph Explorer interface displaying asset types and file counts for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create widget_DCC.png)

![Overview of the Aggregate Grid displaying asset names and file counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create widget options_DCC.png)

## Related

- [Understanding Graph Explorer](/understanding-graph-explorer.md)
- [Managing queries in the Graph Explorer](/managing-queries-in-the-graph-explorer.md)
