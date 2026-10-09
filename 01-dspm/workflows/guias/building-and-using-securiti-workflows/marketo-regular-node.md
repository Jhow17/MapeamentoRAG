---
title: "Marketo"
slug: "marketo-regular-node"
updated: 2025-10-31T14:22:05Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/marketo-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Marketo

Marketo is a marketing automation platform that provides a suite of tools and features to help businesses automate and streamline various aspects of their marketing efforts. Using the Marketo node in Securiti’s Workflow Automation module, you can update consent in Marketo.

### Marketo

Updating consent in Marketo allows users to manage their preferences related to email communications, data processing, and other marketing activities. This includes opting in or out of certain types of communications, specifying communication channels, or adjusting the frequency of marketing messages. You can perform the following set of actions using the Marketo node:

- Update call settings in Marketo
- Update subscriptions
- Get lead details in Marketo
- Create a new lead in Marketo

The consent states for the calls or subscriptions using the Marketo Nodes can be Grant, Withdraw or Decline.

Refer to the [Node configuration section](/v1/docs/marketo) to understand the node working and properties.

#### Example use case

As an example, let’s consider a Workflow that focuses on the seamless synchronization of consents collected in the Securiti consent database with the consent statuses of users in Marketo. This Workflow enhances the business value by seamlessly synchronizing consents between the Securiti consent database and Marketo.

In this Workflow, the Consent Management Trigger node serves as the gateway, capturing consents from diverse channels with precision. By employing conditions that filter consents based on processing purpose, consent purpose, and consent status, the Workflow tailors its responses to each consent scenario.

This node acts as a gatekeeper, reevaluating conditions to ensure alignment with the predefined criteria for synchronization with Marketo. Upon meeting these criteria, the Workflow seamlessly progresses to the Marketo node, initiating the update of the Marketo record and marking the consent status as Grant for the respective user.

The following Nodes are used in this Workflow:

- Consent Management Trigger Node
- Marketo Node

#### Aligning Securiti database consents with Marketo user consent statuses

1. Add Consent Management Trigger node and set the type with a meaningful name and provide the type and source as per your requirement.
2. Add Marketo node and based on the trigger results update the consent status in the Marketo datasystem.

![Screenshot_2024-01-30_at_8_32_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5cbe95e7-3477-d9cf-e016-0530af57a7f9.png)
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-01-30_at_8_32_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66841e3e-c6fd-e126-c828-e593fdcdda36.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the Marketo store instance on which the function is being performed. Make sure that the [instance is configured](/v1/docs/activate-the-adobe-marketo-engage-connector-in-securiti). |
| Operation | Specify the operation to perform on Marketo |
| Update Call Settings | Choose this option to update Do Not Call fields for a data subject |
| Update Subscription | Choose this option to update unsubscribed fields for a data subject |
| Get Lead | Choose this option to get lead details for a data subject |
| Create Lead | Choose this option to create a new lead |
| Email Address | Specify the email address of the data subject |
| Consent Status | Specify the consent status to apply to the data subject |
| Grant | The data subject grants consent |
| Withdraw | The data subject withdraws consent |
| Decline | The data subject declines consent |
| Cause | For consent withdrawal and decline operations, specify the cause for consent withdrawal |
| Reason | For consent withdrawal and decline operations, specify the reason for consent withdrawal |
| Fields | For Get Lead operations, specify the fields to fetch. Separate with commas, no spaces |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
