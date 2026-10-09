---
title: "Assessment role and action eligibility"
slug: "assessment-role-and-action-eligibility"
updated: 2026-09-01T11:50:08Z
published: 2026-09-01T11:50:08Z
canonical: "helpcenter.securiti.ai/assessment-role-and-action-eligibility"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Assessment role and action eligibility

This article explains who can perform each assessment action, including cases where eligibility depends on being assigned to that specific assessment rather than holding a module-wide permission.

## Create Assessment

| Role | Internal assessment | Reassessment |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner | Yes | Yes |
| A custom role with Create Assessment | Yes | Yes |
| A reviewer on the assessment | No | Yes |

> [!NOTE]
> **Note**
> 
> A reviewer can trigger a reassessment of an assessment they review, even without the Create Assessment permission, but can't create a new internal assessment from scratch.

## Read Assessment

| Role | All assessments | Assigned only |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner | Yes | N/A |
| A custom role with Read Assessment | Yes | N/A |
| User | N/A | Yes |
| A custom role with Read Assigned Assessment | N/A | Yes |

## Delete Assessment

| Role | All assessments | Assigned only | Condition |
| --- | --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner | Yes | N/A | N/A |
| A custom role with Delete Assessment | Yes | N/A | N/A |
| User | N/A | Yes | Must be a reviewer on the assessment |
| A custom role with Delete Assigned Assessment | N/A | Yes | Must be a reviewer on the assessment |

## Update Assessment Metadata

Metadata covers the title, managing organization, due date, and linked object.

| Role | Any assessment | Assigned assessment only |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner | Yes | N/A |
| A custom role with Update Assessment Metadata | Yes | N/A |
| A reviewer on the assessment | N/A | Yes, for assessments they review |

## Update Assessment Assignment

For who you can assign as a reviewer or respondent on an assessment, see [Reviewer Respondent prerequisites](/latest/docs/reviewer-respondent-prerequisites).

| Role | Any assessment | Assigned only | Scope |
| --- | --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner | Yes | N/A | Full, even for assessments they're not part of |
| A custom role with Update Assessment Assignment | Yes | N/A | Full assignment |
| Reviewers on the assessment | N/A | Yes | Can assign or unassign both reviewers and respondents |
| Respondents on the assessment | N/A | Yes | Can add or remove respondents only |

## Apply Assessment Filters

Available to all system users except Guest, and to any custom role with Apply Assessment Filters.

## Export

| Action | Who |
| --- | --- |
| Bulk export all assessments | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, or a custom role with Read Assessment |
| Export an assessment's details as PDF | Reviewers on that assessment |

## Assessment Workflow Stages

| Action | Who |
| --- | --- |
| Read Assessment Workflow Stage | Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, or a custom role with Read Assessment Workflow Stage |
| Update Assessment Workflow Stage | Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, or a custom role with Update Assessment Workflow Stage |

## Assessment Templates

| Action | Who |
| --- | --- |
| Read Assessment Template | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, User, Vendor Assessment User, Vendor Assessment Module Owner, or a custom role with Read Assessment Template |
| Create (clone, new, or import) | Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, Vendor Assessment Module Owner, or a custom role with Create Assessment Template |
| Update and publish (sections, questions, logic, rules, launch settings) | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner, or a custom role with Update Assessment Template |
| Delete | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner, or a custom role with Delete Assessment Template |

## Assessment Notification Templates

| Action | Who |
| --- | --- |
| Read | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, or a custom role with Read Assessment Notification Template |
| Create | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, or a custom role with Create Assessment Notification Template |
| Update | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, or a custom role with Update Assessment Notification Template |
| Delete | Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, or a custom role with Delete Assessment Notification Template |

## Reference List Management

Available to all system users except Guest, and to any custom role with Update Assessment Reference List.

## Assessment Dashboard

| Role | All-assessments dashboard | Assigned-assessments dashboard |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner | Yes, full metrics | N/A |
| A custom role with View Assessment Dashboard + Read Assessment | Yes, full metrics across all assessments | N/A |
| A custom role with View Assessment Dashboard + Read Assigned Assessment | N/A | Yes, only their own assigned assessments |

For more information, see [Assessment Automation RBAC permissions](/latest/docs/assessment-automation-rbac-permissions) and [Reviewer Respondent prerequisites](/latest/docs/reviewer-respondent-prerequisites).
