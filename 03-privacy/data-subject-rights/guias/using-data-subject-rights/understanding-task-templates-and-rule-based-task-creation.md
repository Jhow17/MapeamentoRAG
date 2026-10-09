---
title: "Understanding task templates and rule-based task creation"
slug: "understanding-task-templates-and-rule-based-task-creation"
status: "update"
updated: 2026-05-25T01:35:03Z
published: 2026-06-23T07:20:01Z
canonical: "helpcenter.securiti.ai/understanding-task-templates-and-rule-based-task-creation"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Understanding task templates and rule-based task creation

**Scenario**

As a Data Privacy Officer, you need to manage incoming DSR requests across multiple jurisdictions. Manually deciding which tasks to assign and to whom slows you down. While workflows module helps configure custom DSR tasks in the workbench, maintaining them becomes difficult as conditions grow more complex. By using task templates and rules, you can setup task templates once and trigger them automatically based on region, data system or DSR request details. This reduces manual effort, ensures correct ownership, and helps you stay compliant without constantly adjusting workflows.

### Overview

Securiti lets you create tasks within the DSR workbench using either robotic automation or predefined workflows. However, you can’t create tasks based on request type, jurisdiction, data subject type or other conditions. Also for system request types, you can’t create a task unless it’s tied to a data system, limiting flexibility when the task involves legal review, manual steps, or internal validation.

#### Task templates

To handle all these scenarios, Securiti lets you manage task creation and the task lifecycle in a more structured, scalable way. It lets you:

- Create reusable task templates that trigger automatically to create tasks when rule conditions defined in the DSR form configuration are met.
- Create tasks without linking them to a data system, and define one or multiple subtasks under each task. This supports legal reviews, manual steps, or internal validations that aren’t system-specific.
- Create tasks without running robotic automation, even when they are linked to data systems. This setup supports system-specific internal validations that go beyond automatically retrieving data from those systems.
- Reduce manual effort by scaling task creation through templates and rule-based logic reducing the need to configure individual workflows.
- Name tasks and subtasks to match your internal requirements.
- Assign subtasks to specific users or automatically assign them based on your workflow.
- Set deadlines for subtasks.

#### Rules

Rules let you control when a task template applies to a DSR request. A rule defined on DSR forms can include multiple conditions, such as request type, data subject type, jurisdiction, or custom form values. All conditions must be met for the rule to apply to a specific DSR request.

For instance, trigger a task when the request type is "Erasure", the jurisdiction is "GDPR", and the data subject type is "Customer". This ensures only relevant tasks run for European customer deletion requests.
