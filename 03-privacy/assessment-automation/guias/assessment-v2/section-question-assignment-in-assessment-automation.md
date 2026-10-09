---
title: "Section & question assignment in Assessment Automation"
slug: "section-question-assignment-in-assessment-automation"
updated: 2025-12-08T10:39:01Z
published: 2025-12-08T10:39:01Z
canonical: "helpcenter.securiti.ai/section-question-assignment-in-assessment-automation"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Section & question assignment in Assessment Automation

> [!WARNING]
> **Important**
> 
> We have used the [Two Step Review Workflow](/v1/docs/configuring-workflow-settings-custom-stages-in-assessments) as an example to illustrate section and question level assignment.
> 
> In a regular V2 assessment or assessment with the “Base Workflow”, Securiti does not have primary or secondary reviewers assignment.

> [!NOTE]
> Note
> 
> (Applicable to the "Launch New Assessment" popup and the "Bulk Assign" option)
> 
> 
> 
> Reviewer assignment currently requires manual effort. Adding new reviewers through launch assessment or bulk assignment does not automatically assign them to all question types, meaning you must manually select reviewers for every question in both scenarios.
> 
> 
> 
> Default reviewers configured via the launch settings are an exclusion to the rule.

### Template level section and question assignment

On the **Assign Sections and Questions Permissions** popup:

1. Mark the checkbox for a section or questions to bulk assign review or view permissions.
2. Click **Review** and on the permissions popup, click the Assign Permission icon. To add reviewers, Click **+ Add Reviewer**.

You can set reviewers as mandatory, remove review permissions, or delete them from the assessment.

> [!NOTE]
> **Note**
> 
> You can only delete a reviewer if they're not currently assigned to a section or question.

![Screenshot_2025-07-10_at_12_52_27_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78b069b1-416e-052a-57ef-e05c956e19a1.png)![Screenshot_2025-07-10_at_12_53_09_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04453a88-4494-ce0e-b476-a67c2e20bd2d.png)
3. Click **View** and on the permissions popup, click the Assign Permission icon to add users as viewers. They can view the Reviewer questions but do not have the approval rights.

![Screenshot_2025-07-10_at_12_52_45_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b4ca5f7-293f-be30-111f-172178142de8.png)
4. (Optional) Click **Clear Permissions** to remove section or question assignments you made and start afresh.
5. Click **Save**

### Section and question assignment at assessment launch

### 

On the **Assign Sections and Questions Permissions** popup:

1. Click **Review** and on the permissions popup, click the Assign Permission icon. To add reviewers, Click **+ Add Reviewer**.

![Screenshot_2025-07-10_at_12_49_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f3ced63d-9757-03f9-83fe-47d6712c9e38.png)![Screenshot_2025-07-10_at_12_46_50_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2bc7cb9-d403-729c-a573-5539a774caea.png)
2. Mark the checkbox for a section or questions and click **Respond** to assign permissions as required.

To add respondents, click **+ Add Respondent**. Also, you can remove respond permissions or delete them from the assessment.

> [!NOTE]
> **Note**
> 
> You can only delete a user if they're not currently assigned to a section or question.

![Screenshot_2025-07-10_at_12_47_09_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-516af0a3-36cd-e02a-21a3-89e6bf7ff015.png)
3. Click **View** and on the permissions popup, click the Assign Permission icon to add users as viewers. They can add feedback to the responses but do not have the editing rights.

![Screenshot_2025-07-10_at_12_48_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b65a7153-f139-6cd2-b1a2-3ab9d570cf23.png)
4. Click **Launch New Assessment**.

> [!NOTE]
> **Note**
> 
> - **Contain Errors Only -** the toggle shows the questions or sections with unassigned reviewers or respondents.
> - **View Help Guide -** shows you information about the icons and different permissions.

#### Reviewer Only questions assignment

> [!NOTE]
> Note
> 
> You can also configure assignment for reviewer questions in ​[Assessment Launch Settings](/v1/docs/launching-a-new-assessment-in-securiti)​​.

- On the launch assessment popup, you can add respondents and reviewers as normal.
- Reviewer only questions are clearly visible (shown as a chip) in the section assignment popup.

![Overview of assigning permissions for sections and questions in a review process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reviewer_only_assignment.png)
- Assignment restrictions:
  1. Users can’t edit the respondents for reviewer only questions.
  2. Users are only able to edit the reviewer portion for these questions.
  3. Securiti auto-inherits the respondent values for reviewer only questions from the reviewer field.
- When performing a bulk selection or reassignment of sections or questions with the reviewer only flag enabled, any respondent changes are disregarded.

Securiti shows the banner “Your selection contains reviewer-only questions.”

![Permissions assignment interface showing sections and questions for review and response.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/reviewer_only_alert.png)

For more information, see the following topics:

- [Answering assessment questions in Securiti](/v1/docs/answering-assessment-questions-in-securiti)
- [Using the Internal Assessments list view](/v1/docs/using-the-internal-assessments-list-view)
- [Assessments list Filter panel and Saved Views](/v1/docs/assessments-list-filter-panel-and-saved-views)

The term Reviewer is specific to V2 assessments who can review and approve assessments. Previously, referred to as Owner/Co-owner in the V1 world. There can be multiple reviewers on the assessment, similar to how there can be owners and co-owners. Super Admin, Org Admin, Operator, Module Owner, and DPO can all act as and can be assigned a Reviewer role. Additionally, any Mandatory Approver is referred to as a Mandatory Reviewer.

The term Respondent is specific to V2 assessments who can answer and submit assessments. It refers to the user who was previously a Collaborator in the V1 world. Multiple respondents can be added to the assessment, similar to how more than one collaborator can be added. Also, a Guest User can be added as a Respondent.

## Related

- [Assessment V2 system and message digest email notifications](/assessment-v2-system-and-message-digest-email-notifications.md)
