---
title: "Wrap"
slug: "wrap-regular-node"
updated: 2025-10-30T19:09:06Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/wrap-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Wrap

In Workflow Automation, a Wrap node serves the purpose of converting a list of items into an object. This means that it takes a collection of individual items and organizes them into a structured object format. This conversion facilitates more structured and organized data handling, making it easier to process and manipulate the information within the Workflow.

Essentially, the Wrap node streamlines the data from a list into a more coherent and manageable object, enhancing the overall efficiency of the automation process.

Refer to the [Node configuration section](/v1/docs/unwrap) to understand the node properties and descriptions.

#### Example use case

As an example we are creating a use case that fetches a list of assessments and wraps the list of items into an object using the Wrap node. This object is then sent to the Move Binary Data node to create a binary file with the JSON object for further data processing. This data is then added to the database which in this case is MongoDB.

The following Nodes are used in this Workflow:

1. [Assessments Node](/v1/docs/assessment)
2. Wrap Node
3. [Move Binary Node](/v1/docs/move-binary-data)
4. [MongoDB Node](/v1/docs/mongodb)

#### Creating Binary file from list to add to database

1. Start the Workflow by fetching a list of assessments using the Assessments node.
2. Add the Wrap node to convert the list of objects into an object. This object can then further be processed for data storage.

![wrap-properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d092b49-c959-4a88-b56e-16b62b4a4973.png)
3. Add MongoDB Node to write this data into the database.
4. Connect the Nodes and execute the Workflow.

![wrap-wf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-30b1dd86-849a-d9b3-bb26-9f97bd9561bf(1).png)
5. Upon successful execution of the Workflow, you can view the response both in table and JSON format. This is how the success response looks like:

![wrap-result.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6929d367-fea6-6d9f-bb58-9a90d6cb4adb.png)

#### Node configuration

| Parameters |
| --- |
| Key | Provide the title of an object key to hold the results coming from the succeeding node in the form of a JSON object |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
