---
title: "SSE"
slug: "sse-trigger-node"
updated: 2025-10-30T19:13:42Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/sse-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# SSE

An SSE Trigger node enables the client to receive automatic updates from a server using an HTTP connection. The SSE trigger node is used to receive server-sent events and is a trigger node, which means the trigger event starts the Workflow’s next stages.

#### Example use case

As an example, let’s create a use case where an SSE Trigger node is triggered when a server-side event is fired and sends it as a message via Slack node.

By setting up an automated Workflow that captures these events and notifies the relevant team members in real time, the organization can promptly address issues, celebrate successes, or trigger further actions.

The following Nodes are used in this Workflow:

1. SSE Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Real-Time Notification System for Server-Side Events

1. Add the SSE Trigger node and configure it to listen for specific server-side events, such as system errors, warnings, deployment successes, or performance metrics reaching certain thresholds.

![Screenshot_2024-04-24_at_6_19_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2b2fc67d-1496-d4c2-1c96-02b69a46dca4.png)
2. Add the Slack node to notify the user about the triggered server-side event.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-04-24_at_6_18_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-450e1084-e7a6-ffcd-57b3-5bc7f74a7de9.png)
4. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| URL | Specify the URL to receive the events from. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
