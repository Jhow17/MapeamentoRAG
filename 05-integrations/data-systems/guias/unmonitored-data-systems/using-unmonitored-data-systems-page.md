---
title: "Unmonitored Data Systems"
slug: "using-unmonitored-data-systems-page"
updated: 2026-09-22T03:44:33Z
published: 2026-09-22T03:44:33Z
canonical: "helpcenter.securiti.ai/using-unmonitored-data-systems-page"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Unmonitored Data Systems

The new **Unmonitored** **Data Systems** page lets you discover, configure, and manage unmonitored data system connectors from a single, centralized view. It brings together search, filters, status indicators, and quick actions to easily track the state of connector activation. For more information, see [Using unmonitored data systems](/latest/docs/configuring-unmonitored-data-systems).

The **Unmonitored** **Data Systems** page provides the following capabilities:

- A table view for all configured connectors.
- A search bar to search connectors by instance name.
- A top-level filter that lets you search connectors by owner.
- A **Save View** button that lets you save the current filter and search combination as a named view.
- A **Saved Views** button that lets you apply a view you saved earlier.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.13.11 AM.png)

## Understanding the table view

Each row in the table represents a single connector instance. Key columns include:

| Column name | Description |
| --- | --- |
| Instance name | The name assigned to the connector |
| Data system type | Indicates whether the connector is active or inactive |
| Owner | Shows the username for the data system instance |

> [!NOTE]
> Note
> 
> You can add more columns using the column selector. Securiti adds a horizontal scrollbar automatically as the number of columns increases.

## Filtering and searching connectors

Use the search bar at the top of the grid to quickly locate connectors by instance name or data system type, as shown below.

![Integration settings showing monitored and unmonitored data systems with owner selection options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/unmonitored_filters.png)

To narrow down the results, use the top-level filter to focus on connectors for a specific owner, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.14.19 AM.png)

The top-level filter supports filtering by the following properties:

| Property | Description |
| --- | --- |
| Owner | Lets you filter connectors created by a specific user. |

### Saving and reusing filter views

A saved view stores the filters and the search term you apply to the grid, under a name that you choose. Saving a view lets you return to a filter combination you use often, without building it again.

> [!NOTE]
> Note
> 
> The Save View option is disabled until you apply at least one filter or a search term.

**Saving a View**

1. To save a view, on the **Unmonitored Data Systems** page, apply the filters you want to reuse.
2. At the right end of the filter row, click **Save View**.
3. On the **Save View** popup, enter a **Group**, **Name**, and **Description** for the view and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-10 at 3.52.20 PM.png)

Securiti adds the view to the **Saved Views** list for the Unmonitored Data Systems page.

**Using a Saved View**

1. To apply a saved view, on the right end of the filter row for **Unmonitored Data Systems** page, click **Saved Views**.
2. On the **Saved Views**, click the view you want to apply.

Securiti loads the saved filters into the filter row, and the grid shows the matching connectors.
3. To view or delete a saved view, from the Saved Views list, click More Actions (three dots) for that view, then click Edit or Delete, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.05.44 AM.png)
