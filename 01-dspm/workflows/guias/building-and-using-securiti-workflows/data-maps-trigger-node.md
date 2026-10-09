---
title: "Data Maps"
slug: "data-maps-trigger-node"
updated: 2025-10-30T19:10:57Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/data-maps-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Data Maps

Securiti's [Data mapping catalog](/document/preview/32723#UUID-aa432a0f-1691-6fef-cb4d-6a3b207fee3f) captures your entire application or process data lifecycle and lets you monitor, manage and maintain all its properties including data elements in use, vendor interactions, Privacy Impact Assessments, and risks. The data maps are used to create a data flow between the data catalog items such as assets, processes, vendors and institutions. You begin with populating your data catalog and creating data flow processes in Securiti to document the internal processes at your organization that involve the collection, processing, storage, and archiving of data subjects' personal data.Using Data Mapping Automation

Using the **Data Maps trigger** node, you can create a Workflow where the data maps node gets triggered on any operation performed on the items in the data catalog. For instance, if the data maps trigger node is set to trigger on the creation action and the subject is set to asset, the Workflow automatically triggers when a new asset is created.

> [!NOTE]
> **Note**
> 
> You must set your Workflow to run in the automated mode for the data maps trigger node to work automatically. To learn about how to run the Workflow in the automated mode, see [workflow in automated mode](/v1/docs/workflow-node-execution-modes) section.

You can then use this node for any further processing on the data once the trigger is activated.

### Example use case

As an example use case, let’s create a Workflow where every time any process is modified in the catalog, you can send an email to the administrator and alert them to the recent changes. This use case requires the following two Nodes:

1. Data Maps trigger node
2. Send email node

#### Prerequisites

You must have a pre-existing process in your inventory for this Workflow. This does not apply in case the trigger type is entity (asset, process, vendor etc) creation.

#### Sending email to the owner on every process update

1. In the Data Maps Trigger node, fill in the fields as per your requirements as shown below:

![data-map-trigger.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be7513f9-dede-7c73-6152-ebe45b937c8a.png)
2. Add the details in the Send email node as per your requirement. Refer to [Send Email node reference](/v1/docs/send-email) for details.
3. Connect the Nodes to execute the Workflow:

![Data-Maps-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99916525-1dbd-99b5-de2e-42191719c1ab.png)
4. Execute the Workflow and on any event trigger, the Workflow node provides a successful response. Once the Workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

![Data-Maps-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2218133-96c8-b5d9-b41a-2e3e01c6eb04.png)
5. From the response, you can view the type of update that has occurred in the data map catalog. You can also view which item has triggered the event.

> [!NOTE]
> **Note**
> 
> After making the Workflow active, triggers are set to identify changes in the process, assets, or vendors. If multiple catalog items undergo changes, all the changes are captured and addressed for the items sequentially.

### Parameters

| Parameters | Description |
| --- | --- |
| Name | Specify the name of the node |
| Type | Any | The node is triggered on modification in any of the entity in the catalog |
| Asset | The node is triggered on modification in any of the assets |
| Process | The node is triggered on modification in any of the processes |
| Vendor | The node is triggered on modification in any of the vendors |
| Institution | The node is triggered on modification in any of the institutions |
| Event | Any | The node is triggered on any type of modification in the selected catalog item |
| Create | The node is triggered on creation of a new selected catalog item |
| Update | The node is triggered on updating an existing item in the catalog |
| Delete | The node is triggered on deleting the selected catalog item |
| Version Change | The node is triggered on version change in the selected catalog item |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
