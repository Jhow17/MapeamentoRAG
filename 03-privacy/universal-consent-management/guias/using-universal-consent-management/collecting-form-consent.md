---
title: "Collecting form consent"
slug: "collecting-form-consent"
status: "new"
updated: 2026-03-31T09:07:58Z
published: 2026-03-31T09:14:21Z
canonical: "helpcenter.securiti.ai/collecting-form-consent"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Collecting form consent

**Scenario**

As a Data Privacy Officer, you must ensure website visitors clearly consent to how their personal data will be used. When consent is tracked manually, form submissions are stored but the exact consent action and purpose are often missing. For instance, a website visitor fills out a product demo request form, but there is no proof they agreed to follow-up marketing emails. Using Securiti’s web plugin, you can extract form fields and consent options, generate a JSON code snippet, and embed it into your website forms. This ensures each submission automatically captures consent details without manual tracking, reducing errors, while recording consent actions, data, and purpose for clear auditability.

Many regulatory systems require that you inform website visitors how you use personal information that you collect on website forms, and also obtain explicit consent for the collection of this information for certain data processing activities by having data subjects click a consent button or other interface element. Securiti helps you comply with these regulations by recording such consent actions and associating them with the personal data and the reason it was collected.

For each form, you use the Securiti browser plugin to extract the form fields and buttons and compile them into a JSON object that you upload to Securiti. You then use Securiti to generate a code snippet that you add to the code for the web form. The code sends Securiti information about each form consent event and the personal data submitted with it.

> [!NOTE]
> **Important**
> 
> If you make changes to your form, you must repeat this process to generate and embed an updated code snippet in the updated form.

As per most global data protection laws, elements of a valid consent are:

| Consent Element | Purpose |
| --- | --- |
| Freely given consent | Lets your data subjects to refuse and withdraw consent at any time without any detriment. The consent withdrawal mechanism must be as easy for the user as giving consent. |
| Specific consent | Obtain separate consent for separate data processing purposes. |
| Informed consent | Provide adequate and relevant information to data subjects while obtaining consent such as the purposes of processing operations, type of data to be collected and used, and the existence of the right to withdraw consent. |
| Unambiguous consent | Obtain explicit and clear consent, and do not use pre-selected options. |

Organizations must provide following information to fulfill their privacy legal obligations to their data subjects on the front-end forms while acquiring consent from them.

- The legal basis and purpose of each data processing operation
- The type of data that the organization collects and uses
- The right of data subject to withdraw consent at any time along with the method of doing so
- Retention period of personal data

> [!NOTE]
> **Note**
> 
> To collect consent for the weekly newsletters, you must clearly state your intention as expressed below:
> 
> We require your name and email address to provide you with the newsletter. The data processing is based on your consent. You can revoke your consent at any time by clicking on the **unsubscribe link** included in every newsletter, by changing your preferences on the preference center, or by sending us an email. Once unsubscribed, we only retain your necessary information to ensure that we respect your newsletter subscription preferences in the future.

## Related

- [Installing the browser plugin](/installing-the-browser-plugin.md)
- [Extracting the form JSON](/extracting-the-form-json.md)
- [Importing the form JSON into Securiti](/importing-the-form-json-into-securiti.md)
- [Generating and embedding the form consent code](/generating-and-embedding-the-form-consent-code.md)
