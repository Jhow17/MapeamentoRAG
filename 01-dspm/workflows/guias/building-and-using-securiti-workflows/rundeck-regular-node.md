---
title: "Rundeck"
slug: "rundeck-regular-node"
updated: 2025-10-30T19:07:45Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/rundeck-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Rundeck

Rundeck plays a central role in workflows by acting as the conductor that orchestrates the entire process. Think of your Workflow as a recipe with multiple steps. Rundeck allows you to define each step as a specific task or action. These tasks can involve running scripts, deploying code, sending notifications, or interacting with other systems (databases, cloud services, etc.).

A Rundeck node performs the following actions in a Workflow:

- Execute a job against the specified job ID.
- Gets metadata of a job against the specified job ID for further analysis.

See the [node configuration section](/v1/docs/rundeck) to understand the node working and properties.

#### Prerequisites

You must configure the Rundeck node with the valid credentials to access the Rundeck API. Refer to the setting up credentials section to understand how to do it.

#### Example use case

As an example, let’s create a Workflow that proactively tracks the critical Rundeck jobs to ensure that the jobs run consistently and within expected timeframes. The Workflow executes at the set time every day using the CRON trigger node, followed by the Rundeck node. The Rundeck node fetches the metadata of the job using the job ID. This metadata then goes to a CSV file for historical tracking.

The following Nodes are used in this Workflow:

1. [Cron Trigger Node](/v1/docs/cron)
2. Rundeck Node
3. [Process CSV Node](/v1/docs/process-csv)

#### Proactive Rundeck job monitoring with daily Workflow Automation

1. Start the Workflow by adding a Cron node that sets the Workflow off on the set time.
2. Add a Rundeck node next to the Cron node that fetches the metadata of the job ID.

![Screenshot_2024-04-15_at_12_07_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00d7104a-1aea-4ad3-ccdc-1324e1233d05.png)
3. Add Process CSV node to process the metadata into a CSV file.
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-04-15_at_12_07_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-94b23548-211c-59ea-0238-d30d6ef6e5b9.png)
5. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Credentials | Choose or create credentials to access the Rundeck instance. Please refer to the [setting up credentials section](/v1/docs/rundeck) to understand how to create credentials. |
| Resource | Job | Specify the Rundeck resource to operate on. |
| Operation | Execute | Choose this operation to execute a job. |
| Get Metadata | Choose this operation to get metadata for a job. |
| Job ID | Specify the ID of the Rundeck job to operate on. |
| Arguments | Name | Optional argument name |
| Value | Optional argument value |

#### Setting up credentials

Use the following parameters to set up credentials for Rundeck.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| URL | Mention the URL to access the Rundeck API. |
| Token | Specify the token value to access the URL. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
