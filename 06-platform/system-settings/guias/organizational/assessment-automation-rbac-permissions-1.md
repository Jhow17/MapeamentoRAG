---
title: "Assessment Automation RBAC permissions"
slug: "assessment-automation-rbac-permissions-1"
updated: 2026-09-29T07:12:31Z
published: 2026-09-29T07:12:31Z
canonical: "helpcenter.securiti.ai/assessment-automation-rbac-permissions-1"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Assessment Automation RBAC permissions

## Assessment permissions with default roles

This table shows which Assessment Automation permissions are allowed or restricted for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | Super Admin | Org Admin | Operator | DPO | Module Owner | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `Read Assigned Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Update Assigned Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Delete Assigned Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Create Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Assignment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `View Assessment Dashboard` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Review Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Read Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Create Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Assessment Workflow Stage` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Workflow Stage` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Assessment Notification Templates` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Create Assessment Notification Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Notification Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Assessment Notification Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Apply Assessment Filters` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Unmask Emails` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |

> [!NOTE]
> Note
> 
> If Guest User Unmasking is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. When enabled, guest users cannot access the assessment messaging channel. Guest users can still communicate with reviewers through the comments panel.

## Assessment permissions with custom roles

This table lists the Assessment Automation permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `Read Assigned Assessment` | Lets you view an assigned assessment, its details, questions, attachments, workflow stages, and user assignments. | None |
| `Update Assigned Assessment` | Lets you answer questions, submit an assessment, manage attachments, and modify user assignments on an assessment you're assigned to. This also includes any reviewer permission. | `Read Assigned Risks`, `Update Assigned Risk`, `Read Assigned Assessment` |
| `Delete Assigned Assessment` | Lets you delete an assessment instance only as a reviewer. | `Read Assigned Assessment` |
| `Create Assessment` | Lets you create assessments, configure reassessments, and launch assessments from templates. | `Read Assessment`, `Apply Assessment Filters` |
| `Read Assessment` | Lets you see all assessments in the system and export them in bulk. | `View All Tags`, `Read Assigned Assessment`, `Apply Assessment Filters` |
| `Delete Assessment` | Lets you delete any assessment in the system, not only ones you're assigned to. | `Read Assessment`, `Delete Assigned Assessment` |
| `Update Assessment Assignment` | Lets you add, update, or remove respondents, reviewers, and viewers on any assessment, without being assigned to it yourself. | None |
| `View Assessment Dashboard` | Lets you view aggregated assessment analytics and statistics on the dashboard. | `Read Assigned Assessment`, `View All Tags` |
| `Update Assessment Metadata` | Lets you update structural fields on an assessment: title, organization, managing organization, due date, and data-map associations. For this permission to work, you must have access to the Data Mapping Automation module. | `Read Assessment`, `View All Tags`, `Read Assigned Assessment` |
| `Review Assessment` | Lets you approve question answers, create flags and risks on questions, and cancel, hold, resume, or return an assessment. Users with this permission appear in all reviewer dropdowns including launch assessment, reviewer assignment, edit launch settings, rule engine configuration, etc. | `View All Tags`, `Apply Tags To Objects`, `Read Assigned Risk`, `Update Assigned Risk` |
| `Read Assessment Template` | Lets you view assessment templates, their questions, and configuration, and export a template as PDF. This permission also grants view access to template rules. | `View All Tags` |
| `Create Assessment Template` | Lets you create new assessment templates and clone existing ones. Also, you can import templates via CSV or JSON. However, to configure question logics, template rules, etc. you must have Update Assessment Template permission. | `Read Assessment Template` |
| `Update Assessment Template` | Lets you edit templates: questions, sections, and launch settings. | `Read Assessment Template` |
| `Delete Assessment Template` | Lets you delete assessment templates. | `Read Assessment Template` |
| `Read Assessment Workflow Stage` | Lets you view assessment workflow stage configuration. | None |
| `Update Assessment Workflow Stage` | Lets you modify workflow stages. | `Read Assessment Workflow Stage` |
| `Read Assessment Notification Template` | Lets you view assessment email notification templates. | None |
| `Create Assessment Notification Template` | Lets you clone new notification templates from a system template. | `Read Assessment Notification Template` |
| `Update Assessment Notification Template` | Lets you edit existing notification templates. | `Create Assessment Notification Template`, `Read Assessment Notification Template` |
| `Delete Assessment Notification Template` | Lets you delete notification templates. | `Read Assessment Notification Template` |
| `Apply Assessment Filters` | Lets you choose and apply different filters from the list of available properties. | None |
| `Unmask Emails` | Lets you assign view access to guest users for masked emails. | None |

> [!NOTE]
> Note
> 
> Create Assessment, Create Assessment Template, Update Assessment Template, and Delete Assessment Template also rely on a small number of internal permissions that Securiti manages automatically. These don't appear as separate options in the Roles UI, so you don't need to select them yourself.
> 
> The platform permission, View All Tags, generally apply to all listed permissions no matter if it’s not separately mentioned in the dependent column.

###
