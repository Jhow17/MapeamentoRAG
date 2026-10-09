---
title: "Creating questions in Assessment Template Builder"
slug: "creating-questions-in-assessment-template-builder"
updated: 2026-08-03T08:17:59Z
published: 2026-08-03T08:17:59Z
canonical: "helpcenter.securiti.ai/creating-questions-in-assessment-template-builder"
stale: true
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating questions in Assessment Template Builder

To create a new question when building a custom assessment template:

1. If you haven't already done so, create a new custom assessment and add sections as described in [Creating custom assessment templates in Securiti](/v1/docs/creating-custom-assessment-templates-in-securiti).
2. In the Sections area, click the section where you want to add the new question.
3. Scroll to the bottom of the section and click **Add Question**.

> [!NOTE]
> Note
> 
> There is no technical limit enforced when adding questions to a template. However, Securiti recommends staying within 50 questions per section and 1000 questions total per custom template, as assessments beyond this scale may affect performance and usability.

Securiti adds a new question to the assessment. All questions except those with response type Informational--no response include a standard response zone in which the Question Owner can enter a text response and format it using a rich set of style and formatting tools.
4. In the "Response Type" area, choose the response type. Your choices are:

| Multi-choice | You can choose only one of the available options. |
| --- | --- |
| Multi-select | You can choose some or all of the available options. |
| Yes/No | You can choose only "Yes" or "No." |
| Date | You can enter a date either with text entry or using a calendar tool. |
| Text input | You can enter text. |
| Data table | You can fill out a table. |
| Informational -- not sure | Adds a "Not Sure" choice either on its own or below a response of type multi-choice, multi-select, date, or yes/no. |
| Informational -- not applicable | Adds a "Not Applicable" choice either on its own or below a response of type multi-choice, multi-select, date, or yes/no. |
| Informational -- no response | This question doesn't require any response. The Submit (or Approve) button is hidden and only visible when you enter response text for such questions. |
| Object and Field | Adds an object question and its corresponding field question. For more information, see [Object and Field Framework](/v1/docs/securiti-pods-and-elastic-pods). |
5. Use the tools inside the question workspace to customize the new question.
  1. To the right, click the pencil icon to launch "Edit Mode (floating panel)."

![Screenshot_2024-07-08_at_12_29_30_PM_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-958b0b98-d3ac-ce51-fac4-aff42f3dbda7.png)
    1. **Settings -** sets the question as mandatory by toggling **Require Response**. Securiti does not let you publish an assessment in which any mandatory question has not been answered.

![Screenshot_2024-06-25_at_5_11_43_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4cf8f83f-bc49-e630-9cc9-13646360a15a(1).png)You can also configure Reviewer Only questions from the settings. Enable the toggle Reviewer Only which makes the question(s) the sole responsibility of the reviewers on the assessment to answer and then approve. For more information, see [Answer reviewer only questions](/v1/docs/answering-assessment-questions-in-securiti#answer-regular-assessment-questions).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(337).png)

When you toggle on, Securiti notifies you that question logics don't apply to reviewer only questions.
    2. **Question Logics -** lets you configure new question logic. Existing logics show by default for the question.

![Screenshot_2024-07-08_at_1_16_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ba49587-afb0-ec3a-7cdd-b9917c54c6eb.png)
    3. **Reorder Question -** change question order within a section or move it to a different section.

![Screenshot_2024-06-25_at_5_27_00_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-925b8a72-3e9b-333c-b26e-3bba541936ae(1).png)
    4. (Optional)**Tags --** click the Tags icon on the floating panel to view tags that Securiti has applied by default.
      - A question(s) belonging to a particular regulation category such as CCPA, GDPR, LGPD, etc. bears the same tag(s). Disable **Active tags only** toggle to add more tags from the list if that question(s) covers multiple regulation categories. Alternatively, you can add new tags.

> [!NOTE]
> **Note**
> 
> When you edit a Multi category assessment templates by adding a new question, Securiti does not know what tag to assign because the template has multiple tags. If a template has a single question tag across all sections for e.g., GDPR, Securiti nests it under the GDPR regulation category on the templates list page.
> 
> Similarly, if a template has multiple question tags or no question tags, Securiti nests them as Multi category assessment templates and Uncategorized, respectively.

![Screenshot_2024-07-12_at_4_06_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-28af8e21-f046-3cc3-dafc-57be8d5f1a73.png)
    5. **Delete Question -** click the Bin icon to delete an unwanted question from the template.

![Screenshot_2024-06-25_at_5_30_26_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58b1cf0e-b5f9-aad4-fc72-405efdbd93e5(1).png)
    6. **Preview Mode -** applies to more than one published versions of the template. Choose an earlier version of the template from the **Version History** menu and expand the floating panel to view the options you previously selected for the question.

![Screenshot_2024-06-25_at_5_20_14_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-68f71ec6-fcd6-1b7f-42a7-efa0db78d6a6(1).png)

The question can't be deleted or edited in Preview Mode.
  2. (Optional) Near the top of the workspace, use the regulation type tools to tag the question as applying to specific regulation types. By default, the question is tagged with the regulation type you chose when you created the assessment template. You can add additional tags for questions that apply to multiple regulation types. When you do so, Securiti categorizes the template as a multi-category assessment.
  3. In the Question area, type the question or statement.
  4. If you want to include a tooltip explaining the question, enable the tooltip slider and enter the text in the box below it.

You can format the text to suit, such as bold, italic, font color, bullet or numbered list, link, etc. Preview the template before launching an assessment to verify changes, as shown below.

![Enable_Rich_Text_for_Question_Description_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21b1ae56-9564-bad2-1d40-834519f1f048.png)

![Enable_Rich_Text_for_Question_Description_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e442e8f3-3836-5a74-4df7-f8cf09e1851d.png)

> [!NOTE]
> **Note**
> 
> Securiti shows the formatted question tooltip on the assessment.
  5. To customize the response type, for example, to change the text labels of multi-choice or multi-select responses, hover below the response type and click **Edit**. Then use the Display tab on the component popup to customize the response. When you are done, click **Save**.

> [!NOTE]
> **Note**
> 
> For advanced configuration with the elements on the Data, Validation, and Conditional tabs, contact our support team at [support@securiti.ai](mailto:support@securiti.ai) for guidance.

As you apply settings on the Display tab, the Preview area near the upper right corner of the popup shows you how the response will look when you apply your changes, as shown below.

![Component_display_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa143039-1403-b42c-edc8-57d99b31a403(1).png)
6. To collapse a question so that it uses less of your workspace, near the upper right corner of the question click the **X** on the floating panel. Click **Edit** (pencil icon) near the upper right corner of the question to re-expand it so that you can work on it.

> [!NOTE]
> **Note**
> 
> You cannot delete the last question in a section.

For more information, see [Creating Question Logics in assessment template](/v1/docs/creating-question-logics-in-assessment-template).

A Question Owner is someone who owns the question(s). If the Question Owner is also a collaborator, they can answer both their own questions and those they're added to as Collaborators. They can also approve or reject responses to questions they own but not those they collaborate on.

If you're not the Question Owner but are an assessment owner, you're automatically added as a viewer for all assessment response types (submitted, rejected, or approved). You cannot, however, view questions in a draft.
