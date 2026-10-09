---
title: "Slack"
slug: "slack-regular-node"
updated: 2025-10-30T19:08:15Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/slack-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Slack

Slack is a communication and collaboration tool for teams to collaborate. It is an extensive communication tool used massively around the world. In Workflow automation, the Slack node enables Slack’s integration for enhanced productivity and streamlining communication within teams.

Using the Slack node in a Workflow, typically the following actions can be performed:

- **Create or Invite to a Channel:** You can create a new channel or invite users to an existing channel.
- **Send a Message to a Channel or User:** Send a message to a channel or directly to a user.
- **Upload a File to a channel or direct message:** Upload a file in a channel communication or in a direct communication with a user.

In a Workflow, the Slack node can be used to send notifications, manage tasks, automatically share data reports, analytics, or dashboard updates in Slack channels to keep the team informed or capture leads from various sources (website forms, chatbots, etc.) and instantly notify the sales team for follow-up.

Refer to the [Node Configuration](/v1/docs/create-and-configure-the-connecting-app-in-slack) section to understand the node parameters and descriptions.

#### Example use case

As an example use case, we are creating a Workflow that gets triggered every time an assessment is published and the relevant people get notified via Slack. A message is generated using the Slack node with the text message that says “An assessment has been published” and the message goes in the Slack channel with every new assessment being published.

This use case uses the following Nodes:

1. Assessment Trigger node
2. Slack node

#### Prerequisites

A Slack datasource must be configured and must be in active state for the slack node to work. To understand the datasource configuration, see the Slack Datastore configuration section.

#### Notify the users via Slack on assessment publishing

1. Add the Assessment Trigger node with the trigger type set to **Publish**, so that every time an assessment gets published, the node is triggered.
2. Add Slack node with the details of the configured data source along with the resources and operation details. In this case, the resource is set to *Message* and the operation is set to *Send to Channel*.

![Screenshot_2023-10-24_at_1_02_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5fb21c7-e07f-2cd8-d424-560488dec8fb.png)
3. Connect the Nodes and execute the Workflow:

![Screenshot_2023-10-23_at_10_37_23_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78bd87eb-5c83-914e-6f35-7e5339a0cd7a.png)
4. On successful execution the node will return a successful response. Here is how the response looks like:

![Screenshot_2023-10-23_at_10_36_56_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9092f77-6322-44bb-ff20-24835d1d5e2d.png)

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Add the datasource name for Slack in Securiti |
| Resource | Message | Choose this option to operate on a message in Slack. |
| Channel | Choose this option to operate on a channel in Slack. |
| File | Choose this option to operate on a file in Slack. |
| Operation | Create | Choose this option to create a channel in Slack. |
| Invite | Choose this option to invite a user to a channel in Slack. |
| Post to Channel | Choose this option to post a message to the specified channel. |
| Direct Message | Choose this option to send a direct message to a user. |
| Send to Channel | Choose this option to send a file to a channel. |
| Send to User | Choose this option to send a file to a user. |
| Name | Specify the name of the channel to be created. For example, *New_Releases* |
| Channel | Specify the channel ID to invite the user to. You can collect this channel ID from the channel information. For example *C04HKJ8HXEF*. |
| User | Specify the ID of the user to operate on |
| Text | Specify the text to send as a message. |
| Attachments | Options for attachments |
| Fallback Text | Plain-text summary of the attachment |
| Text | Text to send |
| Title | Title of the message |
| Title Link | Link of the title |
| Color | Hex code for the color of the line left of text |
| Pretext | Text that appears before the message block |
| Author Name | Name of author |
| Author Link | Link for the author |
| Author Icon | Icon to appear for the user |
| Image URL | URL for the image |
| Thumbnail URL | URL of thumbnail |
| Footer | Text of footer to add |
| Footer Icon | Icon that appears next to footer |
| Timestamp | Message timestamp |
| Fields | Title | Title of the item |
| Value | Value of the item |
| Short | Enable if items can be displayed next to each other |
| Other Options | Reply Thread ID | Provide the ts value of another message to make this one a reply |
| Unfurl Links | Enable to unfurl primarily text-base content |
| Unfurl Media | Enable to unfurl media content |
| Markdown | Enable to use Slack markdown parsing |
| Reply Broadcast | For messages with a Reply Thread ID, enable to make the reply visible to everyone on the channel or conversation |
| Link Names | Enable to find and link channel names and user names |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
