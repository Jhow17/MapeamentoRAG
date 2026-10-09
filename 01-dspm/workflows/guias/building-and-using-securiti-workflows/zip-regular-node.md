---
title: "Zip"
slug: "zip-regular-node"
updated: 2025-10-30T19:09:21Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/zip-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Zip

A zip node in Securiti's workflows module compresses into or extracts from a zip file. In a Workflow, this functionality might be useful for bundling multiple files or data sets together, reducing file size, and making it more convenient for storage or transmission. Similarly, extraction is beneficial for tasks that require accessing individual files from a compressed archive. For example, if data needs to be processed or analyzed individually, extracting it from a zip file may be a necessary step within a Workflow.

Refer to the [Node Configurations section](/v1/docs/zip) to understand the node working and properties.

#### Example use case

As an example use case, let's create a Workflow that compresses the binary files into zip format and uploads them on Dropbox. The process initiates with an HTTP request node, tasked with retrieving a comprehensive list of users. Following this initial data gathering, the Workflow progresses to a Spreadsheet file node, where the acquired user information is systematically compiled into a binary file. The output of this node is then passed on to the Zip node that compresses the data into a zip file and subsequently uploads it to dropbox.

The following Nodes are covered in this Workflow:

1. [HTTP Request Node](/v1/docs/http-request)
2. [Spreadsheet File Node](/v1/docs/spreadsheet-file)
3. Zip Node
4. [Dropbox Node](/v1/docs/dropbox)

#### Uploading the compressed binary file on Dropbox

1. Start creating the Workflow by adding an HTTP Request Node. This node fetches the list of all the users via a Rest API call.
2. Add the Spreadsheet File node to write the data into a binary file.
3. The Workflow then goes to the Zip node to compress the Binary file into a zip file. Refer to the image below to understand the parameters of the Zip node.

![Screenshot_2023-12-11_at_11_47_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c9931216-3019-4da1-f03a-10cb940b226e.png)
4. Add the Dropbox node to upload the file on Dropbox. Connect the Nodes and execute the Workflow.

![Screenshot_2023-12-11_at_11_44_19_PM_3_31_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f30d35a-d47f-22ef-3bea-bea8cb5f9a9e(1).png)
5. Once the Workflow is successfully executed, you can view both table view and JSON response.

![Screenshot_2023-12-11_at_11_47_11_PM_3_31_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6aea9eec-5c44-6c5e-66f9-b14044e38224.png)

#### Node configurations

| Parameters |
| --- |
| Operation | Compress | Choose this option if you want to compress file(s) into a zip format. |
| Extract | Choose this option if you want to extract the content of a zipped file. |
| Property Name | Specify the property name that holds the file data to compress or extract. For example, data. |
| Consolidate | Enable this toggle to create a single zip file against all the files provided as node input. If disabled, a separate zip file is created against each file provided as node input. |
| File Name | Specify the name of the compressed zip file. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
