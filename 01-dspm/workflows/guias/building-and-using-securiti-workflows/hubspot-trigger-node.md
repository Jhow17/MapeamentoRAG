---
title: "HubSpot"
slug: "hubspot-trigger-node"
updated: 2025-10-30T19:12:21Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/hubspot-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# HubSpot

HubSpot is a comprehensive cloud-based platform that provides tools and integrations for marketing, sales, customer service, and CRM (Customer Relationship Management). It helps businesses attract visitors to their websites, convert those visitors into leads, and then nurture and manage those leads into customers.

HubSpot trigger node in a Workflow typically checks the configured data system for updates, periodically. Based on the polling interval, you can fetch the properties of the updated tickets or deals.

Please refer to the [node configurations section](/v1/docs/register-an-application-in-hubspot) to understand the node working and properties.

#### Example use case

As an example, let’s create a Workflow where every time a ticket is added on the Hubspot data system, the team is notified about the update via Slack channel. The Hubspot trigger node is triggered based on any update on the tickets or deals to keep up with the updated list and to not miss out on any crucial updates.

The trigger node checks Hubspot at every polling interval mentioned in the Node Configurations. Following Nodes are used in this Workflow:

1. Hubspot Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Getting alerts based on updates in Hubspot's tickets

1. Add the Hubspot trigger node and set the configurations as shown below. Note that the polling interval is the time after which the node checks the specified folder for any updates in the members list.

![Screenshot_2024-05-07_at_8_20_48_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7bf6efdf-0531-3410-bf15-4cac91e40c47.png)
2. Add the Slack node to notify the relevant people every time the node is triggered. In this case a message is sent to a channel, notifying the users that a file has been accessed or modified.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-05-07_at_8_18_13_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b62e02ee-d084-2649-aa4f-ef19bf57de64.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Data system instance name in Securiti |
| Resource | Mailchimp resource to operate on: - Deal - Ticket |
| Properties | Select the properties of the deal or ticket to fetch in response |
| Polling Interval | Number of units |
| Unit | Type of units: - Minutes - Hours |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
