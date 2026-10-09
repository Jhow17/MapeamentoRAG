---
title: "Using Table View in Graph Explorer"
slug: "using-table-view-in-graph-explorer"
updated: 2026-05-14T08:18:45Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/using-table-view-in-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Using Table View in Graph Explorer

By default, you can create filters and view them in a grid panel or form of a table in the graph explorer. The table view of the graph explorer contains two main components:

- The entities list on the left side of the page
- Grid on the right side of the page

The entities list contains all the nodes and their related entities you have selected in your filter criteria, along with their respective counts.

The grid on the right displays all instances of a node or entity, along with counts of specific attributes for an entity. Clicking an entity on the left side displays all instances of that entity on the grid.

![Overview of security posture findings with various asset types and statuses listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Grid View_Graph Explorer.png)

### Applying filters from the grid

You can update filters by using the grid as described below:

1. From the left **Entities** navigation bar, select any entity.
2. Apply the increment (+ icon) or decrement (- icon) operator to include or exclude an attribute. On the Expression Builder bar at the bottom, click **Apply Filters**.

![Graph Explorer interface displaying data system and security posture findings with filters applied.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Apply Filter_Graph Explorer.png)
3. Click **Run Query** to execute the updated query. The added filter appears in the top row of the dashboard with the rest of the filters.

![Graph Explorer interface showing data systems and security posture findings with query options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Updated query_Graph Explorer.png)

![Graph Explorer interface displaying data system and security posture findings in Google Cloud.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Updated query results_Graph Explorer.png)

### Customize grid view

You can customize the grid layout according to your preferences. You can select the columns you want to see and rearrange them by dragging and dropping.

> [!NOTE]
> **Note**
> 
> Securiti automatically saves your layout changes in your profile and eliminates the need for you to readjust the layout every time you visit the page.

To modify the grid layout:

1. On the grid view, near the upper right corner of the grid panel, click **Column Selector**.
2. Select columns from the list that you want to display in the table and click **Apply**.

![Graph Explorer displaying data system and security posture findings with asset details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Column Rearrangement_Graph Explorer.png)
3. You can also resize the columns according to your preference. To resize the columns.
  1. Hover your cursor on the column boundary till it transforms into a resize icon.
  2. Click and drag the boundary to the left or right to adjust the column width according to your preference.
  3. Release the mouse once you have reached your desired width, and the columns resize accordingly.

> [!NOTE]
> **Note**
> 
> Click **Restore Default** to revert the grid layout to its default view whenever needed.

![Graph Explorer interface displaying data system and security posture findings with asset details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Column View options_Graph Explorer.png)

### Exporting query results in CSV format

You can download your queries in a grid with filters on the Graph Explorer dashboard in a CSV file. Securiti sends you an email containing the download link to the CSV file.

> [!NOTE]
> **Note**
> 
> The contents of the file reflect the filters applied at the time of the download.

1. Apply filters as per your requirement, as described above.
2. From the upper right corner of the grid, click the export scheduler icon.![Graph Explorer displaying data system and security posture findings with asset details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export CSV option_Graph Explorer.png)
3. In the **Export CSV** dialog box, enter your CSV file name and click **Export CSV**.

![Export CSV dialog showing file name and export options in Graph Explorer interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Export CSV_Graph Explorer.png)
4. Securiti appends a timestamp in milliseconds (ms) to the file name after scheduling an export.
5. Securiti schedules your download, and a success message is displayed on screen. An email with the download link to the file is also sent to your email address.
6. Open your email associated with the Securiti tenant, and click **Download File** to download the CSV file containing your grid with filters, to your local machine, as shown below.

![Download link for exported graph data, with expiration notice for security purposes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download link in email_Graph Explorer.png)
