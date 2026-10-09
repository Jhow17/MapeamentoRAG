---
title: "Error"
slug: "error-trigger-node"
updated: 2025-10-30T19:11:50Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/error-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Error

An error trigger node is a specialized component in the Workflows module that acts like a safety net. It is designed to monitor other workflows or Nodes within a Workflow for errors or exceptions. It can also trigger a separate Workflow when an error occurs, providing a mechanism for error handling and recovery.The error trigger node provides the details of the error along with the Workflow details such as Workflow ID and name.

| Parameters |
| --- |
| Error node does not have any parameters. |

> [!NOTE]
> **Important**
> 
> Securiti does not let you activate the Error Trigger Workflow like other workflows with the trigger Nodes.

#### Example use case

As an example use case, let’s create a Workflow where if the Workflow encounters an error (e.g., data format mismatch, server timeout), the error trigger fires. It then connects to the Jira node to automatically create a ticket in your project, capturing details like error message, timestamp, and affected Workflow. Finally, the Slack node kicks in, notifying the relevant assignee (e.g. developer) about the reported bug.

This automates tedious manual bug reporting, saving time and ensuring consistent capture of errors. Assignees receive prompt notifications, facilitating faster bug resolution and improved Workflow stability.

The following Nodes are used in this Workflow:

- Error Trigger Node
- Jira Node
- Slack Node

#### Automated Bug Reporting and Notification Workflow

1. Place the Error Trigger Node. Position it towards the end of your main Workflow, capturing potential errors during execution. See [Linking Workflows for Error Handling](/v1/docs/error)to understand how to configure the error trigger node for a Workflow.
2. Add Jira node and populate the corresponding fields in the Jira node. Choose the issue type, priority, and other relevant settings for your Jira tickets.
3. Add the Slack node to notify the relevant assignee about the Jira ticket being created.
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-02-20_at_2_22_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-630066ec-5489-8730-b6c6-4567b87f50a5.png)
5. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

![Screenshot_2024-02-20_at_2_22_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa3b6a34-f228-963d-280a-52d5237e434a.png)

#### Linking Workflows for Error Handling

Error Trigger node lets you trigger an error Workflow automatically when some other Workflow encounters any kind of error during its execution. This node receives details about the failed Workflow and the encountered errors.

> [!NOTE]
> **Note**
> 
> Error Trigger only triggers when the workflows are executing in the automated mode.

You can create an error Workflow to suit by adding any node(s). For instance, to receive an alert via email when a certain Workflow encounters any error, you can add the Send Email node with the Error Trigger node. You can set this error Workflow (Workflow B) for any of your Workflow (Workflow A). To set a Workflow as the error Workflow for your Workflow:

1. Open **Workflow A**.
2. Select **Workflow B** from the **Error Workflow** menu.
3. Go to Workflows and on the top right of the left menu, click **Settings**.
4. Click **Save** to set Workflow B as the error Workflow for Workflow A as shown below.

![Screen_Shot_2022-10-05_at_4_44_14_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fbd51921-86d4-bcb2-fefe-b1bf9389c661.png)

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
