---
title: "Using the Inventory page"
slug: "using-the-inventory-dashboard"
status: "update"
updated: 2026-08-30T12:08:38Z
published: 2026-08-30T12:08:38Z
canonical: "helpcenter.securiti.ai/using-the-inventory-dashboard"
stale: true
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using the Inventory page

The Inventory dashboard for Securiti provides a platform-wide collection of all entities. The Inventory page lets you visualize all the entities and their resources. For example, you can view what files have been scanned for a data system account.

The Inventory page displays your data in a tabular form and shows the count of your data at the top of the grid. The top row of the dashboard is the filter bar, where you can apply entity-level filters to view valuable information. On the left side of the page, all entities across the platform are listed along with their total count. On the right side of the entities bar is the grid where you can view your data for a selected entity.

![Inventory interface displaying cloud service count and asset details for management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cloud Service Display_Graph Explorer.png)

The Inventory page features an **Activate Graph Metrics** option to optimize page load performance. With this control, Securiti disables automated graph metric calculations by default for tenants with large volumes of metadata. You can load this detailed data on-demand for your current session by enabling the **Activate Graph Metrics**, as shown below.

![Overview of cloud services with asset types and counts displayed in an inventory interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Activate Graph Metrics_Graph Explorer.png)

![Inventory interface displaying cloud services and data management options with selected filters.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Columns trendlines_Inventory.png)

> [!NOTE]
> **Note**
> 
> - The **Activate Graph Metrics** feature is designed as a performance optimization for tenants with very large data volumes. For all other tenants, the option is hidden, and graph metrics remain enabled by default.
> - Enabling this option for tenants with very large data volumes can result in slower page load times.
> - When **Activate Graph Metrics** is disabled, Securiti displays an approximate entity count instead of an exact count. In the unfiltered entity view, pagination is available only for the first 100 items. To restore pagination beyond the first 100 items, apply a filter to the entity or enable **Activate Graph Metrics**.
> - Securiti stores the **Activate Graph Metrics** toggle state in your browser, not in your account settings. As a result, the toggle can appear turned on in one browser and turned off in another browser for the same account.

Once activated, these additional columns become available in the Column Selector. A purple vertical indicator next to these metrics highlights them as on-demand graph metrics.

### Using filters in the Inventory

You can apply filters to view the graphical representation of the underlying data quickly.

> [!NOTE]
> **Important**
> 
> You can only apply single entity-level filters and cannot create relationships in Inventory.

### Applying filters

To filter your entities by their properties:

1. From the left sidebar, select your entity. Near the upper left corner of the page, click **+** to open the filter menu.

![Inventory management interface displaying cloud services and asset types with selection options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Applying Filters_Inventory.png)
2. Choose the attribute operator depending on your selected attribute from the respective menus.

![Inventory interface displaying cloud service options and filter search functionality.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_dashboard5.png)

The operators displayed on the menu depend on the datatype of an attribute i.e string, integer, number, etc.

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
| Is empty | View records where the string property does not exist or has no value. |
| **Number values** |
| Greater than | View records where the numerical property is greater than the specified value. |
| Greater or Equals to | View records where the numerical property is greater than or equal to the specified value. |
| Less than | View records where the numerical property is less than the specified value. |
| **Timestamp values** > [!NOTE] > ### Note > > The relative date filter for timestamp properties takes the time period relative to the current date, ensuring a more accurate range (e.g., 5 May to 5 June for "last one month" selected on June 5). |
| Before | View records before a certain time and date specified on the calendar. |
| After | View records after a certain time and date specified on the calendar. |
| In the past | View records for all the activities performed in a past time period specified as the number of minutes/hours/days/months/years. |
| In the upcoming | View records for all the activities scheduled for an upcoming time period specified as the number of minutes/hours/days/months/years. |
| Between | View records for all the activities performed between a specified time range. The starting and ending date and time are selected on the calendar. |
3. Click **Apply**.

#### Clearing all filters

You can delete the applied filters as per your requirement. To delete the applied filters:

- In the filter search bar, click **Clear Search** to delete the applied filters.

### Saving filters in Inventory

#### Saving filters

To save a view for your filters and results:

1. On the Inventory page, near the upper right corner of the page, click **Save View.**
2. On the **Save View** popup, add name, description, select group of filters or add a new one, and then click **Save Filter** to save your created filter.

![Inventory view showing cloud services and options to save filtered views.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Saving Filter_Inventory.png)

> [!NOTE]
> **Note**
> 
> You must select a group of the filter and add the name of the filter to save it for later use. However, adding the description is optional.
3. Click **Saved Views** near the upper right corner of the page to view your saved filters in their respective groups. For more information, see below section on [Access and edit saved filters](/v1/docs/using-the-inventory-dashboard).

![Overview of saved views in AWS Cloud, highlighting hosting details and data counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_dashboard7.png)

#### Accessing and editing saved filters

You can access the previously saved filter at any time through the **Saved Views** from the upper right corner of the page. To access a saved filter:

1. On the upper right corner of the page, click **Saved Views.**
2. On the **Saved filters** page, you can view the default groups of saved filters. Click any group to view the list of saved filters.
3. Click options (three dots) on the right side of a filter, and click **View**.

![AWS Cloud hosting details showing region, data system, and account counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_dashboard8.png)
4. You can also edit the saved filter to change its group. To do so, click **Edit**.

![Interface showing AWS Cloud hosting details with options to view, edit, or delete.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_dashboard9.png)

#### Deleting saved filters

You can delete the previously saved filter at any time through the **Saved Views** from the upper right corner of the page. To delete saved filters:

1. On the upper right corner of the page, click **Saved Views.**
2. On the **Saved filters** page, you can view the default groups of saved filters. Click any group to delete a saved filter.
3. Click options (three dots) on the right side of a filter and click **Delete**.

![AWS Cloud hosting options with view, edit, and delete functionalities displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_dashboard10.png)
