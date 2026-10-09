---
title: "Understanding tasks and subtasks"
slug: "understanding-tasks-and-subtasks"
updated: 2026-01-14T08:09:32Z
published: 2026-01-14T08:09:32Z
canonical: "helpcenter.securiti.ai/understanding-tasks-and-subtasks"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Understanding tasks and subtasks

When Securiti accepts a DSR request, it immediately starts automation that checks your data systems for personal data corresponding to the data subject. Securiti then produces a set of tasks and subtasks that break the DSR request down into manageable chunks as shown in the table below:

| Data System type | Tasks | Subtasks |
| --- | --- | --- |
| Monitored - Unstructured | One task for each data system in which the personal data was found | One subtask per request type for each object (typically a file) containing the personal data of the data subject |
| Monitored - Structured | One task for each data system in which the personal data was found | One subtask per request type for each task |
| Monitored - Scanless | One for each data system in which the personal data was found | One subtask per request type for each task |
| User-defined | One task for each data system in which the personal data was found | One subtask per request type for each task |
| Unmonitored | One task for each data system | One subtask per request type for each task |

Initially, all tasks and subtasks are assigned to the owners and co-owners of the data systems from which the tasks originated. Those data system owners can accomplish the subtasks themselves, or they can delegate them by reassigning them to other Securiti users. See [Manually assigning DSR request subtasks](/v1/docs/manually-assigning-dsr-request-subtasks) for more information.

Once all of the DSR request subtasks have been completed and submitted, Securiti automatically generates a report for the data subject and marks the request closed.
