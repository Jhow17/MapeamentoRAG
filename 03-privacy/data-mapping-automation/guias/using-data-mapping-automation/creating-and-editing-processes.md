---
title: "Creating and editing processes"
slug: "creating-and-editing-processes"
updated: 2025-12-09T07:23:41Z
published: 2025-12-09T07:23:41Z
canonical: "helpcenter.securiti.ai/creating-and-editing-processes"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and editing processes

Once you have created a data mapping that contains your data assets, you can create processes that show your data process flow in both graphic and tabular forms.

### Prerequisites

Before creating and editing processes, ensure you must have one or more of the following roles and have access to the Data maps organization:

- Super Admin
- Org Admin
- Operator
- Module Owner
- DPO

### Creating a new empty process

You start creating processes by creating a new empty process as described below. After you create a blank process, you add elements to it. Each process element is a portion of the process that encompasses three elements from your data mapping: A source, an asset, and a destination for the data. If your process only has these three parts, you only need a single process element to encompass it. If your process has more parts, you can use additional process elements.

1. In Securiti choose **Data Mapping > Catalog > Processes**.
2. Near the upper right corner of the Assets page, click **+ Add Process**.
3. On the Add New Process popup, enter basic information about the new process, then click **Create**.

| Setting | Description |
| --- | --- |
| Template | Choose from among the available templates. See [Creating and customizing data mapping templates](/v1/docs/creating-and-customizing-data-mapping-templates) for more information about templates. |
| Name | Enter a unique name for the process element in Securiti. |
| Short description | Enter a short description for the process. |
| Purpose | Enter the purpose of the process. |

Securiti redirects you to the Process Details page for the new vendor.

### Creating a simple process

To create a simple three-part process:

1. If you haven't already, create the three catalog elements that constitute the parts of the process as described in these topics:
  - [Creating and editing data assets](/v1/docs/creating-and-editing-data-assets)
  - [Creating and editing vendors](/v1/docs/creating-and-editing-vendors)
  - [Creating and editing institutions](/v1/docs/creating-and-editing-institutions)
2. If you haven't already, create a new empty process as described in [Creating a new empty process](/v1/docs/creating-and-editing-processes).
3. If necessary, near the upper right corner of the Process Details page, click **Edit**.
4. Click **Add Process Element** to add a new element to the process.
5. In the new process element, use the Source, Asset, and Destination columns to populate information for the three parts of the process. For each part of the process, you must configure at least the entity (data mapping element).

As you configure the three data mapping elements, you can toggle back and forth between the Table View and Map View to make sure the process appears as you expect on the map.

While editing the process, you can also move elements around on the Map View between the different stages and scopes. When you are done, near the upper left corner of the map panel click **Save** as shown below.

![move_element_on_map.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2784aa37-500d-d6e9-b151-7db4e86602e5.png)

For assets, you can configure Data Sets, Data subject Types, and Elements and Element Types. On the Table View, click **Select** and use the Add Data Elements and Types, Sets or Subject Types popup as shown below, then click **Update**.

![RN_click_construct_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e15f01b-6db2-25fe-0cf2-bb0ecb70cbb4.png)

Any change made to the Data Set or Data Subject type constructs on the asset automatically flows through to the process where you used that Data Set or Data Subject type.

> [!NOTE]
> **Note**
> 
> Securiti shows you up to 50 items (where applicable) and returns the most relevant results when you search an item in the Recipient Type or Type of Guarantee field.
6. Use the User Groups tools at the bottom of the process element area to choose the user groups that have access to the data, and their locations, as shown below. ![RN_process_element_user_groups.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c01ff275-0b75-1913-9e8a-c7b1e251ef65.png)

> [!NOTE]
> **Note**
> 
> The options on the User Groups menu come from the Reference List for the template you chose when you created the empty process. See [Creating and customizing Data Mapping Automation reference lists](/v1/docs/creating-and-customizing-data-mapping-automation-reference-lists) for more information.
7. When you are finished configuring the process, near the bottom of the page, click **Save Process Element & Continue**.

### Creating a complex process

Use this procedure to create a more complex four or five-part process. You can also uses similar techniques to create longer and more complex processes by creating process elements that have overlapping entities:

1. Create the first three parts of the process as described in [Creating a simple process](/v1/docs/creating-and-editing-processes).
2. Below the first process element, click **Add Process Element** to add a second element.
3. Do one of the following:

When Securiti detects that the entities, stages, and scopes are identical, it collapses each overlapping entity into one.
  - For a four-part process, make the first two parts of the process identical to the last two parts of the first process element you created. Use the exact same entities, stages, and scopes.
  - For a five-part process, make the first part of the process identical to the last part of the first process element you created. Use the eact same entity, stage and scope.
4. When you are finished configuring the process, near the bottom of the page, click **Save Process Element & Continue**.

### Viewing process element details

After you have created a process, you can easily view details for any of its elements by clicking the link next to each element as shown below. Doing so opens the details page for the element.

![RN_DM_process_element_links.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ade30242-f794-2345-033a-953c57eeeeb7.png)

You can also view process element details for a process without opening it for editing:

1. In Securiti, open **Data Mapping Automation** and choose **Catalog > Processes**.
2. On the Processes tab, click a process.
3. On the Process Details tab, scroll down to the process elements table, and click the down arrow as shown below to expand it to show the read-only view of the element details.

![RN_DMA_read-only1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86f3fe0a-a7e9-0673-918c-60cb2c04e500.png)

The read-only view only shows fields for which information has been filled in. The page shows you the field contents in gray to remind you that you are viewing a read-only view that you cannot edit.

### Deleting a single process

1. If you haven't already done so, In Securiti choose **Data Mapping > Catalog > Processes** to open the Processes page.
2. At the right end of the card for the process, choose **Options > Delete**.
3. When Securiti prompts you to confirm, click **Delete**.

### Deleting multiple processes at a time

1. If you haven't already done so, In Securiti choose **Data Mapping > Catalog > Processes** to open the Processes page.
2. Along the left end of the table of processes, mark the checkboxes for the processes you want to delete.
3. At the right end of the search box, click **Delete** (trash can icon) as shown below.

![delete_multiple_processes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ecc4b865-e86d-ec03-d133-76dc2405b9e5.png)
4. When Securiti prompts you to confirm, click **Delete**.

> [!NOTE]
> **Note**
> 
> If any of the selected processes are ineligible for deletion, Securiti warns that they cannot be deleted and offers to delete the other selected items while skipping the ineligible ones.

A process defines the flow of data between entities and processes.

An asset records data for any application or store. You can use It to record an asset's name, description, purpose, etc. Also, you can use an asset in processes.

A reference list is a set of options or settings that lets you configure questions in a risk assessment, such as Single or Multi-select.
