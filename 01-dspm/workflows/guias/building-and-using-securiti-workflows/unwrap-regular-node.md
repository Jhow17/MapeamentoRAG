---
title: "Unwrap"
slug: "unwrap-regular-node"
updated: 2025-10-30T19:08:57Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/unwrap-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Unwrap

The Unwrap node in Securiti Workflow automation module simplifies incoming data by converting a complex object containing a list of items into a flat list. This transformation aids in data normalization, simplification, and integration with other systems. It is particularly useful for iterating through individual items, enhancing data readability, and improving Workflow efficiency.

Refer to the [Node Configuration section](/v1/docs/unwrap) to understand the node parameters and description.

#### Example use case

As an example, we are creating a Workflow that fetches a list of users using the **HTTP request** node. From the output of the HTTP request node, the field “data” is an object that contains all the details of the user. This object is converted into a list using the **Unwrap node** and the names of the fields are renamed using the **Rename Keys** node.

The Unwrap node makes the data manipulation easy so that an object can be converted into a list to identify the fields that need to be renamed. The renamed keys are then populated in a CSV file.

The following Nodes are used in this Workflow:

1. [HTTP Request Node](/v1/docs/http-request)
2. Unwrap Node
3. [Rename Keys Node](/v1/docs/rename-keys)
4. [Process CSV Node](/v1/docs/process-csv)

#### Converting user’s data from object to list to populate CSV

1. Use the HTTP Request node to fetch the list of all the users. See the HTTP Request node documentation to understand the node working and parameters. Here is how the **data** object looks like in the response:

![HTTP-result.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9714dfe4-93f8-8316-af12-95d7c3efea26.png)
2. Add the Unwrap node with the key value set to **data** to convert the object response into a list of items as shown below.

![Unwrap-parameters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d5783c0-4a88-139b-9140-21efc3370736.png)
3. Add the Rename Keys node to rename the value of the fields from the list of fields. In this case, the values being renamed are *first_name*, *middle_name* and *last_name*.
4. Add the Process CSV node to populated the renamed fields into a CSV file.
5. Connect the Nodes and execute the Workflow:

![unwrap-wf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60aba50c-5831-0da9-1541-b5724138fe4d.png)
6. Once the Workflow is executed, you can view the response in both JSON and table view. Here is how the object looks after being unwrapped.

![Unwrap-result.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e03f6be-f79a-43e2-fba8-7874bd66e1ed.png)

#### Node configurations

| Parameters |
| --- |
| Configure Expression | Enable this toggle if you want to configure an expression. Disabling the toggle means the data from the preceding node will be used. |
| Key | Specify the key name in case the data from the preceding node is being used. |
| Expression | Specify the data expression for the object that needs to be converted to list format. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
