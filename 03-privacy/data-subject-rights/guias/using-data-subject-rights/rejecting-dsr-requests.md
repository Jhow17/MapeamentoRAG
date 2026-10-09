---
title: "Rejecting DSR requests"
slug: "rejecting-dsr-requests"
updated: 2026-08-09T16:48:04Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/rejecting-dsr-requests"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Rejecting DSR requests

You can reject DSR requests in cases where a request is deemed to be excessive, unfounded, or repetitive. Another reason for rejecting a DSR request could be that complying with the request violates other legal obligations.

> [!NOTE]
> **Note**
> 
> You can only reject a DSR once Securiti creates all the subtasks for it.

Additionally, you can also choose not to return any task-level details, such as data processing purposes, to data subjects in the final DSR report.

> [!NOTE]
> **Note**
> 
> If you choose not to provide data processing details to the Data Subject, you might violate the transparency requirements of applicable privacy laws.

To reject a DSR request:

1. In Securiti, open the **Data Subject Rights** module, choose **Data Subject Rights > DSR Dashboard** and click the request card for which tasks creation is completed.
2. In the DSR Workbench, choose **Reports > Reject DSR**.
3. On the **Reject DSR** page do the follow:

> [!NOTE]
> **Note**
> 
> Rejecting a DSR sets all the subtasks to declined status and overwrites the reason for declining for each Subtask with a reject reason. On a sequential DSR request, rejecting the request also does not trigger any further levels, even if a level's condition matches the declined status. For more information, see [Configuring sequential task processing in the DSR form](/latest/docs/configuring-sequential-task-processing-in-dsr-forms).
  1. Select a rejection reason by choosing a template category and then selecting one of the available templates.

Optionally, you can also add internal notes for additional information.
  2. Further, mark or unmark the **Do not show task level details** option to decide whether to send task-level details, such as processing activities, back to the Data Subject in the final DSR report.

Optionally, You can also skip sending notifications to your data subjects when rejecting the DSR.
  3. You can also preview and customize the email you need to send to the data subject on rejecting a request. The preview shows the exact template selected based on the request type and the language in which the request is submitted. You can continue to manage these templates from Settings > Notification Templates. For more information, see Configuring email notification templates.

> [!NOTE]
> Note
> 
> This applies to external DSRs and internal DSRs where a privacy account is associated with the data subject.
  4. Once done, click **Reject this DSR**.

![Screenshot_2025-02-25_at_11_20_45_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bec420b0-7d7c-eb69-1a37-a2c0817b2f13.png)

This sends an email to the Data Subject about the decision of the DSR Owner regarding the DSR request along with the final DSR report.
