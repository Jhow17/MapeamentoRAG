---
title: "Task and subtask creation based on task templates"
slug: "task-and-subtask-creation-based-on-task-templates"
tags: ["create DSR with no data system"]
updated: 2026-09-25T02:41:25Z
published: 2026-09-25T02:41:25Z
canonical: "helpcenter.securiti.ai/task-and-subtask-creation-based-on-task-templates"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Task and subtask creation based on task templates

The way tasks and subtasks are created in the DSR workbench for a given DSR request depends on how the DSR request satisfies rules set on the DSR form.

### Case 1: Template is associated with data system instances

If a Task template is linked to one or more Data System instances, a task is created for each Data System instance. Subtasks in that template are created for each task created.

**Task name**: Matches the name of the associated Data System instance

#### Example

- **Template A** is linked to the “Postgres – Cloud” Data System instance with robotic automation enabled on the template with one Subtask template.
- A Rule set to trigger **Template A** for access and erasure request types.
- Upon receiving an Access request, one task named Postgres – Cloud is created with one Subtask.
- Upon receiving an Erasure request, one task named Postgres – Cloud is created with one Subtask.
- Upon receiving a multi-request DSR for Access and Erasure request, one task named Postgres – Cloud is created with two subtasks: one Subtask for access, one Subtask for erasure.

![Screenshot_2025-06-30_at_12_05_45_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ea3f7b4-6db3-287f-b351-6132e89ab5b2.png)

### Case 2: Template is not associated with any data system instance

If a Task template is not linked to any Data System instance, a single task is created from that template. All subtasks associated with the template are created under that task.

**Task name**: Matches the name of the Task template

#### Example

- **Template B** is not linked to any Data System instance and has one Subtask.
- A Rule is set to trigger **Template B** for access or erasure request types.
- Upon receiving an Access request, one task matching the template name is created with one Subtask.
- Upon receiving an Erasure request, one task matching the template name is created with one Subtask.
- Upon receiving a multi-request DSR for Access and Erasure request, one task matching the template name is created with two subtasks: one Subtask for access, one Subtask for erasure.

![Screenshot_2025-07-10_at_12_58_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eee47982-d668-1237-e534-a65ce6f6407b.png)

### Case 3: Multiple rule conditions

When multiple rules are configured in the DSR form (for example, Rule 1 and Rule 2), and each Rule is associated with a Task template linked to different Data System instances, task and Subtask creation depends on whether each request type satisfies the Rule conditions.

For DSR requests with multiple request types, subtasks are created only for the request types that meet a Rule’s condition.

#### Example

- **Rule 1**: Condition = Request type is Access → Apply Template 1 (linked to a Data System instance)
- **Rule 2:** No condition on request type → Apply Template 2 (linked to a different Data System instance)

If a DSR request is submitted with the request types Access and Erasure, Securiti creates the following tasks in the DSR workbench:
- For Access:
  - Task with one Subtask using Template 1 (satisfies Rule 1)
  - Task with one Subtask using Template 2 (Rule 2 applies to all request types)
- For Erasure:
  - Task with one Subtask using Template 2 (Rule 2 applies to all request types)
- Multi request type DSR for Access and Erasure:
  - Task with one Subtask using Template 1 for Access Request (satisfies Rule 1)
  - Task with two subtasks using Template 2 for Access and Erasure (Rule 2 applies to all request types)

### Additional cases

- If two task templates are associated with the same Data System instance and both match the Rule conditions, the system creates two subtasks under a single primary task.However, if **Name Subtasks using above Subtask Template Name** option is set to false in both Subtask templates, only one Subtask is created because both use the default name, resulting in a naming conflict.
- If the same Data System instance is linked to two task templates, where one has automation enabled and the other has it disabled, and both use default Subtask naming, only one Subtask will be created. The Subtask’s behavior may be inconsistent. It might run automation in some cases and skip it in others.

**Example**

Task templates **Automated Access Review** and **Manual Access Validation** are both linked to the same SQL Data System instance.

In this case,Securiti creates a single Subtask. Since it cannot reliably choose between the two templates’ automation settings, the Subtask may randomly behave as automated or non-automated.
  - Automated Access Review has DSR Automation enabled.
  - Manual Access Validation has DSR Automation disabled.
  - Both templates have Name Subtasks using the above Subtask Template Name set to false (uses default naming).
- When a DSR request includes multiple request types, and the Rule set matches only one type, the system creates subtasks only for that matching type. The dashboard still shows it as a multi-request DSR. For example, if a DSR includes both “Access” and “Port,” and the condition is set to **is_one_of** Access, only an “Access” Subtask is created.

![Screenshot_2025-07-01_at_7_01_32_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eed103aa-b218-9b62-61a1-abe4d5d60fee.png)
