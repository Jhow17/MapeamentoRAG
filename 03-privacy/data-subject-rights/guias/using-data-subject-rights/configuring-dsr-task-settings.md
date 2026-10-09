---
title: "Configuring DSR task settings"
slug: "configuring-dsr-task-settings"
updated: 2026-08-12T07:55:20Z
published: 2026-08-12T07:55:20Z
canonical: "helpcenter.securiti.ai/configuring-dsr-task-settings"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring DSR task settings

Task Settings lets you retain subtasks in the DSR workbench when they are marked as “No Data Found”, either manually by the subtask owner or through DSR Automation. This ensures that important information remains available for reviews and audits, providing subtask owners and DSR owners with complete context.

> [!NOTE]
> **Note**
> 
> Only Securiti super admins can enable this setting. All other roles have read-only access to this page.

1. In the Data Subject Rights module, choose **Settings > DSR Settings**.
2. Scroll to the Task Settings section and click **Edit** (pencil icon) on the right side to open the task settings in edit mode as shown below.

![Settings for data subject rights, including task retention and encryption standards.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.51.25 PM.png)
3. Mark **Retain Task/Subtasks if no data found** checkbox and click **Save**.

![Settings page displaying DSR options and task settings for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.53.10 PM.png)

If you disable this setting, Securiti suppresses tasks and subtasks for data systems that don’t find any matches for a particular data subject.

> [!NOTE]
> Note
> 
> On a sequential DSR request, Securiti never suppresses a subtask that results in No Data found, regardless of this setting. This ensures each level's execution blocks have a subtask status to evaluate against, since a suppressed subtask would leave that condition unresolved. For more information, see [Configuring sequential task processing in the DSR form](/latest/docs/configuring-sequential-task-processing-in-dsr-forms).
