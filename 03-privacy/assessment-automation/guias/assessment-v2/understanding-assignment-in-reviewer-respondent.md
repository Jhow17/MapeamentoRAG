---
title: "Understanding assignment in Reviewer Respondent"
slug: "understanding-assignment-in-reviewer-respondent"
updated: 2026-06-16T06:29:27Z
published: 2026-06-16T06:29:27Z
canonical: "helpcenter.securiti.ai/understanding-assignment-in-reviewer-respondent"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Understanding assignment in Reviewer Respondent

Assessment information from the existing assessments (completed or in progress) is automatically updated from the Owner Collaborator Framework to Reviewer Respondent. The difference in assignments from V1 to V2 is outlined in the role mapping table below.

| Before (V1) | After (V2) | Notes (If any) |
| --- | --- | --- |
| Assessment Owner (System) | Reviewer | Additionally, a Respondent in the case where they're a question owner. |
| Assessment Owner (Guest) | Respondent | For assessments created via SSP (Self Service Portal) |
| Collaborator | Respondent |  |
| Question Owner | Respondent |  |
| Mandatory Approver | Reviewer | Marked as Mandatory Reviewer |
| Risk Owner | Risk Owner | No changes |

For the `Data Conversion` process, observe these caveats:

1. **Tenant Upgrade**

When enabling the Reviewer Respondent functionality in tenants with data, tenants are temporarily inaccessible to users to prevent assessment data from being created or modified during the upgrade process.

This feature is designed in such a way that no existing data is manipulated in any way, which means that Securiti uses the beginning of the upgrade window as a restore point.

After the upgrade process is completed, Securiti validates the integrity of the data through a series of automated checks and restores access to the tenant users if all checks have passed.

> [!NOTE]
> **Note**
> 
> Once additional assessment data is added, you can’t perform a rollback without losing data that was added after the upgrade.
2. **Tenant Rollback**

During the upgrade process, if any of the automated checks do not pass, the feature is disabled and rolls back to the pre-upgrade restore point. The upgrade process is rescheduled while Securiti analyzes the root cause of any such issues.

The feature comparison table below outlines key out-of-the-box differences between Assessment V1 and Assessment V2.

| V1 | V2 | Notes (If any) |
| --- | --- | --- |
| No assessment stage tracking | Includes [workflow stages](/v1/docs/understanding-workflow-stages-and-assessment-use-cases) |  |
| No assessments grid customization | Includes [column configuration](/latest/docs/using-the-internal-assessments-list-view#to-configure-columns) |  |
| No pre-assessment launch configuration | Includes [launch assessment modal](/v1/docs/launching-a-new-assessment-in-securiti) |  |
| No setting for template defaults | Includes [template launch settings](/v1/docs/using-the-assessment-launch-settings) |  |
| No new APIs support | Supports new [APIs](/v1/docs/assessments-api-reference) | Additionally, supported V1 APIs are backward compatible. |

For more information, see [Working with Reviewer Respondent](/v1/docs/working-with-reviewer-respondent) .

The term Reviewer is specific to V2 assessments who can review and approve assessments. Previously, referred to as Owner/Co-owner in the V1 world. There can be multiple reviewers on the assessment, similar to how there can be owners and co-owners. Super Admin, Org Admin, Operator, Module Owner, and DPO can all act as and can be assigned a Reviewer role. Additionally, any Mandatory Approver is referred to as a Mandatory Reviewer.

The term Respondent is specific to V2 assessments who can answer and submit assessments. It refers to the user who was previously a Collaborator in the V1 world. Multiple respondents can be added to the assessment, similar to how more than one collaborator can be added. Also, a Guest User can be added as a Respondent.

## Related

- [Section & question assignment in Assessment Automation](/section-question-assignment-in-assessment-automation.md)
