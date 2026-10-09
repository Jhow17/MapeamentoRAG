---
title: "Box"
slug: "box-trigger-node"
updated: 2025-10-31T14:23:12Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/box-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Box

Box is a cloud-based content management platform that enables users to securely store, share, and collaborate on files. It offers features such as file synchronization, access control, and Workflow automation, making it a valuable tool for businesses to manage their digital content effectively.

Box trigger node gets triggered on any action performed on a file or folder on Box. The trigger is time based and the node checks for updates periodically based on the polling interval selected, for example, 2 hours or 30 minutes.

Refer to the [Node configurations section](/v1/docs/grant-permissions-and-obtain-credentials-in-box) to understand the node working and properties.

#### Example use case

As an example, lets create a Workflow where everytime a critical folder is updated on Box data system, the team is notified about the update. The box trigger node is triggered based on any update on the files mentioned to keep up with the updated data and to not miss out on any crucial updates.

The trigger node checks the Box data system at every polling interval mentioned in the Node Configurations. Following Nodes are used in this Workflow:

1. Box Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Getting alerts based on updates on sensitive files

1. Add the Box trigger node and set the configurations as shown below. Note that the polling interval is the time after which the node checks the specified file for any updates.

![Screenshot_2023-12-12_at_3_53_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5caace36-9898-a2d4-ffe0-7971bbfa0f6f.png)
2. Add Slack node to notify the relevant people every time the node is triggered. In this case a message is sent to a channel, notifying the users that a file has been accessed or modified.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2023-12-12_at_3_44_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b34edbd7-1469-48cf-df49-34f9da408af1.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Specify the datasource name for Box. To understand the data system configuration for Box, see the [box connector documentation](/v1/docs/activate-the-box-securiti-cloud-connector-in-securiti). |
| As User | Specify the username that is performing the action using the node. The users typically appear in the form of a drop down after selecting the active datasource. |
| Folder name | Specify the folder name for the new folder that is being created. Use "root" to operate on root folder |
| Selected folder | Choose the specific folder to operate on. Once you enter a value for Folder Name, Securiti searches for all folders of that name. Select the intended folder from the menu. |
| Polling Interval | Specify the interval on which the trigger works, for example, 2 minutes, 5 hours etc. |
| Unit | Specify the unit of the polling interval for example, minutes or hours. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
