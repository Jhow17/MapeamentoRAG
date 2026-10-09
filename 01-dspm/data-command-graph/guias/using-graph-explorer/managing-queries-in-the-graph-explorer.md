---
title: "Managing queries in the Graph Explorer"
slug: "managing-queries-in-the-graph-explorer"
updated: 2026-05-25T16:41:31Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/managing-queries-in-the-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Managing queries in the Graph Explorer

The Graph Explorer serves as a query interface that lets you define search criteria across all Securiti modules.

You can begin defining your graph search criteria in the following ways:

- Using **Query Builder** mode and clicking the **+** sign in the upper left corner of the top row.
- Using the **Begin Your Search** button in the center.
- Using the **JSON View** mode to paste your JSON query into the editor.
- Opening an existing filter from **Saved Views** from the upper right corner of the page.

![Graph Explorer interface showing options to add filters and begin search.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Graph Explorer_Dashboard.png)

### Creating queries

The sections below describe the process for creating queries, using properties, and adding related entities.

> [!NOTE]
> **Note**
> 
> For more information on using **Aggregations** in your query, see [Using aggregate operations in queries](/v1/docs/using-aggregate-operations-in-queries)

#### Procedure

To create a query:

1. To create a query, click **+** sign in the upper left corner of the top row to choose your root entity, as shown below.

![Graph Explorer interface displaying data system options and descriptions for database management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Adding an entitiy_DCC.png)

The filter menu has three panels as described below.

| Panel | **Description** |
| --- | --- |
| Left panel (Groups) | The left panel shows the entity groups. Clicking on a group name moves the second panel to that group. |
| Center panel (Entities) | The second panel lists all available entities. |
| Right panel (Description) | Hovering over one of the entities in the center panel brings up the description for the entity in the right panel. |
2. Next, click options (three dots) to add a property or a related entity. For more information on using properties and adding relationships, see the below sections.
3. Click **Add Relationship** to add a related entity, as shown below.

![Graph Explorer interface showing options to add properties and relationships for data visualization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add Relationship_DCC.png)
4. Choose your entity from the filter panel, as shown below.

![Search bar displaying various AI-related entities in a graph explorer interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Selecting relationship_DCC.png)
5. Click **Add Property** to apply filter to your entity, as shown below.

![Graph Explorer interface showing options to add filters and properties for data analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add property_DCC.png)
6. Choose your property from the filter panel, as shown below.

![Graph Explorer interface displaying properties related to data systems and file findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Properties_DCC.png)
7. Select a value for the selected property and click **Apply**, as shown below.

![Graph Explorer interface showing filter options for finding status selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Setting property state_DCC.png)
8. Once your query is completely configured, on the upper right corner of the top row, click **Run Query**, as shown below.

> [!NOTE]
> **Note**
> 
> The query does not automatically execute when you build or edit it, unless you click **Run Query**.

![Graph Explorer interface showing options to filter and run queries on data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Running a query_DCC.png)
9. You can cancel the query execution to make any changes by clicking **Cancel Query**.
10. Use the search bar above the grid to locate a specific instance using key properties for entities, as shown below.

![Graph Explorer interface displaying data system and file findings with various asset details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Search bar_DCC.png)

#### Example

To create a query that lets you view security posture findings for all data systems:

1. Near the upper left corner of the page, click **+** and select **Data System** as your root entity.
2. Add **Security Posture Finding** as the related entity.
3. Click **Apply**

The grid displays all the data systems with security posture findings. You can add relationships and properties to suit your preferences and filter the results accordingly.

![Overview of data systems and security posture findings in a graphical interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Security Posture Findings_DCC.png)

#### Using properties

You can add **properties** to filter data associated with an entity. To add a property to your entity:

1. Click options (three dots) on the right side of the node you want to add properties for.
2. Click **Add Property** to add a property as shown below.

![Graph Explorer interface showing data system properties and filtering options for AWS Cloud.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Adding Property_DCC.png)
3. Select the property you want to add from the list of properties associated with your node.

![Graph Explorer interface displaying data system properties and access methods information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Properties list_DCC.png)
4. After selecting the property, you can choose the operator to select what criteria to match on from the menu.

![Graph Explorer interface showing filtering options for data system accounts and assets.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/is one of filter_DCC.png)

The operators displayed on the menu depend on the datatype of a property i.e string, integer, number, etc.

> [!WARNING]
> Caution
> 
> Securiti lets you use only one operator per property in a query. You cannot apply multiple operators to the same property within a single query.
> 
> For example, if you’ve already applied the ​**Contains**​ operator to the **​File Name​** property for an entity, you cannot use the ​**Contains**​​ operator again on the same property within the same query or on similar entities.

