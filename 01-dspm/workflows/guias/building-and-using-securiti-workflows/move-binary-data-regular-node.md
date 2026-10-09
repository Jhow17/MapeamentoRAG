---
title: "Move Binary Data"
slug: "move-binary-data-regular-node"
updated: 2025-10-30T19:06:21Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/move-binary-data-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Move Binary Data

Move Binary Data node in Securiti is used to move the data between JSON and binary properties. When the node receives binary data as input, it employs a process to interpret and convert this binary information into a JSON format.

Conversely, when the node receives JSON data, it performs the reverse operation. It interprets the JSON structure and converts it back into binary data. By converting binary data to JSON and vice versa, it allows for smooth communication and integration between applications or services that may use different data representations.

Refer to the [Node configurations section](/v1/docs/move-binary-data) to understand the node working and properties.

#### Example use case

As an example we are creating a use case that fetches a list of assessments and wraps the list of items into an object using the Wrap node. This object is then sent to the Move Binary Data node to create a binary file with the JSON object for further data processing. This data is then added to the database which in this case is MongoDB.

The following Nodes are used in this Workflow:

1. [Assessments Node](/v1/docs/assessment)
2. [Wrap Node](/v1/docs/wrap)
3. Move Binary Data Node
4. [Mongo DB Node](/v1/docs/mongodb)

#### Creating Binary file from list to add to database

1. Start the Workflow by fetching a list of assessments using the Assessments node.
2. Add the Wrap node to convert the list of objects into an object. This object can then further be processed for data storage.
3. Add the Move Binary Data node to create a binary file from the JSON data produced as a result of Wrap node. See the screenshot below:

![Screenshot_2024-01-16_at_6_10_14_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f7c2fd3b-6e35-a410-3538-493da7699b5c.png)
4. Add MongoDB Node to write this data into the database. Connect the Nodes and execute the Workflow.

![wrap-wf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-30b1dd86-849a-d9b3-bb26-9f97bd9561bf.png)
5. Upon successful execution of the Workflow, you can view the response both in table and JSON format. This is how the success response looks like:

![Screenshot_2024-01-16_at_6_10_43_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff423ac6-1f9f-7ce3-29a5-7a0aab07ab63.png)

#### Node configurations

| Parameters |
| --- |
| Mode | Binary to JSON | Move data from binary to JSON formats |
| JSON to Binary | Move data from JSON to binary formats |
| Set all Data | For Binary to JSON mode, enable to replace all JSON data with the data retrieved from the binary key. When disabled, the data is written to a single key |
| Convert all Data | For JSON to Binary mode, enable to convert all JSON data to binary. When disabled, only the data of one key is converted |
| Source Key | For Binary to JSON mode, sets the name of the binary key to get the data from. You can also define deep keys using dot notation, for example "level1.level2.currentKey" |
| Destination Key | For JSON to Binary mode, sets the name of the binary key to copy the data to. You can also define deep keys using dot notation, for example "level1.level2.currentKey" |
| Options | File Name | The file name to set |
| Keep Source | Enable to keep the source. When disabled, the source is deleted |
| Mime Type | The mime type to set. Default is the mime type for JSON |
| Use Raw Data | Enable to use data as is. When disabled, data is processed with JSON.stringify |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
