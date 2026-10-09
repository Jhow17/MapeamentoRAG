---
title: "Postgres"
slug: "postgres-regular-node"
updated: 2025-11-04T05:20:52Z
published: 2025-11-04T05:20:52Z
canonical: "helpcenter.securiti.ai/postgres-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Postgres

Postgres is an advanced, open-source relational database management system (RDBMS) that supports a large part of the SQL standard and offers many modern features such as complex queries, foreign keys, triggers, updatable views, transactional integrity, and multi version concurrency control.

In the context of Workflow Automation, a Postgres node is typically used to integrate PostgreSQL database operations into automated workflows. This node can perform the following functions within a Workflow environment:

- Insert or update data in the database
- Execute an SQL query to perform any function on the database
- Execute an SQL script to perform an operation or set of operations on the database

Please refer to the [node configurations section](/v1/docs/postgres#node-configurations) to understand the node working and properties.

#### Example use case

In this use case, a Workflow is created to optimize the management of Data Subject Requests (DSRs). The process commences with a DSR Trigger node, triggered in response to a new user request. Subsequently, the Workflow undertakes a meticulous check of the user's presence in the database using the Postgres node, utilizing the user's email address for verification. Upon confirming the user's existence, the system seamlessly progresses to generate a DSR task along with its associated subtask, leveraging dedicated nodes for these specific functions.

In essence, this streamlined Workflow serves as an automated solution for handling DSRs, ensuring prompt and compliant responses to user requests while adhering to data protection regulations.

The following nodes are included in this Workflow:

- [DSR Trigger Node](/v1/docs/dsr)
- Postgres Node
- [IF Node](/v1/docs/if)
- [DSR Task Node](/v1/docs/dsr-task)
- [DSR SubTask Node](/v1/docs/trigger-nodes-dsr-sub-task)

#### Automating Data Subject Request (DSR) Management Workflow

1. Add DSR Trigger Node and set the Type and Source to **Internal** and **Any**.
2. Add Postgres Node with the required datasource. Use the query as shown below:

![Screenshot_2024-05-07_at_4_46_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d41d406c-c9e9-d5a1-e90d-7c2770f62c92.png)
3. Add the IF node to check if the user exists in the database. If the email returns data, then set the node response to True.
4. Add DSR Task and DSR Sub-task node to create the corresponding task and subtask for the data subject using the respective Nodes.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2024-05-07_at_4_47_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03da8646-8d5f-2432-673a-1b05bd2a4254.png)
6. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Data system instance name in Securiti |
| Connect to Database | Database names configured on Privaci Datasources page. |
| Operation | Execute Query | Executes an SQL query |
| Insert | Inserts rows in a database |
| Update | Updates rows in a database |
| Execute Script | Executes an SQL script |
| Query | For Execute Query operations, the SQL query to execute |
| Schema | The name of the schema the table belongs to |
| Table | For Insert and Update operations, the name of the table to insert data into |
| Columns | For Insert and Update operations, a comma-separated list of the properties to be used as columns for the new rows |
| Update Key | For Update operations, the name of the property that determines which rows in the database to update. Usually "id" |
| Script | For Execute Sript operations, the SQL script to execute |
