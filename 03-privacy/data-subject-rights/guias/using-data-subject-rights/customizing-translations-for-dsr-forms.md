---
title: "Customizing translations for DSR forms"
slug: "customizing-translations-for-dsr-forms"
updated: 2026-08-09T18:56:08Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/customizing-translations-for-dsr-forms"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Customizing translations for DSR forms

When you enable multiple languages, Securiti relies on an integrated translation service to automatically convert DSR form content into the selected language. This helps speed up form setup; however, the translated text may not always capture the intended meaning. To address this, you can edit system-generated translations in DSR forms when the default results do not meet your expectations.

While configuring the form, you can edit translations for:

- Request types
- System or custom fields
- Error messages, tooltips, and descriptions for each form label
- DSR request summary page
- Headline and body section of DSR form

If Enable Dynamic Rendering of Request Types is marked on a multi-language form, Securiti generates translations for every request type configured across your tenant when you publish the form. This includes request types not shown in the form builder. For more information, see [Creating and publishing DSR request forms](/latest/docs/creating-and-publishing-dsr-request-forms).

To edit machine generated translations:

1. Open the form in the DSR form builder, configure all relevant components and click the **Language Translations** tab.
2. Enable the language preference option and choose a language from the menu. For more information on how these options work, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).

When you enable the language preference option for the first time, you must publish the form to see system-generated translations.

![Screenshot_2025-03-26_at_2_48_28_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-623750dc-de3f-f9ab-3383-b4beee6d53fc.png)

Once the translations are ready for a newly created form, Securiti notifies form owners via an email.

![Screenshot_2025-03-26_at_6_49_31_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70738a7e-96ac-d840-ca87-abf2d4aa0f41.png)

> [!NOTE]
> **Note**
> 
> After you publish the form, translations reflect within 5–10 minutes and you also receive an email notification. Each time you add a new field or language to the form, you must re-publish it. If you don’t provide custom translations for newly added fields and leave them empty, Securiti generates default translations on publishing the form. To fall back to default translations, clear the translations for the relevant fields and re-publish the form.
3. Once you receive the translation readiness email, reopen the form in the form builder. Under the **Language Translations** tab, you see the following message:

![Screenshot_2025-04-06_at_7_43_12_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-352077b3-8082-4b4a-b8f9-7096bd87c136.png)

From the **Language Translations** section, choose the language for which you want to view system-generated translations. Expand the accordion of the required section and edit translations as per your need.

![Screenshot_2025-08-20_at_9_56_13_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e2717c36-439d-afb8-e98b-29f9ee311b4a.png)

> [!NOTE]
> **Note**
> 
> You cannot manually add custom translations for data elements listed in the rectification fields menu on the DSR form. They rely on system-generated translations only. However, if the label of a data element exactly matches a form field label (case and spacing included), and you have added a custom translation for that form field, that same translation automatically applies to the data element in the **Data Element Type** menu.
> 
> ![Screenshot_2025-03-27_at_5_29_32_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5f5b7a67-2054-330b-434a-0dc4dc89f8a3.png)

Click **Additional Translations** (gear icon) next to any form label to edit its error message, tooltip, or description. Make your changes and click **Save Translations**.

![Screenshot_2025-04-06_at_7_55_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e16238e-0956-9ef0-31d8-57ba9458ae8b.png)

> [!NOTE]
> **Note**
> 
> Observe the following caveats:
> 
> - The gear icon is disabled when no tooltip, placeholder, error message, description or any other textual attribute is not set for a field. For more information on configuring these elements, see [Form Builder Tabs](/v1/docs/form-builder-tabs).
> - After adding any of these attributes, you must publish the form to view the system-generated translations.
4. Once done, publish the DSR form.

## Related

- [Supported languages in Data Subject Rights](/supported-languages-in-data-subject-rights.md)
