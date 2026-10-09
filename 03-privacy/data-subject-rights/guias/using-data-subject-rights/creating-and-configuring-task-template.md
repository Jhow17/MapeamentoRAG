---
title: "Creating and configuring task template"
slug: "creating-and-configuring-task-template"
tags: ["manual subtask template"]
updated: 2026-09-25T03:22:49Z
published: 2026-09-25T03:22:49Z
canonical: "helpcenter.securiti.ai/creating-and-configuring-task-template"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Creating and configuring task template

> [!NOTE]
> **Note**
> 
> Only the following Securiti user roles in your tenant have permission to perform WRITE actions for task templates, while all others have READ permissions:
> 
> - Super Admin
> - DPO
> - Org Admin
> - Module Owner
> - Operator

To access task templates:

In the Data Subject Rights module, choose **Settings > Task Templates**.

On this page, you can use the search bar to search for a particular template by entering its name or description. You can select filter options to specify the criteria for filtering the task templates. There are two filters available: DSR Automation and Associate Data Systems.

- **DSR Automation**: Lets you filter task templates by automation status either “Enabled” or “Disabled”.
- **Associate Data Systems**: Lets you filter templates with specific data systems included.

![Screenshot_2025-06-29_at_10_35_27_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4be555c3-e1b4-74c3-5e96-9a2638aa919c.png)

To create a Task template:

1. At the upper right corner of the page, click **New Template**.
2. On the Task template page, fill the following information:

