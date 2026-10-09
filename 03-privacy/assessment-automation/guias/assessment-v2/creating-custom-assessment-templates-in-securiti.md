---
title: "Creating custom assessment templates in Securiti"
slug: "creating-custom-assessment-templates-in-securiti"
updated: 2026-06-30T05:22:46Z
published: 2026-06-30T05:22:46Z
canonical: "helpcenter.securiti.ai/creating-custom-assessment-templates-in-securiti"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating custom assessment templates in Securiti

> [!NOTE]
> **Note**
> 
> This topic contains information on configuring regular assessment templates. If you have the Object Field Framework enabled, refer to the section [below](/latest/docs/creating-custom-assessment-templates-in-securiti#object-field-framework).

Securiti lets you build custom assessment templates that you can use when our standard templates don't fulfill your specific needs. You can either build a new template from scratch or build from multiple existing templates and modify it to suit your needs.

Once you build a custom assessment template, you can conduct internal assessments and invite vendors to submit assessments based on it just like our standard assessment templates.

(Optional) You can also configure Multi-Org Units for your assessments module.

> [!NOTE]
> **Note**
> 
> If Multi-Org units feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

1. Once you have it enabled for your tenant, in the left sidebar, click your user to de(select) the organizations you want to include or exclude for your tenant.

Securiti displays all the assessments data for your actively selected organizations without switching between them.
2. Now, before you can create a new template or import an existing template, Securiti prompts you to select the Organization you want.

To create a new custom assessment template:

1. In Securiti, open **Assessment Automation** , and choose **Assessments > Templates**.
2. On the Assessment Templates page, on the card for a template, click Options **(three vertical dots)** to access these settings to suit:

Custom templates include additional options:
  - Preview
  - Start an Assessment
  - Clone Template
  - Export as PDF (see step 10 below)
  - Edit Launch Settings

![Overview of assessment templates with details on categories, organizations, and modification dates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ff2bbb2-1f0c-1cea-fbe0-e50f3b63a705.png)
  - Export as CSV
  - Export as JSON
  - Delete
  - Copy to Another Org

> [!NOTE]
> Note
> 
> The Copy to Another Org option is not available for templates that contain Object Field questions. This is because object field configurations depend on catalog definitions and subtypes that may not exist in the target organization, and the same configuration cannot be guaranteed across organizations.

![List of assessment templates with details on organization, questions, and sections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c08c5e81-fd24-fc87-35bf-c7a46a8af7df.png)

To automate assessment workflows, see the [associate rules guide](/v1/docs/configuring-template-rules).
3. (Optional) To disable assessment non-owners from configuring the risk settings:
  1. Edit or clone an existing template on the Assessment Templates page.
  2. In the upper right corner of the template builder, click **Template Settings**.
  3. Mark the checkbox for "Hide ability to set risk manually from users who are not assessment owners" on the Template Settings popup, and click **Confirm**.

![Template settings for an assessment portal with options for reviewers and sections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7298f18-c774-7ee3-95b9-9f4afaed3846.png)
4. Near the top of the page, do one of the following:
  - To build a new template from scratch, near the top of the page, click **+ Build New Template > Start a Blank Template**.
    1. Enter a name in the **Template Name** field.
    2. In **Regulation Category**, select the desired category from the menu.
    3. Click **Create** to proceed.

![Creating a custom template with various assessment options and organization selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cd653ee-b370-2cbb-78a7-1f2d20ff1abe.png)
  - To build a new template by modifying (cloning) an existing template, near the top of the page, click **+ Build New Template > Use Existing Templates**.
    1. Enter a name in the **Template Name** field.
    2. In **Select Templates**, choose the preferred template from the menu for cloning.
    3. Click **Create** to proceed.
  - To build a new template by modifying multiple existing templates, near the top of the page, click **+ Build New Template > Use Existing Templates**.
    1. Enter a name in the **Template Name** field.
    2. In **Select Templates**, choose multiple templates from the menu.
    3. Click **Create** to proceed.

![Creating a new assessment template with organization and template name fields filled.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bacd3d1f-b30b-be49-f885-9a1711185465.png)
5. On the Build New Assessment Template page, use the tools in the Sections area to create and name assessment sections. You use sections to group the assessment questions into logical groups. You can create sections from scratch or import them from other templates.

"Active" status is displayed for the template you've published.
  - To create a new section, click **Actions** in the Sections area, and choose **Add Section**.
  - Similarly, to import a section from an existing template, on the Actions menu, choose **Import Sections**. Then use the popup to select the template and section to import.

![Overview of Securiti's Assessment Portal with sections for adding and importing assessments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2a90da7f-74d8-993c-a003-8fa9fb3b121b.png)

![Import sections for assessment template with options for category and template selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07bcc2d8-14bd-200e-b8a4-3de03dcc9614.png)
  - To edit the name of a section, click Options (three vertical dots) and **Edit** for the section, enter or modify the name, and click the "checkmark" when you are done.
  - To delete an unwanted section, click the card for the section, then near the upper right corner of the questions workspace, click **Delete Section**. Alternatively, click Options for the section and select **Delete**.

![Assessment template builder interface showing sections and actions for editing questions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5ee8960-e560-10cc-9523-4ad21ab01b13.png)
  - To move a section to a different place within the assessment, drag it up or down to the new location in the section list.
6. If you want, in each section of the template, do one of the following:
  - Add new or edit existing assessment questions.

For more information, [Creating questions in Assessment Template Builder](/v1/docs/creating-questions-in-assessment-template-builder).
  - Import questions from existing assessment templates:
    1. On the section, near the upper right corner, click **Import Questions**.

![Import questions into the assessment template with various selection options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6518c92-3b8c-5489-3fb1-daf10afafcb0.png)
    2. Use the popup to build a list of the questions you want to import, then click **Import**.
7. If you want, you can insert a "Welcome Section" to the assessment.

After enabling, click the "pencil icon" near the upper right corner to edit and compose a message. This also enables the option to "Add Attachment" for uploading any attachments with the message.

![Welcome section of an assessment template with instructions and options for attachments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-068c3f00-7135-7883-e01b-b75bad09499f.png)

See [Managing assessment files using Attachments](/v1/docs/managing-assessment-files-using-attachments) on information about what file types you can upload.
  - You must enable Welcome Section from the Template Settings for all the previously published or system-cloned templates.
  - If you have used a template with a welcome section before, Securiti also shows it in Vendor Assessments.
  - If you have made changes in the Welcome Section, on Reassessment, Securiti shows all the updated changes in the assessment.
  - Only an exported JSON assessment contains a welcome section. For any other assessment export, including PDF, CSV, or template export CSV does not contain a welcome section.
  - A welcome message does not change per user across a given assessment or template.
  - When you clone a custom template, Securiti only shows the Welcome Section in the newly created template if the template you cloned from had a welcome section. Otherwise, you have to enable it manually, as previously mentioned.
8. Click **Save** near the upper right corner of the page. Securiti automatically sets the status for the version you're editing to "Draft."

> [!NOTE]
> Note
> 
> Unless you save and publish the template, the previous version (if any) and its template settings you published take priority.
  - Click the **Version History** to view different versions of the template (if any). The menu shows the current version as "Active" while others are shown as "Archived."

![Assessment template builder interface showing sections, actions, and version history options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ef33559-a5c8-415e-1199-2a5ec6d77fd7.png)
  - (Optional) Choose the assessment version you want to view. Click **Restore** to open that version for editing or **Return to Current Draft** to return to the active version.

> [!NOTE]
> Note
> 
> By restoring the template to an earlier version you would lose any unsaved changes. We recommend you save the draft before proceeding.

![Assessment template builder interface showing version details and status options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5081222d-d27f-8525-2a7e-4f2e08763d78.png)
9. When you're done, click **Publish**.
10. (Optional) You can export the template or its previous versions. In the upper right corner of the template builder, click **Export as PDF**.

The menu shows you the version numbers (if any). Choose the one you want to export and the link to download is sent to your inbox. The PDF includes template details during the time of export such as date published, published by, question types, configured question properties enabled, errors recorded (object field only), etc.

![Interface for building a new assessment template with version history and status options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f602c7bd-4e76-e7be-863e-ca418bb30fe1.png)

You can also generate a PDF of the latest template version directly from the templates list page.

For more information, see the following topics:

- [Using the Assessment Launch Settings](/v1/docs/using-the-assessment-launch-settings)
- [Launching a new assessment in Securiti](/v1/docs/launching-a-new-assessment-in-securiti)

## Object Field Framework

> [!NOTE]
> **Note**
> 
> If Object and Field feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

Securiti introduces an improved way to manage object and field questions in assessments. The update links assessment questions to objects such as data mapping (assets, vendors, or processes) and fields, making them more meaningful and directly tied to real entities.

Securiti's Object Field Framework bakes multiple object and field questions into a single template which you can later use to answer assessments. After an object question is created, you can create a field question. You can subsequently create a new one or link an existing field question to associate with a single object.

> [!NOTE]
> **Note**
> 
> Securiti, by default, prevents editing of the existing catalog definition attributes, such as their labels and input types, when Object Field is enabled for the tenant. You can only delete or deactivate the individual items.
> 
> To edit information, delete and recreate a custom attribute, such as Host Type to modify its Label and Input Type fields.

This feature lets you select an existing entity or create a new entity for an object question in assessments.

Observe these caveats:

1. An object question for an existing data mapping entity is based on its subtype, AKA Definition Type. Any new object added during the assessment follows the same Definition Type, such as 'AWS S3.'

> [!NOTE]
> Important
> 
> You can’t select an Object question as “Reviewer only.”

![Screenshot_2025-01-20_at_2_23_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a07c2e3d-7751-2d1c-cb9e-49058b8aaf9b.png)
  1. On the **Settings** for the question, enable the **Allow Other** toggle to enable an object to be added at the assessment level.

![Screenshot_2025-01-20_at_2_23_56_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31fba512-c95b-b3fe-454b-83a39d8bd026.png)
  2. Similarly, click Settings and from the properties, enable the **Allow Multi-Select** toggle. Object Multi-Select questions allow respondents to select multiple instances of an object within a single question in an assessment.

> [!NOTE]
> Note
> 
> This setting is disabled by default and upon enabling, Securiti asks you for confirmation.
> 
> ![Dialog box explaining multi-select conversion and its effects on logic rules.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be3ffdee-22d2-9a48-2523-f55969e8bf83.png)

Click **Convert to Multi-select** to proceed.
  3. You can set the question as *required* but can’t configure any question logic.
  4. The template is invalid if you have not selected the Object Type, e.g., an Asset.

![Screenshot_2025-01-21_at_1_48_35_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66b3be02-29e2-4b5a-f0fe-6da4cc113281.png)
  5. Similarly, the template is invalid if you have not specified the **Subtype** of the object.

> [!NOTE]
> **Note**
> 
> You can't save or publish the template. Securiti shows you a message that your template has issues.
> 
> Clicking **Show Issues** opens up a side panel that shows all such questions. Click **Go to Question** for each question to resolve the issues.
> 
> ![Screenshot_2025-01-21_at_1_51_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5a52ff88-3697-d795-7473-2f598cd78791.png)
2. A field question sources its information from Catalog Definitions and its input type like Reference Lists, Date, etc., and the parent object details.

![Screenshot_2025-01-20_at_2_24_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c66b3f1-6b34-fe1a-c307-a5aa910687a9.png)
  1. The template is considered invalid if you do not specify the question in the **Link Object Question** field or subsequently fail to specify the item in the **Select Field**.

> [!NOTE]
> **Note**
> 
> You can't save or publish the template. Securiti shows you a message that your template has issues.
> 
> Clicking **Show Issues** opens up a side panel that shows all such questions. Click **Go to Question** for each question to resolve the issues.
  2. You can configure question logic for the question. It only applies to Boolean or Reference List field question types.

With the 1.130 release, Securiti lets you control skip logic for field questions. You can choose to show an empty value in the object details for skipped text or reference list type field questions by enabling the **Clear values on write back** toggle in question settings, as shown below.

![Screenshot_2025-04-08_at_12_25_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2405b297-bafa-66bd-259a-68fb7e331499.png)

By default, for a skipped field question, Securiti shows the existing value in the source of truth module on assessment completion.
  3. Securiti shows an invalid error for the field question in the template upon page refresh if a catalog definition attribute is deactivated or removed. You must update the template with a new field value for that question or enable the item.

![Screenshot_2025-01-20_at_2_29_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9256a4ab-aada-bb96-0727-208c7e3ccda0.png)

![Screenshot_2025-01-20_at_2_45_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3104adaa-0579-03a3-d81a-7088ed59a654.png)

> [!NOTE]
> **Note**
> 
> You can save the template, but Securiti doesn’t let you publish it and shows an error.
> 
> ![Screenshot_2025-01-20_at_2_45_50_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-239a59e4-2fa1-642d-bedd-90fb13c431c1.png)
  4. If a field question containing any Reference List item is deleted or deactivated, at the template level, the question isn’t impacted.
  5. You can’t link the same field question to the same object question. For example, you must choose a different object to link with another Purpose field question. Similarly, you can’t link two Description field questions to the same object question.

> [!NOTE]
> **Note**
> 
> You can’t link a field question to an object question in the section below. Field questions linking works upward, meaning, either to the object question within the same section or to those in the sections above.
  6. Securiti shows you the impact of deactivating or deleting the catalog definition attribute or Reference List item(s) on the object details page in the Data Mapping module.
3. If an object question is removed from the template, Securiti shows a confirmation popup that any linked field questions will also be removed.

![Screenshot_2025-01-20_at_2_57_17_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85193bee-9578-c6a3-b4d0-77e6a815f6ed.png)
  1. If you move a field question atop its object question, Securiti shows an error message, and vice versa.
  2. If you move a section containing a field question(s) atop the section that contains its object question(s), Securiti shows an error message.

![Screenshot_2025-01-20_at_3_01_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2577b494-caf3-bdb7-e721-a7ed7e8ada19.png)
4. In the cases where the subscription has expired for your Securiti tenant or due to the deactivation of the module by the admin, templates containing object and field questions become invalid. They’re no longer available for you to launch an assessment.

![Screenshot_2025-01-20_at_3_22_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5e597bb2-3acb-4b8c-4c02-9229c79b5d2f.png)

Similarly, if an error isn’t fixed or exists at the template level, Securiti doesn’t let you initiate an assessment using that template.

![Screenshot_2025-01-20_at_3_32_50_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f87cfe8-8d26-3d63-1441-09b77c7721af.png)

> [!NOTE]
> **Note**
> 
> Currently, Securiti shows the template in the Template dropdown, but it displays an error when you choose to start an assessment.
5. > [!NOTE]
> **Important**
> 
> The current Object and Field implementation is limited to Data Mapping, and the object referred to is currently a data mapping entity (asset, vendor, etc.).

Proceed to [Answering Object Field questions](/v1/docs/answering-assessment-questions-in-securiti).

Reassessing an assessment lets you identify changes in regulatory compliance and organizational behaviors. As a Question Owner, you can modify the reassessment by filling in new responses or resubmitting previous answers. Where response option(s) are modified, the question is treated as new with no answers.

An asset records data for any application or store. You can use It to record an asset's name, description, purpose, etc. Also, you can use an asset in processes.

Catalog Definitions define what sections and fields an entity uses to record the details.

A reference list is a set of options or settings that lets you configure questions in a risk assessment, such as Single or Multi-select.

## Related

- [Creating and customizing data mapping templates](/creating-and-customizing-data-mapping-templates.md)
- [Configuring email notification templates](/configuring-settings-email-notification-templates.md)
