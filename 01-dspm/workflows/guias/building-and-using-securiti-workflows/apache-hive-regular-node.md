---
title: "Apache Hive"
slug: "apache-hive-regular-node"
updated: 2026-01-09T00:43:06Z
published: 2026-01-09T00:43:06Z
canonical: "helpcenter.securiti.ai/apache-hive-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Apache Hive

Apache Hive node plays various roles in big data workflows. Apache Hive is a central database that stores metadata about tables and data partitions. Hive Servers provide an interface for clients to submit HiveQL queries, which are processed on a Hadoop cluster. Hive nodes can execute distributed queries, insert data into the database or update the already existing data in the database.

Refer to the [Node configuration section](/v1/docs/configure-discovery-scans-in-apache-hive) to understand the node properties and configurations.

#### Example use case

In this use case, let’s design a workflow to manage Data Subject Requests (DSRs) efficiently. It begins with a **DSR Trigger node**, triggered with initiation of a new user request. The workflow then verifies if the user exists in the database using an **Apache Hive node** and the user's email address. If the user exists in the database, the system proceeds to create a DSR task and its corresponding subtask through dedicated nodes.

Overall, this workflow automates and streamlines the response to DSRs, ensuring that user requests are handled swiftly and in compliance with data protection regulations. By automating these processes, organizations can reduce manual effort, enhance their response to data subject requests, and bolster data security and regulatory compliance.

Following nodes are used in this workflow:

1. [DSR Trigger Node](/v1/docs/dsr)
2. Apache Hive Node
3. [IF Node](/v1/docs/if)
4. [DSR Task Node](/v1/docs/dsr-task)
5. [DSR Sub-task Node](/v1/docs/dsr-sub-task)

#### Prerequisites

Make sure that the Apache Hive connector is configured and active to use in the workflow.

#### Automating Data Subject Request (DSR) Management Workflow

1. Add DSR Trigger Node and set the Type and Source to **Internal** and **Any**.
2. Add Apache Hive Node with the required datasource. Use the query as shown below:

![Screenshot_2023-11-07_at_6_58_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bb7c4e84-6f0d-07d8-70dd-1edc1d0f858c.png)
3. Add the IF node to check if the user exists in the database. If the email returns data, then set the node response to **True**.
4. Add DSR Task and DSR Sub-task node to create the corresponding task and subtask for the data subject using the respective nodes.
5. Connect the nodes and execute the workflow.

![Screenshot_2023-11-07_at_6_58_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-28d1a8e9-9e47-9378-2ae2-d8f830e0f1bd.png)
6. Once the workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the datasource configured for Apache Hive data system. Refer to the [Apache Hive connector documentation](/v1/docs/activate-the-apache-hive-connector-in-securiti) to understand how to configure a data system. |
| Connect to Database | Choose the database to connect to. The databases appear in a menu for the datasource selected. |
| Operation | The operation to perform |
| Execute Query | Select this option to execute a custom query on the database. The query can perform any CRUD operation. An example query is, *Delete from Users where ID = 1034* |
| Insert | Select this option if data is inserted into the database. |
| Update | Select this option if existing data is updated in the database. |
| Schema | Specify the name of the database as multiple databases is supported for this node. For example, users. |
| Table | Specify the name of the table in the database in which the data is inserted or updated as per the selected operation. For example, *employee*. |
| Columns | Specify the key to update in the table if the selected operation is Update It is usually the primary identifier. for example, *ID*. |
