---
title: "External Event"
slug: "external-event-trigger-node"
updated: 2025-10-31T14:23:33Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/external-event-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# External Event

An External Event Trigger node in a Workflow automation platform acts as a "listener" that waits for specific events or signals from outside the Workflow itself. The main purpose of an External Event Trigger node is to start a Workflow in response to a specific external event.

The node establishes a connection or listening mechanism to receive signals or data from an external system or application via webhooks. Webhooks are configured to respond to a specific webhook URL. When a POST request hits that URL, it triggers the Workflow.

See the [Node configurations section](/v1/docs/external-event) to understand the node working and properties.

#### Prerequisites

You must use webhooks URLs to use this node with an external application. See the [Managing webhooks URLs section](/v1/doc/managing-webhook-urls) to understand how to manage webhook URLs in Securiti.

#### Example use case

As an example, let’s consider a Workflow where you want to monitor a shared Box folder where the team collaborates on important documents. Any time a new file is uploaded or an existing file is modified, you want key team members notified on a Slack channel.

This use case requires enabling webhooks in the Box data system. The webhook link is then copied and added to the node configuration of the external trigger event node so that on every event, the node gets executed.

The following Nodes are used in this use case:

1. External Event Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Getting real time updates for efficient team collaboration

1. Add the external trigger node by adding an appropriate name and the webhook URL that listens to the events on the Box data system.

![Screenshot_2024-04-02_at_5_07_29_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-073c394a-5bdd-db76-7db0-7519edc97eb1.png)
2. Add a Slack node to notify the users about the updated event.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-04-01_at_10_30_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b979161-ded9-e5fc-f17d-9e1b78d46f69.png)
4. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Name | Specify the name of the trigger. It is an optional field. |
| Webhook | The webhook configured in Securiti |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
