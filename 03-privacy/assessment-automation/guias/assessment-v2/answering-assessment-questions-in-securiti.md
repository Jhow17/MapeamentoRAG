---
title: "Answering assessment questions in Securiti"
slug: "answering-assessment-questions-in-securiti"
updated: 2026-08-28T14:04:10Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/answering-assessment-questions-in-securiti"
stale: true
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Answering assessment questions in Securiti

**Scenario**

As a Data Compliance Officer, you're responsible for evaluating assessments. Manually reviewing every response is time-consuming, and critical risks may go unnoticed. With flagged responses highlighted, you focus on potential issues, assign appropriate risk ratings, and provide feedback for mitigation. This targeted review process helps you manage risks proactively and maintain compliance standards. If you’re working with a vendor team, you're tasked with validating compliance documentation during onboarding. Without a shared platform, updates get lost in emails and responses lack detail. By collaborating directly in the assessment, your team uploads required documents and answers questions thoroughly. This ensures complete submissions and alignment with contractual requirements.

The topic contains information on answering the following V2 assessment types:

- [Regular assessments](/v1/docs/answering-assessment-questions-in-securiti#answer-regular-assessment-questions)
- [Multiple respondents](/v1/docs/answering-assessment-questions-in-securiti#answer-multirespondent-assessment-questions)
- [Two Step Review Workflow](/v1/docs/answering-assessment-questions-in-securiti#answer-two-step-review-workflow-assessment-questions)
- [Object and Field](/v1/docs/answering-assessment-questions-in-securiti#answer-object-and-field-assessment-questions)

To learn about what fulfilling a Securiti Assessment helps you achieve, refer to [Internal Assessments overview](https://securiti.ai/videos/internal-assessment-automation/) video.

## Understanding Assessment details

### 

After you launch an assessment, use the following tools on the assessment details view to navigate and perform the necessary steps in the assessment.

| Common UI Element | Description |
| --- | --- |
| Assessment header | Securiti shows you the Title, Stage type and Stage, Submit button, Move to, Details, and Actions menus. - **Assessment title** - The name of your assessment. - **Stage type** - Assessment workflow stage such as Not Started, In Review, etc. **Stage** (label) - Stage labels you have configured in [workflow settings](/v1/docs/configuring-workflow-settings-custom-stages-in-assessments). In the Two Step Review Workflow, for example, the badge may show Primary Review, Legal Review, etc. For more information, see [Understanding Workflow Stages and assessment use cases](/v1/docs/understanding-workflow-stages-and-assessment-use-cases). - **Submit** - Click to the submit the assessment. - **Move to** - Securiti shows “On Hold” and “Cancel” options. “Approve” and “Send Back” options become visible when stage is In Review. - **Details** menu - Shows items such as Id, Regulation, Response, Submission, and Review progress, Associated Workflow, Assignees for In Progress and In Review stages, etc. > [!NOTE] > Note > > Risk rating is also shown under Details for completed assessments where rating logic is configured. - **Actions** menu - Shows options such as View Related Assessments, Reassessment Configuration, Linked Objects, Export and Delete assessment, etc. For information on linking assessments to data mapping object or removing exisiting associations, see [Enriching existing data mapping objects with assessments](/v1/docs/enriching-existing-data-mapping-objects-with-assessments). > [!NOTE] > **Note** > > The Actions menu always shows for reviewers. For assessments that are not started or in progress, only respondents with super admin rights can see it. > [!WARNING] > Important > > Deleting an assessment requires admin or assessment owner roles. Once deleted, you can't retrieve assessment data or restore it so proceed with caution. |
| Assessment toolbar | Securiti shows you Filters, Flags, Attachments, Risks, Overall and Mandatory progress, Review Progress, and All Assignees. - **Open Flags** - The badge count strictly shows unresolved flags. Click to view information about both unresolved and resolved flags. You can sort resolved flags by enabling the Show Resolved toggle. - **Attachments** - The badge count show all attachments. Click to view information about attachments in the assessment. For more information, see [Managing assessment files using Attachments](/v1/docs/managing-assessment-files-using-attachments). - **Risks** - The badge count shows all risks. Click to view information about risks associated with the assessment. - **Overall** - Shows the progress for overall assessment answered. - **Mandatory** - Shows the progress for mandatory questions answered. - **Review Progress** (visible when stage In Review) - Shows the progress for assessment questions reviewed. - **All Assignees** - Clicking the avatars show the reviewers and respondents assigned to the assessments. Click the **Edit user** icon next to it to open the **Assign Sections and Questions Permissions** popup. For more information, see [Section and question level assignment](/v1/docs/section-question-assignment-in-assessment-automation). |
| Understanding Readiness Ratings (scores show for assessments with readiness rating) | The overall readiness rating (percentage) summarizes readiness to ensure data security. For an assessment, it is calculated based on the total score of the responses divided by the number of applicable questions. Applicable assessment questions mean multi-choice or those using conditional logic (Set Rating configured on the question response). Only the revealed and answered questions are counted in the denominator. The score is determined by assigning point values to the responses. - **Compliant**: 1 point - **Partially compliant**: 0.5 points - **Non-compliant**: 0 points - **N/A**: Not counted in the denominator For example, if an assessment has five questions with responses yielding a total score of 2.5 and four applicable questions, Securiti would calculate the Readiness Rating as follows: 2.5 (total score) divided by 4 (number of applicable questions) multiplied by 100, resulting in a readiness rating of 63%. |
| Section pane | Below, Securiti shows you sections in the left hand side pane. To the right, you have questions for the section you have selected. Also, you can expand or collapse the section pane to suit. |
| “Out of sync” assessment message | If you edit the same assessment in another browser tab, Securiti notifies you that the current session is inactive, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-29 at 1.30.57 PM.png) |

## Answer Regular Assessment questions

### 

1. On the question, click the **Message** icon to open the messaging channel to collaborate with users on the assessment. Use '@' to mention them.

![Screenshot_2025-07-07_at_4_04_56_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-92310c0f-48f9-6df6-2bfd-ddf5c97703ad.png)

![Screenshot_2025-07-07_at_4_06_47_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47d3254f-aaea-f313-3d4e-23dd862b1cdd.png)

> [!NOTE]
> **Note**
> 
> The message icon displays a red dot if a conversation is initiated or there are new (unread) messages.
> 
> Also, assessment question-level messaging has a limit of 1024 characters. When you send a message, or choose to edit a message and save, Securiti shows you an error if you exceed the character limit.

Click **History** icon to view the full history of all actions taken for each question. The history logs are populated, as shown below. For more information, see the [rich question history section in multiple-respondents](/v1/docs/answering-assessment-questions-in-securiti#answer-multirespondent-assessment-questions).

![Screenshot_2025-07-07_at_4_05_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-50ae38dd-9fe3-432b-b5f5-62df285f67da.png)
2. (Optional) On the question, click **Edit** (pencil icon). Securiti shows a minor popup with Respondents and Reviewers tabs, as shown below.
  1. In the search bar, type the names or email addresses of users to add.
  2. On the popup, Securiti provides you with the option to choose the Stage and Permission.
    - **Stage -** For the Base Workflow, these are usually the default 'In Progress' and 'In Review' stage labels for respective users. For the Two Step Review Workflow, especially, you can choose Primary or Privacy Review and Secondary or Legal Review stage labels for reviewers.

![Screenshot_2025-07-11_at_1_47_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a887e3d4-79e0-fdce-274f-a1f59f48d446.png)![Screenshot_2025-07-11_at_1_47_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-491cb6b1-581a-c482-4a5c-789b3967a4cc.png)
    - **Permission -** A quick access permission selection menu. Choose from “Respond” or “Review”, “View Only”, or “No Access”.

> [!NOTE]
> Note
> 
> In reviewer only questions, only the Reviewers tab is visible, as shown below.
> 
> ![User interface showing reviewer permissions and compliance options for a document review process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reviewers_tab.png)

![Screenshot_2025-07-11_at_1_48_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fb712126-8378-dc83-ea5e-ff237a282ff6.png)
  3. Click **Save Changes**

![Screenshot_2025-07-11_at_1_48_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-09d6266e-df87-e754-73d5-710dae78e564.png)
3. Enter your response based on question type: Rich text, Yes/No, Multi-select, etc.

| Field | Description |
| --- | --- |
| Add a Response | Add a Response is the field for rich text responses. |
| Additional Information | Additional Information is a field to provide supplementary information for all question types. Also, it is visible to all customers with whom you have shared the assessment. You can add attachments to Additional Information. |
| Notes | Assessment notes lets respondents enter their comments for the internal team to view, and supports attachments. > [!NOTE] > Note > > These are available on any assessment question, internal or vendor, during the Not Started or In Progress stage. |

Click **Clear Response** to reset question area progress.
4. (Optional) If you have a skip logic in place or weren’t assigned that question, Securiti shows you the message, as shown below.

"Question 2.2 has been skipped or is assigned to another user."

![Screenshot_2025-07-10_at_1_09_07_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-818bc9f5-76c4-47f9-8ab7-079428b7bac4.png)

The question remains hidden:

For more information, see [Applying the Skip Logic for assessment questions](/v1/docs/applying-the-skip-logic-for-assessment-questions).

> [!NOTE]
> **Note**
> 
> This message disappears when your response to another question no longer triggers the skip logic and the question is assigned to you, allowing the question to become visible.
  - If you started a new assessment.
  - If your response to another question triggers the skip logic configured for it at the template level.
  - If you're not assigned the question.
5. Click **Submit**. You must answer all required questions before submitting. They're marked with an 'asterisk.'

If there are unanswered non-required questions, Securiti shows you a popup asking if you want to continue with the submission process anyway. After successful assessment submission, submitted questions are denoted by 'checkmark circle', as shown below.

![Screenshot_2025-07-11_at_2_02_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b020ea7-a271-15b0-1159-55aeb71a2a5b.png)

![Screenshot_2025-07-11_at_2_04_26_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e90dca1-2be7-07dd-ec10-5b4100fc99e7.png)

For more information, see [workflow stages impact on assessment submission](/v1/docs/understanding-workflow-stages-and-assessment-use-cases#transition-to-and-from-different-assessment-stages).
6. As a reviewer, if responses are good to go, select **Move to > Approve** the assessment, the question(s) state changes to approved indicated by a 'checkmark.' If you seek clarification due to incomplete information or a security vulnerability, click **Move to >** Send Back so the respondent can edit responses and resubmit the assessment.

![Screenshot_2025-07-11_at_12_47_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48cde808-9964-59ae-13f6-334d88f3891e.png)

For more information, see [flagging a question](/latest/docs/understanding-workflow-stages-and-assessment-use-cases#assign-flags) and [assigning risk](/latest/docs/understanding-workflow-stages-and-assessment-use-cases#add-risks).

### Reviewer Only Questions

If you are a reviewer assigned to an assessment containing "reviewer only" questions:

- Reviewers can edit the responses of reviewer type questions.

> [!NOTE]
> **Note**
> 
> Reviewers are only able to interact with or edit the reviewer only questions after the assessment has moved to one of the "in-review" states.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(334).png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(335).png)
- Reviewers must answer all assigned mandatory reviewer questions in order to complete the assessment. The "Approve" button is disabled if mandatory reviewer questions remain unanswered.
- You can use the Quick Filters for "unanswered" and "required" to easily locate any mandatory reviewer questions that require your input.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(336).png)
- Reviewers can send back the assessment even if there are unanswered reviewer questions. The submission logic for moving from "in progress" to "in review" stages checks only non-reviewer questions to determine when the assessment changes state.

> [!NOTE]
> **Note**
> 
> Sending back, depending on the use case, mean:
> 
> - To other reviewers such as from secondary to primary reviewer (two-step workflow).
> - When more than one reviewer is assigned to a single question (multi-respondent).
> - To the respondents
- Real-time collaboration is supported for “reviewer only” questions when the assessment is in an "in review" stage type. Reviewers can collaborate on question response, additional information, and notes.
- Respondents can submit the assessment and proceed to the "in-review" stage even if reviewer-only mandatory and non-mandatory questions are unanswered. This is because the primary submission logic for this transition checks only the non-reviewer questions.

However, as noted earlier, reviewers themselves must answer their assigned mandatory reviewer questions to complete their review and approve the assessment. For more information, see [Creating questions in Assessment Template Builder](/v1/docs/creating-questions-in-assessment-template-builder).

## Answer Multi-respondent Assessment questions

### 

When working with one or more respondents side by side, take note of the following use cases:

| Use Case | Description |
| --- | --- |
| Collaborative editing | To prevent data quality issues when multiple respondents attempt to edit the same question, Securiti has implemented a few safety controls. For more information on how we've reduced steps to invite a team member to collaborate, see [step 2 in the regular assessments section](/v1/docs/answering-assessment-questions-in-securiti#answer-regular-assessment-questions). - Two users can edit the same question, but not the same part of the question. For this example, consider users UA and UD. When user UA is answering an assessment question, Securiti disables the response area for the other user. It displays user UA’s avatar, indicating that user UA is currently editing the answer, as shown below. User UD is still able to edit the additional response section. ![Screenshot_2025-07-10_at_3_10_54_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78f0db54-1b5e-5fb1-d074-ea3f527fffbc.png) - When user UD is answering they lock out question editing until they click away or remain inactive for 15 seconds. Hovering over the response area, Securiti shows user UA the following message: "You shall only respond once User UD finishes responding." ![Screenshot_2025-07-11_at_12_34_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e73deee1-bf2f-97e4-61fc-8950f52756a7.png) - Managing question attachments during this collaborative effort remains unaffected. Even during the *question lock window*, you can upload and access these attachments. |
| Submission logic | Securiti has slightly updated the submission logic to account for multiple respondents working on the question. - Respondents must still answer all required questions assigned to them in order to submit. - When submitting the assessment, Securiti submits all assigned questions and prevents them from further editing. - If you are editing one or more of the other respondents' questions, Securiti temporarily disables the assessment submission. ![Screenshot_2025-07-11_at_12_42_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a3d44084-34ee-3c1a-b61b-372a68a5739f.png) - You must mark all questions as submitted before reviewers can approve the assessment. - Securiti enables all existing question respondents to modify their responses when an assessment is sent back, regardless of the user it was sent to. |
| Rich question history | With multiple respondents, it is essential to know what changed and when. - You can track key events including changes to responses, notes, risk assignments, and question submissions. - It helps maintain a transparent record of edits for internal reviews or external compliance checks. - The audit trail doesn't record changes related to: - Reviewer and respondent assignments for questions. - Question state changes (e.g., in draft, approved). - Addition or removal of comments. - Assignment, resolution, and removal of flags. |

## Answer Two Step Review Workflow questions

### 

Exceptions when [Two Step Review Workflow](/v1/docs/configuring-workflow-settings-custom-stages-in-assessments) is configured:

| Assessment logged in user (User avatar taking action shows first) | UI Change |
| --- | --- |
| Details menu | The Assignees area shows primary and secondary reviewers. ![Screenshot_2025-07-11_at_1_04_09_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99345c9f-1e17-48e7-d822-c1a3458e27a8.png) |
| Assessment on submit | Assessment moves to primary review and the **Stage type** changes to In Review. The **Stage** or the stage label changes to 'Primary (Privacy) Review', as shown below. ![Screenshot_2025-07-11_at_1_11_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6ca9f95b-9a79-9707-e1a9-2f8938222a46.png) The stage changes only if all assigned respondents have submitted the assessment from their end. |
| Assessment in primary review | As primary reviewer, you can approve the sections or question assigned to you. After you approve, the assessment now moves to secondary review. The questions status changes to **Approval Pending** and the stage changes to 'Secondary (Legal) Review.' The Stage type remains In Review, as shown below. ![Screenshot_2025-07-11_at_1_04_59_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b70d00e5-35dc-4cb4-10df-70594f5be697.png) Clicking Approval Pending opens up the **Approval status** popup. It shows what users have approved and are yet to approve the questions or assessment. ![Screenshot_2025-07-11_at_1_05_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd6cf9f3-22e2-e48d-8f2e-a026de3a2893.png) |
| Assessment in secondary review | As secondary reviewer, you can approve the assessment to its Complete stage. If the 'Bypass Stage' toggle was enabled in [workflow settings](/v1/docs/configuring-workflow-settings-custom-stages-in-assessments), on send back, the assessment stage moves to In Progress. On resubmit it moves back to secondary review *bypassing* the primary review stage. > [!NOTE] > **Note** > > An assessment moves to the primary review stage, with the Bypass Stage toggle enabled, only when all previously skipped questions are unskipped. When the Bypass Stage toggle is disabled: - Sent back assessments are routed to the respondent. - Upon their resubmission, they first go to the primary reviewer, then to the secondary reviewer. |

## Answer Object Field Assessment questions

### 

> [!NOTE]
> **Note**
> 
> If Object and Field feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Securiti shows you object questions based on your template on the assessment details view. By default, Securiti hides the field question(s) until you answer the object question. The corresponding field question is shown on the page when you enter a response or answer the question. The corresponding field question is shown on the page when you enter a response or answer the question.

![Screenshot_2025-01-21_at_12_48_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7d9391d-7b83-82bb-0df1-127341548e6e.png)

Observe these caveats when answering object field assessment questions:

- If you have enabled Allow Other in the template for a question, that question lets you add a new object (asset, process, etc.) on the go. Securiti shows you a **+** symbol when you’re adding a new object. Once a new object has been added, it is denoted by a **wrench icon**.

![Screenshot_2025-01-21_at_1_17_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e21afbdf-26fb-afbd-59bb-1d082daa145a.png)

![Screenshot_2025-01-21_at_1_39_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21b96eaa-c386-510c-7f82-d96f25db60a2.png)

![Screenshot_2025-01-21_at_1_40_53_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f72a183a-9fb4-0ae2-b78b-6abb9ef4151e.png)

> [!NOTE]
> **Note**
> 
> ‘assessment_generated’ only applies to Asset and Vendor. It is not shown for Process or Institution.
  1. Your newly added object question is based on the Subtype (Definition Type in Data Mapping) selected in the template, such as 'AWS S3.'

![Screenshot_2025-01-21_at_1_19_51_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-245ffc63-3ea5-53c3-2479-e936a64d4458.png)

Securiti *only* shows the override and keep responses popup if you change an existing value in a single-select object question.

![Override_or_Keep_Previous_Field_Responses.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-53acc655-409e-ea51-5b5b-fdc7baf0f907.png)
    1. Click **Override Response** if you want Securiti to fetch latest field values from data mapping object details.
    2. Click **Keep Previous Response** if you want the current field values (text based, Reference List, etc.) to persist.
  2. After the assessment is complete, the new object starts to show in data mapping. Securiti assigns the Technology Type ‘assessment_generated’ to any such objects.

- Any field questions you have previously answered on the object details page, such as values for Purpose, Description, Managing Organization, etc., Securiti pre-fills the fields accordingly.

![Screenshot_2025-01-21_at_1_00_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f4b180cf-2be3-5310-22c1-90b2df8d8cca.png)![Screenshot_2025-01-21_at_1_03_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae8a6191-cb02-e447-28ee-0f71ed2a9dfe.png)

> [!NOTE]
> **Note**
> 
> You can have the same objects with the same fields more than once in an assessment across different sections. The updated one is reflected under the object details if you change any value.
> 
> If you later change values for the object in data mapping details, any reassessment you initiate with the **Include last approved responses** toggle disabled now fetches new values.

### Error Handling

Also, the Object Field Framework provides a robust assessment error handling. See the following use cases:

- If a catalog definition attribute is disabled or removed, Securiti shows the object and field questions as **Deactivated/Deleted**. You must enable the item in Catalog Definitions to resolve the error or add a new item.

![Screenshot_2025-01-22_at_10_17_12_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9755bd97-6b37-e081-6168-627181f1f37a.png)

> [!NOTE]
> **Note**
> 
> You can’t add a deleted attribute to the definition, even with the same name.
- If a Reference List item is disabled or removed, Securiti shows an error with missing items (chips) on the question. Click the label **Contains Errors** in the header to open a side panel. From there, jump to questions you're required to fix.

![Screenshot_2025-01-22_at_10_19_10_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-588b17ae-66d2-c2a1-47a9-b9917eecb86d.png)

Either choose different items or enable the items in the Reference List.
- If an object is removed, Securiti shows an error the object no longer exists. Click the label **Contains Errors** in the header to open a side panel. From there, jump to questions you're required to fix.

![Screenshot_2025-01-22_at_10_23_03_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a91fe3d5-ec38-0ccd-1f7f-86b779d58722.png)

You must choose a different object or create a new one.
- In the state where errors are present, you can still submit and approve the assessment. Securiti does not prevent you from completing the assessment for remaining valid questions or that are not object and field.

> [!NOTE]
> **Note**
> 
> Securiti ignores questions with errors and updates valid data for that module, in this case, a data mapping object.
- Similarly, if the Object Field module is disabled, the assessment details page shows all object and field questions as **Deactivated/Deleted**. You can still submit and approve the assessment for other questions.

### Object Multi-select

When responding to an object question with multi-select enabled, take note of the following settings:

| Assessment with Object Multi-Select | Setting Description |
| --- | --- |
| Answering multi-select object questions as a respondent | - On the object question, select an object. To add more objects, simply select another one. > [!NOTE] > Note > > The selected objects appear as a “chip” below the entry box. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89cc12d6-a5e6-bce5-a446-09e3bdb590c9.png) - If the "Allow other" option is enabled for the question, you can also create and add multiple new objects. Same as in object single-select. |
| Dynamic field questions | Each time an object response is added, a corresponding field question is dynamically generated for each field question. For example, if "Salesforce" and "ADP" are selected in Q1.1, field question Q1.2 now displays Q1.2.1 (Salesforce) and Q1.2.2 (ADP). > [!NOTE] > Note > > Dynamically generated field questions automatically inherit their assignments from their parent multi-select object question. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0e0d021-5c26-37f5-b8fe-291fdb099018.png) You can manage each of these dynamically generated field questions independently in terms of risks, responses, flags, notes, messaging, and question history. |
| Multi-select object child question logic limitations | When a parent object question has multi-select enabled, its corresponding field (child) questions have specific logic limitations. 1. Is Not A Source Of: 1. Skip Logic - Child questions cannot determine if other questions are skipped. 2. Workflow Logic - Child questions cannot control workflow progression. 2. Is A Target Of: 1. Skip Logic - If the entire question group (including the parent) is skipped, Securiti also considers all its field questions as skipped. 3. Is An Independent Source Of: 1. Risk Logic - When a risk is triggered on a child question, it triggers independently for that specific field question. 2. Rating Logic - When a rating is triggered on a child question, it triggers independently for that specific field question. |
| Removing a response from a multi-select object question | To remove a previously selected object from a multi-select object question: 1. Click Remove (x icon) next to the object you wish to remove. > [!NOTE] > Note > > A warning popup appears, asking you to confirm the deletion. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1466b87c-2d4e-79eb-8008-f8a984ffa156.png) 2. If you confirm, the object response is removed from the question. - Any corresponding field responses associated with that object are also removed. - The ordering of remaining field questions updates automatically (e.g., if Q1.2.1 (ADP) is removed, Q1.2.2 (Salesforce) becomes Q1.2.1 (Salesforce)). - Any associated risks, attachments, flags, or notes on the deleted child question are permanently removed. - The Object Question History records the removal (e.g., "Previous Value: ADP \| Salesforce; New Value: Salesforce"). 1. If you cancel, the popup closes and no changes are made to the assessment. |
| Reassessment and error handling | Same as with object single-select, when you reassess: - The object question is automatically populated with the values from the previous assessment. - Corresponding field questions are automatically populated with the latest available data mapping values. - If one or more of the previously selected objects no longer exist in the system, they're shown as “orange chips” below the question. > [!NOTE] > Note > > You can view these by clicking the “Contain Errors” badge in the header. - If one or more of the corresponding fields no longer exist, Securiti shows the questions as deactivated or deleted in the assessment. |

> [!WARNING]
> **Important**
> 
> The current Object and Field implementation is limited to Data Mapping, and the object referred to is currently a data mapping entity (asset, vendor, process, institution).

For more information, see [Configuring Object Field templates](/v1/docs/creating-custom-assessment-templates-in-securiti).

The Send Back in Assessment V2 means the Reviewer has requested more information from the Respondent. It could be because the assessment responses submitted had incomplete information or showed a security vulnerability.

At this point, the Respondent attaches (where applicable) necessary evidence, adds supplementary information to support their answers, and resubmits. If the Reviewer then assesses the risk to be minimized or the argument supplied is enough to validate the assessment complete, they approve it.

Reassessing an assessment lets you identify changes in regulatory compliance and organizational behaviors. As a Question Owner, you can modify the reassessment by filling in new responses or resubmitting previous answers. Where response option(s) are modified, the question is treated as new with no answers.

The term Reviewer is specific to V2 assessments who can review and approve assessments. Previously, referred to as Owner/Co-owner in the V1 world. There can be multiple reviewers on the assessment, similar to how there can be owners and co-owners. Super Admin, Org Admin, Operator, Module Owner, and DPO can all act as and can be assigned a Reviewer role. Additionally, any Mandatory Approver is referred to as a Mandatory Reviewer.

A reference list is a set of options or settings that lets you configure questions in a risk assessment, such as Single or Multi-select.

A Technology Type defines what type of asset or vendor an entity belongs to. These may include 101Data, ServiceNow, MySQL, and the likes thereof.

An asset records data for any application or store. You can use It to record an asset's name, description, purpose, etc. Also, you can use an asset in processes.

A process defines the flow of data between entities and processes.

Institution is the same as an asset - an entity that serves a different purpose.

Catalog Definitions define what sections and fields an entity uses to record the details.
