---
title: "Oracle"
slug: "oracle-regular-node"
updated: 2025-10-31T14:22:20Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/oracle-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Oracle

Oracle is a relational database management system (RDBMS) and is one of the most widely used database systems in the world, particularly in enterprise-level applications. It is renowned for its scalability, security, and high performance and it supports efficient data organization and retrieval through SQL.

In Securiti's Workflows module, the Oracle node is used to connect to Oracle databases, fetch data, or execute queries as part of a Workflow. Using the Workflow node, a series of steps can be performed on the Oracle database such as:

- Inserting or updating data in the database
- Executing an SQL query to perform any function on the database
- Execute an SQL script to perform an operation or set of operations on the database

Refer to the [Node configurations section](/v1/docs/granting-db-permissions-for-oracle) to understand the node properties and descriptions.

#### Example use case

In this use case, a Workflow is created to optimize the management of Data Subject Requests (DSRs). The process commences with a DSR Trigger node, triggered in response to a new user request. Subsequently, the Workflow undertakes a meticulous check of the user's presence in the database using the Oracle node, utilizing the user's email address for verification. Upon confirming the user's existence, the system seamlessly progresses to generate a DSR task along with its associated subtask, leveraging dedicated Nodes for these specific functions.

In essence, this streamlined Workflow serves as an automated solution for handling DSRs, ensuring prompt and compliant responses to user requests while adhering to data protection regulations.

The following Nodes are included in this Workflow:

1. [DSR Trigger Node](/v1/docs/dsr)
2. Oracle Node
3. [IF Node](/v1/docs/if)
4. [DSR Task Node](/v1/docs/dsr-sub-task)
5. [DSR SubTask Node](/v1/docs/dsr-sub-task)

#### Automating Data Subject Request (DSR) Management Workflow

1. Add **DSR Trigger Node** and set the Type and Source to **Internal** and **Any**.
2. Add Oracle Node with the required datasource. Use the query as shown below:

![Screenshot_2023-12-12_at_11_47_43_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b94784ce-e5aa-4a85-4200-d3c7e49e342f.png)
3. Add the **IF node** to check if the user exists in the database. If the email returns data, then set the node response to True.
4. Add **DSR Task** and **DSR Sub-task node** to create the corresponding task and subtask for the data subject using the respective Nodes.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2023-12-12_at_11_47_30_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-876c7762-ff8b-a63b-130a-e77991b7ba5e.png)

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the datasource configured for Oracle data system. See the [Oracle connector documentation](/v1/docs/activate-the-oracle-connector-in-securiti) to understand how to configure a data system. |
| Connect to Database | Choose the database to connect to. The databases appear in a dropdown for the datasource selected. |
| Operation | Execute Query | Select this option to execute a custom query on the database. The query can perform any CRUD operation. |
| Insert | Select this option if data is inserted into the database. |
| Update | Select this option if existing data is updated in the database. |
| Execute Script | Select this option to execute a script that contains multiple queries and commands. |
| Database | Specify the name of the database as multiple databases are supported for this node. For example, users. |
| Query | Specify the query to execute on the database. An example query below deletes a user in the database: *Delete from Users where ID = 1034* |
| Table | Specify the name of the table in the database in which the data is inserted or updated as per the selected operation. For example, *employees*. |
| Columns | Specify the name(s) of properties (comma separated if multiple) that are used as columns for the rows to update. For example, *name.description* |
| Update Key | Specify the key to update in the table if the selected operation is Update It is usually the primary identifier. for example, *ID.* |
| Script | Specify the script to execute on the database. An example script is: *SELECT user_id, username, email FROM users WHERE user_type = 'customer';* *SELECT order_id, user_id, product_name, order_date FROM orders WHERE user_id IN (SELECT user_id FROM users WHERE user_type = 'customer');* |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
