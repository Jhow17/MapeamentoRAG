---
title: "Using Relationship view in Graph Explorer"
slug: "using-relationship-view-in-graph-explorer"
updated: 2026-05-15T11:41:22Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/using-relationship-view-in-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using Relationship view in Graph Explorer

Securiti Graph Explorer lets you view the relationships between entities in a more user-friendly and structured format using the **Relationship** view. The view uses the Cartesian Product to display records for a query by listing all possible relationships between the entities in the query.

Unlike the **Table view,** where results are loaded depth-first and require multiple clicks to load relationships, the **Relationship** view displays a row for every combination of your related entities in a segmented layout. The **Relationship** view is the most useful when you are working with complex, multi-level queries in the Graph Explorer.

![Graph Explorer displaying security posture findings for AWS S3 bucket configurations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Relationship tab_Graph Explorer(1).png)

The relationship view contains the following components.

- Query Builder or JSON view: The top section of the page lets you build queries using Securiti's query builder or via JSON code.
- List view: The relationships are displayed in a list view by default. Each row of the grid represents a relationship between the entities.
- Search bar: Use the search bar in the ​**List**​​ view to search entities. This lets you find any specific relationship from multiple records.
- Graph view: You can switch between ​**List**​ and ​**Graph**​​ views to analyze relationships. The graph view displays all the nodes as circles connected to their related nodes. The relationships are represented by a line connecting the nodes. You can also see the respective count for each entity.

![Graph Explorer interface displaying security posture findings and data system relationships.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Table and Relationship tan_Graph Explorer.png)

To use the **Relationship** view.

1. Create a query by adding relationships. For more information, see [Managing queries in the Graph Explorer](/v1/docs/managing-queries-in-the-graph-explorer).

Once you click ​**Run Query**​​, from the upper right corner of the page, click ​**Relationship**​​, as shown below.

![Graph Explorer interface showing security posture findings for GCP Pub Sub subscriptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Query relationship view_Graph Explorer(1).png)
2. By default, all relationships are displayed in a ​List​​ view, as shown below. The list is populated with all entities present in your query. Each column represents an entity, as shown below.

The leftmost column represents the root entity in a query.

![Graph Explorer displaying security posture findings for GCP Pub Sub subscriptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Query result_Graph Explorer.png)
3. Each row in the grid represents a possible relationship combination between the entities.
4. Traverse the rows from left to right to understand the relationship path.
5. To switch from list view to graph view, near the upper right corner of the page, click ​Graph​​, as shown below.

![Graph Explorer displaying relationships of security posture findings in a data system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Added properties query result_Graph Explorer.png)

### Applying filters

You can apply filters to your query from the Relationship view grid directly. To apply filters to your entities:

1. Apply the increment (+ icon) or decrement (- icon) operator to include or exclude an attribute. On the Expression Builder bar at the bottom, click **Apply Filters**.

![Graph Explorer interface showing security posture findings and filter options for data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Apply Filters_Graph Explorer.png)
2. Click **Run Query** to execute the updated query. The added filter appears in the top row of the dashboard with the rest of the filters.

![Graph Explorer interface displaying security posture findings for various database instances.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Run Query for filter option_Graph Explorer.png)

![Graph Explorer displaying security posture findings for GCP Pub Sub subscriptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filtered query result_Graph Explorer.png)
