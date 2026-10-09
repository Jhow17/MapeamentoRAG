---
title: "Assessments release notes"
slug: "assessments-release-notes"
updated: 2026-09-28T21:00:00Z
published: 2026-09-28T21:00:00Z
canonical: "helpcenter.securiti.ai/assessments-release-notes"
area: privacy
modulo: assessment-automation
tipo: release
data_captura: 2026-10-08
---

# Assessments release notes

## 1.151

### Patch 1 updates - September 2026

#### Resolved issue

- Fixed an issue where guest users in the Self-Service Portal could see all assessments across the organization, even when not assigned as a respondent, reviewer, or approver. Guest users are now limited to viewing only the assessments they are assigned to (PRIV-262557).

### Release updates - September 2026

No updates

---

## 1.150

### Patch 2 updates - September 2026

#### Resolved issue

- Fixed an issue where risks created in a vendor assessment did not appear on the vendor’s **Risk** tab in Data Maps (PRIV-241405).

### Release updates - August 2026

#### Introducing RBAC v2 for Assessment Automation and Vendor Assessment

Securiti has introduced Role-Based Access Control (RBAC) v2 for Assessment Automation and Vendor Assessment. This replaces hardcoded role checks with fine-grained, action-based permissions, so you can build custom roles scoped to exactly what each job needs. The new permissions cover assessment templates, questions, responses, and risk settings. Previously, only Access Profiles governed access to these modules. You can now select granular permissions for actions such as viewing, creating, or approving assessments and risks.

For more information, see [Assessment RBAC permissions](/latest/docs/assessment-automation-rbac-permissions) and [Vendor RBAC permissions](/latest/docs/vendor-assessments-rbac-permissions).

#### Resolved issue

- Fixed an issue where Securiti remove spaces from an attachment's file name on upload at the assessment level (PRIV-248021).

---

## 1.149

### Release updates - August 2026

#### Pre-tagging risks in assessment template logic

Securiti now lets template admins pre-select tags when adding a risk in the assessment template logic. When a risk is triggered from the template, tags are automatically assigned to it. You can further edit tags after the risk is created. These are shown in the Risk Register list after you enable tags from the column selector.

For more information, see [Creating question logics in assessment template](/latest/docs/creating-question-logics-in-assessment-template).

#### Risk rating by template tag now shown in assessment details panel

Securiti now shows risk rating by template tag in the assessment details panel. Previously, this information was visible in the risk tab under Assessment V2.

#### Resolved issue

- Fixed an issue where the assessments list displayed duplicate records when navigating between pages with the Reviewer filter applied and sorted by Stage (PRIV-245048).
- Fixed an issue where vendor assessments did not support custom workflow stages and internal notes. When a vendor assessment template was configured with a multi-stage approval workflow, the launched assessment fell back to a basic approval flow instead of applying the configured stages (PRIV-247338).

> [!NOTE]
> Note
> 
> If Custom Stages feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

---

## 1.148

### Release updates - July 2026

#### Assessment attachments improvements

Securiti now shows flag attachments in the Assessment Attachments panel alongside other attachment types. Users can also download all attachments in an assessment at once using the Download All option. For more information, see [Attachments panel](/latest/docs/managing-assessment-files-using-attachments#navigating-the-attachments-panel).

#### SSP Assessments list revamp

Securiti now has a new layout for the SSP Assessments list. The page includes a search bar and supports default sort by Due Date as well as Assessment ID.

Also, SSP users can use quick filters: Stage, Overdue status, and Template to narrow assessments. A default filter is in place for Not Started and In Progress assessment stages but you can modify it to suit.

For more information, see [Self-Service Portal](/latest/docs/start-an-assessment).

#### API updates

Use the following table to understand the API updates made for Assessment Automation in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/user/assessments?ref=asmtListFilter` `/privaci/v1/user/assessments?ref=assessmentsList` | GET | - Removed `response_counts` from the assessment list response. - Trimmed `assessment_stats` to only include `total_active_questions`. Removed `answered_question_count`, `approved_question_count`, `rejected_question_count`, and `total_skipped_questions`. - Removed `total_mandatory_answered`, `total_mandatory_approved`, `total_mandatory_questions`, `total_questions`, `user_agnostic_total_mandatory_approved`, and `user_agnostic_total_mandatory_questions` from the assessment list response. |

#### Resolved issues

- Fixed an issue where users with the User Assessment role received a "user does not have Read Workflow permission" error when clicking Set a Risk on an assessment question (PRIV-246328).
- Fixed an issue where risk notification emails displayed raw HTML tags such as `&lt;p&gt;&lt;/p&gt;` in the Activity Description when a risk owner proposed a remediation or requested an exception (PRIV-240342).
- Fixed an issue where a two-step review assessment with a mandatory reviewer moved back to In Review retained its completion date (PRIV-243193).

---

## 1.147

### Patch 1 updates - June 2026

#### API updates

Use the following table to understand the API updates made for Assessment Automation in this patch:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/user/assessments/start/v2` | POST | - Added `mandatory` property to the `reviewers` object. When set to `true`, the reviewer's approval is required before the assessment can proceed to the next stage. - Added `stages` property to the `reviewers` object to support assigning reviewers to specific workflow stages in a 2-step reviewer workflow. |
| `/privaci/v1/user/assessments/{assessmentID}/user` | PATCH | - Added `stages` property to the `reviewers` object to align with 2-step reviewer workflow support. |

### Release updates - June 2026

#### Migration to V2 tenants

We have now migrated all V1 tenants to V2 which is our latest and more robust assessment solution. If you were previously on V1, with the release 1.147, Securiti automatically upgrades you to V2.

For more information, see [Upgrading from Assessment V1](/latest/docs/upgrading-from-assessment-v1-v1v2-comparison) and [Reviewer Respondent Assignment in V2](/latest/docs/understanding-assignment-in-reviewer-respondent).

#### Response % in assessments

Securiti now shows the Response % column in the assessments list view. It is also available as a filter. Use the column selector to show or hide it from the assessment grid and filter assessments by providing a numeric value for the Response %.

Additionally, the response progress is included in the bulk summary report. For more information, see [Assessments list](/latest/docs/using-the-internal-assessments-list-view) and [Assessment exports](/latest/docs/assessments-list-search-and-exports).

#### API updates

Use the following table to understand the API updates made for Assessment Automation in this release:

| Endpoint | Method | What’s changed |
| --- | --- | --- |
| `/privaci/v1/user/assessments?ref=asmtListFilter` | GET | - Updated `stage` filter documentation to remove integer enum mappings. - Added `stage__code` filter to support filtering assessments by stage code (`NOT_STARTED`, `IN_PROGRESS`, `IN_REVIEW`, `COMPLETE`, `ON_HOLD`, `CANCELLED`). - Added `progress_percent` filter to support filtering assessments by response completion percentage. - Updated `due_date` filter to include the `due_date__lt` operator. To fetch overdue assessments, pass `due_date__lt` with the current time in ms as the value. Removed the separate Overdue filter entry. |

#### Resolved issues

- Fixed an issue where spaces in attachment file names were removed upon upload in assessments (PRIV-242283).
- Fixed an issue where the Due Date Configuration popup in assessment details with no due date set displayed a default date automatically. This caused the Clear Configuration option to appear non-functional, as the pre-populated date persisted even after clearing (PRIV-242695).
- Fixed an issue where selecting an assessment-generated vendor object in Vendor Assessment Automation caused a 500 server error (PRIV-244523).
