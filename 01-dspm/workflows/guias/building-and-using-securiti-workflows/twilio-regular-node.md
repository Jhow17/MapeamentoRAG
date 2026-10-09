---
title: "Twilio"
slug: "twilio-regular-node"
updated: 2025-10-30T19:08:52Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/twilio-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Twilio

Twilio Node in Workflows allows you to interact with Twilio API in applications. Twilio is a cloud communications platform that provides APIs for sending and receiving SMS messages, making voice calls, managing phone numbers etc. Twilio Node simplifies the integration of Twilio services into your applications, making it easier to build communication features into your software.

Refer to the [Node configurations section](/v1/docs/twilio) to understand the Node Configurations and properties.

#### Example use cases

Twilio Nodes can be used in a variety of ways. Here are a few examples of use cases for Twilio.

- **Sending out mass notifications and alerts:**

You can use Twilio node to send notifications and alerts to a predefined list of recipients. In case of a disaster, security breach, or other critical situation, organizations can quickly broadcast messages, provide safety instructions, and keep the community informed via SMS or voice calls. It can also be used to send out notifications in case of a Workflow failure.
- **Sending out reminders:**

You can also use the node to send SMS or voice call reminders for reservations, and meetings. By automating these reminders, you can enhance scheduling efficiency and reduce missed schedules. You can also set reminders for renewing or updating any current applications or softwares.
- **Automate receiving daily reports or data summary**

Using Twilio node in a Workflow, you can automate receiving a daily report for data usage, regular updates, summaries etc. These reports can be initiated at a specific time of the day and you can receive a text message to analyze the summary at the end of a day.
- **SMS Notifications:**

Use Twilio Node to send SMS notifications for account updates, order confirmations, appointment reminders, and shipping status updates etc.

#### Getting alerts via Twilio on every breach incident

In this use case, we are creating a Workflow that is triggered every time a breach incident is created. The [**Breach Management Trigger node**](/v1/docs/breach-management) is triggered and connected to Twilio to alert the user about a breach incident.

1. Add the Breach Management node and set the type to **Incident** and the action to **Created**, so that whenever a breach incident is created, the Workflow is executed.
2. Add the Twilio node with the required configurations and set the resource to **Message** and the operation to **Send**. Provide the **To** and **From** numbers to send the message. Add the message content in the Message box as shown:

![Screenshot_2023-11-07_at_4_42_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6b9dcba-ddca-ccac-4316-433508d3209c.png)
3. Connect the Nodes and execute the Workflow.

![Screenshot_2023-11-07_at_4_15_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-232427cd-0b68-73c2-f334-44e59a94d822.png)
4. Once the Workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Specify the name of the datasource configured for Twilio data system. See the Twilio connector documentation to understand how to configure a data system. |
| Resource | Message | Choose this option to use messaging as the mode of communication for the node. |
| Call | Choose this option to use call as the mode of communication for the node. |
| Operation | Send | Choose this operation to send a message using the node. |
| Make | Choose this operation to make an outbound call using this node. |
| Read | Choose this operation to read the messages or list of calls to and from the specified contacts. |
| Delete | Choose this option to delete the messages or calls using the specific SID. |
| From | Specify the number that initiates the call or message, for example, *+1829475284*. |
| To | Specify the number to which to send a message or call, or the destination phone number to filter calls or messages on, for example, *+1829475284* |
| Message | Specify the message content that needs to be sent. |
| Say | Specify what to say when an outbound call is made using the node. |
| Date filter | Enable this toggle to apply a date filter to fetch the messages or calls for the specific dates. |
| Condition | Before | Choose this option to fetch the messages from before the specified date. |
| After | Choose this option to fetch the messages from after the specified date. |
| On | Choose this option to fetch the messages from the specified date. |
| Between | Choose this option to fetch the messages between the specified dates. You can specify Date 1 and Date 2 to use the dates as the starting and ending point of the period respectively. |
| Date | Specify the date in the format **YYYY-MM-DD** in **GMT**. |
| SID | Specify the unique ID to delete all the messages or calls against the ID. A Twilio Account SID can be found on the Twilio Console dashboard under Account. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