| **Task Information** |
| --- |
| Template Name | Enter the name of your template. It must be unique within the organization. The maximum character limit is 255. > [!NOTE] > **Note** > > If no data system is associated with the template, Securiti creates a task in the DSR workbench using the template name. If a data system is included, the task is named after the associated data system connector. |
| Description | Enter the description of the template. |
| Exclude this Task from the Report | Mark this checkbox to exclude the subtask from the DSR report sent to the data subject. If all subtasks are excluded, Securiti validates whether required data is available based on the request type. - For Access and Port requests, attachments are required. If no attachments are available, Securiti shows an error and blocks approving and publishing the DSR request. - For Confirmation requests, process records are expected. If no process records are available, Securiti shows a warning but lets you proceed. If both attachments and process records are missing, Securiti prioritizes the attachment error and blocks the action. |
| **Data Systems** |
| Associate with data systems | Enable this toggle to include or exclude data systems from the respective task template. |
| Include Data Systems | Click this card to add one or more data systems to apply this task template. When a DSR request is submitted through a linked form, Securiti creates tasks for the selected data systems following the respective template. > [!NOTE] > **Note** > > - Selecting “All Data Systems” options is not the same as selecting all of the individual data systems. “All Data Systems” option, if selected, Securiti looks for all the data systems that are marked for DSR robotic automation at the time tasks are created for a DSR request. > - You must mark the "Include this instance in DSR workflow" checkbox on the Permissions tab for each associated data system connector. For more information, see [Setting up data systems for DSR automation](/v1/docs/setting-up-data-systems-for-dsr-automation). > - When no data systems are configured in the organization, and task templates are set to include all data systems, Securiti does not create tasks or subtasks. However, the DSR request is created and moves to the **Tasks Completed** state. |
| Exclude Data Systems | Choose one or more data systems to explicitly not associate with the task template. |
| Delay Task Creation | Mark the checkbox to make Securiti delay creation of subtasks for the associated data systems. You can delay task creation by hours or days. > [!NOTE] > **Note** > > Observe the following caveats: > > - This option stays disabled if you select **All Data Systems** when including data systems in the task template. > - This option works only for templates where DSR Automation is enabled. |
| DSR Robotic Automation | Enable this toggle to let data systems automatically search for and retrieve data for data subjects across cloud and self-hosted environments. |
| Assign Subtasks to System Owners and Collaborators associated with the Data System | This toggle lets you automatically assign subtasks to data system owners and other users. Enable this toggle to automatically assign subtasks to all data system owners of the data systems included in the task template. If this toggle is disabled, you must add at least one assignee or collaborator while creating the subtask template. If this toggle is enabled and you have added assignees or collaborators in the subtask template, the subtask is assigned to all those users. |
| **Subtask Settings** |
| Add Subtasks | Click this (+) to add subtask templates. Observe the following caveats: - You must create at least one subtask template for the given task template. - If the **Associated with Data Systems** toggle is disabled, you can create as many subtask templates as you want. - If **Associated with Data Systems** is on but **DSR Robotic Automation** is off, you can still create multiple subtask templates. - If both **Associated with Data Systems** and **DSR Robotic Automation** toggles are enabled, you can create only one subtask template for the task template |
| **Subtask Details** |
| Subtask Name | Enter the subtask template name. The maximum character limit is 255. It must be unique within a task template. |
| Description | Enter the description for the subtask template. |
| Name Subtasks using above Subtask Template Name | Mark this checkbox to display subtasks in the DSR workbench using the subtask template name. - If this option is enabled, the subtask name appears in the format: [Request Type] [Subtask Template Name]. For instance, if the request type is “Access” and the subtask template name is “Validate User Identity”, the subtask appears as: Access Validate User Identity. - If the option is disabled, Securiti uses the format:[Request Type] for [Data System]. For instance, if the request type is “Access” and the data system instance is “Salesforce instance”, the subtask appears as: Access for Salesforce instance. - If a task template is not associated with any data system instance, all subtasks created under that task in the DSR Workbench follow the subtask template names, regardless of the naming settings configured in the individual subtask templates. > [!NOTE] > **Note** > > For unstructured data systems, where automation creates multiple subtasks against a single task because the data subject’s information appears in multiple files, subtasks do not follow this naming format or use the subtask template name. |
| Assignees | Select one or more assignees to assign this subtask to. > [!NOTE] > **Note** > > If the option “Assign Subtasks to System Owners and Collaborators associated with the Data System” is disabled while creating the task template, you must add at least one assignee here to ensure the subtask is assigned. |
| Collaborators | Add the list of collaborators/guest users. Type a collaborator’s email address, then press **Enter** to add it to the list. Repeat as necessary to build a list of collaborators.This sends an invite to the selected users using the collaboration notification template. |
| Customize Email Template & Guidance Text | Enable this to make changes to the collaborator invite. This is reflected in the DSR subtask action panel in the DSR workbench for guest user’s assigned subtasks. You can also update this text on the **Permissions** tab for each associated data system connector. |
| Deadlines | - **Set Deadline**: Set the number of days to define the deadline for subtask completion. > [!NOTE] > Note > > The maximum subtask deadline value must be between 1 and 1000. - **Same as the DSR Deadline**: Use this option to match the subtask deadline with the DSR request deadline. - **None**: Use this option to remove the subtask deadline. This is the default option. > [!NOTE] > **Note** > > If a subtask deadline is longer than the DSR request deadline, Securiti automatically sets it to match the DSR deadline. For example, if the subtask deadline is 45 days and the DSR deadline is 30 days, the system sets the subtask deadline to 30 days. When a DSR request is extended, the subtask deadline does not change. |
| Subtask Instructions |
| Edit Subtask Instructions for this Task | Mark this checkbox to append or override request type instructions when subtasks are created using this task template. Click **+Add New** to add new instructions. - Enter the title of instruction. The maximum character limit is 100. - Enter the instruction description. The description can contain up to 5000 characters. If you include links, ensure the content uses valid HTML. You can also use the toolbar to format the description text with different fonts, colors, and styles. - Choose the data system type from the Associate System Types menu. You must choose at least one from the list. > [!NOTE] > Note > > Make sure the selected system type matches the type of data system instances selected in **Choose Data Systems** to Include. For example, if you select a Google Drive instance, choose the corresponding monitored unstructured system type. - Enable at least one action before adding the instruction. - **Mark as done**: Adds a checkbox in the subtask to confirm completion. Mark Mandatory checkbox to require users to mark the instruction as done before completing the subtask. - **Notes**: Lets users add additional information as notes. Mark Mandatory checkbox to require notes before completing the subtask. - **Upload Attachment**: Lets users upload attachments for the instruction. Mark Mandatory checkbox to require at least one attachment. Once done click **Save**. - **Append Instructions**: Choose this to add the instruction to the existing request type instructions - **Override Instructions**: Choose this option to replace the request type instructions with the ones defined in the task template Observe the following caveats: - Instructions are saved only after you save the task template. - If you disable **Edit subtask instructions for this task** and save the template, all instructions added to the template are removed. - When **Edit subtask instructions for this** **task** option is disabled, the system applies only the request type instructions. - If you select **Override Instructions**, the system replaces request type instructions with the task template instructions. - The **Record DSR Response Status** field always appears on every subtask, even when you select Override Instructions and define only one or two custom instructions. - If no other instructions apply to a subtask, this field is the only thing a subtask shows, and that is expected. - Review your configuration if no instructions appear, and update the template as needed. |
3. Once you add a task template and subtask templates, click **Save Template**.

You can also edit or delete subtask templates as per your requirement.

Once you create the required templates, associate them with rules in the DSR form builder. For information, see [Configuring rules in the DSR form](/v1/docs/configuring-rules-in-the-dsr-form).

### Editing or deleting a task template

1. On the Task Templates page, choose the template you want to edit or delete.
2. Near the right end of the row for the template, choose **Options** (three dots) > **Edit or Delete**.
