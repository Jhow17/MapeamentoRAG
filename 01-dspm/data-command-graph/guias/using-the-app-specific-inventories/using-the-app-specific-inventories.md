---
title: "Using the app-specific inventories"
slug: "using-the-app-specific-inventories"
status: "update"
updated: 2026-05-25T16:52:20Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/using-the-app-specific-inventories"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using the app-specific inventories

The Data Command Graph for Securiti apps provides an app-specific inventory of select entities, also known as a sub-graph. It displays your data in a Circular Graph view. This view automatically traverses every relationship between the entities when you apply property filters.

In Securiti, open **Sensitive Data Intelligence** or **Enterprise Data Catalog**, and from the left panel, choose **Dashboard > DataCommand Graph** to access the data command graph. You can access the Data Command Graph dashboard for Data Access Graph by simply opening the **Data Access Governance** module.

> [!NOTE]
> **Note**
> 
> - The Circular Graph view is currently supported for Sensitive Data Intelligence (SDI), Enterprise Data Catalog (EDC), and Data Access Governance (DAG) modules only.
> - The Circular Graph view does not return complete results for all related entities. We recommend you do not use these results for reporting purposes.

The Circular graph displays a module's entities and their connections, along with the metadata count. It lets you view rich context for any entity, including a data system, a user, a policy, etc. You can visualise your data at a granular level and apply filters on aggregates of entity types and all their relationship types.

The top row of the dashboard is the filter bar, where you can apply entity-level and attribute-level filters to view valuable information. The second row displays the module-specific statistics of the data as metrics. Near the left side of the page is the **Saved Views** panel that shows you the list of all your saved views.

![Data command graph displaying relationships among various data systems and scanned documents.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_view.png)

For example, you can view what data has been scanned and what or how much sensitive information your M365 environment has in the SDI Data Command Graph dashboard.

### Applying filters in the circular graph

You can apply filters across entities to quickly view the graphical representation of the underlying data.

#### Applying filters

1. In Securiti, open **Sensitive Data Intelligence** , and from the left panel, choose **Dashboard > DataCommand Graph** to access the data command graph. You can access the Data Command Graph dashboard for Data Access Graph by simply opening the **Data Access Governance** module.
2. Near the upper left corner of the page, click + to open the filter menu.
  1. On the filter menu, select entity, attribute operator and attributes from the respective menus and click **Apply**.

The applied filter appears in the first row of the dashboard, and the circular graph shows you the entities, their relationships, and respective counts of the filter.

![Data Command Graph displaying account properties and scanned document statistics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_filters.png)

#### Deleting filters

You can delete the applied filters by clicking **Clear Search** or clicking options (three dots) and selecting **Clear Filter**, as shown below:

![Data Command Graph displaying data systems, scanned tables, and filter options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_clearfilter.png)

#### Saving filters

To save a view for your set filters and results:

1. On the data command graph page, near the upper right corner of the page, click **Save View.**

![Data Command Graph displaying relationships between various data systems and scanned tables.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_saveview.png)
2. On the **Save View** popup, add a name, description, select a group of filters or add a new one, and then click **Save Filter** to save your created filter.

![Data command graph showing compliance view with data systems and scanned table details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_savingview.png)

> [!NOTE]
> **Note**
> 
> You must select a group of filter and add the name of the filter to save it for later use. However, adding the description is optional.
3. Click **Saved Views** near the upper right corner of the page to view your saved filters in their respective groups. For more information, see below section on Accessing saved filters.

#### Accessing saved filters

You can access the previously saved filter at any time through the **Saved Views** from the upper right corner of the page.

1. On the upper right corner of the page, click **Saved Views.**
2. On the **Saved filters** page, you can view the default groups of saved filters. Click any group to view the list of saved filters.
3. Click options (three dots) on the right side of a filter, and click **View**.

![Overview of compliance data with scanned documents and table count displayed prominently.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_viewsavedfilter.png)

#### Deleting saved filters

You can delete the previously saved filter at any time through the **Saved Views** from the upper right corner of the page.

1. On the upper right corner of the page, click **Saved Views.**
2. On the **Saved filters** page, you can view the default groups of saved filters. Click any group to delete a saved filter.
3. Click options (three dots) on the right side of a filter and click **Delete**.

![Overview of compliance data with various metrics and visual connections displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_deletesavedfilter.png)

#### Updating filters

You can update the applied filters as per your requirement.

- Near the upper left corner of the page, click **+** to open the filter menu and enter entities and attributes to update the filter. See Applying filters section for more information. You can also remove the existing filters if required. See Deleting filters section for more information.

![Data Command Graph displaying access methods and properties for data systems and entities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dcg_editingfilters.png)

## Related

- [Understanding app-specific inventories](/understanding-app-specific-inventories.md)
- [Using the Universal Data Explorer](/using-the-universal-data-explorer.md)
