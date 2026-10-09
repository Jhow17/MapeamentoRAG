---
title: "Creating Question Logics in assessment template"
slug: "creating-question-logics-in-assessment-template"
updated: 2026-08-10T12:32:17Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/creating-question-logics-in-assessment-template"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating Question Logics in assessment template

You can build custom assessment templates that use conditional logic to assign ratings to customized responses. For example, you can have a multi-choice question with various responses that map to established ratings such as compliant, partially compliant, or non-compliant. When you conduct an assessment based on the template, the Securiti rating shown at the top of the assessment responds immediately to all questions' aggregate rating.

You can also use conditional logic in internal Assessments to delegate, evaluate, and track Risks revealed by assessment responses. Furthermore, you can configure assessment templates with more than one risk logic element for each question.

> [!WARNING]
> **Important**
> 
> Securiti shows an error message that you must fill out required fields when creating assessment questions with conditional logic.
> 
> Only after this can you save or start the assessment.

### Configuring assessment questions with risk conditional logic

1. In Securiti Dashboard view, open **Assessment Automation**, and choose **Assessments > Templates**.
2. Create a new template or edit an existing template described in [Creating custom assessment templates in Securiti](/v1/docs/creating-custom-assessment-templates-in-securiti).
3. Open a question for editing by clicking Edit (pencil icon) near its upper right corner. See [Creating questions in Assessment Template Builder](/v1/docs/creating-questions-in-assessment-template-builder) for more information about creating questions.
4. Below the standard response zone, click **+ Add New Question Logic**.
5. Use the logic tools to associate the responses with the ratings or define conditions, as described below.

| Logic tool | Description |
| --- | --- |
| If Condition | When the condition fulfills, the next logical step takes place. |
| If Response | A response - needed to test for compliance. |
| Set Ratings | Set either rating or the risk level. For risk, you can also choose the owner and set a review deadline. > [!NOTE] > Note > > When adding a risk in the question logic, you can pre-select tags to assign to it. When the risk is triggered from the template, these tags are automatically assigned. You can further edit tags after the risk is created. > > ![Interface for setting risk levels with options for response and tagging.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-10 at 5.31.37 PM.png) > > For more information, see [Tags management](/latest/docs/managing-assessment-tags). |
6. Use the conditional logic operators to configure question flow logic for default response values, i.e., N/A, Non-Compliant, Partially Compliant, and Compliant, as described below:

> [!NOTE]
> **Note**
> 
> You can add multiple "Any of" and "Not any of" operators when configuring questions with conditional logic.

| Conditional logic operator | Description |
| --- | --- |
| Equals to | When "If Condition" equals a default response value, question conditional logic triggers a risk priority you configured in the assessment template. |
| Not Equals to | When "If Condition" does not equal a default response value, question conditional logic triggers a risk priority that you configured in the assessment template. |
| Any of | When "If Condition" equals any or all of the default response values -- N/A, Non-Compliant, Partially Compliant, and Compliant, question conditional logic triggers a risk priority which you configured in the assessment template. |
| Not Any of | When "If Condition" does not equal any or all of the default response values, question conditional logic triggers a risk priority that you configured in the assessment template. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-24 at 5.12.51 PM.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-24 at 5.13.46 PM.png)
7. (Optional) Repeat 4-6 (above) to develop a new question logic and define its conditions. You can then set Securiti, for example, to generate a *Medium* risk level warning against "partially compliant" response, or *Very High* for "non-compliant" response, and so on.
8. Save the template.

### Configuring assessment questions that apply Readiness Ratings

1. Create a new question or open a question for editing.
2. Choose one of the following question types:
  - Multi-choice
  - Yes/No
3. Near the bottom of the question, click **+ Add New Question Logic**.
4. From the Logic menu, choose **Set Rating**.
5. For each of the different responses, add a Response Logic entry for which the If condition is **Equals to**.
6. In the If Response and Set Ratings columns, create relationships between each response and the rating Securiti assigns as shown below.

> [!NOTE]
> **Important**
> 
> The following four response types determine a question's default readiness rating score. If you select another option besides these predefined options, such as "Set Rating" for the question, the Readiness Rating transforms into a custom risk rating score that does not show the correct readiness score for the question and overall assessment.

![Screenshot_2024-08-02_at_3_42_29_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c19333fa-106c-b013-6c55-8828575219b5.png)
7. Repeat as necessary for additional questions, then save the template.

### Configuring assessment questions to apply custom risk rating scores

To configure assessment questions that use custom risk rating scores:

1. In Securiti, open **Assessment Automation**, then choose **Assessments > Templates** (select new or open an existing one for editing).
2. Near the upper right corner of a question, click **Edit** (floating panel).
3. Choose from one of the question types that applies to question logic:
  - Multi-choice

> [!NOTE]
> **Note**
> 
> Securiti shows the respective rating for each multi-choice question with default response values.
  - Yes/No
  - Multi-select
4. Near the bottom of the question, click **+ Add New Question Logic**.
5. For example, choose **Equals to** and select the desired response for it from the If Response menu.

> [!NOTE]
> **Note**
> 
> For questions of multi-select, you can choose more than one.

Select a predefined rating In the "Set Ratings" menu, or choose **Custom** to enter a rating in the value field.
6. Securiti assigns a custom rating score upon conducting the assessment.

> [!NOTE]
> **Note**
> 
> According to the rating logic, the custom rating score is a sum of the custom rating score for all questions in the assessment.

### Viewing custom rating scores by tag

You can also visualize a custom rating score by tag. Securiti sums up the custom rating scores across questions and breaks the scores down by tag.

1. In Securiti, open Assessment Automation. Then choose **Internal Assessments > Assessments** and select an assessment.
2. Near the upper right corner of the page, click **Details > Show Risks**. You'd see the Custom Rating Score by tags under the Risks panel tab.

For more information, see [Applying the Skip Logic for assessment questions](/v1/docs/applying-the-skip-logic-for-assessment-questions).

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

Risks help assess the criticality of an asset, and measure breaches and repercussions in the event of a breach.

Risk is the likelihood of effects or implications that would negatively impact what you value. Risk in Securiti refers to risks that may arise when conducting internal or vendor assessments. You can track them using the risk dashboard.

## Related

- [Answering assessment questions in Securiti](/answering-assessment-questions-in-securiti.md)
