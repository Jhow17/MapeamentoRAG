---
title: "Accepting non-digital DSR requests"
slug: "accepting-non-digital-dsr-requests"
updated: 2025-11-02T11:29:07Z
published: 2025-11-02T11:29:07Z
canonical: "helpcenter.securiti.ai/accepting-non-digital-dsr-requests"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Accepting non-digital DSR requests

You can use Securiti to accept and process DSR requests from data subjects who do not have, or do not want to use, email addresses. Securiti can also now process DSR requests for data subjects who want to receive their reports in physical format.

You enable non-digital DSR requests on a DSR request form. You must also configure that form so that it requires an alternative form of identification. For example, for Brazilian residents, CPF can be used as an alternative to verify the Data Subject’s identity. To configure CPF:

1. In Securiti, open **Data Subject Rights**, then choose **Settings > Form Builder**.
2. Choose the form you want to use or create a new one.
3. On the **Form Settings** tab, expand the **Report Settings** area and mark the checkbox for **Allow non-digital report access**. This action adds a **Report Access** menu in the DSR form with options for "Physical" and "Digital" reports.Under this setting, on published DSR forms, an email address is no longer a required field to access the report in a physical (non-digital) format.
4. On the **Customize Content** tab, add a new custom field of type “text field” onto the form.
5. On the Text Field Component popup Display tab, set the Label to “CPF” or similar and set the Input Mask to **999.999.999-99**.
6. On the API tab, set the Property Name to **cpf_brazil**.
7. On the Validation tab, mark the checkbox for **Required**.
8. On the Identity Profile tab, mark the checkbox for **This field is a Data Subject identifier**, and for PD Attribute choose **BR CPF**. Then click **Save** to save the new custom field for CPF.
9. Click **Review & Publish** and then click **Publish** to publish the DSR request form.
10. Once the DSR form is published, data subjects can choose the "Physical" option from the **Report Access** menu to make the email address field optional when submitting the request.

![Screenshot_2024-07-10_at_12_54_29_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a49ac2f7-5fe1-19ff-c32d-cdce01247321.png)
