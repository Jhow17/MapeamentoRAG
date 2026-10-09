---
title: "DSR Sub-Task"
slug: "dsr-sub-task-regular-node"
updated: 2026-02-12T06:05:33Z
published: 2026-02-12T06:05:33Z
canonical: "helpcenter.securiti.ai/dsr-sub-task-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DSR Sub-Task

In the Data Subject Rights module, Securiti simplifies processing DSR requests by breaking them down into a series of subtasks that you assign to the team members with the specialized knowledge to accomplish them. When Securiti generates a DSR request, it initially assigns its subtasks to the primary owners and co-owners of each data system for which it creates the tasks. Data system owners can delegate their subtasks by reassigning them to others inside and outside your organization. Securiti admins and operators can also reassign subtasks. Each subtask fulfills part of the requirement by checking for the data subject’s data within a specific sector of your data storage, and if found, providing copies of that data.

The DSR subtask node lets you perform key operations such as creating, listing, deleting, and updating subtasks. Using this node, you can get subtask owners' information or re-assign subtasks to different owners.

- **Creating a subtask**: You can create a subtask by specifying the Parent Task ID of the task to which the subtask belongs, the title of the subtask, and the DSR request type for which you are creating the subtask.
- **Listing subtasks:** You can list/view all subtasks created for a particular DSR task. To list tasks, you must specify the Parent Task ID.
- **Delete a subtask:** You can delete the subtask using the subtask ID.
- **Fetch subtask owners:** You can also fetch the subtask owners' details by specifying the subtask ID. By default, the subtask owners are the primary owners or co-owners of data systems containing the data subject's data.
- **Add subtask owners:** You can assign subtasks to other organization members or default owners. To add subtask owners, you must specify the subtask ID.
- **Remove subtask owner:** You can also remove the subtask owner by specifying the subtask ID and owner’s email address.

#### Example use case

As an example use case, we are creating a workflow that processes and accesses the user’s data that resides in an unmonitored data system. Unmonitored data systems are the data systems that Securiti does not connect with and has no visibility into. You define these data systems as placeholders so that Securiti can alert subtask owners to check them for personal data when DSR requests come in.

The workflow generates tasks and subtasks for an unmonitored data system when an access request is submitted by the data subject. The workflow utilizes an **HTTP Request** node to retrieve the data subject's information using a POST API endpoint. Subsequently, a **Process CSV** component processes the fetched information in the form of a CSV file and attaches the resulting CSV to the subtask.

This use case requires the following 6 nodes:

- [DSR Trigger](/v1/docs/trigger-nodes-dsr)
- [DSR Task](/v1/docs/dsr-task)
- DSR Sub-Task
- HTTP Request
- [Process CSV](/v1/docs/process-csv)
- DSR Sub-Task Attachment

#### Automated Workflow for unmonitored data systems handling access requests

1. Begin the Workflow by adding the **DSR Trigger** node to initiate the workflow on submission of a DSR request of type access.
2. Add **DSR Task** and **DSR Sub-task** nodes to create tasks and subtasks against the unmonitored data system for submitted requests.

![dsr-sub-task.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-20257082-6bc0-c628-bbda-a3850c760c7c.png)
3. Further, add an HTTP Request node to fetch data subject details using Rest API POST call.
4. The information being fetched is passed onto the **Process CSV** node.
5. Subsequently, add the DSR Sub-Task Attachment node to fetch the processed information and attach it to the subtask.
6. Connect the nodes and execute the workflow.

![Subtask_workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-93f7c16a-ba78-0b90-7f22-42564e4ecd27.png)
7. Once the workflow is successfully executed, you can view the DSR Sub-Task node response, both table view and JSON response.

![subtask_success_response.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e305db2f-2982-6270-20a9-fb59578a19cf.png)

#### Node configurations

| **Parameter** | **Description** |
| --- | --- |
| Operation | Create | Choose this option to create a new subtask. |
| List | Choose this option to list subtasks for a given task. |
| Delete | Choose this option to delete a subtask. |
| Update | Choose this option to update the subtask ID and/or DSR type. > [!NOTE] > **Note** > > For update operation, Securiti currently supports only the "Confirmation" and "Disclosure of Subprocessors" DSR types when updating a subtask via a node. |
| Get Owner(s) | Choose this option to fetch a list of subtask owners. |
| Add Owner(s) | Choose this option to add or reassign subtask ownership. |
| Remove Owner(s) | Choose this option to Remove subtask owners. |
| Parent Task ID | Specify the ID number of the parent task on which to operate, for example 1234. |
| Title | Enter the title of the new subtask to create, for example Outlook Access Request. |
| DSR Type | Select one or more DSR types from the menu.The menu shows all system and custom request types defined in the [Request Types page](/v1/docs/configuring-dsr-request-types) of the DSR settings. You can configure these request types at the tenant level, ensuring they apply across all organizations. While you can switch between organizations, the request types remain consistent across all organizations within the same tenant. For more information, see [Configuring DSR request types](/v1/docs/configuring-dsr-request-types) |
| Subtask ID | Specify the ID number of the subtask to update or delete. |
| Reassign | Enable this option to clear all previous ownership assignments. |
| Default Owner(s) | Enable this option to assign to the default owners, usually the data system owners. |
| Users | Select Securiti users to add or remove as subtask owners. |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
