---
title: "Creating a custom request type"
slug: "creating-a-custom-request-type"
updated: 2026-04-25T13:19:22Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/creating-a-custom-request-type"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Creating a custom request type

You can create new custom request types to align with your organization's specific needs. You can also update labels for existing system-supported request types to tailor them to your requirements.

> [!NOTE]
> **Note**
> 
> Only Super Admins in your Securiti tenant can add or update request types. All other roles, except default users and guest users, have read-only access to this page. Additionally, you can configure request types at the tenant level, ensuring they apply across all organizations. While you can switch between organizations, the request types remain consistent across all organizations within the same tenant.

To create a custom request type:

1. In the Data Subject Rights module choose **Settings > Request Types**. On the **Request Types** page, in the upper right corner click **Create Custom Request Type**.

![Overview of request types in system settings with highlighted custom request type option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-05 at 3.37.37 PM.png)
2. On the Create Request Type page, add the following:

| Field/Setting | Description |
| --- | --- |
| Request Type Label | Enter a name for the request type. The label can contain up to 100 characters. |
| Request Type Value | Enter a unique identifier for the request type. Use only lowercase letters and hyphens. Do not use spaces. The value must be unique and cannot match an existing request type. |
| Description | Enter details about the request type. The description can contain up to 500 characters. |
| Subtask Instructions | Click this (+) to add subtask instructions. On Add Subtask Instruction popup: - Enter the title of instruction. The maximum character limit is 100. - Enter the instruction description. The description can contain up to 5000 characters. If you include links, ensure the content uses valid HTML. You can also use the toolbar to format the description text with different fonts, colors, and styles. - Choose the data system type from the **Associate System Types** menu. You must choose at least one from the list. > [!NOTE] > Notes > > The instruction appears only if a subtask is created for the selected system type in the DSR Workbench. If no subtask is created for that system type, the instruction does not appear. - Enable at least one action before adding the instruction. - **Mark as done**: Adds a checkbox in the subtask to confirm completion. Mark Mandatory checkbox to require users to mark the instruction as done before completing the subtask. - **Notes**: Lets users add additional information as notes. Mark Mandatory checkbox to require notes before completing the subtask. - **Upload Attachment**: Lets users upload attachments for the instruction. Mark Mandatory checkbox to require at least one attachment. Once done click Save. Observe the following caveats: - Instructions are saved only after you save the request type. - System instructions are not visible when you create a custom request type. They appear only after you save the request type and open it for editing. - You can update the title and description of system instructions. Some system instructions can also be disabled. - You cannot delete system or custom instructions. You can only delete user-defined instructions - You cannot disable actions for system or custom instructions. You can only make them optional where supported - User-defined instructions support only three actions: attachments, notes, and mark as completed. - Some instructions appear in the DSR Workbench only when DSR automation is enabled for the request type. For instance, instructions such as object and data element discovery and auto-generated data element report appear only when DSR automation is enabled or data is found on rescanning a DSR. - For Access and Port requests, if attachments are optional, you cannot publish the request without adding attachments. - For Access and Confirmation requests, if processing details are optional, the system shows a warning but lets you publish the request. |
| DSR Automation | Turn on this toggle to enable DSR automation for the request type. > [!NOTE] > Note > > Enabling this also activates the Task per Data System option. |
| Task Per Data System | Turn on this toggle to create tasks for each data system associated with the request. |

> [!NOTE]
> Note
> 
> Securiti does not support the deletion of custom request types.

#### Updating DSR request types

To update an existing request type:

- On the Request Types page, locate the request you want to update and click **Option** (3 dots) next to that request record.
- On the **Edit Request Type** page, update the required information and click **Save**.

![Settings page for editing request types, including privacy request details and instructions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-05 at 4.16.24 PM.png)

> [!NOTE]
> **Note**
> 
> You cannot update the Request Type Value after it has been set. For system-supported request types, you can only update the label and description. Also, editing a request type label doesn’t affect any published DSR forms that already use that label.

While editing a request type, you can disable instructions such as processing details and attachments. Securiti shows a warning when you disable these instructions for request types where regulatory requirements may apply.

![Settings page displaying data element report and compliance regulations for data subjects.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-21 at 12.51.05 PM.png)

#### Add the custom DSR request to the DSR form

Once you have created a custom request type, while configuring the DSR form click **Customize Content**. On the **Customize Content** page, click **Edit**(gear icon) in the section where DSR requests are defined.

![Screenshot_2024-12-11_at_8_03_02_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-65ec2ba4-f9b4-fe3e-2267-cdb986993635.png)

On the **DSR Radio Component** page, under the **Display** tab, click **Add Another** and from the **Value** menu choose the custom request you want to add to the DSR form. To add more request types, click **Add Another** for each additional request and repeat the process. Once you have added all the requests, click **Save** and publish the form. For more information on DSR form builder options, see [Form Builder Tabs](/v1/docs/form-builder-tabs).

![Screenshot_2024-12-30_at_9_26_46_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dadd92ed-aae2-9b52-a8df-e1872cf65870.png)

> [!NOTE]
> **Note**
> 
> The form-level request type labels take precedence over labels defined in the [Request Types](/v1/docs/configuring-dsr-request-types) page of the DSR settings. If you update the label while configuring the DSR form, this new label will override the one set in the DSR settings.

To process a custom request type in the DSR workbench, see [Processing a custom request subtasks](/v1/docs/processing-a-custom-request-subtasks).
