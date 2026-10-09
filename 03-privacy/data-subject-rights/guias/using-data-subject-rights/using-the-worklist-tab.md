---
title: "Using the worklist tab"
slug: "using-the-worklist-tab"
updated: 2026-09-21T10:57:18Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/using-the-worklist-tab"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Using the worklist tab

Of the tabs in the DSR Workbench, the worklist tab deserves special attention. This tab has several features that you use to process subtasks.

### Tasks list

The Tasks list shows you all of the tasks belonging to the current DSR request. The header at the top of the list shows you the ID number and type of the currently selected DSR request. Click a task on the list to view its subtasks.

![Data Subject Rights dashboard showing tasks and data element discovery for a request.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.33.38 AM.png)

For sequential DSR requests, you can also filter tasks and subtasks by rule and level. For more information, see [Processing sequential DSR requests in the workbench](/latest/docs/configuring-sequential-task-processing-in-dsr-forms#processing-sequential-dsr-requests-in-the-workbench).

### Subtasks list

The subtasks list shows you all of the subtasks, both open and completed, belonging to the currently selected task.

You can also create subtasks directly within the DSR workbench. To create a Subtask:

1. In the DSR Workbench, on the Subtask list click **Add Subtask** (+ icon).

![Dashboard view showing tasks and subtasks for data subject access request management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.34.42 AM.png)
2. Enter the **Subtask Name**, choose the request option from **Request Type**, and click **Create**.

> [!NOTE]
> **Note**
> 
> The **Request Type** menu shows the labels for custom or system request types submitted by the Data Subject. These labels may differ from those listed on the [Request Types page](/v1/docs/configuring-dsr-request-types) in DSR settings.

When a new Subtask is created, Securiti sends an email notification to the Subtask owners and guest users, informing them about the new Subtask assigned to them.

![Screenshot_2024-08-02_at_11_56_05_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-06933801-c1af-1bdc-f677-3a9d80ed4647.png)

The Subtask name must be unique and **Request type** for the created Subtask can be only one of the DSR ticket’s request types.

> [!NOTE]
> **Note**
> 
> You can only create subtasks for DSR requests against which the DSR report is not being published. Additionally, you must be a DSR owner to create a Subtask within the DSR workbench.

### Subtask Action panel

The Subtask action panel is where you do the bulk of the work involved in processing a DSR request. This panel shows you the currently selected Subtask and guides you through its processing. For more information, see [Processing DSR subtasks](/v1/docs/processing-dsr-subtasks).

![Data Subject Rights request overview with task details and report options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.40.11 AM.png)

When you customize subtask instructions, behavior in the DSR workbench depends on how these instructions are configured. For more information, see [Customizing Subtask Instructions](/latest/docs/customizing-subtask-instructions).

> [!NOTE]
> Note
> 
> Observe the following caveats
> 
> - For Access, Port, and custom request types, user-defined instructions include an Include in report checkbox for attachments. This option is not available for other request types.
> - If an instruction is optional, you do not need to select Include in report to mark it as done. Uploading an attachment is sufficient to complete the instruction.
> 
> ![Data subject access request details with highlighted report and processing information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-30 at 3.28.36 PM.png)
> - The Record DSR response status section is fixed and does not behave as a [configurable instruction](/latest/docs/customizing-subtask-instructions).
> - Instructions such as erasure scripts or object details appear in the workbench only when relevant data is available.
> - Responses for user-defined instructions do not appear in the subtask completion summary in the DSR workbench.
> 
> ![Overview of a task management interface showing completed subtasks and submission details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-30 at 3.33.24 PM.png)

When you are working on a DSR Subtask, the workbench uses regulatory details that help you understand regulations applicable to the various portions of that Subtask. This information helps you properly complete the Subtask. The information show is for the regulatory jurisdiction configured for the DSR request form response deadline (CCPA, GDPR, etc.).

![Dashboard displaying DSR access request details and task management for Kimberely Fisher.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.43.01 AM.png)

When you click the **Regulatory Details** link, Securiti shows you details of the applicable regulation.

The panel sometimes displays notes or error messages from Securiti regarding the Subtask, for instance when it encounters low confidence associations or failure in running database query.

![Screenshot_2025-08-05_at_1_25_46_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9e31a31-0acc-b46b-d38d-74480fe4c665.png)![Screenshot_2025-08-05_at_1_27_03_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ee4739dc-ad17-c612-23c2-d3d0c4e17b3a.png)

> [!NOTE]
> **Note**
> 
> Securiti sends an email notification to the Subtask owner each time a Subtask execution encounters an error. This feature notifies Subtask owners immediately and gives them quick access to a list of subtasks that have failed.

In such cases, Securiti sets the Subtask status to error. You can also manually change the status of the Subtask to error on data systems where you perform scanning independently and encounter errors.

![DSR access request interface showing tasks, subtasks, and response status options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.49.06 AM.png)

> [!NOTE]
> **Note**
> 
> You cannot publish a report if any subtasks are in an error state. You must either approve or decline the Subtask before proceeding to publish the report.

You can also set the Subtask to “No Data” state. Securiti retains or suppresses the Subtask depending upon the [task settings](/v1/docs/configuring-dsr-task-settings).

> [!NOTE]
> **Note**
> 
> When the [task setting](/v1/docs/configuring-dsr-task-settings) to retain subtasks changes from "true" to "false", rescanning behaves differently based on connector type. For unstructured and hybrid connectors, subtasks in the “no data found” state are deleted and only recreated if new data is found. For structured connectors, the original “no data found” Subtask remains, and a new Subtask is added if data is available.

You can review all uploaded attachments for the **Approved** and **Declined** DSR subtasks. Attachments in the DSR subtasks can be mandatory or optional depending upon the DSR type.

- Access (Mandatory)
- Port (Mandatory)
- Confirmation (Optional)
- Discloser of subprocessors (Optional)
- Do Not Sell or Share(Optional)
- Erasure (Optional)
- Objection (Optional)
- Rectification (Optional)
- Restrict Automated Individual Decision-making (Optional)
- Restrict Processing (Optional)

> [!NOTE]
> **Note**
> 
> A Subtask owner can manually upload up to 30 attachments. Each file can be up to 100 MB in size. Additionally, Securiti performs anti-virus checks on any attachments submitted by the subtask owners through the DSR Workbench.

Securiti sends an email notification to Subtask owners whenever an attachment is uploaded to a Subtask. You receive these notifications in the following cases:

- When DSR robotic automation completes and Securiti attaches files containing Data Subject information to the Subtask.

> [!NOTE]
> **Note**
> 
> This first case applies only to DSR requests of type **access** and **port**.
- When you manually attach a file in the **DSR Workbench**.
- When a file uploads as a result of a DSR workflow executed using Workflow Orchestration module.
- When you upload an attachment or file to a Subtask via API.

Click on the **Eye** icon to view the uploaded attachments in the Subtask as shown below.

![Dashboard displaying DSR access request details and task completion status.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 8.51.27 AM.png)

#### Exporting subtasks errors

You can export DSR Subtask errors in JSON format to easily share error lists with database engineers, removing the need for manual screenshots.

1. In the DSR workbench, from the top, click **More Actions > Export Subtask Errors.**

![DSR access request dashboard showing tasks, errors, and options for exporting data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-03 at 9.04.29 AM.png)

> [!NOTE]
> **Note**
> 
> The DSR workbench displays the export Subtask errors option only when at least one Subtask in the workbench has an error. If there are no errors in any Subtask, the option does not appear.
2. This sends you an email with a link to the subtasks errors file and the password needed to open it.

![Screenshot_2024-04-19_at_10_02_43_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78b743f4-ec7a-8934-0f54-3a1e50cbf198.png)

> [!NOTE]
> **Note**
> 
> If you disable the encryption standard, you don't receive any passwords and can download and access the Subtask error file directly. For more information, see [Configuring DSR encryption standards](/v1/docs/configuring-dsr-encryption-standards).

---

### FAQs

#### 1. If we have Robotic Automation configured, how can we add additional tasks that require manual intervention?

Yes, , you can add manual tasks by creating assets in the Data Mapping module and adding them in the DSR workflow. Once done, each time you raise a DSR request, Securiti creates tasks and subtasks against those assets and shows them in the DSR task list.

For more information on creating assets in Data Mapping, see [Creating and editing data assets](/v1/docs/creating-and-editing-data-assets).

Further, you can also create subtasks directly within the DSR workbench. For more information, see [Subtasks list](/v1/docs/using-the-worklist-tab) .

#### 2. How does DSR automation for self-hosted connectors work when the pod is off, and how does it recover when turned back on? Is there a retry or time limit before rescanning?

If the pod is off when a DSR request is received, the DSR Automation fails, and the DSR workbench shows an error in the Subtask created against that Data System.

![Screenshot_2025-02-21_at_5_11_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2239ca56-5b36-84b9-84bd-79e565963059(1).png)

There is no automatic retry. Once the pod is back up, you can manually rescan the Subtask to retrieve the results. There’s no time limit for rescanning the same DSR request. The only conditions are that the DSR should not be published and no other scan for that DSR request is in progress.
