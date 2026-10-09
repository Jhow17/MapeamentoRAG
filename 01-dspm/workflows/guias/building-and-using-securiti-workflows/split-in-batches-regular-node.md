---
title: "Split In Batches"
slug: "split-in-batches-regular-node"
updated: 2025-10-30T19:08:26Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/split-in-batches-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Split In Batches

The Split in batches node basically splits the data into smaller batches as per definition and then sends the defined batch on each iteration. You can set the batch size as per your requirement, along with enabling the reset option to re-initialize the current output.

This node is typically used where the output is large and the smaller batch sizes are required. For example, for an API request or a large dataset that fetches a huge amount of output data, the Split in Batches node can break up the output into smaller chunks. It is a valuable tool for businesses looking to streamline their processes, improve efficiency, and manage tasks involving a large volume of items or data. It helps break down complex workflows into manageable chunks, making it easier to track progress, troubleshoot issues, and optimise operations.

Refer to the [Node configuration section](/v1/docs/split-in-batches) for more information about the node properties and description.

#### Example use case

We are creating a sample Workflow that fetches a list of all the assets (data systems). This Workflow use case involves a technical process for handling a large list of data systems and creating separate CSV files for groups of 10 data systems, making the data more manageable and organized for further analysis or use.

In the first step, the **Asset** node is used to retrieve a list of all the assets. This list can be extensive and may contain a substantial number of data systems.

Use the **Split in Batches** node to split this large list into smaller, manageable batches. It divides the list into smaller groups, with each group containing exactly 10 data systems.

Once the list of data systems has been split into batches of 10, the next step is to process each batch individually. The **Process CSV** node indicates a technical operation or module responsible for generating CSV files for each batch of data systems. This process involves iterating through each batch, formatting the data as required, and saving it as a separate CSV file. The output of this step will be a set of CSV files, each containing information about 10 data systems.

The following Nodes are used in this Workflow:

1. Assets Node
2. Split in Batches Node
3. Process CSV

#### Splitting large datasets into smaller batches for processing

1. Create an Asset node and set the operation as List. Refer to the [Asset node](/v1/docs/asset) for details.
2. Add the Split in batches node and set the batch size to 10.

![split-in-batches-prop.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58431667-5fd5-d8ff-904e-c14f40368077.png)
3. Add the Process CSV and use the **Produce** operation to produce CSV. Provide a meaningful name for the CSV file. Refer to the [Process CSV](/v1/docs/process-csv) node reference for details.
4. Connect the Nodes and execute the Workflow.

![process-csv-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c9d839f8-7528-d46b-42f3-b43c05d3641a.png)
5. Once the Workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

![split-in-batches-output.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-30a91ae2-8b73-e54d-c2a3-0d2e7a805eba.png)

#### Node Configuration

| Parameters |
| --- |
| Batch Size | Specify the number of items to return with each cell. For example, If the value is set to be 10, then the result will populate 10 values per iteration. |
| Options | Reset | Enable this option to re-initialize the current output. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
