---
title: "Drivers"
slug: "drivers"
updated: 2026-09-15T13:18:37Z
published: 2026-09-22T03:45:48Z
canonical: "helpcenter.securiti.ai/drivers"
area: integrations
modulo: drivers
tipo: guia
data_captura: 2026-10-08
---

# Drivers

The Drivers page in **Integrations** lets you upload, view, and manage driver files used by structured data system connectors in Securiti.

To access the **Drivers** dashboard:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Integrations** from the left navigation bar.
2. From the left menu of the **Integrations** page, select **Drivers**.

> [!NOTE]
> Note
> 
> The **Drivers** load count remains hidden by default. Click the visibility icon next to **Drivers** in the left panel to view the load count. This lets you quickly check how many driver files are currently loaded in Securiti.
> 
> ![Integration dashboard displaying various data systems and drivers with highlighted options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/drivers_loadcount.png)

The dashboard displays a summary count and a table of all uploaded driver files in your tenant. The page provides the following capabilities:

- A table view for all driver files.
- Summary metrics displayed at the top of the grid that show counts for total **Drivers** and associated **Data Systems**.
- A search bar to search driver files by name.
- A top-level filter that lets you search drivers by the file name or data system.
- A **Save View** button that lets you save the current filter and search combination as a named view.
- A **Saved Views** button that lets you apply a view you saved earlier.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.
- An **Add Drivers** button that lets you upload driver files for your selected data system.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.36.00 AM.png)

## Understanding the table view

Each row in the table represents a single driver file. Key columns include:

| Column | Description |
| --- | --- |
| Name | Displays the name for driver file. |
| Data System | Displays the associated data system for a driver file, such as Amazon Athena. |
| Updated On | Displays the timestamp of the file’s most recent update. |

> [!NOTE]
> **Note**
> 
> You can remove columns using the column selector. Securiti adds a horizontal scrollbar automatically as the number of columns increases.

For each driver, click options (three dots) to update or delete the file.

![Integration settings display with options to upload new versions or delete drivers.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/drivers_settings(1).png)

## Filtering and searching drivers

Use the search bar at the top of the grid to quickly locate driver files by name or data system.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.29.17 AM.png)

To narrow down the results, use the top-level filter to focus on specific driver file or filter them by a property.

![Integration settings showing data systems with options to filter and select drivers.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/drivers_filters.png)

The top-level filter supports filtering by the following properties:

| Property | Description |
| --- | --- |
| File Name | Lets you filter by a driver’s file name. |
| Data System | Lets you filter by the data system associated with the driver file. |

#### Saving and reusing filter views

A saved view stores the filters and the search term you apply to the grid, under a name that you choose. Saving a view lets you return to a filter combination you use often, without building it again.

> [!NOTE]
> Note
> 
> The Save View option is disabled until you apply at least one filter or a search term.

**Saving a View**

1. To save a view, on the **Drivers** page, apply the filters you want to reuse.
2. At the right end of the filter row, click **Save View**.
3. On the **Save View** popup, enter a **Group**, **Name**, and **Description** for the view and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.32.29 AM.png)

Securiti adds the view to the **Saved Views** list for the Drivers page.

**Using a Saved View**

1. To apply a saved view, on the right end of the filter row for **Drivers** page, click **Saved Views**.
2. On the **Saved Views**, click the view you want to apply.

Securiti loads the saved filters into the filter row, and the grid shows the matching connectors.
3. To view or delete a saved view, from the Saved Views list, click More Actions (three dots) for that view, then click Edit or Delete, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.34.19 AM.png)
