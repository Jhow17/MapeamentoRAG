---
title: "Rename Keys"
slug: "rename-keys-regular-node"
updated: 2025-10-30T19:07:37Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/rename-keys-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Rename Keys

The Rename Keys node in a Workflow typically refers to a step or operation in a data transformation or data processing pipeline that allows you to change or modify the names of keys (also known as fields or columns) in a dataset or data structure. This operation is often used when you need to standardize or clean up the names of keys, or when you want to map keys from one naming convention to another.

See the [Node Configuration section](/v1/docs/rename-keys) to understand the node properties and their examples.

#### Example use case

As an example, we are creating a Workflow that takes data from an HTTP request node, rename specific keys in that data, and process it as a CSV file, potentially aggregating the results.

The **HTTP Request node** fetches the data of the users using an API. The next node in the Workflow is the **Unwrap Node** that unwraps the data from the API response to a list format. From that response, the **Rename Keys** renames the details of the user such as “First Name”, “Last Name” etc. This data is then processed in a CSV file using the **Process CSV** node.

Following Nodes are used in the Workflow:

1. HTTP Request Node
2. Unwrap Node
3. Rename Keys Node
4. Process CSV Node

#### Renaming keys from an API response to add to a CSV File

1. Start the Workflow by adding the HTTP request node that uses the Fetch all users API to fetch the list of users along with their details. Refer to the [HTTP Request node](/v1/docs/http-request) for more details.
2. Add the Unwrap node to unwrap the result from the API response to create a list of items. Refer to the [Unwrap node reference](/v1/docs/unwrap) for more details.
3. Next, add the Rename Keys node to rename the data. In this example we are renaming the following fields:

![rename-keys-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84a0a39a-3a15-2cb9-d88e-c88fa6cad90f.png)
  - first_name to First Name
  - middle_name to Middle Name
  - last_name to Last Name
4. Add the [Process CSV node](/v1/docs/process-csv) to process the data into a CSV file for any further data processing. Refer to the process CSV node for more details.
5. Connect the Nodes and execute the Workflow.

![rename-keys-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5a96e14-ced5-e600-7ead-dbae1173edd4.png)
6. Upon successful execution, the Rename Keys Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response.

![rename-keys-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5acb3ce3-ed13-adf8-b6a1-e8fff7c671cd.png)

#### Node Configuration

| Parameters |
| --- |
| Current Key Name | Specify the current name of the key. You can also define deep keys using dot notation, for example "level1.level2.currentKey" |
| New Key Name | Specify the new name for the key. You can also define deep keys using dot notation, for example "level1.level2.currentKey" |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
