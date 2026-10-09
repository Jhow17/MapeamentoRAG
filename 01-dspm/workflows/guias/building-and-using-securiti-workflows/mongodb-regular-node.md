---
title: "MongoDB"
slug: "mongodb-regular-node"
updated: 2026-07-20T14:44:31Z
published: 2026-07-20T14:44:31Z
canonical: "helpcenter.securiti.ai/mongodb-regular-node"
stale: true
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# MongoDB

In Securiti’s workflows module, MongoDB is used as a data system to store and manage various aspects of the Workflow, and the MongoDB node handles the interactions with the MongoDB database within a Workflow.

Following actions are performed using the Securiti’s MongoDB Workflow node.

- Find documents from within the MongoDB database.
- Insert documents into the MongoDB database.
- Update pre-existing documents within the MongoDB database.

Refer to the [Node configurations section](/v1/docs/acquire-authentication-credentials-in-azure-cosmos-db-for-mongodb) to understand the node working and properties.

#### Example use case

As an example use case, let’s create a Workflow that gets triggered every time a new asset is created. The asset details are then fetched using the Asset ID of the asset that triggered the Workflow. The details are then fed to the MongoDB database using the MongoDB node.

Here is the breakdown of Nodes used in this Workflow:

1. [Data Maps Trigger Node](/v1/docs/data-maps)
2. [Assets Node](/v1/docs/asset)
3. MongoDB Node

#### Prerequisites

Make sure that the credentials for MongoDB are set up. Refer to the Setting up credentials section to understand how to do that.

#### Write Assets Data to MongoDB on Asset Creation

1. Add the **Data Maps trigger node** and set the trigger type to asset creation.
2. Add the **Assets node** to fetch the details of the asset that triggered the Workflow.
3. Finally write the data to MongoDB using the MongoDB node. Add the parameters as shown below:

![Screenshot_2023-12-12_at_1_45_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08e8afc1-0d01-fafc-342d-ce635364c599.png)
4. Connect the Nodes and execute the Workflow.

![Screenshot_2023-12-12_at_1_45_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-01711982-d3a5-a698-6186-61be149db48d.png)
5. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| MongoDB | Specify the MongoDB database to connect to. See the [Setting up credentials section](/v1/docs/acquire-authentication-credentials-in-azure-cosmos-db-for-mongodb) to set up credentials to connect to the database. |
| Operation | Find | Select this option to find a specific collection in the database. |
| Insert | Select this option to insert a document or field in the database. |
| Update | Select this option to update a pre-existing document in the database. |
| Collection | Specify the MongoDB collection. |
| Query | Specify the query in JSON format to find the specific documents from the database. An example query is: *{ "_id": ObjectId("50")}* This query searches for the object with the ID “50”. |
| Update Key | Specify the name of the property that determines which rows in the database to update. For example, *ID*. |
| Field | For Insert and Update operations, a comma-separated list of the fields to be included in the new document |

#### Setting up credentials

Use the following credentials to set up MongoDB connection

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, Users. |
| **Credentials Data** |
| User | Specify the user email address |
| Password | Specify the password for the user account |
| Host | Specify the host name. |
| Database | Specify the database name to connect to. |
| Port | Specify the active port number |
| Nodes with access | Add the Nodes who can access using the credentials and mark the checkbox to select them |

.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
