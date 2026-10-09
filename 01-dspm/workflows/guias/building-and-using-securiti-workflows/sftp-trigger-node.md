---
title: "SFTP"
slug: "sftp-trigger-node"
updated: 2025-10-30T19:13:34Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/sftp-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# SFTP

An SFTP node in a Workflow automation platform enables secure file transfer operations using the SFTP (Secure File Transfer Protocol). An SFTP trigger node in Workflows module connects to a designated SFTP server and continuously monitors a specified directory. It gets triggered on the specific polling interval and sends the data of the modified files to the subsequent Nodes.

Refer to the [Node configurations section](/v1/docs/acquire-authentication-credentials-in-sftp) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow where a company receives daily sales reports from its distributors via a secure SFTP server. These reports are uploaded at varying times throughout the day.

An SFTP Trigger node is configured to connect to the designated SFTP server and monitor the directory where the sales reports are uploaded on the specified interval for example, 5 hours. The Workflow then integrates with the **Slack node** and sends a notification to a designated channel or specific users. This notification includes the summarized sales data for the latest report, keeping everyone informed without requiring manual report checking.

The following Nodes are used in this Workflow.

1. SFTP Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Getting alerts based on updates on daily reports

1. Add the SFTP trigger node and set the configurations as shown below. Note that the polling interval is the time after which the node checks the specified file for any updates.

![Screenshot_2024-03-19_at_4_32_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-defddbce-943c-7ce0-4fc7-4feea80ae09b.png)
2. Add Slack node to notify the relevant people every time the node is triggered. In this case a message is sent to a channel, notifying the users that a file has been accessed or modified.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-03-19_at_4_34_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-db2ebb02-2087-0886-78bc-a643ede0af67.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Host | Host for the SFTP server |
| Port | Port for the SFTP server |
| User | Username for SFTP authentication |
| Authentication type | - Basic Auth - Key Based Auth |
| Password | For basic authentication, the password |
| Key | For key-based authentication, the key |
| Path | For list operations, the path of the directory |
| Pattern | The filename pattern to match |
| Polling Inerval | Number of units |
| Unit | Type of units: - Minutes - Hours |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
