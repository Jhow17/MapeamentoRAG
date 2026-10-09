---
title: "DSR workbench overview"
slug: "dsr-workbench-overview"
status: "update"
updated: 2026-09-24T11:43:14Z
published: 2026-09-24T11:43:14Z
canonical: "helpcenter.securiti.ai/dsr-workbench-overview"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# DSR workbench overview

The **DSR Workbench** is a place where privacy team members or technical resources of your organization can process tasks and subtasks created for a submitted DSR request.

Securiti creates Tasks and subtasks against data systems containing the personal data of the requester. These tasks and subtasks specify actionable steps that your organization must undertake to process a DSR. For more information, see [Understanding tasks and subtasks](/v1/docs/understanding-tasks-and-subtasks).

DSR owners primarily use the DSR Dashboard for tracking DSR requests and identifying the requests assigned to them for processing. They can use filters on the DSR Dashboard to simplify locating DSR requests. They can drill down to see requests that are pending or overdue. For more information, see [Filtering the DSR Dashboard](/v1/docs/filtering-the-dsr-dashboard-1) .

Securiti automatically assigns tasks to data system owners. On assigning subtasks to individuals (from within or outside the organization), Securiti sends an email containing the request number and link to the subtask individuals must process. See [Manually assigning DSR request subtasks](/v1/docs/manually-assigning-dsr-request-subtasks) for more information.

> [!WARNING]
> **Important**
> 
> If you don’t have a subscription for the Sensitive Data Intelligence module to automate the DSR process, you can manually create assets in the Data Mapping module and add them in the DSR workflow. Once done, each time you raise a DSR request, Securiti creates tasks and subtasks for those assets and shows them in the DSR task list. See [Creating and editing data assets](/v1/docs/creating-and-editing-data-assets) for more information.

Once you are in the DSR Workbench, the top header displays the following for the currently selected DSR request:

| Type(s) of request | It shows the type of DSR request submitted by the data subject. |
| --- | --- |
| Deadline | It shows number of days until its deadline. You can set this deadline when you configure a DSR form. |
| Identity Verified | The Identity Verification bar updates fully only after Securiti verifies identity of the data subject, either through email or an external verification process configured during the setup of the DSR form. |
| Automation | Updates fully once Securiti generates all tasks for data systems containing the personal information of the data subject and completes any robotic automation running on those data systems. > [!NOTE] > Note > > If a DSR request remains incomplete in this state for more than 5 days, Securiti automatically unblocks it. |
| Tasks Progress | Updates fully once you complete all subtasks. Click the info icon next to Tasks Progress to see a breakdown of task completion and subtask status counts. |
| Report Sent | The Report Sent bar updates fully only when the data subject downloads the report from privacy central (data subject Portal). |

At the top of the page are tools you can use to get more information about the data subject and the request:

- **Regulation Summary--**Click to view a summary of the privacy regulations applicable to the DSR request. For more information, see [Viewing regulation summary](/v1/docs/viewing-data-subject-details).
- **Subject details**--Click to view all information provided by the data subject in their request, including any file attachments they included. For more information, see [Viewing data subject details](/v1/docs/viewing-data-subject-details).
- **Messages**--Click to view messages exchanged with other Securiti users about the DSR request.

Below the header is a series of tabs that you use while processing the DSR request:

- As a subtask owner use the **Worklist** tab to see the DSRs list, Tasks list, and Subtasks list respectively. Click **Expand Sidebar** (expansion icon) to expand DSR requests list. On any of these lists, you can jump from one item to another. For more information, see [Using the Worklist tab](/v1/docs/using-the-worklist-tab).

![Workbench interface displaying DSR access request details and task progress for a user.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-07 at 5.15.23 PM.png)

Once you click on any subtask, you see a Subtask Action panel containing guidance to process a subtask. The content in this panel varies based on the data subject type. It typically presents a checklist showing what Auti has done and what you must do.

In the DSR workbench, each DSR request is processed differently. For instance, in the case of Access and Port request types, you also need to attach process records in the subtask. For more information, see [Understanding process records](/v1/docs/understanding-process-records) .

See [Processing DSR subtasks](/v1/docs/processing-dsr-subtasks) for more information on how the processing of a subtask varies in case of different DSR request types.

Other than processing a subtask you can perform the following actions in the Worklist tab:

