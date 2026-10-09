---
title: "SQL Server"
slug: "sql-server-regular-node"
updated: 2025-10-31T14:22:54Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/sql-server-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# SQL Server

Using the SQL Server node in Securiti’s Workflows module, you can directly write and execute SQL statements within the node to perform various database operations on a Microsoft SQL Server instance. This includes:

- Inserting, updating, or deleting data
- Retrieving specific records or sets of data
- Executing scripts or query to perform the desired action

The node allows capturing input from previous Workflow Nodes and using them as parameters within the SQL query, enabling dynamic interactions with the database. After execution, the node returns the resulting data (if applicable) back to the following Workflow Nodes for further processing. SQL server node automates various database interactions within your Workflow, improving efficiency and reducing manual effort.

Refer to the [Node configurations section](/v1/docs/prerequisites-for-google-cloud-sql-for-sql-server) to understand the node working and properties.

#### Example use case

This use case demonstrates an automated Workflow for handling Data Subject Requests (DSRs), ensuring efficient and compliant responses to the user queries while adhering to data protection regulations.

A dedicated **DSR Trigger** node starts the Workflow, responding to a newly submitted user request. This node interacts with your designated SQL database, executing a query to search for the user's email address within the relevant user table.

Upon successful user verification, a dedicated **DSR Task** Generation Node creates a new task corresponding to the DSR request. Another node, specific to Subtask Creation, generates any associated subtasks necessary for fulfilling the DSR, ensuring a comprehensive request resolution.

The following Nodes are used in this Workflow:

1. [DSR Trigger Node](/v1/docs/dsr)
2. SQL Server Node
3. [IF Node](/v1/docs/if)
4. [DSR Task Node](/v1/docs/dsr-task)
5. [DSR SubTask Node](/v1/docs/dsr-sub-task)

#### Automating Data Subject Request (DSR) Management Workflow

1. Add DSR Trigger node and set the Type and Source to **Internal** and **Any**.
2. Add SQL Server node with the required datasource. Use the query as shown below:

![Screenshot_2024-02-20_at_3_32_09_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a40d96ff-85b2-2ad0-f90a-461c35d6f854.png)
3. Add the IF node to check if the user exists in the database. If the email returns data, then set the node response to **True**.
4. Add DSR Task and DSR Sub-task node to create the corresponding task and subtask for the data subject using the respective Nodes.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2024-02-20_at_3_30_59_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d8402d72-97f2-d889-0179-8cbc13a4e602.png)

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the datasource configured for SQL Server data system. See the [SQL connector documentation](/v1/docs/activate-the-microsoft-sql-server-connector-in-securiti) to understand how to configure a data system. |
| Connect to Database | Choose the database to connect to. The databases appear in a menu for the datasource selected. |
| Operation | Execute Query | Select this option to execute a custom query on the database. The query can perform any CRUD operation. An example query is *Delete from Users where ID = 1034* |
| Insert | Select this option if data is inserted into the database. |
| Update | Select this option if existing data is updated in the database. |
| Execute Script | Executes an SQL script |
| Query | For Execute Query operations, the SQL query to execute |
| Table | Specify the name of the table in the database in which the data is inserted or updated as per the selected operation. For example, *employees*. |
| Columns | For Insert and Update operations, a comma-separated list of the properties to be used as columns for the new rows |
| Update Key | Specify the key to update in the table if the selected operation is Update It is usually the primary identifier, for example, *ID*. |
| Script | Specify the name(s) of properties (comma separated if multiple) that are used as columns for the rows to update. For example, *name.description*. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
