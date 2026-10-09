---
title: "Verifying and configuring joins"
slug: "verifying-and-configuring-joins-1"
updated: 2026-02-03T14:58:39Z
published: 2026-02-09T22:00:18Z
canonical: "helpcenter.securiti.ai/verifying-and-configuring-joins-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Verifying and configuring joins

For all tables, identify the Joins (Foreign Key links) that relate the Table to any other tables. Securiti uses this information to correctly query the Table and any related tables for personal data when it collects information to fulfill DSR requests. When Securiti does its initial scanning, it reads the Joins from the metadata for each Table.

> [!NOTE]
> **Important**
> 
> We recommend you ensure that only one Table contains the Primary Identifier (PI) columns, and other tables contain the **DataElement** Column for the PI value. This approach successfully Joins all the tables and retrieves data for all related tables.

During Table training, you confirm the Joins or correct them as necessary:

1. In the Tables & Schemas list, click the relationship view icon.

Securiti shows you a graphical view of all tables and their Joins.
2. For all tables:
  - Evaluate the Joins and make sure that they are valid and appropriate.
  - Evaluate whether there are Joins that should be shown but are not.

If necessary, you can add Joins that Securiti uses when querying tables for personal data when fulfilling DSRs, and supports joining columns with either the same or different Data element types. For example:

- You can join two *BIGINT* columns like *user_id* and *customer_id*.
- Or you join across types such as *user_id (BIGINT)* and *email (STRING)*.

You can configure joints using either the list or graphical views, as described below:

**To add Joins using the graphical relationship view**, you draw a path between the Foreign Key and the Primary key as follows:

1. If you haven't already done so, in the Tables & Schemas list, click the relationship view icon.
2. Find the Foreign Key you want to join.
3. Click on the Foreign Key, drag outside its box, and release.

Securiti creates a join arrow that starts from the Foreign Key and follows the mouse pointer.
4. Hover over the Primary key you want to join and check to see whether Securiti draws a box around the key.

The box indicates that both keys are of the same Data element type, and are eligible for joining. If the box does not appear, it means that the keys are of different types, and you cannot join them.
5. Click on the Primary key inside the box.

Securiti draws a join arrow between the foreign and primary keys, and rearranges the tables so that the arrow points generally to the right between the foreign and primary keys.

**To add Joins using the list view**, you click on the Foreign Key, then choose the Primary key from among the eligible columns:

1. If you haven't already done so, in the Tables & Schemas list, click the list view icon.
2. In the Schemas & Tables list, click the entry for the Table containing the Foreign Key in question.

Securiti shows the Table columns in the Table Column list area.
3. Find the card for the Column that contains the Foreign Key and click **+ Add** in the Reference Column Column as shown below.

![C00199.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3209a6ac-1d7a-9926-c9b8-17c68f7e53b9.png)

Privacy opens a panel that shows you all Table columns that are eligible for joining.
4. Click on the Primary key you want to join as shown below.

![C00200.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4236d6e-ec27-af0a-08c1-a749405c388b.png)
5. Click **OK**.

Securiti closes the panel and adds the Primary key as an entry in the Reference Column Column for the Foreign Key.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
