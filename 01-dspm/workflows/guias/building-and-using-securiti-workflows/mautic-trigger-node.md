---
title: "Mautic"
slug: "mautic-trigger-node"
updated: 2026-02-12T15:24:38Z
published: 2026-02-12T15:24:38Z
canonical: "helpcenter.securiti.ai/mautic-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Mautic

Mautic is an open-source marketing automation platform that provides tools for managing and automating marketing campaigns. Securiti provides a Mautic trigger node in Workflow Automation module that gets triggered based on the events in an ascending or descending order.

Refer to the [Node configurations section](/v1/docs/mautic) to understand the node working and properties.

#### Prerequisites

You must have Mautic credentials set up to use the Mautic node. Refer to the [setting up credentials section](/v1/docs/mautic) for more information.

#### Example use case

In this use case, a business uses Mautic's trigger node to respond to a webhook event, initiating a Workflow that sends real-time notifications to relevant team members on Slack. An external system or service generates a webhook event, such as a user sign-up, a completed form submission, or any other significant interaction. This webhook event is configured to trigger Mautic's webhook trigger node.

The node then connects to the Slack node that is configured to send messages to a specific channel or directly to relevant team members. This use case demonstrates how Mautic's trigger node can seamlessly integrate with external events through webhooks, triggering workflows that enable real-time notifications on Slack.

The following Nodes are used in this Workflow:

1. Mautic Trigger Node
2. [Slack Node](/v1/docs/slack)

#### Real-time event notification with Mautic trigger node and Slack integration

1. Add Mautic trigger that gets triggered on a webhook event to initiate the Workflow.
2. Add Slack node to notify the relevant team via message upon any new event.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-01-30_at_8_14_55_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0176c61-6c84-be0a-8d98-bee6db4c6e8b.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Mautic API credentials | Choose or create credentials to access the Mautic instance |
| Webhooks URLs | Copy the production or test webhook URL onto the clipboard |
| Events | Mautic events to handle |
| Events order | - Ascending order - Descending order |

#### Setting up credentials

Use the following parameters to set up credentials for Mautic:

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| URL | Specify the Mautic URL to access the Mautic API. |
| Username | Specify the username of the data subject's account, for example, john. |
| Password | Specify the password for the user account |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
