---
title: "Azure Cosmos DB"
slug: "azure-cosmos-db-regular-node"
updated: 2026-01-09T06:51:56Z
published: 2026-01-09T06:51:56Z
canonical: "helpcenter.securiti.ai/azure-cosmos-db-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Azure Cosmos DB

In Workflows, a Cosmos DB node plays a crucial role in managing and interacting with the Azure Cosmos DB database service. It serves as a bridge or interface between the workflow and the database, allowing data to be read from or written to the database, and performing various database operations.

The Cosmos DB node can execute tasks such as querying the database for specific data, inserting new records, updating existing documents, or deleting data as needed. It provides the workflow with the necessary means to interact with the database in a seamless and efficient manner.

Refer to the [Node configuration section](/v1/docs/prerequisites-for-azure-cosmos-db) to understand the Node Configurations and properties.

#### Example use case

In this use case, a workflow is designed to manage Data Subject Requests (DSRs) efficiently. It begins with a DSR Trigger node, activated upon the initiation of a new user request. The workflow then checks the user's existence in the database using an Azure Cosmos DB node and the user's email address. If the user is found, the system proceeds to create a DSR task and its corresponding subtask through dedicated nodes.

Overall, this workflow automates and streamlines the response to DSRs, ensuring that user requests are handled swiftly and in compliance with data protection regulations. By automating these processes, organizations can reduce manual effort, enhance their response to data subject requests, and bolster data security and regulatory compliance.

Following nodes are used in this workflow:

1. [DSR Trigger Node](/v1/docs/dsr)
2. Azure Cosmos DB Node
3. [IF Node](/v1/docs/if)
4. [DSR Task Node](/v1/docs/dsr-task)
5. [DSR Sub-task Node](/v1/docs/dsr-sub-task)

#### Automating Data Subject Request (DSR) Management Workflow

1. Add DSR Trigger Node and set the Type and Source to **Internal** and **Any**.
2. Add Azure Cosmos DB with the required datasource. Use the query as shown below:

![Screenshot_2023-11-07_at_7_28_29_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c452e416-b9dc-33fe-0475-32c72c0fd947.png)
3. Add the IF node to check if the user exists in the database. If the email returns data, then set the node response to True.
4. Add DSR Task and DSR Sub-task node to create the corresponding task and subtask for the data subject using the respective nodes.
5. Connect the nodes and execute the workflow.

![Screenshot_2023-11-07_at_7_26_28_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b62186f-b874-1617-c9a3-c7efec7e2893.png)
6. Once the workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the datasource configured for Azure Cosmos DB data system. See the [Cosmos DB connector documentation](/v1/docs/activate-the-azure-cosmos-db-connector-in-securiti) to understand how to configure a data system. |
| Connect to Database | Choose the database to connect to. The databases appear in a menu for the datasource selected. |
| Operation | The operation to perform |
| Execute Query | Select this option to execute a custom query on the database. The query can perform any CRUD operation. An example query is *Delete from Users where ID = 1034* |
| Insert | Select this option if data is inserted into the database. |
| Update | Select this option if existing data is updated in the database. |
| Schema | Specify the name of the schema to which the table belongs. |
| Table | Specify the name of the table in the database in which the data is inserted or updated as per the selected operation. For example, *employees*. |
| Update Key | Specify the key to update in the table if the selected operation is Update It is usually the primary identifier, for example, *ID*. |
| Columns | Specify the name(s) of properties (comma separated if multiple) that are used as columns for the rows to update. For example, *name.description*. |
