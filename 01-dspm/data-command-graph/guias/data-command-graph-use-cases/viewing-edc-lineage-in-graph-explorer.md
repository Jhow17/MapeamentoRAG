---
title: "Viewing EDC lineage in Graph Explorer"
slug: "viewing-edc-lineage-in-graph-explorer"
updated: 2026-07-21T08:55:04Z
published: 2026-07-21T08:55:04Z
canonical: "helpcenter.securiti.ai/viewing-edc-lineage-in-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Viewing EDC lineage in Graph Explorer

Lineage provides a comprehensive view of how data moves through various systems, pipelines, and processes, from its origin to its consumption, while also capturing metadata about the data itself. The lineage information is critical for ensuring data quality, governance, compliance, and understanding the impact of changes in data sources and transformations. For more information, read [EDC Lineage](/v1/docs/datasets).

### Viewing lineage

1. From the left **Entities** navigation bar in the grid panel, select **Table** node.
2. Near the right corner of the page, click the window icon and mark the **Data Catalog URN** checkbox. This fetches all the tables and views that are registered in the Enterprise Data Catalog.
3. Click **Apply**.

![Graph Explorer interface displaying various database tables and options for data selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filtering tables with EDC URN.png)
4. Click the dataset for which you want to view the lineage.

> [!NOTE]
> **Note**
> 
> Lineage information is only available for tables and views that have been registered within the Enterprise Data Catalog. Tables or views lacking lineage details in the Enterprise Data Catalog are not displayed in the Graph Explorer instance visualizer. However, you can still view these datasets (both views and tables) even if their lineage information is absent.
5. On the Instance Explorer, near the right corner of the page, select **Lineage** from the menu to open the lineage visualization screen.

![Overview of VW_CUSTOMER_SALES table with various properties and data elements displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Lineag selection.png)

![Overview of VW_CUSTOMER_SALES table with highlighted data elements and properties.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-21 at 1.25.20 PM.png)

The above screenshot shows the flow of data from source to destination. The orange arrows show table level lineage relationship. In the table level lineage you can also see relationships among functions, procedures, and views. However, the blue arrows show column level lineage relationship. In the above screenshot, the orange arrow represents that the view **VW_CUSTOMER_SALES** is taking data from the table **CUSTOMER**. The blue arrows show that the view is taking data from the table columns, for example, **EMAIL_ADDRESS** is represented as **EMAIL** in the view.

> [!NOTE]
> **Note**
> 
> Press the command button while holding the mouse pointer to seamlessly navigate through the lineage visualization screen for complex views.

### Relationship among tables through foreign keys

The Instance Explorer lets you view relationships among different tables. Foreign keys in relational databases are a fundamental component of database design that establishes relationships between tables. They ensure data integrity and maintain the referential integrity of the database. Foreign keys are critical for creating associations between tables and enforcing consistency in the data.

1. From the left **Entities** navigation bar, select any **Table** node.
2. On the Instance Explorer, near the right corner of the page, select **Foreign Key** to view the relationship between the table with other tables.

![Overview of invoices table with highlighted columns and properties for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-21 at 1.51.57 PM.png)

In the above screenshot, the **order_Id** is used as the foreign key in the **invoices** table (This type of column-to-column relation can be visualized by the blue arrows). These two tables are relatable (one-to-one).

1. You can find the **+** expansion icon on each table that is linked to another table.

![Overview of invoices table with related data elements and connections to other tables.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-21 at 1.52.19 PM.png)

## Related

- [Managing queries in the Graph Explorer](/managing-queries-in-the-graph-explorer.md)
- [Inspecting instances in Graph Explorer](/inspecting-instances-in-graph-explorer.md)
