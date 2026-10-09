---
title: "AWS SNS"
slug: "aws-sns-trigger-node"
updated: 2025-10-30T19:10:24Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/aws-sns-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# AWS SNS

AWS SNS (Amazon Simple Notification Service) is a cloud-based service within the Amazon Web Services suite. It's designed for mass message delivery and communication between different applications and services. It can send out notifications via various channels including SMS, email, HTTP endpoints, and even mobile push notifications.

The AWS SNS trigger node subscribes to a specific AWS SNS topic within your AWS account.Whenever a message is published to that SNS topic, the trigger node initiates your Workflow.

See the [Node configurations section](/v1/docs/aws-sns) to understand the node working and properties.

#### Prerequisites

You must have valid AWS credentials set to use the node. See the [Setting up credentials section](/v1/docs/aws-sns).

#### Example use case

As an example, let's create a use case where you have an e-commerce system where the customers place orders and you want to streamline the order fulfilment process and send immediate notification when a new order is placed.

You have a topic called *new_orders*, such that whenever a new order is placed, your order system publishes a message to the *new_orders* SNS topic. A Send Email node then sends an email to the relevant customer for the order confirmation. This Workflow eliminates delays in order processing as it's handled the moment an order is placed.

The following Nodes are used in this Workflow:

1. AWS SNS Trigger Node
2. [Send Email Node](/v1/docs/send-email)

#### Real-time order processing with AWS SNS Node

1. Add an AWS SNS trigger node that listens to the topic *new_orders*. Make sure that the credentials are set up.

![Screenshot_2024-04-02_at_5_13_26_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-88cf5a36-4be0-927c-4eac-900c61a62ec6.png)
2. Add Send Email node that sends a confirmation email to the customer for order confirmation.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-04-02_at_5_14_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-551e89f0-9185-b975-8e86-9a7c417234a5.png)
4. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| AWS Credentials | Choose or create credentials to access the AWS instance. Refer to the [setting up credentials section](/v1/docs/aws-sns). |
| Webhooks URLs | Copy the production or test webhook URL onto the clipboard |
| Topic | Specify the AWS SNS topic ID. |

#### Setting up credentials

To set up credentials to use the node, open your AWS Management console and choose Security Credentials from the menu on top right. Create a new **Access key** from there and collect the **Secret Access key**, **Access Key ID** and **Session Token**.

| Parameters |
| --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself |
| Region | Specify the region of your AWS account, for example, us-west. |
| Secret Access Key | Specify the Secret access key, selected from your AWS account. |
| Access Key ID | Specify the Access Key ID, selected from your AWS account. For example, *AKIASLVL6RD3RSJZBERS* |
| Session Token | Specify the session token for your AWS account. This is an optional field. |
| Nodes with access | Add the Nodes who can access using the credentials and mark the checkbox to select them |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
