---
title: "Creating and customizing Data Mapping Automation reference lists"
slug: "creating-and-customizing-data-mapping-automation-reference-lists"
updated: 2025-12-09T08:24:46Z
published: 2025-12-09T08:24:46Z
canonical: "helpcenter.securiti.ai/creating-and-customizing-data-mapping-automation-reference-lists"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and customizing Data Mapping Automation reference lists

You use reference lists to define the available choices for fields when you add data mapping items such as assets or vendors. You select items from reference lists when you create or customize data mapping element templates.

Each data mapping template has its own set of reference lists. The reference lists in the template depend on the template type.

### Viewing an existing reference list

1. In Securiti, open Data Mapping Automation, choose **Settings >** Definitions and click **Reference Lists**.
2. Click the card for the catalog definition (template) or enter the template name in the search box for which you want to open a reference list.
3. In the Sections list, click the section that the reference list belongs to.
4. In the list of reference lists for the section, find the reference list and click it.

### Editing a reference list

1. Click the pencil icon to open the reference list for editing.

The Edit Reference List page shows you the 'Name,' 'Status,' 'Created by,' 'Created on,' 'Last Modified by,' and 'Last Modified' columns. Also, you can search for items and apply sort by **Name & Content**.

![Screenshot_2024-03-05_at_4_16_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4d556be-dd3d-670c-00e5-538d87ea0d78.png)
2. Use the tools on the Edit Reference List page to customize the reference list to suit.

> [!NOTE]
> **Note**
> 
> You must click Edit List to apply any changes on the page.
  - Near the upper right corner of the page, click **Edit List**. Click **+Add New** to add multiple reference list items. Click **Add**, then **Save**.

![Screenshot_2024-03-04_at_4_54_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-40b7ca33-9f34-8603-3d89-1ce246adecad.png)

![Screenshot_2024-03-04_at_4_55_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd3b8dee-f43a-1fb2-93ad-ce852ee7aa2d.png)
  - Also, Edit List offers you the option to perform actions in bulk for the selected items. From the **Select Bulk Action** dropdown, choose **Change Status** or **Delete**.

![Screenshot_2024-03-04_at_4_54_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-702a982f-449f-2133-a143-f29944a6a7e5.png)

Change Status changes the status of all selected items, for example, from *active* to *inactive*. Similarly, Delete lets you remove selected items from the list.
  - Use the Options menu **(three vertical dots)** at the right end of an item to edit, delete, de(activate), etc. from the list.
  - (Optional) If you want, you can edit the reference list sort order by clicking the "sort icon" near the top right.

![Editing the reference list for data disposal methods in system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e6b59efb-7462-7858-78a0-a6fc5b83ada9.png)

The options include:

1. Alphabetically (A-Z, Z-A)

2. Last Modified (Descending or Ascending)

3. Date Created (Descending or Ascending)

4. Custom

> [!NOTE]
> Note
> 
> When "Custom" is selected, you can manually set what item goes where on the page; up, down, or assign number to it. This appears logically in data mapping and Field questions.

![List of lawful bases for data processing with active status indicators.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc22d3af-a6a5-c6a6-3551-b6a31c351fd3.png)
3. When you're done, click **Save**.

### Creating a new reference list

1. In Securiti, open Data Mapping Automation, choose **Settings > Definitions** and click **Reference Lists**.
2. Click the card for the catalog definition (template) to which you want to add a new reference list.
3. In the Sections list, click the section that you want to add the reference list to.
4. Near the upper right corner of the main panel, click **+**.
5. On the New Reference List popup, apply the following settings, then click **Save**:

| List name | Type a convenient name for the new list. |
| --- | --- |
| Select Section | Choose the section of the template to which to add the new list. |

### Deleting a reference list

1. In Securiti, open Data Mapping Automation, choose **Settings > Definitions** and click **Reference Lists**.
2. Click the card for the catalog definition (template) from which you want to delete a reference list.
3. In the Sections list, click the section that the reference list belongs to.
4. In the list of reference lists for the section, find the reference list and choose **Options > Delete**.
5. On the popup, click **Yes** to confirm.

### Cloning a reference list

You can clone a reference list into different sections of the same catalog definition, or into any section of a different catalog definition.

1. In Securiti, open Data Mapping Automation, choose **Settings > Definitions** and click **Reference Lists**.
2. Click the card for the catalog definition (template) for which you want to clone a reference list.
3. In the Sections list, click the section that the reference list belongs to.
4. In the list of reference lists for the section, find the reference list choose **Options > Clone**.
5. On the Clone Reference List popup, use the Select Catalog Definition menu and the Select Section menu to choose the catalog definition and section to clone the reference list into as shown below.

![RN_clone_reference_list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-33b9e98c-aba7-b5c2-f70d-93a841ada978.png)
6. On the popup, click **Save**.

### Importing a reference list from CSV

1. Create a CSV file with one column; that is, with the elements separated by line returns (not commas). If an element in the reference list contains a comma, enclose it in double quotes.
2. In Securiti, open Data Mapping Automation, choose **Settings > Definitions** and click **Reference Lists**.
3. Click the card for the catalog definition (template) into which you want to import a reference list.
4. Near the upper right corner of the main panel, click **+**.
5. On the New Reference List popup, give the new list a name and choose the section of the catalog definition where you want to import the reference list.
6. In the Reference List Values area, click the **Upload** link as shown below, then use the drag & drop box to identify and upload the file you created earlier.

![RN_import_reference_list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-44ffdc3f-bb3a-d247-8cde-5bf162f3614d.png)
7. When you are done, click **Save** to upload the file and create the new reference list in the catalog definition and section you chose.
