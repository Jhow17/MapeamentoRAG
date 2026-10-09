---
title: "Configuring Workflow Settings (Custom Stages) in assessments"
slug: "configuring-workflow-settings-custom-stages-in-assessments"
updated: 2026-02-18T09:09:49Z
published: 2026-02-18T09:09:49Z
canonical: "helpcenter.securiti.ai/configuring-workflow-settings-custom-stages-in-assessments"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Configuring Workflow Settings (Custom Stages) in assessments

> [!NOTE]
> **Note**
> 
> If Custom Workflow Stages feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

With Custom Workflow Stages, you can configure a multi-tier review process in assessments. It also shows you a flow diagram of how assessments moves through different stages including those On Hold or Canceled. You can also customize assessment stage labels for convenience.

> [!NOTE]
> **Note**
> 
> You can only rename stages In Progress and In Review.

To configure Custom Workflow Stages:

1. On the Securiti Dashboard view, click **Settings**.
2. In the **System Settings**, select **Assessments > Workflow Stages**.

Alternatively, on the Internal Assessments list, in the left sidebar, select **Settings > Workflow Stages**, as shown below.

![Screenshot_2025-07-15_at_2_40_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bee91689-8d04-1c6a-eed3-f13087dad2d9.png)
3. On the following page, Securiti shows you **Base Workflow** (default workflow denoted by a 'star icon') and the **Two Step Review Workflow**.
  1. The **Base Workflow** follows the usual assessment lifecycle irrespective of whether Custom Workflow Stages is enabled for your tenant.

![Screenshot_2025-07-11_at_1_57_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81ecfc62-f978-7727-63ac-60e24cd4a249.png)
  2. The **Two Step Review Workflow** includes two review stages:

![Screenshot_2025-07-11_at_1_58_12_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-06dd01ff-bede-03d5-16ff-2f39f9d29c99.png)

You can use Bypass Stage to skip Primary Review on assessment resubmit.
    - Primary Review, AKA, a team of data privacy officers who perform preliminary review of the assessment.
    - Secondary Review, AKA, a team of data compliance officers who are assigned high level questions because of their sole knowledge of the domain or expertise in the area.

If they're mandatory reviewers on the questions, their review is also required before approving those questions.
4. (Optional) To rename a stage label, click **Options** and select **Rename Label**.

![Screenshot_2025-07-15_at_2_58_39_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4460b624-3bbb-b495-b95a-65b12ec2ef8f.png)

> [!NOTE]
> **Note**
> 
> You can't create a duplicate stage label or, otherwise Securiti shows you the error message. When renaming, we recommend you keep a unique name for each stage label.

![Screenshot_2025-07-15_at_2_53_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c50dc9e6-f527-4593-63af-3d02af911078.png)

Enter a custom name and click **Done** (‘checkmark icon’). Near the upper right corner, click **Save**.
5. (Optional) To skip Primary Review on assessment resubmit, click Options and enabled the **Bypass Stage** toggle, as shown below.

![Screenshot_2025-07-11_at_1_58_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00d06d31-e72e-0be0-dca0-257676184ed4.png)

For more information, see these topics:

- [Assessment Launch Settings](/v1/docs/using-the-assessment-launch-settings)
- [Section and question level assignment](/v1/docs/section-question-assignment-in-assessment-automation)
- [Launch New Assessment](/v1/docs/launching-a-new-assessment-in-securiti)
- [Answer assessment questions](/v1/docs/answering-assessment-questions-in-securiti)
