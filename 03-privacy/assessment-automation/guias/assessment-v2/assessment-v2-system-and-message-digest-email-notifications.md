---
title: "Assessment V2 system and message digest email notifications"
slug: "assessment-v2-system-and-message-digest-email-notifications"
updated: 2026-08-03T07:17:13Z
published: 2026-08-03T07:17:13Z
canonical: "helpcenter.securiti.ai/assessment-v2-system-and-message-digest-email-notifications"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Assessment V2 system and message digest email notifications

This topic contains information about the system and message digest email notifications in Assessments (Reviewer Respondent Framework). See the table below:

> [!NOTE]
> **Note**
> 
> Securiti sends message digest email notifications if you've configured **Message Digest** to **Periodically** or **Daily** in the profile settings.
> 
> Email notifications for non-digest messages are always sent.
> 
> Observe these caveats for risk notifications:
> 
> - With the digest enabled, Securiti consolidates multiple risk notifications into a single email occurring at the same time for one user. The email subject reads "Risk(s) are ready for you to review."
> - With the digest disabled, Securiti sends separate emails for each risk. The email subject reads "A risk is ready for you to review."

> [!NOTE]
> **Important**
> 
> If a Reviewer (current logged in user) is also a Respondent (same user) on the assessment, question, or section, Securiti doesn't notify when you resend the assessment link (notification use case *3* in the table).
> 
> For more information on email notifications when *launching an assessment*, see the section [below](/v1/docs/assessment-v2-system-and-message-digest-email-notifications#email-notifications-on-launch-assessment).

| Notification use case | Notification type | Affects assessment | Notifies | System (portal) notifications | Ability to customize email | From where on the UI | Subject | Message digest |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1. Add a reviewer to the assessment | Assessment Reviewer Email | All assessment types | Reviewer | Yes | No | Launch Assessment popup | “You have been assigned as a reviewer.” | No |
| 2. Add respondent to the assessment | Assessment Respondent email | No impact | Respondent | No | Yes | Launch Assessment popup | “invites you to collaborate on” | No |
| 3. Re-send assessment invite | Assessment Respondent email | No impact | Respondent | No | Yes | Assessment details view | “invites you to collaborate on” | No |
| 4. Assign questions to the respondent | Question assignment | All assessment types | Respondent | Yes | No | Assessment details view | “has assigned you...“ | No |
| 5. Assign sections to respondent | Section assignment | All assessment types | Respondent | No | No | Assessment details view | “has assigned you...“ | No |
| 6. The Reviewer sends back responses | Send Back email | All assessment types | Respondent | Yes | No | Assessment details view | "has been sent back." | No |
| 7. Notifies before seven days of the scheduled reassessment date | Reassess Reminder before seven days | All assessment types | Reviewer and Respondent | No | No | Assessment details view |  | No |
| 8. Upon reassessing the assessment | Reassess now | All assessment types | Reviewer and Respondent | Yes | No | Assessment details view | “is refreshed with new responses.” | No |
| 9. Assigning risk | Risk assignment | All assessment types | Risk owner | Yes | No | Assessment details view | Message digest disabled or enabled: “You have been assigned as a risk owner.” > [!NOTE] > Note > > Risk owner notification fires when a risk is assigned during review. This can happen before the assessment reaches Complete stage, and is independent of assessment completion status. |  |
| 10. Upon proposing remediation / requesting exception in the risk cycle | Risk flagged (Propose Remediation or Request Exception) | All assessment types | Reviewer | Yes | No | Assessment details view | Message digest disabled: "A risk is ready for you to review." Message digest enabled: "Risk(s) are ready for you to review." |  |
| 11. Upon rejecting the remediation/ exception | Risk rejection | All assessment types | Risk owner | Yes | No | Assessment details view | Message digest disabled: “Your risk response has been rejected.” Messages digest enabled: "Your risk response(s) has been rejected." |  |
| 12. Assigning flag | Flag assignment | All assessment types | Flag owner | No | No | Assessment details view | “You have been assigned a Flag for Review.” | No |
| 13. Notifies after unflagging the flag | Flag unflagging | All assessment types | Flag owner | No | No | Assessment details view | “A Flag for Review has been Unflagged.” | No |
| 14. The user is notified periodically (if the digest is enabled) for a new comment or mention on the assessment. It also includes the Messaging Channel notifications. | Message notification email | All assessment types |  | No | No | Assessment details view | Securiti email digest | Yes |
| 15. Notifies of the approved assessment | Assessment completion email | All assessment types | Reviewer | No | No | Assessment details view | "has been completed." | No |
| 16. Bulk exporting assessments | Assessment details export (bulk export) | All assessment types | Assessment owner | No | No | Internal/Vendor Assessment list view | "Details Export" | No |
| 17. Bulk exporting assessments | Assessment summary export (bulk export) | All assessment types | Assessment owner | No | No | Internal/Vendor Assessment list view | "Summary Export" | No |
| 18. Upon exporting the assessment | Assessment export | All assessment types | Reviewer | No | No | Assessment details view | "Export" | No |
| 19. After sending an approval reminder to the mandatory approver | Mandatory Approval Approver Reminder email | All assessment types | Reviewer with mandatory approver permission | No | No | Assessment details view | "Approval Reminder" | No |
| 20. Notifies of the due date approaching | Question due date | All assessment types | Respondent | No | No | Assessment details view | "You have unanswered questions in..." | Yes |
| 21. The assessment owner is notified | Assessment approval email | All assessment types | Reviewer | No | No | Assessment details view | "Recent assessments have been approved." | Yes |
| 22. The assessment owner is notified | Assessment deletion | All assessment types | Assessment owner | No | No | Internal/Vendor Assessments list view | "assessments have been Deleted" | Yes |
| 23. Upon proposing remediation / requesting exception in the risk cycle | [Multiple risks] Risk flagged (Propose Remediation or Request Exception) | All assessment types | Reviewer | No | No | Assessment details view | "Risk(s) are ready for you to review." | Yes |
| 24. Respondent submits the assessment | Assessment submission notification email | All assessment types | Reviewer | No | No | Assessment details view | "has been completed" | No |
| 25. Respondent resubmits the assessment | Resubmit Assessment | All assessment types | Reviewer | No | No | Assessment details view | "has been resubmitted" | No |

Additionally, Securiti generates portal notifications for the following actions:

- Assessment creation notification
- Multiple question assignment notification
- Question respondent reassignment notification
- Remove reviewer notification (notifies Question Owner)
- Message notifications
- Chat mention notification

### Email notifications on Launch Assessment

| Use case# | User role (un)assigned based on logged in tenant | Email notification(s) |
| --- | --- | --- |
| 1 | Logged in user is both the Reviewer and Respondent | Securiti does not send email notifications. |
| 2 | Logged in user is the Reviewer but the Respondent is a different user | Securiti sends an invite email to the Respondent to collaborate on the assessment. |
| 3 | Logged in user is the Respondent but the Reviewer is a different user. | Securiti notifies the Reviewer via email that an assessment [name] was assigned to you. |
| 4 | Logged in user is neither the Reviewer nor Respondent | Securiti sends out email notifications to the relevant Reviewer(s) and Respondent(s). |

The term Reviewer is specific to V2 assessments who can review and approve assessments. Previously, referred to as Owner/Co-owner in the V1 world. There can be multiple reviewers on the assessment, similar to how there can be owners and co-owners. Super Admin, Org Admin, Operator, Module Owner, and DPO can all act as and can be assigned a Reviewer role. Additionally, any Mandatory Approver is referred to as a Mandatory Reviewer.

The term Respondent is specific to V2 assessments who can answer and submit assessments. It refers to the user who was previously a Collaborator in the V1 world. Multiple respondents can be added to the assessment, similar to how more than one collaborator can be added. Also, a Guest User can be added as a Respondent.

The Send Back in Assessment V2 means the Reviewer has requested more information from the Respondent. It could be because the assessment responses submitted had incomplete information or showed a security vulnerability.

At this point, the Respondent attaches (where applicable) necessary evidence, adds supplementary information to support their answers, and resubmits. If the Reviewer then assesses the risk to be minimized or the argument supplied is enough to validate the assessment complete, they approve it.

## Related

- [Understanding Workflow Stages and assessment use cases](/understanding-workflow-stages-and-assessment-use-cases.md)
