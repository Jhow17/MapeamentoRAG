---
title: "Mattermost"
slug: "mattermost-regular-node"
updated: 2025-10-30T19:06:03Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/mattermost-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Mattermost

Mattermost node in Workflows acts as a bridge between your workflows and the Mattermost communication platform. It allows you to interact with Mattermost channels and users in various ways to enhance collaboration and information sharing within your workflows.

You can configure the node to send messages to specific Mattermost channels or directly to users. Below is the list of operations you can perform using the Mattermost node:

- **Channel:** You can add a user to a channel, create or soft delete a new channel, restore a soft deleted channel, or get statistics of a channel.
- **Message:** You can post a channel to a message or soft delete a post, by marking the post as deleted in the database
- **Users:** You can deactivate a user and revoke all its sessions by archiving its user object against the user ID.

See the [node configuration section](/v1/docs/mattermost) to understand the node working and properties.

#### Prerequisites

You must have valid Mattermost credentials set to use the node. See the [Setting up credentials section](/v1/docs/mattermost).

#### Example use case

As an example, let’s create a use case where a team works with Salesforce that is updated regularly with new leads. Staying up-to-date on these changes is crucial for the team's sales initiatives. These updates are then pushed to the Mattermost communication channel.

An Interval node initiates the Workflow every 45 minutes. This ensures regular checks for database updates. A **Salesforce** node fetches a list of all the leads at the initiated interval. A **function** node checks if any new data is added to Salesforce and subsequently sends the message using the **Mattermost** node to notify the team with the new data points.

This encourages faster decision-making and coordinated action as the team becomes instantly aware of crucial data updates. It also maintains a log of data updates within the channel for future reference. The following Nodes are used in this Workflow:

1. [CRON Trigger Node](/v1/docs/cron)
2. [Salesforce Node](/v1/docs/salesforce)
3. [Function Node](/v1/docs/function)
4. Mattermost Node

#### New Data Alerts for Team Collaboration

1. Add the CRON trigger node to trigger the Workflow on the set time, in this case, 45 minutes.
2. Add a Salesforce node to fetch the data of the leads, followed by a Function node that checks if any new data is present in the Salesforce data system.
3. Add Mattermost node to post a channel to the message notifying the team about the new leads with their IDs.

![Screenshot_2024-04-02_at_5_10_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1663d77-c704-6607-ec9d-31b563343d76.png)
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-04-01_at_4_21_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0efb96bb-f9c4-ca2c-34f0-24b3e21e97de.png)
5. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Credentials | Choose or create credentials to access the Mattermost instance. See the [setting up credentials section](/v1/docs/mattermost). |
| Resource | Specify the resource to operate on: - Channel - Message - User |
| Operation | Specify the operation to perform on the resource. Operations available depend on the resource type |
| Add User | Choose this operation to add a user to a channel |
| Create | Choose this operation to create a new channel |
| Delete | For Channel, soft deletes the channel. For Message, soft deletes the post by marking it as deleted in the database |
| Restore | Choose this operation to restore a soft-deleted channel |
| Statistics | Choose this operation to get statistics for a channel |
| Post | Choose this operation to post a message to a channel |
| Deactivate | Choose this operation to deactivates a user |
| Post ID | Specify the ID number of the post to operate on |
| Channel ID | Specify the ID of the channel to post to |
| Message | Specify the text of the message to send |
| User ID | Specify the ID of the user to operate on |
| Team ID | Specify the ID of the Mattermost team to operate on |
| Display Name | Specify the non-unique UI name for the channel |
| Name | Specify the unique handle for the channel. Used in the channel URL |
| Type | Specify the type of channel to create. Choose either Public or Private |
| Attachments | The attachment to add |
| Fallback Text | Plain-text summary of the attachment |
| Text | Text to send |
| Title | Title of the message |
| Title Link | Link of the title |
| Color | Color of the line left of text |
| Pretext | Text that appears before the message block |
| Author Name | Name of author |
| Author Link | Link for the author |
| Author Icon | Icon to appear for the user |
| Image URL | URL for the image |
| Thumbnail URL | URL of thumbnail |
| Footer | Text of footer to add |
| Footer Icon | Icon that appears next to footer |
| Fields | Title | Title of the item |
| Value | Value of the item |
| Short | Enable if items can be displayed next to each other |
| Other Options | Make Comment | The post ID co comment on |

#### Setting up credentials

To set up credentials for the node, go to the **Account settings** from the Mattermost dashboard and create your access token from the **Security** tab. Add the details as mentioned below:

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| Access Token | Specify the access token generated from the Mattermost account settings. |
| Base URL | Specify the base URL to access the Mattermost functionality. |
| Nodes with access | Add the Nodes who can access using the credentials and mark the checkbox to select them |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