> [!NOTE]
> **Note**
> 
> - In the DSR Workbench, a logged in user with the default role or module owner role (with restricted permissions enabled) sees incorrect completed task counts. This occurs when the user is assigned only a few subtasks from a task, while other subtasks for the same task remain incomplete. The “my completed tasks” count displayed is incorrect.
> - When you apply the DSR Subtask Owner filter on the Dashboard to view only DSR requests with subtasks assigned to a specific subtask owner, the completed versus total task counts are incorrect.
  - [Assigning Subtasks to other resources](/v1/docs/manually-assigning-dsr-request-subtasks)
  - [Communicate with other subtask owners](/v1/docs/communicating-with-dsr-and-subtask-owners)
  - [Communicate with the Data Subject](/v1/docs/communicating-with-data-subjects)
  - [View Regulation Summary](/v1/docs/viewing-data-subject-details)
- The **Chatroom** tab displays messages related to the DSR request, followed by messages for each accessible subtask. What you see in the Chatroom depends on your Securiti role and your DSR request ownership roles. For more information, see [Using the Chatroom](/v1/docs/using-the-chatroom-tab) .

As a subtask owner, you can also use the message panel to communicate with other owners working on different parts of the same subtask. For more information, see [Using the DSR request and subtask messaging side panels](/v1/docs/using-the-dsr-request-and-subtask-messaging-side-panels).
- The **Data Subject Explorer** tab lets you swiftly review the personal data you have for the data subject, the nature of the data, where it resides, and the compliance location of the data subject. For more information, see [Using the Data Subject Explorer](/v1/docs/using-the-data-subject-explorer-tab).
- The Audit log tab for each DSR request provides a comprehensive record of all actions taken on the request, whether by the Securiti system, a Securiti user, an admin, or a DPO. Fore more information, see [Auditing DSR requests](/v1/docs/auditing-dsr-requests).
- Once all the subtasks are completed, as a DSR owner use the Reports tab to publish the DSR report. The Reports tab shows each subtask details such as attached process records and attachments . This tab only shows data for completed DSR requests. For more information, see [Approving and publishing reports](/v1/docs/approving-and-publishing-reports).

> [!NOTE]
> **Note**
> 
> The **Report Sent** bar updates fully only when the data subject downloads the report from Privacy Central (Data Subject Portal).
- Similarly, the DSR owner can use the **Batch Update** tab to approve or reject all tasks or subtasks at once. For more information, see [Applying batch updates to DSR subtasks](/v1/docs/applying-batch-updates-to-dsr-subtasks).

> [!WARNING]
> **Important**
> 
> The Subtask owner with the default role of "User," is unable to access the Batch Update tab in the DSR Workbench. Likewise, when a Subtask is assigned to a guest user, their visibility is restricted to the Worklist and Chatroom tabs only.

---

### FAQ

#### 1. If we purchase DSR without SDI, how can we create assets for tasks to be generated in DSR?

If you don’t have a subscription for the Sensitive Data Intelligence module to automate the DSR process, you can manually create assets in the Data Mapping module and add them in the DSR workflow. Once done, each time you raise a DSR request, Securiti creates tasks and subtasks against those assets and shows them in the DSR task list. For more information on creating assets in Data Mapping, see [Creating and editing data assets](/v1/docs/creating-and-editing-data-assets).

#### 2. How can I process a DSR request without associating it with any data system?

You can use a task template that has no data system linked to it. This creates a single task named after the template, with no data system association at all. Using a template with no data system link is different from selecting an unmonitored data system, which is still a data system category, just one Securiti cannot connect to directly. For more information, see [Understanding task templates and rule-based task creation.](/latest/docs/understanding-task-templates-and-rule-based-task-creation)

#### 3. Why are DSR tasks and subtasks not getting created in DSR Workbench?

If the DSR task creation has completed but the desired subtasks are not created for a particular data system, it is possible that the data system has not been marked as participating in the DSR workflow. To verify this, you must check two things:

- In the data system configuration, the Include this instance in the DSR workflow option under the Permissions tab is marked. For more information, see [configuring connectors for data systems](/v1/docs/configuring-connectors-for-monitored-data-systems).
- In the DSR form setting, the respective data system is included in the DSR workflow.

![Screenshot_2024-06-09_at_1_25_50_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6f8c662-052c-fe1a-e5e4-c5dd6f8e4ca4.png)

It is possible that a data system doesn’t result in any matches for a particular data subject and tasks/subtasks are suppressed. To verify this, check for logs in the audit trail for the DSR request under consideration.

![no_search_results.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d92dcbd6-ac2e-4c4c-20a0-da6c790452ac.png)

If you see any logs like the above for your data system, it means that there was no match found for the data subject in the respective data system hence tasks/subtasks were suppressed. Securiti also lets you retain subtasks with no data found status. For more information, see [Configuring DSR task settings](/v1/docs/configuring-dsr-task-settings).
