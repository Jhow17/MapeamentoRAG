---
title: "Launching a new assessment in Securiti"
slug: "launching-a-new-assessment-in-securiti"
status: "update"
updated: 2026-08-28T13:32:13Z
published: 2026-09-01T05:28:06Z
canonical: "helpcenter.securiti.ai/launching-a-new-assessment-in-securiti"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Launching a new assessment in Securiti

**Scenario**

As a Data Compliance Officer, you're responsible for coordinating your organization’s GDPR readiness assessment. Manually tracking who owns which sections leads to confusion and delays. With section and question assignment, you delegate tasks directly to the right teams or individuals. This keeps collaboration structured and responsibilities clear, helping you complete the assessment faster and with full accountability.

This topic covers information about launching an assessment from the Assessments list view. If you have the Custom Workflow Stages enabled, see [here](/v1/docs/launching-a-new-assessment-in-securiti#launch-assessment-with-custom-workflow-stages).

For information on user roles and permissions before the assessment launch, see [Reviewer Respondent prerequisites](/v1/docs/reviewer-respondent-prerequisites) .

To launch an assessment:

1. On the Securiti Dashboard view, click **Assessment Automation**.
2. Near the upper right corner of the page, click **Launch Assessment**.
3. On the **Launch New Assessment** popup, from the **Select Template** menu, choose your preferred template.
4. Enter a name in the **Assessment Name** field.

> [!NOTE]
> **Note**
> 
> The assessment name does not support special characters such as these:
> 
> ` ~ $ % ^ * + = [ { } ] \ " ; < > ?
5. Under **Assign** Reviewer**(s)**, enter the name or search for the system user.

> [!NOTE]
> **Note**
> 
> Eligible reviewers are Super Admin, Org Admin, Operator, DPO, Module Owner, and User. Guest User can't be assigned as a reviewer. A custom role can also be made eligible as a reviewer, but needs the Update Assigned Assessment permission to edit the assessment once assigned.
6. (Optional) For the selected reviewers:
  - Click Options **(three vertical dots)** and enable the **Mandatory Approver** toggle if you want.
  - Click **Remove Reviewer** for the reviewers you do not want on the assessment.
7. Under **Assign Respondent(s)**, enter the name or search for the system users to whom you want to assign response permissions, i.e., answer the assessment.

> [!NOTE]
> **Note**
> 
> You can invite guest users to the assessment. For example, when you enter *janedoe@gmail.com* as a respondent, Securiti shows you the **+ Invite janedoe@gmail.com as Guest** option.
> 
> You can also add reviewers as respondents.
8. In the **Select Email Notification Template** field, you can select the default Securiti email invite or click the edit (pencil icon) button below to customize your template.
9. In the **Due Date** and **Reminder Date** fields, respectively, specify the dates you want the desired action to take place.

![Screenshot_2025-06-17_at_11_58_46_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2fbd5fcc-da50-7743-ee23-a3bf72b4e722.png)
10. (Optional) For multiple reviewers, Securiti shows you the option to **Assign Sections/Questions**.
11. Click **Launch New Assessment**

To learn about what launching a Securiti assessment can help you achieve, refer to [Internal Assessments overview](/v1/docs/securiti-pods-and-elastic-pods) video.

### Launch assessment with Custom Workflow Stages

> [!NOTE]
> **Note**
> 
> If Custom Workflow Stages feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

On the **Launch New Assessment** popup:

1. From the **Select Template** menu, select the template with the **Two Step Review Workflow** you configured in the assessment launch settings.

Securiti shows the **Select Workflow Stage Template** field preselected with the Two Step Review Workflow.

> [!NOTE]
> **Note**
> 
> If a template does not have a Two Step Review Workflow, Securiti switches to the **Base Workflow** instead.
2. Under **Assign Reviewer(s)**, Securiti shows the reviewers you assigned to primary and secondary review stages at the template level.

You can manually add more or remove reviewers later. Also, *you can skip a review stage if you want by not assigning any reviewers to that stage*.
3. Under **Assign Respondent(s)**, enter the name or search by email address for users you want to assign respond permissions. In case of guest users, Securiti sends them an invite to collaborate on the assessment.

![Screenshot_2025-06-17_at_12_14_43_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f8aaeabd-7226-95a1-772e-20c67f2811a8.png)
4. (Optional) For multiple reviewers, click **Assign Sections/Questions**.
5. Apply other settings to suit and click **Launch New Assessment**.

> [!NOTE]
> Important
> 
> Magic Links sent to guest users expire after seven days. If a user clicks an expired link, a new one is automatically sent to them with a refreshed seven-day expiration.

For more information, see the following topics:

- [Section & question assignment in Assessment Automation](/v1/docs/section-question-assignment-in-assessment-automation).
- [Answering assessment questions in Securiti](/v1/docs/answering-assessment-questions-in-securiti).

Workflow Stages relate to the assessment lifecycle in V2. A typical Securiti assessment has four stages: Not Started, In Progress, In Review, and Complete. The Not Started stage is when you haven't begun answering. As soon as you interact with at least one question, the stage changes to In Progress. After the assessment is submitted, the reviewer is called In Review. Once the concerned parties approve, the assessment transitions to the Complete stage.

## Related

- [Start an assessment](/start-an-assessment.md)
