---
title: "Customizing subtask instructions"
slug: "customizing-subtask-instructions"
updated: 2026-04-07T10:09:33Z
published: 2026-04-07T10:09:33Z
canonical: "helpcenter.securiti.ai/customizing-subtask-instructions"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Customizing subtask instructions

## Scenario

As a Data Privacy Officer, you process DSRs where each request creates subtasks across multiple data systems holding user data. Previously, subtask instructions were fixed. You could not adjust system-generated instructions, control attachment requirements, or manage how processing details were handled across subtasks. This created extra work and inconsistent outputs.

With customizable subtask instructions, you tailor instructions per request type and task. For example, in access requests, you keep processing details required where needed, while making them optional for specific systems with clear warnings. You also make attachments optional for low-risk systems and exclude internal steps from reports. This reduces manual effort and keeps reports accurate and relevant.

## Introduction

Customizable subtask instructions let you control how DSR subtasks behave across request types and data systems. These instructions act as to-do steps that guide how each subtask is completed during request processing.

You can update system instruction text, add user-defined instructions, and manage actions such as attachments, notes, and completion checks. You can also decide whether attachments or processing details are required and choose which subtasks contribute to the final report.

System subtask instructions support different levels of customization. Some can be edited or made optional, while others are fixed and cannot be disabled; the table below summarizes these variations.

> [!NOTE]
> Note
> 
> You can edit the title and description for all system subtask instructions.

| Instruction | Available in Request Type | Can be Disabled | Can Actions be Marked as Optional | Supported Actions |
| --- | --- | --- | --- | --- |
| Object & Data Element Discovery | All | No | No | System-driven (no user action) |
| Auto-generated Data Element Report | Access, Port, Erasure, Rectification, Others | No | No | View-only (system generated) |
| Data Element Report | Access, Port | Yes | Yes | Attachment, Notes |
| Data Element Report Request | Access, Port, Confirmation, Disclosure of Subprocessors | Yes | Yes | Attachment, Notes |
| Processing Details | Access | Yes | Yes | Process record selection |
| User Data Deletion | Erasure, Objection | No | No | Checkbox confirmation |
| Download Erasure Script | Erasure | No | No | Download action |
| Object & Data Element Auti-Discovery & Deletion | Erasure | No | No | System-driven |
| Data Element Deletion Request | Erasure | No | No | Attachment, Notes |
| Rectification Log | Rectification | No | No | Notes |
| Processing Restriction on Data Subject's Data | Restrict Processing, Objection | No | No | Checkbox confirmation |
| Restrict Automated Decision-making on Data Subject's Data | Restrict Automated Decision-making | No | No | Checkbox confirmation |
| Restrict Sale of Personal Information | Do Not Sell or Share | No | No | Checkbox confirmation |
| Confirm Processes | Confirmation | Yes | Yes | Checkbox confirmation |
| Confirm Presence of Data Element | Confirmation | No | No | Checkbox confirmation |
| Identify Sub-Processors | Disclosure of Subprocessors | No | No | Checkbox confirmation |
| Additional Documentation | All | Yes | Yes | Attachment, Notes |

### Configure subtask instructions

You can configure subtask instructions while setting up request types or task templates, depending on how you want instructions to apply during DSR processing.

If the required steps remain consistent across all subtasks for a request type, configure instructions at the request type level. These instructions apply to all subtasks created for that request type.

If specific tasks require different instructions, configure them at the task template level. These instructions apply only to subtasks created using that template.

You can configure subtask instructions while setting up request types or task templates.

To configure instructions for a request type, see [Creating a custom request type](/latest/docs/creating-a-custom-request-type).

To configure instructions for task templates, see [Creating and configuring task template](/latest/docs/creating-and-configuring-task-template).
