---
title: "Configuring DSR request types"
slug: "configuring-dsr-request-types"
status: "new"
updated: 2026-04-05T10:34:17Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/configuring-dsr-request-types"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring DSR request types

You can configure custom request types and add them to DSR forms, accommodating a wide range of scenarios from privacy-related to non-privacy-related use cases. The **Request Types** table lists cards for both system-supported request types offered by the DSR module and custom request types that you can create. Each request card shows:

| Column Name | Description |
| --- | --- |
| Request Type | Displays the designated label for the DSR request on the published DSR form. |
| Request Type Value: | Represents the DSR request within the system for processing and tracking. |
| Category | Classifies the request type as either system-supported (predefined) or custom (user-created). |
| DSR Automation | Indicates whether DSR Automation is enabled for this request type. > [!NOTE] > Note > > For system-supported request types this option is enabled by default and you cannot disable it. |
| Task per Data System | Indicates whether creating a task and subtask for each data system was enabled when this request type was created. > [!NOTE] > Note > > For system-supported request types this option is enabled by default and you cannot disable it. |
| Created | Records the creation date for custom request types. For system-provided request types, this field remains blank (null). |

You can also sort the Request Types list in ascending or descending order to organize them in a particular arrangement. Sort the list using by following columns:

- Request Type
- Request Type Value
- Created

![request_types_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b7964e8a-7920-8328-2d90-8689a1d404cf.png)

When configuring these custom request types, you have precise control over the workflow through the following options:

**DSR Automation:**

- **Enabled**: Triggers automated workflow to execute and fetch results in the DSR workbench, and implicitly enables "Task per Data System" which creates separate tasks for each involved system. For more information on DSR Automation, see [Setting up data systems for DSR automation](/v1/docs/setting-up-data-systems-for-dsr-automation).

> [!NOTE]
> Note
> 
> Securiti doesn’t support custom request types for scanless data systems.
- **Disabled**: Defaults to manual processing of DSR requests, still offering flexibility to configure a task per data system creation as needed.

**Task per Data System (configurable regardless of DSR Automation state):**

- **Enabled**: Creates a separate task (and subtask) in the DSR workbench for each data system involved in the DSR processing, providing a detailed breakdown per system.
- **Disabled**: Results in the creation of a single task (and subtask) in the DSR Workbench for the entire DSR request, consolidating follow-up actions at the request level.

> [!NOTE]
> Note
> 
> If a data subject submits a DSR request with multiple custom request types, and DSR Automation and tasks per DS are disabled, Securiti creates one task labeled 'Multiple request types' and separate subtasks for each type.

Securiti logs the creation and updates of request types in the audit log. For more information, see [Viewing the Securiti audit log](/v1/docs/securiti-platform-viewing-the-securiti-audit-log).

## Viewing subtask instructions associated with request type

You can expand a request type to view the subtask instructions associated with it. Each instruction represents a step used to process subtasks for that request type.

1. In the Data Subject Rights module, choose **Settings > Request Types**, then locate and expand the required request type.

You can view the subtask details as follows:

| Column | Description |
| --- | --- |
| Subtask instruction | Displays the instruction title and a short description. This defines the step to be performed. |
| Associated system types | Shows the data system types where the instruction applies, such as unmonitored, user defined, monitored - hybrid, monitored - unstructured, monitored - scanless or structure |
| Status | Indicates whether the instruction is enabled or disabled. > [!NOTE] > Note > > Some system instructions can be disabled, while others remain required. User-defined instructions can be disabled and deleted. |
| Category | Indicates the instruction type: - **System**: Default instructions provided by the Securiti. You can update the title and description. - **Custom**: System instructions that have been modified. Once you make any change to the system instruction, you cannot revert the changes. - **User Defined**: Instructions created by the user. You can edit, enable or disable, and delete these instructions. |

At the end of the instruction row, click the **Show Metadata Explorer** option.

![Overview of request types in system settings with highlighted data element report.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-29 at 8.37.52 PM.png)

The metadata explorer panel displays details for the selected instruction. You can view the associated system types, status, and category. You can also review the actions linked to the instruction and check whether each action is optional or mandatory.

![Overview of request types and associated instructions in system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-29 at 8.43.20 PM.png)
