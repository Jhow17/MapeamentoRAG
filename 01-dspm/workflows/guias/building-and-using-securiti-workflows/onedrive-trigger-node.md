---
title: "OneDrive"
slug: "onedrive-trigger-node"
updated: 2025-10-30T19:13:07Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/onedrive-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# OneDrive

OneDrive is the Microsoft cloud service that lets you store and protect your files, share them with others, and get to them from anywhere on all your devices. Microsoft OneDrive node in Securiti’s workflows module helps you automate work in Microsoft OneDrive, and integrate Microsoft OneDrive with other applications.

The OneDrive trigger node checks the OneDrive account on the defined intervals for any updates or events occurring in the account such as a new file being uploaded to the account or an existing file being deleted from the OneDrive account.

Refer to the [Node configurations section](/v1/docs/creating-a-data-labeling-policy-for-microsoft-365-onedrive) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow where every time a critical folder is updated on OneDrive, the team is notified about the update via Slack. The OneDrive trigger node is triggered based on any update on the files mentioned to keep up with the updated data and to not miss out on any crucial updates. The trigger node checks the OneDrive data system at every polling interval mentioned in the Node Configurations.

The following Nodes are covered in this Workflow:

1. OneDrive Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Getting alerts based on updates on sensitive files on OneDrive

1. Start creating the Workflow by adding the OneDrive trigger node and setting the configurations as per your requirement. Note that the polling interval is the time after which the node checks the specified folder for any updates in the files.
2. Add the Slack node to notify the relevant people every time the node is triggered. In this case a message is sent to a channel, notifying the users that a file has been accessed or modified.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-01-16_at_8_57_02_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a4935e25-62f0-3ff6-812c-201b763c98a2.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Data system instance name in Securiti |
| User | User to perform operation as |
| Drive | Choose from among the users drives to operate on |
| Folder path | Path of the folder to scan |
| Polling Interval | Number of units |
| Unit | Type of unit (hours or minutes) |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
