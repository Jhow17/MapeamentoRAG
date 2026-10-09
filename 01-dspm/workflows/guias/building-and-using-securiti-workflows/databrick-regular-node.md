---
title: "Databrick"
slug: "databrick-regular-node"
updated: 2026-01-09T09:48:43Z
published: 2026-01-09T09:48:43Z
canonical: "helpcenter.securiti.ai/databrick-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Databrick

Databricks is a unified data analytics platform built on top of Apache Spark, designed to help organizations process, analyze, and derive insights from large volumes of data efficiently. The Databricks node lets you seamlessly integrate Databricks into your workflow automation, unlocking the power of large-scale data processing and analytics directly within your existing workflows.

You can perform the following operations using the Databricks node:

- Insert or update data directly into your Databricks tables, enabling dynamic data management within your workflows.
- Run custom queries or execute custom scripts as part of your workflow, extracting insights and manipulating data.

Refer to the [Node configurations section](/v1/docs/databrick) to understand the node working and properties.

#### Example use case

This use case demonstrates an automated workflow for handling Data Subject Requests (DSRs), ensuring efficient and compliant responses to the user queries while adhering to data protection regulations.

A dedicated DSR Trigger node starts the workflow, responding to a newly submitted user request. The Databricks node executes a tailored Spark SQL query to scan the user table for the provided email address.

Upon successful user verification, a dedicated DSR Task Generation Node creates a new task corresponding to the specific user request.Another node, specific to Subtask Creation, generates any associated subtasks necessary for fulfilling the DSR, ensuring a comprehensive request resolution.

The following nodes are used in this workflow:

- [DSR Trigger Node](/v1/docs/dsr)
- Databricks Node
- [IF Node](/v1/docs/if)
- [DSR Task Node](/v1/docs/dsr-task)
- [DSR Subtask Node](/v1/docs/dsr-sub-task)

#### Automating Data Subject Request (DSR) Management Workflow

1. Add DSR Trigger node and set the Type and Source to **Internal** and **Any**.
2. Add Databricks node with the required datasource. Use the query as shown below:

![Screenshot_2024-02-20_at_3_34_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9923e111-6eac-f1c0-6dc7-398b71af827c.png)
3. Add the IF node to check if the user exists in the database. If the email returns data, then set the node response to True.
4. Add DSR Task and DSR Sub-task node to create the corresponding task and subtask for the data subject using the respective nodes.
5. Connect the nodes and execute the workflow.

![Screenshot_2024-02-20_at_3_34_47_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8b62508-c53c-7c3c-8228-9e3873c2575a.png)

#### Node configurations

| Parameters |
| --- |
| Datasource Name | Specify the name of the datasource configured for Databricks data system. See [Databricks connector documentation](/v1/docs/activate-the-databricks-connector-in-securiti) to understand how to configure a data system. |
| Operation | Execute Query | Select this option to execute a custom query on the database. The query can perform any CRUD operation. An example query is *Delete from Users where ID = 1034* |
| Insert | Select this option if data is inserted into the database. |
| Update | Select this option if existing data is updated in the database. |
| Query | Specify the SQL query to execute. |
| Catalog name | Specify the catalog name. |
| Schema | Specify the name of the schema to which the table belongs. |
| Table | Specify the name of the table in the database in which the data is inserted or updated as per the selected operation. For example, *employees*. |
| Columns | Specify the name(s) of properties (comma separated if multiple) that are used as columns for the rows to update. For example, *name.description*. |
| Update key | Specify the key to update in the table if the selected operation is Update It is usually the primary identifier, for example, *ID*. |
