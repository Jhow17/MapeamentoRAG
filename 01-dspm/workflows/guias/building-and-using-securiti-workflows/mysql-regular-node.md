---
title: "MySQL"
slug: "mysql-regular-node"
updated: 2025-10-31T14:22:14Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/mysql-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# MySQL

MySQL is an open-source relational database management system (RDBMS), widely used for managing and organizing data. It is known for its speed, reliability, and ease of use. MySQL uses a client-server model and is a popular choice for web applications and small to medium-sized databases.

In Securiti’s Workflows module, a MySQL node is used to connect to the database and perform a certain set of actions. Following are the operations that can be performed using the MySQL node:

- Inserting or updating data in the database.
- Executing an SQL query to perform an operation on the database.
- Execute an SQL script to perform an operation or set of operations on the database.

Refer to the [Node Configurations section](/v1/docs/obtain-authentication-credentials-in-amazon-rds-for-mysql) to understand the node working and properties.

#### Example use case

In this use case, a Workflow is designed to manage Data Subject Requests (DSRs) efficiently. It begins with a DSR Trigger node, activated upon the initiation of a new user request. The Workflow then checks the user's existence in the database using MySQL node and the user's email address. If the user is found, the system proceeds to create a DSR task and its corresponding subtask through dedicated Nodes.

Overall, this Workflow automates and streamlines the responses to DSRs, ensuring that user requests are handled swiftly and in compliance with data protection regulations. By automating these processes, organizations can reduce manual effort, enhance their response to data subject requests, and bolster data security and regulatory compliance.

The following Nodes are included in this Workflow:

1. [DSR Trigger Node](/v1/docs/dsr)
2. MySQL Node
3. [IF Node](/v1/docs/if)
4. [DSR Task Node](/v1/docs/dsr-task)
5. [DSR Sub-Task Node](/v1/docs/dsr-sub-task)

#### Automating Data Subject Request (DSR) Management Workflow

1. Add **DSR Trigger Node** and set the Type and Source to Internal and Any.
2. Add **MySQL node** with the required datasource. Use the query as shown below:

![Screenshot_2023-12-12_at_11_54_22_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fb9a38c1-0e3b-6949-b248-e25766c3f98e.png)
3. Add the **IF node** to check if the user exists in the database. If the email returns data, then set the node response to *True*.
4. Add **DSR Task** and **DSR Sub-task node** to create the corresponding task and subtask for the data subject using the respective Nodes.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2023-12-12_at_11_54_04_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75a33a54-12a5-a183-25f6-15ce3ec10a4d.png)

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the datasource configured for MySQL data system. See the [MySQL connector documentation](/v1/docs/activate-the-adobe-marketo-engage-connector-in-securiti) to understand how to configure a data system. |
| Operation | Execute Query | Select this option to execute a custom query on the database. The query can perform any CRUD operation. |
| Insert | Select this option if data is inserted into the database. |
| Update | Select this option if existing data is updated in the database. |
| Execute Script | Select this option to execute a script that contains multiple queries and commands. |
| Connect to Database | Choose the database to connect to. The databases appear in a dropdown for the datasource selected. |
| Database | Specify the name of the database as multiple databases are supported for this node. For example, users. |
| Query | Specify the query to execute on the database. An example query below deletes a user in the database: *Delete from Users where ID = 1034* |
| Table | Specify the name of the table in the database in which the data is inserted or updated as per the selected operation. For example, *employees*. |
| Columns | Specify the name(s) of properties (comma separated if multiple) that are used as columns for the rows to update. For example, *name.description*. |
| Update Key | Specify the key to update in the table if the selected operation is Update It is usually the primary identifier. for example, *ID*. |
| Script | Specify the script to execute on the database. An example script is: *SELECT user_id, username, email FROM users WHERE user_type = 'customer';* *SELECT order_id, user_id, product_name, order_date FROM orders WHERE user_id IN (SELECT user_id FROM users WHERE user_type = 'customer');* |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
