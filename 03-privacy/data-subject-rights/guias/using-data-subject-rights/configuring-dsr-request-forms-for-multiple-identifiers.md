---
title: "Configuring DSR request forms for multiple identifiers"
slug: "configuring-dsr-request-forms-for-multiple-identifiers"
updated: 2025-11-02T11:24:00Z
published: 2025-11-02T11:24:00Z
canonical: "helpcenter.securiti.ai/configuring-dsr-request-forms-for-multiple-identifiers"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring DSR request forms for multiple identifiers

To process DSR requests with multiple identity identifiers, you must configure your DSR request forms to collect the identity PDs you want to use to identify personal data in your data systems.

> [!NOTE]
> **Note**
> 
> While searching data through data systems, DSR robotic automation uses **OR** logic when multiple data subject identifiers are set in a DSR form. This means it returns records that match any of the identifiers. If you want results for a single identifier (for example, CPF only), disable other identifiers in the form.

For more information about creating and editing DSR request forms, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms) .

1. In Securiti, choose **Data Subject Rights > DSR Request Form Builder**.
2. Click the card for the DSR request form you want to configure.
3. Advance to the **Customize Content** tab.

Depending on the state of the form, you may have to click **Save & Next** on the DSR Template or Logo & Branding tab.
4. In the Define Form Fields and Requirements area, drag in a new Custom field of type **Text Field**.

![Enhanced_DSR_drag_custom_text_field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a28a2827-e6eb-735a-092f-305748d59f79.png)
5. On the Text Field component popup Display tab, edit the label for the text field to suit.

![Enhanced_DSR_field_label.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-568145ff-ef71-6436-c6aa-7c452d074462.png)
6. (Optional) If you want the text field to be required and so marked with a red asterisk, click the **Validation** tab and mark the Required checkbox.

![Enhanced_DSR_optional_required_field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10e1fb95-8ab5-9143-15ee-3eff5bce7165.png)
7. Click the **Identity Profile** tab and mark the **Identity PD** checkbox.
8. From the PD Attribute menu, choose the type of attribute being collected in the text field.

![Enhanced_DSR_Identity_PD.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2022065e-dbe2-062d-97ee-be9c0bce5d8d.png)
9. On the Text Field Component popup, click **Save**.
10. On the DSR Form Builder page, click **Save & Next**.

Securiti shows you a preview of the form.
11. Near the bottom of the form preview, click **Publish**.
