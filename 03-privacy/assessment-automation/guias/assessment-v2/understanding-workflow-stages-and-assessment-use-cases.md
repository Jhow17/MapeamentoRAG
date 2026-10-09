---
title: "Understanding Workflow Stages and assessment use cases"
slug: "understanding-workflow-stages-and-assessment-use-cases"
updated: 2026-09-22T06:35:35Z
published: 2026-09-22T06:35:35Z
canonical: "helpcenter.securiti.ai/understanding-workflow-stages-and-assessment-use-cases"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Understanding Workflow Stages and assessment use cases

**Scenario**

As a Data Compliance Officer, you're reviewing vendor assessment responses for accuracy. Manually spotting inconsistencies across documents is time-consuming and unreliable. With in-platform review tools, you flag discrepancies in real time and assign follow-up tasks to the vendor or internal teams. This ensures issues are addressed promptly and gaps are resolved before approvals proceed.

This topic describes the use cases for Workflow Stages in assessments.

### Transition to and from different assessment stages

The following assessment workflow stages show where you’re in the process of submitting and reviewing the assessments:

- **Not Started**
- **In Progress**
- **In Review**
- (Optional) **On Hold**
- (Optional) **Cancelled**
- **Complete**

The Not Started stage is visible when you first launch an assessment. The assessment moves to the In Progress stage when a respondent answers at least one question. Responses remain in *draft* denoted by a 'pencil icon' until you submit the assessment. If only one question was answered, clearing the response reverts the stage back to Not Started.

The In Review stage is when all of the respondents have *submitted* their answers and are now *pending approval* by the reviewer(s) assigned on the assessment.

You may want to put an assessment on *hold* or *cancel*. For example, if a user is on PTOs or started assessment is no longer valid because compliance requirements have changed. Securiti lets both respondents and reviewers transition an assessment to On Hold or Canceled from Not Started, In Progress and In Review stages.

![Screenshot_2025-07-11_at_2_17_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2cd448a-83d1-e0ae-9d7a-d5d250a4ec4b.png)![Screenshot_2025-07-11_at_2_16_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-474f956d-24ae-511a-e8ed-6b781660b299.png)

To pause an assessment:

1. Near the upper right corner, click **Move to > Hold**.
2. On the Put Assessment On Hold popup, enter a required reason.

![Screenshot_2025-07-11_at_2_26_15_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-30c76a4f-d1a6-89f3-00eb-7a374020b037.png)

Click **Put On-Hold**

> [!NOTE]
> **Note**
> 
> The same procedure is followed for canceling an assessment.

When paused, any scheduled reassessments and reminder or due date notifications are paused.

To resume:

1. Select **Move to > Resume**

![Screenshot_2025-07-11_at_2_29_44_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ec796a5-7716-c1df-641f-d4c5345333c4.png)

You can also cancel an On Hold assessment.
2. (Optional) Configure revised due or reminder dates.

![Screenshot_2025-07-11_at_2_30_27_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8387e42c-804b-f99a-1cfc-883be99b187e.png)

Click **Resume Assessment**. Securiti reverts the assessment to the exact stage from before.

By canceling an assessment you can longer modify its contents. You must enter a required reason and acknowledge it by marking the checkbox, as shown below.

![Screenshot_2025-07-11_at_2_48_44_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9eb3dec-093e-93da-df78-ada18e0bcf6c.png)

> [!NOTE]
> **Note**
> 
> Securiti halts any configured reassessments, email notifications or reminders.

After the reviewer(s) have approved the responses, the assessment is considered published, AKA, Complete.

Observe these caveats:

- After you have submitted your answers, the assessment is locked and is sent to the reviewers for approval.
- Once it’s sent for approval, you cannot edit or make changes to the assessment.
- Any unanswered questions can only be answered when the reviewer sends back the assessment (if an action is required from you).

> [!NOTE]
> **Note**
> 
> You can, however, collaborate with each other on assessment (questions) using the messaging channel.
- You can reassess any canceled assessment but after it's moved to cancel, you can't reopen it.

