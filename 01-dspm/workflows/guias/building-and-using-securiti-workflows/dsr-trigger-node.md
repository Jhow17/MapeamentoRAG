---
title: "DSR"
slug: "dsr-trigger-node"
updated: 2025-10-31T14:23:26Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/dsr-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DSR

In Securiti, **Data Subject Rights** module is an automated system that facilitates and streamlines the process of responding to Data Subject Requests (DSRs) from individuals seeking to exercise their rights over their data. Once the DSR request is submitted and created in the DSR workbench, Securiti uses the information in the request to locate matching personal data in your data systems corresponding to the data subject. Securiti then produces a set of subtasks relating to data system owners that they must accomplish to fulfill the data subject’s request.

The DSR Trigger node lets you initiate a Workflow or get triggered within a Workflow when any of the following events occur:

- Approval of either any or a specific DSR request
- Completion of DSR tasks/subtasks
- Publication of a DSR report
- Completion of tasks creation for a DSR request

The **DSR Trigger** node also lets you trigger Workflow when a DSR request is submitted in different ways. For instance, set **Source** in node configuration as “DSP” if you intend to submit a DSR request using an external Form.

Similarly, the node lets you trigger the Workflow at various stages of processing a DSR request. For instance, if the DSR trigger node is set to trigger when the Status is set to Published, the Workflow automatically activates when a DSR report is published.

> [!NOTE]
> **Note**
> 
> You must set your Workflow to run in the automated mode for the DSR trigger node to work automatically. To learn how to run the Workflow in the automated mode, see the [workflow in the automated mode](/v1/docs/workflow-node-execution-modes) section.

#### Example Use case

In this example, we are outlining a Workflow to process erasure requests on the MySQL data system. The Workflow is initiated through the **DSR Trigger** node. The Workflow executes when the data subject submits an Erasure DSR request using an **external form** and the data subject’s identity is **approved**.

Further, the email address collected in the DSR request is passed on to the **MySQL** node to process a delete query that explicitly instructs the removal of the collected email address. Then, the Workflow creates tasks and subtasks against the MySQL data system for the submitted DSR request. Then, using the **MySQL** node, the Workflow checks the count of records that exist in the data system and processes that information in the form of a CSV using the Process CSV node. That processed information is further passed on to the **DSR Sub-Task Attachment** node and attached to the subtask as evidence.

> [!NOTE]
> **Note**
> 
> If the count of records against the data subject’s email returns 0, that means all data of the data subject is deleted successfully.

This use case requires the following 6 Nodes:

- DSR Trigger
- MySQL
- DSR Task
- DSR Sub-Task
- Process CSV
- DSR Sub-Task Attachment

#### DSR Deletion Workflow

1. Add the DSR Trigger node and add a meaningful name such as “Submitting an Erasure Request”. Further, set **Type** “Erasure”, **Source** “DSP” and **Status** “In progress”.

![dsr-trigger.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-560f57f7-1b12-c2c0-ec5d-17b72f2e1ab1.png)
2. Add MySQL node to fetch the email address of the data subject who submitted the DSR request. Write a query to delete the data subject’s email address from the MySQL data system.
3. Further, add the **DSR Task** node to create a task by fetching the DSR ticket ID (DSR request ID) from the DSR Trigger node and Data Source information from the MySQL node respectively.
4. Next, add the DSR Sub-Task to create a subtask against the MySQL data system.
5. Add a MySQL node and write a query to count the number of records that exist against the email address of the data subject and pass on that information to the **Process CSV** node to process it and further add the **DSR Sub-Task Attachment** to attach the processed information to the subtask.
6. Connect the Nodes and execute the Workflow.

![Screenshot_2023-12-13_at_2_56_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2328da47-3a7a-9709-147c-9f0e4f213777.png)
7. Once the Workflow is successfully executed, you can view both table view and JSON response. This is what the success response of the DSR Trigger node looks like:

![Screenshot_2024-01-14_at_3_40_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1817d9da-aa56-621a-fdcf-9a082093c8a7.png)

You can also associate the Workflow in the DSR form to trigger a specific Workflow before accepting the DSR requests.

1. In **Data Subject Rights** choose **Settings > Form Builder** and select the form with which you like to associate the Workflow.
2. In the **Automation** section, mark **Associate with Workflows** and select Workflows you want to associate with the DSR form. For more information, refer to the **External Workflow Trigger** section in [Creating and Publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms)

![associate_worflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-597ef8f0-3f0d-faee-e620-bdbaf830d884.png)

> [!NOTE]
> **Important**
> 
> - Only saved workflows are shown in the list
> - If a Workflow is inactive when the form is triggered, then Securiti raises an alert in the event log with a UI notification that “A DSR request failed to trigger a pre-configured Workflow”
> - The workflows must have **DSR trigger** Nodes.
> 
> Securiti executes this Workflow when you submit a DSR request using the associated form.

#### Node Configuration

To fill up the fields in the DSR Trigger node, look at the table below for details about the properties:

| Parameter | Description |
| --- | --- |
| Name | Specify a suitable name for the node. |
| Execution Mode | Event Mode | Choose this option to set the execution to event based execution. In this mode, the selected events trigger the node. |
| Cron Mode | Choose this option to execute the node periodically on the set interval. |
| Operation | List | Choose this operation to list the available assessments. |
| Page Size | Specify the number of objects to fetch per page. |
| Polling Interval | Specify the minutes/hours for the trigger to work. |
| Unit | Specify the unit of the polling interval i.e. hours or minutes |
| From Date | Specify the date to fetch the records from the selected date to current time, in initial sync. By default, data will be fetched from the very beginning if no starting date is mentioned. |
| Choose this option to trigger the node when a DSR request is submitted using **any** source such as internal or external form. Select one or more DSR types from the menu.The menu shows all system and custom request types defined in the [Request Types page](/v1/docs/configuring-dsr-request-types) of the DSR settings. You can configure these request types at the tenant level, ensuring they apply across all organizations. While you can switch between organizations, the request types remain consistent across all organizations within the same tenant. For more information, see [Configuring DSR request types.](/v1/docs/configuring-dsr-request-types) |
| Type |
| Source | Any | Choose this option to trigger the node when a DSR request is submitted using **any** source such as internal or external form. |
| Internal | Choose this option to trigger the node when a DSR request is submitted using an internal form. |
| DSP | Choose this option to trigger the node when a DSR request is submitted using an external form. |
| Workflow | Choose this option to trigger the node when a DSR request is submitted using another Workflow. |
| Status | In progress | Choose this option to trigger the node on approval of either any or a specific DSR request. |
| Completed | Choose this option to trigger the node once DSR tasks are completed. |
| Published | Choose this option to trigger the node once the DSR report is published. |
| Task Creation Completed | Choose this option to trigger the node once tasks are created against the submitted DSR request. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
