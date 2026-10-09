---
title: "Using the Assessment Launch Settings"
slug: "using-the-assessment-launch-settings"
updated: 2026-06-16T07:06:48Z
published: 2026-06-16T07:06:48Z
canonical: "helpcenter.securiti.ai/using-the-assessment-launch-settings"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Using the Assessment Launch Settings

This section describes how to configure template defaults. This enables you to pre-populate the launch assessment popup when using that template to launch an assessment.

If you have the Custom Workflow Stages enabled, see [here](/v1/docs/using-the-assessment-launch-settings#configuring-custom-workflow-stages-in-assessment-launch-settings)

> [!NOTE]
> **Important**
> 
> Securiti, currently does not support launch settings for Data Maps and Vendor Assessment templates.
> 
> When starting an assessment from a Data Maps or Vendor Assessment template, follow the usual steps to clone a system template and customize it to suit before proceeding.
> 
> If you don't specify reviewers in the launch settings, the SSP user can configure them when launching an assessment. If you assign reviewers in the launch settings, Securiti locks the SSP assessment with default reviewers.

To configure Assessment Launch Settings:

1. On the Securiti Dashboard view, click **Assessment Automation**.
2. In the left sidebar, select **Assessments > Templates**.
3. For a template, click **Options** (three vertical dots) and select **Edit Launch Settings**.

![Screenshot_2025-04-07_at_3_53_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b825e17e-40e4-9ca8-391b-8f084048fc87.png)
4. On the **Assessment Launch Settings** popup, select reviewers, configure the email template, and specify due and reminder dates - *Base Workflow* by default.
5. Click **Assign Sections/Questions** if you're sure and want to save time during launch assessment by assigning who's responsible for what section or question, now.
6. Alternatively, click **Save** if you want to configure section or question level assignment later.

### Configuring Custom Workflow Stages in Assessment Launch Settings

> [!NOTE]
> **Note**
> 
> If Custom Workflow Stages feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

See [Workflow Settings](/latest/docs/configuring-workflow-settings-custom-stages-in-assessments) on how to apply a custom stage.

To configure the launch settings:

1. For a template, click options and select **Edit Launch Settings**.
2. On the following popup, from the **Select Workflow Stage Template** menu, choose **Base Workflow** or **Two Step Review Workflow**.
3. For Base Workflow, under **Assign Reviewers**, select the reviewers you want.

![Screenshot_2025-06-17_at_1_07_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7d108d73-0828-8b39-c79a-3813b3bfac2f.png)

For Two Step Review Workflow, select reviewers from both the **Primary Review** and **Secondary Review** fields. In our example, we have used the stage labels "Primary Review Privacy Review" and "Secondary Review Legal Review."

![Screenshot_2025-06-17_at_1_07_25_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75a4c5f5-4bcb-e555-f8b0-86190d41f9f6.png)

> [!NOTE]
> **Note**
> 
> You can rename the Primary Review or Secondary Review labels in workflow settings.
> 
> Also, reviewer selection isn't mandatory at this stage. If you choose to skip a review stage, you can do so by not assigning any reviewers to that stage.

> [!NOTE]
> **Note**
> 
> In Two Step Review Workflow, a primary reviewer can't be added as a secondary reviewer and vice versa. This ensures no reviewer is repeated and only reviews their set of questions owing to their expertise, knowledge, or assessment owner's general preference.
4. Once done, click **Assign Sections/Questions**.
5. Apply other settings to suit and click **Save**.

For more information, see these topics:

- [Section and question level assignment](/v1/docs/section-question-assignment-in-assessment-automation)
- [Assessment launch popup](/v1/docs/launching-a-new-assessment-in-securiti).

Workflow Stages relate to the assessment lifecycle in V2. A typical Securiti assessment has four stages: Not Started, In Progress, In Review, and Complete. The Not Started stage is when you haven't begun answering. As soon as you interact with at least one question, the stage changes to In Progress. After the assessment is submitted, the reviewer is called In Review. Once the concerned parties approve, the assessment transitions to the Complete stage.

## Related

- [Answering assessment questions in Securiti](/answering-assessment-questions-in-securiti.md)
