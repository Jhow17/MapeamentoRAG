---
title: "Dropbox"
slug: "dropbox-trigger-node"
updated: 2025-10-31T14:23:23Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/dropbox-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Dropbox

Dropbox is a cloud-based file hosting service that allows users to store, sync, and share files across multiple devices. Users can access their files from anywhere with an internet connection, collaborate on documents in real-time, and benefit from features like version history and file recovery.

Box trigger node gets triggered on any action performed on a file or folder on Box. The trigger is time based and is triggered periodically based on the polling interval selected, for example, 2 hours or 30 minutes.

See the [Node configurations section](/v1/docs/register-an-application-in-dropbox) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow where every time a critical folder is updated on Dropbox data system, the team is notified about the update. The Dropbox trigger node is triggered based on any update on the files mentioned to keep up with the updated data and to not miss out on any crucial updates.

The trigger node checks the Dropbox data system at every polling interval mentioned in the Node Configurations. Following Nodes are used in this Workflow:

1. Dropbox Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Getting alerts based on updates on sensitive files

1. Add the Dropbox trigger node and set the configurations as shown below. Note that the polling interval is the time after which the node checks the specified folder for any updates in the files.

![Screenshot_2024-01-16_at_2_14_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-11c5e091-1859-64a3-6fda-b0378923b89b.png)
2. Add the Slack node to notify the relevant people every time the node is triggered. In this case a message is sent to a channel, notifying the users that a file has been accessed or modified.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-01-16_at_2_16_27_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a78930e3-e214-4903-de30-a33d9180a556.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Specify the data source name. See [Dropbox connector documentation](/v1/docs/activate-the-dropbox-connector-in-securiti) to understand how to configure a data system. |
| User | Select the user from the dropdown against the selected data source. |
| Folder path | Specify the path of the folder to scan for updates, for example, */root/my_folder* |
| Polling Interval | Specify the interval on which the trigger works, for example, *2 minutes, 5 hours etc.* |
| Unit | Specify the unit of the polling interval for example, minutes or hours. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
