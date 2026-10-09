---
title: "Using JSON expression for queries"
slug: "using-json-expression-for-queries"
updated: 2026-05-14T07:50:37Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/using-json-expression-for-queries"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using JSON expression for queries

Data Command Graph lets you save, share, and use your queries as a JSON expression. As you create a query or filter on Graph Explorer, the following two modes are available on the Graph Explorer page for building queries:

- **Query builder**: By default, the Query Builder mode is selected, where you create your filters or queries by adding entities, relationships, and properties from the Graph Explorer filter panel. See [Managing queries in the Graph Explorer](/v1/docs/managing-queries-in-the-graph-explorer) for more information.

![Graph Explorer displaying IaaS Cloud and Data System with counts and properties.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Query Builder_DCG.png)
- **JSON View**: On the right side of the **Query Builder** mode, you can click on **Show Query in JSON Mode** to switch to this mode where you can paste your JSON queries to fetch results or generate JSON for your query created in the **Query Builder** mode.

![Graph Explorer interface displaying JSON data and options for downloading and querying.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download JSON_DCG.png)

Using the JSON expression, you can share your views or queries or create widgets using JSON in the Reporting Dashboard. For more information, see [Creating widgets from JSON queries](/v1/docs/creating-widgets-from-json-queries).

> [!NOTE]
> **Note**
> 
> You must log into the Securiti tenant to view and edit the shared filter.

### Understanding JSON queries

JSON queries are structured to represent nodes, their properties, and relationships in a graph query. Securiti's Graph Explorer lets you generate JSON expressions for your queries, which can be used for multiple purposes, including sharing of views, or creating customised queries and widgets. By understanding how to construct and modify these queries, you can tailor the system to meet your specific analytical needs.

JSON queries are built using arrays and objects of keys in a graph database model. The table below explains the basic components in a JSON query. See the query example below for better understanding.

| Component | Type | Description |
| --- | --- | --- |
| **nodeType** | Array | Specify the entity name of the parent node in your query in this array. For example, "IAAS". |
| (Optional) **withPropertyFilter** | Object | Specify any properties to apply on the parent node to filter results. You can choose not to apply any property to fetch all records. For example, "AWS" in the **displayName**. See the code snippet below. ```plaintext { "nodeType": ["IAAS"], "withPropertyFilter": { "displayName": { "in": ["AWS"] } } } ``` |
| **connections** | Array of objects | Specify the relationships and their properties in this array of objects. You can add relationships in the **relationshipType** nested object and specify the related entity names in the **nodeType** array. Specify the properties for related entities in the **withPropertyFilter** nested object. For example, you want to fetch data systems for AWS IaaS cloud having "asset type" as a property. The **connections** array contains the information as shown in code snippet below. ```plaintext "connections": [ { "relationshipType": [ { "label": "CLOUD_HAS_DATASYSTEM", "backwards": false } ], "withNode": { "nodeType": [ "DATASYSTEM" ], "withPropertyFilter": { "graphAssetType": { "in": [ "amazon_athena", "amazon_redshift" ] } }, "connections": [] } } ] ``` |

#### Example

To create a query that fetches all AWS data systems having the following asset types:

- Amazon Athena
- Amazon Redshift

The complete query looks as shown in the code below.

```plaintext
{
    "nodeType": [
        "IAAS"
    ],
    "withPropertyFilter": {
        "displayName": {
            "in": [
                "AWS"
            ]
        }
    },
    "connections": [
        {
            "relationshipType": [
                {
                    "label": "CLOUD_HAS_DATASYSTEM",
                    "backwards": false
                }
            ],
            "withNode": {
                "nodeType": [
                    "DATASYSTEM"
                ],
                "withPropertyFilter": {
                    "graphAssetType": {
                        "in": [
                            "amazon_athena",
                            "amazon_redshift"
                        ]
                    }
                },
                "connections": []
            }
        }
    ]
}
```

### Acquiring and uploading JSON files

To view your filters as a JSON file or code:

1. In the Graph Explorer, near the upper right side of the page, click **Show Query in JSON Mode** to generate the JSON expression for your view. Click **More** **Actions** (three dots) icon and select **Download JSON** option to save the JSON expression of your query.

![Graph Explorer interface displaying JSON data and options for downloading and querying.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download JSON_DCG(1).png)
2. You can also view the JSON expression for a particular instance from the grid. To do so, click on the instance and in the **Metadata explorer**, click **View JSON**.

![Graph Explorer displaying AWS Cloud data system counts and related properties.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/View JSON_DCG.png)
3. On the **JSON Expression** popup, click either the **the save** (clipboard) icon or the **download** (down arrow) icon to save the generated JSON code of your view.

![JSON expression displayed in Graph Explorer for filtering AWS data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Copy and download JSON_DCG.png)
4. The copied JSON expression can be shared directly or as a downloaded JSON file.

### Building queries in JSON View mode

To build a query using JSON.

1. Open the Graph Explorer and near the upper right corner of the top row, click **Show Query in JSON Mode**.
2. Paste the shared code in the code window.
3. Click **Run Query**.

![Graph Explorer interface displaying query filters and options for data selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Running JSON query_DCG.png)

## Related

- [Creating widgets in Graph Explorer](/creating-widgets-in-graph-explorer.md)
- [Creating widgets from JSON queries](/creating-widgets-from-json-queries.md)
