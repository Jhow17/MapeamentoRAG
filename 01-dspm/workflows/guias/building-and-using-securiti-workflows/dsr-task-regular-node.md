---
title: "DSR Task"
slug: "dsr-task-regular-node"
updated: 2026-02-12T06:12:28Z
published: 2026-02-12T06:12:28Z
canonical: "helpcenter.securiti.ai/dsr-task-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DSR Task

The DSR Task node lets you perform key operations such as creating, listing, or deleting tasks for a submitted DSR request. DSR tasks are created against data systems containing the data subject's data. The following actions can be performed using the DSR Task node:

- **Creating a task:** You can create a DSR task by specifying the DSR Ticket ID, the Datasource Name against which you need to create the task, and the appropriate title of the task.
- **Listing tasks:** You can list all or some specific tasks created against the DSR request. To list tasks, you must specify the DSR Ticket ID and use a data source filter option to specify whether you want a list of all tasks or tasks associated with a particular data source.
- **Delete a task:** You can delete a DSR task by specifying the Task ID of the task you want to delete.

#### Example Case

In this example, we create a workflow that fulfills the use case where a DSR access request requires a summary of emails from O365 Outlook. O365 Outlook provides a function to query by email address and returns a message digest of all messages where the specified email is a sender or recipient.

The **DSR Trigger** node initiates the workflow. The workflow executes when the data subject submits an Access DSR request using an **internal form**. Further, the email address that is collected as a part of the request is passed on to the DSR Task node. Then tasks and subtasks are created against the Outlook data system for the submitted access request.

Further, the email address is passed to the Outlook node which queries emails by the submitted email address and returns a summary of all emails where the specified email address is the sender or the receiver. The Process CSV node processes this information as a CSV, then passes it on to the DSR Sub-Task Attachment node, attaching it to the subtask as an evidence.

The following nodes are used in this workflow:

- DSR Trigger
- DSR Task
- DSR Sub-Task
- Outlook
- Process CSV
- DSR Sub-task Attachment

#### Prerequisite

The email address of the data subject must exist in the Outlook data system.

#### Outlook Email Summary for DSR Access Request

1. Add the DSR Trigger node and add a meaningful name such as “Submitting an Access Request”. Further, set **Type** “Access”, **Source** “Internal” and **Status** “In progress” so that the node triggers when a data subject submits a DSR request of type Access and Securiti verifies the identity of the data subject.
2. Further, add the **DSR Task** node to create a task by fetching the DSR ticket ID from the DSR Trigger node and setting the **Data Source Name** as an instance of the Outlook data system.

![DSR_Task_config.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3cf29a1c-4f47-b726-48d1-398860785611.png)
3. Next, add the DSR Sub-Task to create a subtask against Outlook.
4. Add **Outlook** node to return the email summary for the email address of the data subject who submitted the DSR request. This information is then passed on to the **Process CSV** node for processing. Subsequently, the **DSR Sub-Task Attachment** node is employed to fetch the processed information and attach it to the subtask.
5. Connect the nodes and execute the workflow.

![OUtlook_workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-44b5e885-1186-0f3c-f8ee-f9952f2dbdd2.png)
6. Once the workflow is successfully executed, you can view both table view and JSON response. This is what the success response of the DSR Task node looks like:

![DSR_Task_success_response.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-af99a2fb-a4ea-ea6d-9b25-e886c74a6d5b.png)

#### Node Configuration

To fill up the fields in the DSR Task node, look at the table below for details about the properties:

| **Parameters** | Description |
| --- | --- |
| Operation | Create | Choose this option to create a DSR task. |
| List | Choose this option to view a list of all DSR tasks against DSR requests. |
| Delete | Choose this option to delete a DSR Task. |
| DSR Ticket ID | Specify the DSR request ID of the submitted request, for example 1234. |
| DataSource Name | Choose the data source that contains the personal data of the data subject for which you intend to create the task. |
| Title | Specify the title or name of the DSR task, for example, DSR Task for Outlook data system. |
| DataSource Filter | Enable this to apply a data source filter for listing tasks against specific data systems. |
| Task ID | Specify the task ID of the task you want to delete, for example 6534. |
