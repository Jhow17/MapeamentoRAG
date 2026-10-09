---
title: "Zendesk"
slug: "zendesk-regular-node"
updated: 2025-10-30T19:09:17Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/zendesk-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Zendesk

A Zendesk node in Workflows allows you to automate a wide range of actions and integrate Zendesk with other systems within your processes. You can perform the following functions using the Zendesk node:

- Generate new Zendesk tickets triggered by events in other systems or data from your Workflow (e.g., new customer sign-up, critical alert).
- Fetch details about existing Zendesk tickets (status, comments, custom fields, etc.) based on ticket ID.
- Modify ticket properties like status, assignee, priority, or add comments within your Workflow, all without manual agent interaction.
- Delete a ticket against a specific ticket ID.

Refer to the [node configuration section](/v1/docs/zendesk) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow that automates identifying unassigned tickets in Zendesk and notifying the relevant team on Slack. A **Zendesk node** fetches all the tickets from Zendesk. A **Function node** then executes a code that iterates through every ticket fetched by the Zendesk node and checks if the ticket has an assignee field set to empty or null.

Subsequently, the **Slack node** posts a message to a designated channel within your Slack workspace. The message content can include details like ticket ID, title, and a link to the ticket in Zendesk. This Workflow alerts your team about unassigned tickets promptly, ensuring faster handling and customer satisfaction.

The following Nodes are used in this Workflow:

1. [CRON trigger Node](/v1/docs/cron)
2. Zendesk Node
3. [Function Node](/v1/docs/function)
4. [Slack Node](/v1/docs/slack)

#### Zendesk to Slack workflow for unassigned ticket alerts

1. Add A Cron Trigger Node that starts the Workflow on the set time, for example, at 12 pm everyday.
2. Add Zendesk node and fetch all Zendesk tickets using the node.

![Screenshot_2024-04-23_at_4_48_47_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-730a3ce0-b4e0-0939-1d22-6241c5dcabf3.png)
3. Add Function node and write a function to filter out the tickets that do not have an assignee field set.
4. Subsequently, add a Slack node to write a message that notifies the relevant team about the unassigned tickets.
5. Connect the Nodes and execute the Workflow.

![Screenshot_2024-04-23_at_4_54_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c4d656e5-5ff8-5892-30b0-aee1869fdb48.png)
6. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the data system instance name in Securiti. See the connector documentation to understand how to configure the Zendesk connector. |
| Operation | Specify the operation you want to perform using the node. - Create Ticket - Update Ticket - Get Ticket - Get All Tickets - Delete Ticket |
| Description | Specify the ticket description, such as what is the ticket about and other details. |
| Ticket ID | Specify the ID of the ticket to operate on. |
| Ticket Fields | Click **Add Field** to add any of the following fields: |
| Visibility | Choose the visibility of the comment or description such as **Public Reply** or **Private Note** from the menu. |
| Requester | Mention the reporter of the ticket (defaults to the account that enabled authorization). |
| Tags | Specify a list of tag names to apply to the new task separated by commas. |
| Attachment | Specify the name of the binary property from which to read the data. > [!NOTE] > **Note** > > You must add a comment along with the attachment |
| External ID | Specify the external ID you use to link Zendesk Support tickets to local records. |
| Subject | Specify the value of the subject field for the ticket. |
| Recipient | Specify the original recipient email address of the ticket. |
| Type | Specify the ticket type from the following - Question - Incident - Problem - Task |
| Status | Specify the ticket status from the following: - Open - New - Pending - Solved - Closed |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