To learn about what Securiti Assessments lifecycle can help you achieve, refer to [Internal Assessments overview](https://securiti.ai/videos/internal-assessment-automation/) video.

### Add and manage assessment comments

You can add and track comments directly within assessments at any stage of the assessment lifecycle, including during On Hold, Canceled, and Complete stages. See the table below for all the use cases.

| Use case | Description |
| --- | --- |
| Adding a comment | 1. Click **Comments** on the assessment toolbar. Securiti opens the comments panel on the right side of the page. 2. Enter your feedback in the text box. 3. Click the **Post Comment (blue arrow icon)** to submit your comment. The “Comments” badge shows the number of unread comments. This count disappears once the comments are viewed. |
| Controlling comment visibility | You have options for controlling who can see your comments: - *Public Comments -* Reviewers have the option to comment publicly or privately. With "All" selected in the comments panel, your comments are visible to all assigned users on the assessment (respondents and reviewers). - *Private Comments -* Reviewers can restrict comments to other reviewers only. - To draft a comment privately, select **Reviewers Only** in the comments panel before posting. - To change the visibility of a posted comment, click the **Options (three vertical dots)** next to the comment and select **Set To Private**. - To make a private comment visible to everyone again, click options and choose **Make Public**. - (Optional) You can enable the "Show Private Only" toggle in the panel to view all private comments in one place. |
| Editing, deleting, and tagging | - *Edit or Delete -* To manage an existing comment, click the **Options (three vertical dots)** next to the comment, and select **Edit Comment** or **Delete**. - *Tagging Users -* For larger assessments, you can notify individuals by typing the @ symbol and selecting their name to "@mention" them in a comment. |

### Add risks

Reviewers can assign new risks or update triggered risks configured via template. For more information, see [create and edit risks in Risk V2](/latest/docs/create-risks-using-the-risk-register).

> [!NOTE]
> Note
> 
> Reviewer only questions also entail risks.

To add risk to the assessment:

1. Click the ‘Set Risk’ icon below the question.
2. Add or edit the following:

![Assessment interface displaying risk levels, descriptions, and user input sections for evaluation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-24 at 4.21.24 PM.png)

After you're done, click **Submit**.
  1. Risk Level - choose from the linear or matrix risk.
  2. (Optional) Risk Description
  3. (Optional) Recommendation
  4. Set Risk Owner(s)

> [!NOTE]
> **Note**
> 
> Reviewers can assign risk to a guest user by entering their email in the **Risk Owner** field and they can, in turn, assign it to other guest users.
  5. (Optional) Set Risk Reviewer(s)
  6. (Optional) Set Review Deadline \ Workflow
3. Securiti shows you the risk details, as shown below.

![Screenshot 2026-04-24 at 1.22.59 PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot%202026-04-24%20at%201.22.59%E2%80%AFPM.png)

As a reviewer, you may want to add some context to the risk or change fields like risk owner. Securiti lets you edit the risk and you can also remove it, if not required.
4. To propose remediation or request exception, see [Pending Actions](/latest/docs/navigating-the-risk-details-page#pending-actions).
5. To view all assigned risks, In the assessment toolbar, click **Risks** which also shows you the count. Securiti opens up the Risks panel to the right, as shown below.
6. In addition to showing which sections entail risks, Securiti provides an aggregate view of inherent and residual risks for the assessment. In this example, both inherent and residual risks have the same value.

![Assessment interface showing very high risk status and detailed risk breakdown information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-24 at 1.26.10 PM.png)

The aggregate values reflect the aggregation methodology set in Risk Settings. Available methodologies are Mean, Median, and Maximum. For more information, see [Configuring risk settings in V2](/latest/docs/configuring-settings-in-risk-v2#risk-aggregation-methodology).

> [!NOTE]
> **Note**
> 
> Risks are not visible to respondents both at the question level and in the Risks panel.

### Assign flags

> [!NOTE]
> **Note**
> 
> With the [Two Step Review Workflow](/v1/docs/configuring-workflow-settings-custom-stages-in-assessments), privacy reviewers can create flags or assign risks while an assessment is in secondary review, and legal reviewers have the same capabilities when it's in primary review. For more information on Two Step Review assessments, see [here](/v1/docs/answering-assessment-questions-in-securiti#answer-two-step-review-workflow-assessment-questions).
> 
> In multi-respondent assessments, flags added or risks assigned by reviewers aren't visible to respondents immediately since the Stage type is In Review. Only after respondents refresh the page, they can view them. For more information on Multiple Respondents assessments, see [here](/v1/docs/answering-assessment-questions-in-securiti#answer-multirespondent-assessment-questions).

After the respondent submits the assessment, reviewers can flag questions. For example, you want the respondent to provide more information.

To add and view flags:

> [!NOTE]
> **Note**
> 
> Reviewers can add, remove, or resolve flags at any assessment stage. Flagged questions are denoted by a “red flag” across the assessment. In "reviewer only" questions, flags do not apply.
> 
> Respondents can:
> 
> - Resolve flags
> - Add explanation while resolving.
> - Add or edit attachments when resolving flags.
> 
> Respondents can't:
> 
> - Export a (completed) assessment.
> - Create a new flag.
> - Edit or submit a draft flag (including due date and attachments on a draft flag).
> - Delete a flag

1. Click the **Flag Question** icon below the question and enter a description.
2. (Optional) Select a deadline for the flag resolution, add any attachments, or click **Delete Flag**.

![Screenshot_2025-07-14_at_11_08_30_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0fc016e-4e95-617c-0df6-531f37cbbe43.png)

Click **Submit**. After the risk is created the status changes to 'Flagged', as shown below.

![Screenshot_2025-07-14_at_11_15_26_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0a3c290-c408-442c-6dcc-9c64bebb5e5a.png)
3. In the upper left corner, on the assessment toolbar, the “Open Flags” badge strictly shows the unresolved flags count.

![Overview of assessment details including filters, flags, attachments, and review progress.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/open_flags.png) Click to open the Open Flags panel on the right containing both in review and resolved flags. You can use the panel to jump to the relevant question to address unresolved flags.

Toggling on "Show Resolved" filters information by already resolved flags.

![Screenshot_2025-07-14_at_11_25_05_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5a2c640f-ac4b-0e24-8bcf-011150510191.png)

Sending back the assessment now enables the respondents to come and address the flags.

![Screenshot_2025-07-14_at_11_36_28_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07ac19ad-5fc1-5e9f-dba9-0c6453559389.png)

> [!NOTE]
> **Note**
> 
> Reviewers can reopen the flag if they want by adding a note.

- Respondents are notified via email that an assessment was flagged or a risk was created, and requires attention. Reviewers can assign, remove and approve remediation or exception in both On Hold and Canceled stages.
- When In Review, the email notifying about flags is bundled into a single Send Back email. It includes all flags added by the reviewer. However, when the assessment is In Progress, and reviewer adds a flag, individual emails are sent for every flag created.

> [!NOTE]
> Note
> 
> We recommend adding flags when the assessment is in In Review stage to suppress multiple emails and collate all the flags into a single email.
- When flagging a question, the owner is any respondent already assigned to that question. You can’t assign separate respondents for that flag.

### Reassessment and related assessments

The only way to edit a completed or canceled assessment is to reassess. Securiti creates an assessment with a unique ID. For example, when you reassess assessment *35115*, a new version, *35117* is created. Typically, you can perform reassessment at any stage.

To reassess and access existing records for the same assessment:

1. From the **Actions** menu, select Reassessment **Configuration**.

![Screenshot_2025-07-14_at_1_41_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f44ea39-17d5-992d-9b36-81a49cb16eaf.png)
2. On the popup, select **Schedule Reassessment** or **Reassess Now**.

![Screenshot_2025-07-14_at_1_40_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9c396883-d37e-b43e-511e-9c235283746e.png)

Disable the **Include last approved responses** toggle and click **Start**.

> [!NOTE]
> **Note**
> 
> Including last approved responses carry forward answers from the previous assessment. For scheduled reassessments, they are initiated on the date and time of your choosing.
3. To view past associations, select **Actions menu > View Related Assessments**. Securiti opens up a side panel to the right with details, as shown below.

![Screenshot_2025-07-14_at_1_41_05_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-15aa19d7-5c4a-16c3-979f-83152307278e.png)

![Screenshot_2025-07-14_at_1_42_47_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2c377486-b8f5-809c-2b0f-f87de3c3cdf9.png)

For more information, see the following topics:

- [Answering assessment questions in](/v1/docs/answering-assessment-questions-in-securiti) Securiti
- [Tracking Assessment Stages](/v1/docs/tracking-assessment-stages)
- [Assessment V2 system and message digest email notifications](/v1/docs/assessment-v2-system-and-message-digest-email-notifications)

The Send Back in Assessment V2 means the Reviewer has requested more information from the Respondent. It could be because the assessment responses submitted had incomplete information or showed a security vulnerability.

At this point, the Respondent attaches (where applicable) necessary evidence, adds supplementary information to support their answers, and resubmits. If the Reviewer then assesses the risk to be minimized or the argument supplied is enough to validate the assessment complete, they approve it.

Reassessing an assessment lets you identify changes in regulatory compliance and organizational behaviors. As a Question Owner, you can modify the reassessment by filling in new responses or resubmitting previous answers. Where response option(s) are modified, the question is treated as new with no answers.

## Related

- [Answering assessment questions in Securiti](/answering-assessment-questions-in-securiti.md)
