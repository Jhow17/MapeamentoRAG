---
title: "Applying the Skip Logic for assessment questions"
slug: "applying-the-skip-logic-for-assessment-questions"
updated: 2025-10-30T19:49:18Z
published: 2025-11-03T06:12:21Z
canonical: "helpcenter.securiti.ai/applying-the-skip-logic-for-assessment-questions"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Applying the Skip Logic for assessment questions

**Scenario**

As a Data Privacy Officer managing vendor onboarding, you need to collect relevant information without overwhelming vendors. Static questionnaires lead to unnecessary or confusing questions. With skip logic, you tailor follow-ups based on earlier responses. For example, only showing security questions if a vendor handles personal data. This makes the questionnaire adaptive, clear, and faster to complete.

When you build custom assessment templates, you can use conditional logic to skip over questions within a section that responses to earlier questions in that section, indicated as not relevant. You can use this feature to build responsive assessment templates that adjust themselves according to the responses provided. Skip logic even shows the actual sequence number for each skipped question.

Furthermore, you can create questions using the nested "skip logic" up to 10 layers deep. This means:

If the response is "no" for Question 1, the assessment exposes (doesn’t skip) Question 1.1. Meanwhile, Question 1.1 can have its own skip logic that exposes or hides Question 1.1.1 depending on the response, and so on for up to five layers in depth. See the three-layer example below.

In other words, nested skip logic lets you construct sophisticated context-sensitive assessments that dig deeply into complex issues with questions that expose or omit subsequent questions depending on the responses.

You can use Skip Logic in a template to skip questions including those in another section. Also, you can skip entire sections.

> [!NOTE]
> **Note**
> 
> - Creates multiple dependants when you decide to skip a question or a section.
> - Moving a parent question below a child question, the skip logic for the child is removed. Conversely, If you move a parent question above, the skip logic for the child is retained. Also, the same logic (for moving questions) applies when it comes to skip-section reordering.
> 
> Furthermore, you can now see which questions are skipped based on your configured skip logic by hovering over the "dependent" icon next to their question number.

### Skip logic and customizations

Do the following to configure Skip Question Logic:

1. On the Securiti Dashboard view, click the card for **Assessment Automation**.
2. In the left-hand navigation, select **Assessments > Templates**. On the following page, near the upper right corner, click **Use Existing Template** and configure the options on the popup to suit.
3. On the template builder page, click the pencil icon next to a question to expand it and click **Add New Question Logic**.
4. Select the logic from the menu as “Skip Question.” In the Skip Questions / Sections area, click **Select Questions / Sections**, as shown below.

![Screenshot_2024-08-02_at_3_46_20_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d206982-f89b-183f-632c-b0f476167f05.png)![Screenshot_2024-08-02_at_3_58_27_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-29199ef3-0067-9a99-3056-458fc9800615.png)
5. On the popup, expand the current section to skip individual questions or mark the checkbox next to the section to skip the entire section, including all questions.

Enable the **Skip Section** toggle to skip other sections or expand them to skip individual questions by marking the checkboxes next to them. Once you’ve made the selections, click **Save** to close the popup.

![Screenshot_2024-08-02_at_3_47_51_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9b2b784-2ee7-ec8d-ea4e-ec09a552145d.png)
6. In the upper right corner, click **Save**, then **Publish** to publish the assessment template.

You can customize skip logic further. To configure additional options:

1. On the assessment template builder page, for the question click **+ Add New Question Logic** and apply the skip logic to suit.
2. On the **Skip Sections / Questions** card, choose sections or questions you want, and click **Save**.
3. To illustrate, consider Question 2 getting skipped based on the skip logic you’ve applied in Question 1 using the above method. For the now dependant or child question, AKA Question 2, choose these options:

![Screenshot_2024-08-02_at_3_48_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9546ea4-b3ed-4c56-fa54-b5b52fe4ca43.png)
  1. **If Question is skipped**, then select **Skip Selected Sections / Questions** or **Suppress Skip Logic** from the dropdown.
  2. **If Question is unanswered**, then select **Skip Selected Sections / Questions or Suppress Skip Logic** from the dropdown.
  1. Based on settings in step *3a*:

Securiti either skips questions dependent on Question 2 (for example, Questions 3 and 4), or bypasses the skip logic you configured in Question 2 (meaning, does not hide Questions 3 and 4). All other configured questions as usual are skipped as usual.
  2. Based on settings in step *3b*:

Securiti skips Question 2 when Question 1 is unanswered and hides questions dependent on Question 2 (for example, Question 3 and 4). If selected ‘Suppress Skip Logic,’ Securiti bypasses the skip logic you configured in Question 1 (meaning, does not skip Question 2). All other configured questions are skipped as usual.

For more information, see the following topics:

- [Creating custom assessment templates in Securiti](/v1/docs/creating-custom-assessment-templates-in-securiti)
- [Creating questions in Assessment Template Builder](/v1/docs/creating-questions-in-assessment-template-builder)
- [Creating Question Logics in assessment template](/v1/docs/creating-question-logics-in-assessment-template)

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