| **Operator** | **Description** |
| --- | --- |
| **String values** |
| Equals | View records where the string property is exactly equal to the specified value. |
| Contains | View records where the string property contains the specified substring. |
| Begins with | View records where the string property begins with the specified substring. |
| Ends with | View records where the string property ends with the specified substring. |
| Not equals | View records where the string property is not equal to the specified value. |
| Not contains | View records where the string property does not contain the specified substring. |
| Not begins with | View records where the string property does not begin with the specified substring. |
| Not ends with | View records where the string property does not end with the specified substring. |
| Is one of | View records where the string property matches any value in a specified list. |
| Is not one of | View records where the string property does not match any value in a specified list. |
| **Number values** |
| Greater than | View records where the numerical property is greater than the specified value. |
| Greater or Equals to | View records where the numerical property is greater than or equal to the specified value. |
| Less than | View records where the numerical property is less than the specified value. |
| **Timestamp values** > [!NOTE] > **Note** > > The relative date filter for timestamp properties takes the time period relative to the current date, ensuring a more accurate range (e.g., 5 May to 5 June for "last one month" selected on June 5). |
| Before | View records before a certain time and date specified on the calendar. |
| After | View records after a certain time and date specified on the calendar. |
| In the past | View records for all the activities performed in a past time period specified as the number of minutes, hours, days, months, or years. |
| Older than | View records created or modified earlier than the specified time period as the number of days, months, or years. |
| In the upcoming | View records for all the activities scheduled for an upcoming time period specified as the number of minutes, hours, days, months, or years. |
| Between | View records for all the activities performed between a specified time range. The starting and ending date and time are selected on the calendar. |
5. Choose a value from the menu list that corresponds to the selected property based on the chosen operator, and click **Apply**.
6. You can change the value to match property with by clicking on the selected value name and clicking on the new value from the menu. You can also select multiple values for a property. Click **Apply** to set the new value for property to match on.

After adding properties, the grid shows filtered results based on the property selected having a **with properties** connector. The added property shows on the first row of the dashboard linked with its node. You can also see the property and its value on the grid.

![Graph Explorer interface displaying data systems and their properties in a table format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filter for results_DCC.png)

#### Deleting properties

You can delete an added property from your node to add a new one or simply keep the node without a property. To remove a property:

- From the right side of the property that you want to remove, click options (three dots) and select **Remove property**.

![Graph Explorer interface showing data system properties and options for managing accounts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deleting a property_DCC.png)

#### Adding relationships

You can add **relationships** to view all entities or nodes having direct relationship with your entity. To add a relationship to your entity:

1. From the right side of the node for which you want to add a relationship, click options (three dots).

![Graph Explorer interface showing data system entities and options for adding relationships.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Adding Relationship_DCC.png)
2. Click **Add Relationship** to add a see list of all entities and their corresponding groups on the left panel which are related to your node. The right panel displays a description for the selected node.

![Graph Explorer interface displaying entity search and data organization options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Relationship entities_DCC.png)
3. Select the entity you want to add as a related entity.
4. After selecting the entity, the related entity is added to the filter with a connector displaying the relationship such as **belongs to**.

![Graph Explorer interface displaying data system assets and their properties in a table format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Belongs to query_DCC.png)

> [!NOTE]
> **Note**
> 
> After adding properties and relationships to an entity, the grid displays filtered results based on your filter. You can continue to add more relationships and properties for further customization.

#### Using negated relations in a query

Securiti lets you filter for lack of relationships between entities by using negated relations. This feature lets identify data systems or assets that do not have certain relationships, such as those without findings or classifications.

To use negated relations in your query:

1. Build your query with a root entity and its related entity, as shown below. For example, **Data System Belongs to Location**.
2. Click on the relationship connector between the two entities to change it to a negated relation, such as "Belong to" to "Doesn't belong to".

![Graph Explorer interface displaying data systems and their attributes in a table format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Doesnt belong to_DCC.png)
3. Click **Run Query**.

Use the table below to understand some example use cases:

| Use case | Example query |
| --- | --- |
| Search for IAM roles not assigned to users | 1. Create a query with **Role** as root entity and select a **Provider Type**, such as **Dropbox**. Add **User Principal** as the related entity create a **Role Is Assigned To User Principal** relation. 2. Click **Uses** to convert it into a negated relaton, i.e **Is Not Assigned To**. 3. Click **Run Query**. The results show all Dropbox IAM roles that are not assigned to a user principal. ![Graph Explorer interface showing roles and user principal details for Dropbox organization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graphexplorer_usecase.png) |
| Search for disk storage not associated with any Virtual Machine (VM) | 1. Create a query with **Block Storage** as root entity and **Compute Instance** as the related entity to create a **Block Storage Uses Compute Instance** relation. 2. Click **Uses** to convert it into a negated relation, i.e **Doesn't use**. 3. Click **Run Query**. The results show disk storages that do not belong to any compute instance, such as VMs. ![Graph Explorer displaying Block Storage and Compute Instance asset details and usage statistics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graphexplorer_diskstorageusecase.png) |

