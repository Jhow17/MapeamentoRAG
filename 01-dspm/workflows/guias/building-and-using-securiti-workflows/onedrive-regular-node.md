---
title: "OneDrive"
slug: "onedrive-regular-node"
updated: 2025-10-30T19:06:37Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/onedrive-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# OneDrive

OneDrive is the Microsoft cloud service that lets you store and protect your files, share them with others, and get to them from anywhere on all your devices. Microsoft OneDrive node in Securiti’s workflows module helps you automate work in Microsoft OneDrive, and integrate Microsoft OneDrive with other applications. The node provides support for a wide range of Microsoft OneDrive features, including creating, updating, deleting, and getting files, and folders.Sends data to OneDrive

Refer to the [Node configurations section](/v1/docs/creating-a-data-labeling-policy-for-microsoft-365-onedrive) to understand the node working and properties.

#### Example use case

#### Example use case

As an example use case, let's create a Workflow that compresses the binary files into zip format and uploads them on OneDrive. The process initiates with an HTTP request node, tasked with retrieving a comprehensive list of users. Following this initial data gathering, the Workflow progresses to a Spreadsheet file node, where the acquired user information is systematically compiled into a binary file. The output of this node is then passed on to the Zip node that compresses the data into a zip file and subsequently uploads it to OneDrive.

The following Nodes are covered in this Workflow:

1. HTTP Request Node
2. Spreadsheet File Node
3. Zip Node
4. OneDrive Node

#### Uploading the compressed binary file on OneDrive

1. Start creating the Workflow by adding an HTTP Request Node. This node fetches the list of all the users via a Rest API call.
2. Add the Spreadsheet File node to write the data into a binary file.
3. The Workflow then goes to the Zip node to compress the Binary file into a zip file.
4. Add the OneDrive node to upload the file on OneDrive.
5. Connect the Nodes and execute the Workflow.
6. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Specify the data source name. See the OneDrive connector documentation to understand how to configure a data system. |
| User | Select the user from the dropdown in case the Load all users toggle is enabled. Otherwise, add the email address of the user. |
| Load all users | Enable this toggle to load all the users against the selected datasource. If disabled, add the user email address in the User field. |
| Resource | The type of resource to operate on - File - Folder |
| Operation | The operation to perform on the resource |
| Create | Create a new folder |
| Upload | Upload a new file. The maximum file size allowed for uploading via the node is 100 MB. |
| Download | Download an existing file. The maximum file size allowed for downloading via the node is 100 MB. |
| Delete | Delete an existing file or folder |
| Move | Change the location of a file or folder |
| Copy | Create a copy of a file or folder |
| Path | The path to the file for upload, download, and delete operations |
| Source path | The current path of the file or folder for move operations |
| Destination Path | The destination path of the file or folder for move operations |
| Parent Directory | For Folder Create operations, the directory in which to create the folder |
| Folder Name | For Folder Create operations, the name of the new folder |
| Property Name | The name of the binary property to which to write the data of the read file for upload and download operations |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
