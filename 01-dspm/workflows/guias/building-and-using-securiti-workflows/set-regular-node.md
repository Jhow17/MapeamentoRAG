---
title: "Set"
slug: "set-regular-node"
updated: 2025-10-30T19:08:04Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/set-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Set

A Set node in Workflow automation, is used to modify and manipulate data within a Workflow. It enables you to assign values to fields or variables, perform data transformation, and apply conditional assignments. This node is useful for data cleanup, enrichment, variable assignment, branching based on conditions, data validation, and expression evaluations.

It's a versatile tool for preparing and customizing data for downstream Workflow steps, allowing for greater flexibility and control in automation processes. In some Workflow automation platforms, Set Nodes can create or modify Workflow-specific variables that can be used in subsequent steps. It's often used to add additional information or metadata to data objects, making it more useful for downstream processes, map data from one field to another, reformat data, or extract specific information from a dataset.

Refer to the [Node Configuration section](/v1/docs/asset) to understand the node parameters and descriptions.

#### Example use case

In this example, we are creating a Workflow designed to retrieve asset details and subsequently format them into a CSV file to align with a specific structure. The Assets node is responsible for fetching asset details based on the provided asset name, while the Set node is employed to assign field names and populate them with data sourced from the Asset node.

Subsequently, these configured values are appended to a CSV file, harmonizing with the structured format of the remaining fields. An important aspect of utilizing the values from the Set node is the selective extraction of only the required fields from the response, hence eliminating the need to retrieve all values and write them into the database file.

The following Nodes are used in this Workflow:

1. [Assets Node](/v1/docs/asset)
2. Set Node
3. [Process CSV Node](/v1/docs/process-csv)

#### Setting the values for structured formatting in a CSV file

1. Start the Workflow by adding an Asset node that fetches the details of an asset. Enter the asset name and fetch the relevant details.

![set-parameters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-20eefbba-b866-767d-7625-e3e68f1f5540.png)
2. Add Set node to set the name and values of the asset details that need to go into the CSV file. Look at the screenshot below to see a number and two string values being set.
3. Add the Process CSV node and set the parameters to write the values into a CSV file.
4. Connect the Nodes and execute the Workflow.

![set-workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bca134e2-357f-46eb-f038-261b23ff59df.png)
5. Upon successful execution of the Workflow, you can view the response both in table and JSON format. This is how the success response looks like:

![set-result.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad910963-258a-998e-a335-61099a3bfa58.png)

#### Node configuration

| Parameters |
| --- |
| Keep Only Set | Turn this toggle on if the values set on this node should be used and the rest of the values are to be removed |
| Values to set | Specify the values to set using the node. |
| Boolean | Name | Specify the name of the property to write the data to. Supports dot notation, for example "data.person[0].name" |
| Value | Turn the toggle on for the boolean value to write in the property. Enable the toggle for true value and disable the toggle for false. |
| Number | Name | Specify the name of the property to write the data to. Supports dot notation, for example "data.person[0].name" |
| Value | Specify the number value to write in the property. |
| String | Name | Specify the name of the property to write string data to. Supports dot notation, for example "data.person[0].name" |
| Value | Specify the string value to write in the property |
| Options | Dot Notation | Enable to use dot notation in property names. For example, "a.b" sets the property "b" underneath "a" so {"a":{"b":value}}. When disabled, it sets {"a.b":value} instead |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