Currently, Securiti does not let you apply negation to a query if the following entities are present:

- Column
- Data Test Finding
- Discovery Scan Files
- Files
- File Findings
- Folders
- Resource Access
- Structured Data Findings
- Workflow Execution

#### Deleting filters

- To delete the filters applied at entity level, click options (three dots) for your entity and select **Clear Filter**, as shown below.

> [!NOTE]
> **Note**
> 
> The **Clear Filter** option, when applied to a parent node or a node having related entities, deletes the complete filter by clearing all nested filters.

![Graph Explorer interface showing filter options and a message indicating no data available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Clear Filter_DCC.png)
- To delete all the applied filter, at the upper right corner of the top row, click options (three dots) and select **Clear Query** from the menu, as shown below.

![Graph Explorer interface displaying data analytics assets and their details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Clear Query_DCC.png)

#### Hiding filters

To hide your filter and query results, you can mark or clear the **Show Filter** option as shown below.

![Graph Explorer interface showing data analytics options and asset details for Amazon Athena.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Show Filter_DCC.png)

### Saving queries in Graph Explorer

#### Saving queries

To save a view for your set filters and search results:

1. On the graph explorer, near the upper right corner of the page, click **Save View.**

![Graph Explorer interface displaying structured database and asset information for Snowflake.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Save View_DCC.png)
2. On the **Save View** popup, add name, description, select group of views or add a new one, and then click **Save View** to save your view.

![Graph Explorer interface displaying structured database filtering options and save view functionality.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Saving query filter_DCC.png)

> [!NOTE]
> **Note**
> 
> You must select a group of the view and add the name of the view to save it for later use. However, adding the description is optional.

To change the group, name, or description for your saved filter:

- From the upper right corner of the page, click **Saved Views**.
- Clicking **Saved Views** will open a panel for saved filters on the left side of the page. The panel displays default and custom groups of saved filters.
- Click any group to view the list of saved filters.
- From the right side of the filter, click options (three dots), and then click **Edit**.

![User interface displaying data labeling policies and options for structured database management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Editing saved views_DCC.png)
- Enter your updated details for the view on the **Save View** popup on the right side of the page. Click **Save View** to save the changes.

#### Accessing saved queries

You can access the previously saved views at any time through the **Saved Views** from the upper right corner of the page.

1. On the upper right corner of the page, click **Saved Views**.
2. Clicking **Saved Views** opens up a panel for saved filters on the left side of the page. The panel displays default and custom groups of saved filters.
3. Click any group to view the list of saved filters.
4. From the right side of the filter, click options (three dots), and the click **View**.

![Menu displaying data labeling policies with options to view, edit, or delete.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Viewing query filter_DCC.png)

#### Deleting saved queries

You can delete the previously saved filter at any time through the **Saved Views** from the upper right corner of the page.

1. On the upper right corner of the page, click **Saved Views**.
2. On the **Saved Views** page, you can view the default groups of saved filters. Click any group to view the list of saved filters.
3. From the right side of the filter, click options (three dots), and then click **Delete**.

![Menu displaying saved views and options for managing data labeling policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deleting a query filter_DCC.png)

#### Updating saved queries

You can update your previously saved views to add or remove filters and create a new view. To update a filter.

1. On the upper right corner of the page, click **Saved Views**.
2. On the **Saved Views** page, you can view the default groups of saved filters. Click any group to view the list of saved filters.
3. From the right side of the filter, click options (three dots), and click **View**.

![User interface displaying saved views and structured database options for data labeling policies.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Editing a saved view_DCC.png)
4. Make the required changes in the saved view from the top row of the dashboard and click **Save View** once you are ready to save the changes.

![Graph Explorer interface displaying structured database and asset details for Snowflake columns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Editing a saved query_DCC.png)

## Related

- [Using aggregate operations in queries](/using-aggregate-operations-in-queries.md)
- [Using JSON expression for queries](/using-json-expression-for-queries.md)
- [Inspecting instances in Graph Explorer](/inspecting-instances-in-graph-explorer.md)
- [Creating widgets in Graph Explorer](/creating-widgets-in-graph-explorer.md)
