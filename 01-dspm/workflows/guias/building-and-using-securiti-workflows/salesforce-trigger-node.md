---
title: "Salesforce"
slug: "salesforce-trigger-node"
updated: 2025-10-30T19:13:27Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/salesforce-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Salesforce

Salesforce is a cloud-based platform that helps businesses manage their relationships and interactions with customers and prospects. It provides a comprehensive suite of tools and functionalities designed to streamline sales, marketing, customer service, and collaboration efforts within an organization.

A Salesforce trigger node acts like an attentive listener within your Workflow. It constantly monitors your Salesforce environment on a regular schedule you define (e.g., every 10 minutes, every hour). You have to provide the following information to configure the node:

- The type of Salesforce object to monitor (e.g., Account, Lead, Case, Opportunity, or custom objects).
- .Polling Interval i.e How frequently to check Salesforce (e.g., every 5 minutes).
- What to look for, such as records created or updated since the last check, or records matching specific conditions (e.g., high-priority support cases).

Refer to the [Node configurations section](/v1/docs/register-a-connecting-app-in-salesforce) to understand the node working and properties.

#### Example use case

As an example, let's create a Workflow where the Salesforce trigger node is set to poll the Lead object with a daily interval. Each day, the node queries Salesforce for leads created or updated within the last 24 hours. If new or updated leads are found, the trigger node sends the relevant lead information to the rest of the Process CSV node.

This node generates a comprehensive report of the leads and then sends the daily lead summary report to the relevant sales team.

This Workflow uses the following Nodes:

1. Salesforce Trigger Node
2. [Process CSV Node](/v1/docs/process-csv)
3. [Send Email Node](/v1/docs/send-email)

#### Generating daily lead summary report

1. Add the Salesforce Trigger node and set the polling interval to 24 hours. Set the **Object** to lead and provide the fields required such as email address, ID, phone number, etc.

![Screenshot_2024-03-05_at_7_13_47_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2966966-7789-4ee8-007c-09748c7a1914.png)
2. Add the Process CSV node to generate a report of the collected data, followed by the Send Email node. Set the send email node such that the email is sent to the Sales team.
3. Connect the Nodes and execute the Workflow.

![Screenshot_2024-03-05_at_7_13_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bad094e8-c5e2-d545-38b0-8ae59b8830a1.png)
4. Execute the Workflow and on any event trigger, the Workflow node provides a successful response. Once the Workflow is successfully executed, you can view both table view and JSON response.

![Screenshot_2024-03-05_at_7_12_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-20df7467-738a-5caf-6a19-22648fbe6540.png)

#### Node configurations

| Parameters |
| --- |
| Data Source Name | Data system instance name in Securiti |
| Object | Salesforce object to operate on |
| Fields | Object fields to fetch. Separate with commas, no spaces |
| Polling Interval | Number of units |
| Unit | Type of units: - Minutes - Hours |
| Page Size | Specify the number of objects to fetch per page. |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
