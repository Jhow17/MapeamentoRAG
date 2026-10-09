---
title: "DSR Sub-Task Attachment"
slug: "dsr-sub-task-attachment-regular-node"
updated: 2026-01-12T06:59:48Z
published: 2026-01-12T06:59:48Z
canonical: "helpcenter.securiti.ai/dsr-sub-task-attachment-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DSR Sub-Task Attachment

Data Subject Rights module is an automated system that facilitates and streamlines the process of responding to Data Subject Requests (DSRs) from individuals seeking to exercise their rights over their data. Once the DSR request is submitted and created in the DSR workbench, Securiti uses the information in the request to locate matching personal data in your data systems corresponding to the data subject. Securiti then produces a set of subtasks relating to data system owners that they must accomplish to fulfill the data subject’s request.

The DSR Sub-Task Attachment node lets you attach a file or a folder containing personal data of the data subject to the subtask created against a particular data system. Subtask attachment can be an image, csv or a pdf file.

#### Example Case

In this example, we create a workflow that fulfills the use case where a DSR access request requires personal information of the data subject from Box. Box is a cloud-based content management platform that enables users to securely store, share, and collaborate on files.

The **DSR Trigger** node initiates the workflow. The workflow executes when the data subject submits an Access DSR request using an internal or external form. To learn more about internal/external DSR forms, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms)

Further, the email address that is collected as a part of the request is passed on to the DSR Task node. Then tasks and subtasks are created against the Box data system for the submitted access request.

Box node returns all personal data residing in a file based on the file details you provided while configuring the box node. The details include email addresses of data subjects along with other details.

Next, the **Spreadsheet File** node reads all data from the Box node, converts into a csv and passes it to the **Function** node. The **Function** node compares the email address of the data subject in the DSR request with the one in the spreadsheet and if the email address exists, it fetches all data against that email address and sends it to the next **Spreadsheet File** node to prepare a csv file.

That CSV file is passed on to the **DSR Subtask Attachment** node which further attaches the csv to the subtask as an evidence. This way you can fetch information of data subject from a Box data system and return it as an attachment to the subtask to fulfill the DSR request.

The following nodes are used in this workflow:

- [Box](/v1/docs/box)
- [DSR Trigger](/v1/docs/dsr)
- [DSR Task](/v1/docs/dsr-task)
- [DSR Sub-Task](/v1/docs/dsr-sub-task)
- [Spreadsheet File](/v1/docs/spreadsheet-file)
- [Function](/v1/docs/function)
- DSR Sub-Task Attachment

#### Prerequisite:

The email address of the data subject must exist in the Box data system.

#### Return personal data records as an attachment for DSR Access Request

1. Add the DSR Trigger node and add a meaningful name such as “Submitting an Access Request”. Further, set **Type** “Access”, **Source** “Any” and **Status** “In progress” so that the node triggers when a data subject submits a DSR request of type Access and Securiti verifies the identity of the data subject in case if DSR is raised using an external DSR form.
2. Further, add the **DSR Task** node to create a task by fetching the DSR ticket ID from the DSR Trigger node and set the **Data Source Name** as an instance of the Box data system.
3. Next, add the **DSR Sub-Task** to create a subtask against Box.
4. Further, add **Box** node and configure it by providing the file details containing personal information records of all data subjects and pass on to the next node.
5. Next, the **SpreadSheet File** node converts the data into a csv and pass it onto the **Function** node.
6. The **Function** node executes code to verify if the data subject's email address matches any record in the data retrieved from the box. If the condition is true, it fetches the data for the data subject and passes it to the **SpreadSheet File** node which further converts the data in a csv format and sends it to the **DSR Subtask Attachment** node.
7. Subsequently, add the **DSR Sub-Task Attachment** node to fetch the processed information and attach it to the subtask.

![Screenshot_2024-02-14_at_11_33_30_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c9a9f863-671b-2ab4-d251-8efc2b9b45d8.png)
8. Connect the nodes and execute the workflow.

![Succes_Workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e131bd38-264f-762a-c1ec-b144d8c6c70a.png)
9. Once the workflow is successfully executed, you can view the DSR Sub-Task Attachment node response, both table view and JSON response.

![Subtask_attachment_result.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ac20ec7-a122-d465-9b8c-ad482e3207ed.png)

#### Node configurations

| Parameters |
| --- |
| Sub-Task ID | The ID number of the sub-task to which to attach the file, for instance 1234. |
| File Name | Specify the file name for the attachment, for instance dsr_results.csv. |
| Property name | Specify the name of the binary property that holds the data. |

> [!NOTE]
> **Note**
> 
> Securiti notifies the subtask owners of the new attachment with:
> 
> - An event in the Securiti audit log.
> - A system notification in the subtask owner’s **Messages&Notifications** list.
> - An email notification.
