---
title: "Auditing DSR requests"
slug: "auditing-dsr-requests"
updated: 2026-01-14T08:32:53Z
published: 2026-01-14T08:32:53Z
canonical: "helpcenter.securiti.ai/auditing-dsr-requests"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Auditing DSR requests

The audit log for each DSR request shows you a record of every action taken on the request by the Securiti system, or by any Securiti user, admin, or DPO. The audit log also shows when a data subject has downloaded a report for an access or port request, or has clicked on the report for other request types. Use the audit log to demonstrate compliance with regulatory systems such as GDPR or CPRA.

If you are the DSR request co-owner, you can view all audit log entries for the request, and you can download the audit log to a CSV file. If you are a subtask owner but not the DSR request co-owner, you can only view audit log entries for subtasks you own.

![Screenshot_2025-08-05_at_4_27_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-80c3db5b-78c6-097f-b981-6a0dca2d76d5.png)

> [!NOTE]
> **Note**
> 
> DPO users can view DSR audit logs only for activities they performed on a specific DSR request.

To view the audit log for a DSR request:

1. If you haven’t already done so, open a DSR request in the DSR Workbench as described in [Opening DSR requests in the DSR workbench](/v1/docs/opening-dsr-requests-in-the-dsr-workbench-1).
2. Click the **Audit Log** tab.

Securiti opens the Audit log to show you a list of activities for the DSR request and its tasks and subtasks. If you are the DSR request owner, the list shows all log entries for the request. If you are a subtask owner, the list only shows log entries for the DSR request subtasks that you own.
  - Near the right end of the card, choose either **Grouped** or **Chronological** as the sort type. The default sort is grouped by activity type.

![Screenshot_2025-08-05_at_4_32_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac41036a-3c02-a232-f788-97f184498c75.png)
  - Click **View log metadata** near the right end of the card for any group or any activity to view more information.

![Screenshot_2025-08-05_at_4_27_46_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b7a994c8-7cc9-62ce-6e0d-cecfcc890b7f.png)
  - In the Chronological view, use the **View** menu near the upper left corner of the tab to filter the tab on activity types.

![Screenshot_2025-08-05_at_4_28_02_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b6406b9-b3c1-b0f3-487b-da691524a1f9.png)
  - Use the full text search box at the top to filter activities on text strings within the Message field.

![Screenshot_2025-08-05_at_4_28_23_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6bcaa540-8cf9-67f0-8811-6f0b81166b50.png)

To export the contents of the Audit Log tab for any DSR request for which you are a co-owner into a CSV file:

1. If you haven’t already done so, open a DSR request in the DSR Workbench as described in [Opening DSR requests in the DSR workbench](/v1/docs/opening-dsr-requests-in-the-dsr-workbench-1) and click the **Audit Log** tab.
2. From the top of the page, click **Export > Export Audit log** as shown below.

![Screenshot_2025-08-05_at_4_28_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0aa19f1a-9c5a-4554-64f3-941c6b8634e9.png)
3. Use the Export DSR Audit Report popup to customize the report as shown below, then click **Export**.

![Screenshot_2025-08-05_at_4_28_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-934e8d0f-4cd6-7d53-a45b-87fbec1d1d03.png)

Securiti downloads the contents of the DSR request audit log to your downloads folder in a zip file.

Securiti generates and maintains audit logs for the Data Subject Rights module when DSR owners, subtask owners, data subject or Securiti perform different actions on the DSR request. These actions are further divided into categories.

> [!NOTE]
> **Note**
> 
> The audit logs not only capture these documented actions but also record numerous other activities that occur throughout the handling of a DSR request.

Some of the key actions are as follows:

#### Identity Verified

- Identity verification of the data subject is successful for the submitted DSR request.

### DSR Details

| User | Actions |
| --- | --- |
| Securiti | - Creates the DSR request. - Skips automation for data systems if they are in inactive states or authentication fails. - Shows indication if no data or search results found for a particular data system. - Submit a people data graph request. - Completes people data graph completion and creates subtasks. - Skips subtask creation for data systems where no matching documents are found. - Auto extends DSR deadline. - Sends out auto extension notification to the data subject. - Auto extends the DSR deadline. |
| DSR Owner | - Adds a new DSR owner. - Removes an existing DSR owner. - Exports subtasks errors. - Initiates a rescan for DSR request. - Exports audit logs in csv format. - Initiates batch update for DSR subtasks. - Views or downloads DSR request attachment. > [!NOTE] > **Note** > > In certain cases, the DSR module may not be able to differentiate between a user viewing and downloading an attachment. In such instances, the log records that the user "accessed the attachment. For instance, when you download a DSR request attachment, the log records: "DSR request attachment <filename> is accessed." - Views or downloads an attachment sent by the data subject in a message. - Downloads DSR Report generated using **Generate Report** button. - Manually extends the DSR deadline. - Pause the DSR deadline. - Resumes the DSR deadline. |

### DSR Tasks

| User | Actions |
| --- | --- |
| Securiti | - Creates a task for DSR request. - Creates a subtask for DSR request. - Runs smart search queries for subtasks. - Suppresses the subtask where no data is found. - Retains subtasks even when no data is found if [subtask retention](/v1/docs/configuring-dsr-task-settings) is enabled. - Uploads/returns attachment to the subtask containing data subject’s information. |
| Subtask Owners | - Adds response status to subtasks such as approve, decline, no data or to do. - Set the subtask to no data found when [subtask retention](/v1/docs/configuring-dsr-task-settings) is enabled. - Uploads attachment to the subtask. - Includes attachment in the DSR report. - Deletes an attachment from the subtask. - Skips Process Record related warning message on approving a subtask. - Adds a new subtask owner. - Views or downloads subtask attachment |
| DSR Owner | - Creates a new subtask - Views or downloads subtask attachment |

### DSR Report

| User | Actions |
| --- | --- |
| DSR Owner | Approves or rejects DSR requests and publishes DSR reports. |
| Data Subject | Downloads DSR report from Privacy Central. |

### DSR Messaging

| User | Actions |
| --- | --- |
| Securiti | Confirms request completion once DSR owner publishes DSR report. |
| DSR Owner | Sends a message to the data subject. |
| Data Subject | Responds to the message sent by the DSR Owner |
| Privacy Central | Securiti records all notification emails sent to the data subject, such as: - Sends a notification for request verification. - Sends a notification when identity verification is successful. - Sends a notification when a request is completed. - Sends a notification when identity verification fails. - Sends a notification when DSR is paused. - Sends a notification when the DSR is resumed. You can filter all emails sent to the data subject by selecting “Email” in the **Activity** filter. > [!NOTE] > **Note** > > Securiti doesn't record audit logs in the following cases: > > - Data subjects delete their privacy central account. > - Data subjects change the password for their account from privacy central. Additionally as the request ID is the same for regular and appeals DSR requests, all email audit logs appear under both the regular DSR and its associated appeals DSR audit log tab. |

A process record outlines key details regarding the processing of personal data. Specifically designed for Access and Confirmation DSR types, it fulfills regulatory requirements by informing data subjects about how and why their data is processed. This includes categories of personal data, processing purposes, recipients, data storage duration, data source details, etc.
