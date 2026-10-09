---
title: "DSR Sub-Task"
slug: "dsr-sub-task-trigger-node"
updated: 2025-10-31T14:23:28Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/dsr-sub-task-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DSR Sub-Task

In the Data Subject Rights module, Securiti streamlines DSR request processing by breaking them into subtasks assigned to team members with the required expertise. When Securiti generates a DSR request, it assigns subtasks to the primary owners and co-owners of each data system. Data system owners, as well as Securiti admins and operators, can reassign these subtasks. Each subtask checks for the data subject's data within a specific data storage sector and, if found, provides copies of that data.

The DSR subtask trigger node is triggered when a subtask of any or a particular request type is created in the DSR workbench.

> [!NOTE]
> Note
> 
> You must set your Workflow to run in the automated mode for the Subtask trigger node to work automatically. This means that the Workflow executes each time Securiti creates a subtask in the DSR workbench.

#### Example Case

As an example use case, let’s create a Workflow where every time Securiti or DSR Owner creates a new subtask in the DSR workbench, a list of users are automatically added to it. This streamlines the process by eliminating the need to manually add users to a subtask.

This use case requires the following two Nodes:

- DSR Sub-task Trigger
- HTTP

#### Adding a list of owners to a subtask

- Add the DSR Sub-Task Trigger node and name it "Subtask Creation." Set the Type to "Any" to trigger the Workflow whenever a subtask is created for any request type supported by Securiti.

![1st_screenshot.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9896182a-60a6-1c18-79dc-23d277d9f5c1.png)
- Add HTTP Request node to fetch subtask ID and further use REST POST API call to add a list of users to the respective subtask.
- Connect the Nodes and execute the Workflow.

![unnamed__3_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab5130fe-ae52-6352-a6a5-37187e62ab65.png)
- Once the Workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

![3rd_screenshot.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8058f7d-7099-f35e-ccc9-65440704dc47.png)

#### Node Configuration

| Parameters |
| --- |
| Name | (Optional) Name of DSR subtask trigger |
| Execution Mode | Event Mode | Choose this option to set the execution to event based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to trigger the node based on the interval set. |
| Operation | List | Choose this operation to list the available assessments. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling Interval | Specify the minutes/hours for the trigger to work |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |
| Type | Choose this option to trigger the node for any subtask created. Select one or more DSR types from the menu.The menu shows all system and custom request types defined in the [Request Types page](/v1/docs/configuring-dsr-request-types) of the DSR settings. You can configure these request types at the tenant level, ensuring they apply across all organizations. While you can switch between organizations, the request types remain consistent across all organizations within the same tenant. For more information, see [Configuring DSR request types.](/v1/docs/configuring-dsr-request-types) |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
