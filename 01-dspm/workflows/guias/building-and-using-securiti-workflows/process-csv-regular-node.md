---
title: "Process CSV"
slug: "process-csv-regular-node"
updated: 2025-10-30T19:07:18Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/process-csv-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Process CSV

In Securiti, the Process CSV node lets you create (produce, produce(Split by Size)) a CSV file from the data of the preceding node or utilize (consume) that data for several purposes. Its primary role is to take input data, often in a non-CSV format, and convert it into a structured CSV format.

Refer to the [Node configuration section](/v1/docs/process-csv) to understand the node parameters and descriptions.

#### Example use case

We are creating a sample Workflow that fetches a list of all the assets (data systems). This Workflow use case involves a technical process for handling a large list of data systems and creating separate CSV files making the data more manageable and organized for further analysis or use.

In the first step, the Asset node retrieves a comprehensive list of assets, which may include a large number of data systems. To manage this extensive list, use the Produce (Split by Size) operation to divide the CSV files into smaller, manageable files based on the defined file size.

> [!NOTE]
> **Note**
> 
> - The file size must be between 10 KB and 5120 KB.
> - The created file may not match the exact defined size but is approximately the same.

The following Nodes are used in this Workflow:

1. Assets Node
2. Process CSV

#### Creating CSV files for Assets

1. Create an Asset node and set the operation as List. Refer to the [Asset node](/v1/docs/asset) for details.
2. Add the Process CSV node and use the “Produce (Split by Size)” operation to produce CSV based on the defined file size. Provide a meaningful name for the CSV file along with other parameters.

![Process-CSV-HC-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8af5705a-0bb5-72fe-6bfd-16d76d04a657.png)
3. Connect the Nodes and execute the Workflow.

![Process-CSV-HC-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab4beef1-e964-b00e-9d5a-f39c2f7e5f96.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

> [!NOTE]
> **Note**
> 
> The **Process CSV** node outputs files in **US-ASCII** encoding by default.

![Process-CSV-HC-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9c25f0c7-5652-c168-e315-e62708b16667.png)

#### Node configuration

| Parameters |
| --- |
| Operation | Consume | Specify this option to consume a CSV file within a Workflow. |
| Produce | Specify this option to produce a CSV file based on the output from the previous node. |
| Produce (Split by Size) | Specify this option to produce a CSV file based on defined size and the output from the previous node. |
| Property Name | Specify the name of the binary property that holds the data. |
| File name | Specify the name of the file to produce as CSV. |
| Aggregate | Enable to combine all input data into a singe CSV file. |
| Data Expression | Specify the data expression to construct CSV rows. |
| Max File Size | Specify the file size for the output CSV files. |
| Delimiter | Specify the delimiter between elements. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
