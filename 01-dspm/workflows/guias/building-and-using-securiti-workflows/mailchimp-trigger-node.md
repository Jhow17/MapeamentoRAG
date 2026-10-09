---
title: "Mailchimp"
slug: "mailchimp-trigger-node"
updated: 2025-10-30T19:12:51Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/mailchimp-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Mailchimp

Mailchimp is a comprehensive marketing platform offering a range of tools and services for businesses and individuals. Originally recognized for email marketing, Mailchimp has expanded its features to include automation, audience management, analytics, and reporting. Users can create visually appealing emails, set up automated campaigns, and segment audiences for personalized communication.

Mailchimp trigger node in Securiti’s Workflow automation module is typically set up to monitor specific events or changes within a Mailchimp account. These events could include new subscribers, updated subscriber information, campaign activities, etc. The node gets triggered on the specified polling interval and fetches any updates on Mailchimp audience, members or campaigns.

Refer to the [node configurations section](/v1/docs/mailchimp) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow where every time a member is added or updated on Mailchimp data system, the team is notified about the update via Slack channel. The Mailchimp trigger node is triggered based on any update on the audience members to keep up with the updated member list and to not miss out on any crucial updates.

The trigger node checks Mailchimp at every polling interval mentioned in the Node Configurations. Following Nodes are used in this Workflow:

1. Mailchimp Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Getting alerts based on updates in Mailchimp’s members list

1. Add the Mailchimp trigger node and set the configurations as shown below. Note that the polling interval is the time after which the node checks the specified folder for any updates in the members list.
2. Add the Slack node to notify the relevant people every time the node is triggered. In this case a message is sent to a channel, notifying the users that a file has been accessed or modified.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-01-16_at_8_56_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3c7facc3-ac37-d83b-7bf9-b48125ef1a5e.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Data system instance name in Securiti |
| Resource | Mailchimp resource to operate on: - Audience - Members - Campaigns |
| Audience | For resource Members, their audience |
| Polling Interval | Number of units |
| Unit | Type of units: - Minutes - Hours |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
