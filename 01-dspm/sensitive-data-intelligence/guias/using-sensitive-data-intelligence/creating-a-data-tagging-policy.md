---
title: "Creating a Data Tagging policy"
slug: "creating-a-data-tagging-policy"
updated: 2026-07-21T04:31:02Z
published: 2026-07-21T04:31:02Z
canonical: "helpcenter.securiti.ai/creating-a-data-tagging-policy"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating a Data Tagging policy

> [!WARNING]
> Important
> 
> - Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.
> - You must configure the required tags and tag categories before creating a Data Tagging policy. For more information, see [Tag management](/latest/docs/tag-management).

To create a Data Tagging policy:

1. From the main menu, choose **Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-C6016LEL.png)
2. From **Policies**, choose **Data Tagging** policy, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-U8UCR4JI.png)
3. Click **+ Create** to create a Data Tagging policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EQ87BLZ3.png)
4. Enter a **Name** and **Description** for the policy, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1F7BQVGO.png)
5. Set the policy **owner**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VNAZHQYG.png)
6. (Optional) Set the policy **co-owners**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-R46WFG8Z.png)
7. Enable **Activate Policy** to run the policy immediately after creation, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YHEKXFXG.png)
8. Click **Add scope** to open the **Graph Explorer** as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BN7CLVOR.png)
9. In the **Graph Explorer**, define your query by selecting the target objects. For example, files, data systems, datasets, tables, and columns, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-P58OLUNA.png)
10. Click **Run Query** to view the number of objects that match your defined criteria, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RVR23R3G.png)
11. Here, 59,626 files matched your defined criteria. Click **Use Query**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EK5WOZ9P.png)

> [!NOTE]
> Note
> 
> A Data Tagging policy can include multiple scopes. Securiti evaluates and processes each scope independently, as shown below. Tags apply only to the primary (first) node selected in the query. For instance, to apply tags on the **Data System**, you must begin your query with the **Data System** entity.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OGZFKR62.png)
12. Click **Edit** to configure tagging actions, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IBVC7EVZ.png)

## Adding tags

## Removing Tags
  1. To add tags, click **Add Tags** on the **Tag Items** popup, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-V3NLA3QT.png)
  2. Click **Search or Add New**, to choose or add a tag category, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-E51HOXCT.png)
  3. Click **Search or Add New**, to choose or add a tag, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JUK333O8.png)
  4. Click **Save Action**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CT8T0HUI.png)
  1. To remove tags, click **Remove Tags** on the **Tag Items** popup, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Z7V20XDI.png)
  2. Choose one of the following options

| Options | Description |
| --- | --- |
| Remove specific tags | To remove specific tags: 1. Select **Remove specific tags.** 2. Click **Search or Add New**, to choose or remove a tag category. 3. Click **Search or Add New**, to choose or remove a tag. 4. Click **Save Action.** ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JROIA270.png) |
| Remove all tags | To remove all tags: 1. Select **Remove all tags.** 2. Click **Save Action.** ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZMDCL4P2.png) |
13. Click **Create Policy**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-P1GMVUZX.png)
14. You can view your newly created Data Tagging policy on the Data Tagging **Policies** page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BBKHFUE7.png)
