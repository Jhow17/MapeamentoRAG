---
title: "User-defined systems"
slug: "user-defined-systems"
updated: 2026-09-15T13:17:45Z
published: 2026-09-22T03:45:04Z
canonical: "helpcenter.securiti.ai/user-defined-systems"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# User-defined systems

The User-defined page in **Integrations** lets you manage custom connectors and data systems that you create.

The **User-Defined Data Systems** page let you integrate custom data systems defined by your organization, often integrated using Webhooks. These systems provide flexibility for DSR requests and compliance workflows based on proprietary configurations.

To access the **User-defined** dashboard:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Integrations** from the left navigation bar.
2. From the left menu of the **Integrations** page, select **User-defined**.

The dashboard displays a summary count and a table of all user-defined connector in your tenant. The page provides the following capabilities:

- A table view for all connectors.
- Summary metrics displayed at the top of the grid that show count for **Configured Connectors**, **Active Connectors**, **Securiti Cloud Hosted** and **Self Hosted** connectors**.**
- A search bar to search connectors by name or data system type.
- A top-level filter that lets you search connectors by the connector type and owner.
- A **Save View** button that lets you save the current filter and search combination as a named view.
- A **Saved Views** button that lets you apply a view you saved earlier.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.
- An **Add Integration** button that lets you configure and activate a user-defined connector.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.37.42 AM.png)

## Understanding the table view

Each row in the table represents a single connector instance file. Key columns include:

| Column | Description |
| --- | --- |
| Instance Name | Displays the name of the user-defined connector instance. |
| Data System Type | Displays the associated data system for the connector, such as **Webhooks** |
| Connector Type | Displays the connector type as **Self Hosted** or **Securiti Cloud Hosted**. |
| Owner | Displays the owner name for the connector. |

> [!NOTE]
> **Note**
> 
> You can remove columns using the column selector. Securiti adds a horizontal scrollbar automatically as the number of columns increases.

- To edit or delete a connector, click options (three dots) and select **Edit** or **Delete**.

![Integration settings showing user-defined connectors with options to edit or delete.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/udsystems_settings.png)

## Filtering and searching certificates

Use the search bar at the top of the grid to quickly locate connectors by name or data system.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.42.13 AM.png)

To narrow down the results, use the top-level filter to focus on specific connectors or filter them by a property.

| Property | Description |
| --- | --- |
| Connector Type | Lets you filter by connectors by their type such as self-hosted or Securiti cloud hosted connectors. |
| Owner | Lets you filter connectors by their owner. |

![Integration settings showing connector types and options for user-defined systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/udsystems_filter.png)

### Saving and reusing filter views

A saved view stores the filters and the search term you apply to the grid, under a name that you choose. Saving a view lets you return to a filter combination you use often, without building it again.

> [!NOTE]
> Note
> 
> The Save View option is disabled until you apply at least one filter or a search term.

**Saving a View**

1. To save a view, on the **Open DSR Connector** page, apply the filters you want to reuse.
2. At the right end of the filter row, click **Save View**.
3. On the **Save View** popup, enter a **Group**, **Name**, and **Description** for the view and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.45.18 AM.png)

Securiti adds the view to the **Saved Views** list for the User-Defined Data Systems page.

**Using a Saved View**

1. To apply a saved view, on the right end of the filter row for **Open DSR Connector** page, click **Saved Views**.
2. On the **Saved Views**, click the view you want to apply.

Securiti loads the saved filters into the filter row, and the grid shows the matching connectors.
3. To view or delete a saved view, from the Saved Views list, click More Actions (three dots) for that view, then click Edit or Delete, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 10.27.48 AM.png)
