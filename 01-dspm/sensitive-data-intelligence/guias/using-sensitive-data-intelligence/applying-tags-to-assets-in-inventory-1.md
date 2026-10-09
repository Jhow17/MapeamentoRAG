---
title: "Applying tags to graph objects"
slug: "applying-tags-to-assets-in-inventory-1"
updated: 2026-09-17T16:18:06Z
published: 2026-09-17T16:18:06Z
canonical: "helpcenter.securiti.ai/applying-tags-to-assets-in-inventory-1"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Applying tags to graph objects

You can apply tags to graph objects directly from the Inventory dashboard to organize and manage metadata at scale. Tagging helps you classify assets consistently, improve search and filtering, and support governance workflows.

## Tag application in Inventory

The **Inventory** dashboard provides a bulk action bar that lets you apply tags to your assets and perform actions such as add, remove, or replace tags for one or more selected assets.

> [!NOTE]
> Note
> 
> You can apply Security Tags to any supported node from the Inventory dashboard, except the following graph entities:
> 
> - Activity Log
> - Column
> - Discovery Scan File
> - File
> - File Findings
> - Folder
> - IAM Resource Access
> - IAM Resource Access Sharing Link
> - Security Posture Findings
> - Structured Findings
> - Workflow
> - Workflow Execution
> 
> 
> 
> For the entities listed above, use a Data Tagging Policy to apply tags to **File**, **Folder**, and **Column** entities. For more information, see [Using Data Tagging Policies](/latest/docs/using-data-tagging-policies).

To apply tags to your assets in **Inventory:**

1. From the left menu, select the required entity, such as **Hosting**, to display its assets in the grid.
2. In the grid, mark the checkboxes to select one or more assets, as shown below.
3. In the bulk action bar above the grid, select **Tag**.

![Inventory management interface displaying hosting options and security tags for data services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tags_inventorydash_option.png)
4. In the **Tags** dialog, choose one of the following actions:
  - **Add Tags:** This lets you add new tags while keeping existing ones.

![Inventory management interface displaying cloud assets and tagging options for data organization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tags_addtags.png)
  - **Remove Tags:** This lets you remove selected tags from the assets.

![Inventory management interface displaying cloud assets and tagging options for data organization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tags_removetags.png)
  - **Replace Tags:** This lets you remove all existing tags and apply the selected ones.

![Interface displaying cloud inventory management with options for tagging data types and categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tags_replacetags.png)
5. Select the category and choose the required tag value(s).
6. Click **Save**.

Securiti updates the selected assets accordingly.

The applied tags appear in the **Securiti Tags** column in the Inventory table, as shown below. You can view multiple tags associated with each asset and can also use filters to refine results based on tags.

![Inventory management interface displaying hosting options and security tags for cloud services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/tags_appliedtags.png)
