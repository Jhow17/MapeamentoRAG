---
title: "Importing the form JSON into Securiti"
slug: "importing-the-form-json-into-securiti"
updated: 2026-06-19T09:09:27Z
published: 2026-06-19T09:09:27Z
canonical: "helpcenter.securiti.ai/importing-the-form-json-into-securiti"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Importing the form JSON into Securiti

After you extract the form JSON, you create a form object in Securiti and import the form JSON into it.

1. In Securiti, open Universal Consent Management and choose **Universal Consent** > **Form-Based Consents**.
2. On the **Form-Based Consent** page, from the upper right corner, click **+ New Endpoint** to create a new endpoint.

Each endpoint is a domain containing one or more forms.
3. On the **Form Consent** page, from the **Basic Information** tab enter the following information, as shown below:

| Information Field | Description |
| --- | --- |
| Endpoint Name | Enter a convenient name for the endpoint. |
| Endpoint URL | Enter the URL for the page containing the form. |
| Enable referer-based CSRF check (checkbox) | Mark this checkbox if you want Securiti to secure your web consent forms from the Cross-Site Request Forgery (CSRF) attacks. Once enabled, this setting prevents vulnerability tools from detecting your hosted consent forms as vulnerable. > [!NOTE] > **Important** > > This functionality works only if the domain name in the **Endpoint URL** field matches where your consent form is hosted. For instance, if you have added `https://www.securiti.cloud.ai` in the Endpoint URL field, only the consent form on that exact domain undergoes the referer-based CSRF check. ![Checkbox--Form-Consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf4a1b90-4a35-be6d-a0bd-8c0a2df72ed8.png) |
| Notes | (Optional) Enter supplementary details or context that you think is important for the purpose of the consent form. Use this field as a flexible area to include any additional information that is relevant to the form, but not covered by its standard fields as shown below. ![Notes--Form-Consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8396412-3347-b6f3-5082-3d72e83cac50.png) |
| Business Unit | (Optional) Enter the name of the business unit that maintains the form. |
| Team | (Optional) Enter the name of the team that maintains the form. |

![All-Fields--Form-Consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e88ef171-ca10-4f84-04d0-6e4dab8f777c.png)
4. Near the bottom of the page, click **Create Endpoint & Continue**.
5. On the **Form Configuration** tab, and from the side panel on the left side of the page, click **+** to create a new form instance.
6. Near the upper left corner of the form workspace, click **Import JSON**. On the drag & drop box, click **Select a file to upload** and navigate to the file. ![form_consent_drag_drop.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e133e1a-9532-2293-175e-993d214ba546.png)
7. If you upload JSON with two forms in it, Securiti extracts the form names from the `formSelector` fields and displays the **Import Form Configuration** popup.

Mark the checkbox for the form to import, and click **Import**, as shown below.

![Import form configuration window showing options for selecting consent forms.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/multi_consent_form.png)

> [!NOTE]
> **Important**
> 
> Securiti does not support multi-selection form fields. If your web form includes a field that lets site visitors or data subjects select multiple options, such as a menu with checkboxes, you must manually update the value of `type` key in the extracted JSON. Change its value from `select-multiple` to `select-one` before importing the JSON file into Securiti, as shown in the following code snippet.
> 
> Additionally, ensure that the selected values from the multi-selection field are collected and stored as a single value, such as a concatenated string or an array, based on your implementation.
> 
> ```json
> {
> "type": "select-one",
> "name": "example_model[]",
> "selector": "[name = \"example_model[]\"]"
> }
> ```

Securiti imports the JSON file and parses it.
8. Inspect each form field to make sure that Securiti correctly parsed it, and adjust it as necessary. The following table describes the fields:

| Form Name | Form Configuration Name | Enter a convenient name. |
| --- | --- | --- |
| Purpose | Enter the processing purpose for which you are collecting personal data, choose one from the menu, or add a new one. For details on adding a new processing purpose see, [Adding a new processing or consent purpose](/v1/docs/importing-the-form-json-into-securiti#adding-a-new-processing-or-consent-purpose). |
| Import JSON | Navigate to the file containing the JSON. |
| Form Identifier | Type | Choose Attribute or Name. |
| Identifier Attribute | The attribute that identifies the form on the page. |
| Identifier Value | The ID value of the form on the page. |
| Form Subject Identifier | Field Type | Choose Input or Select. |
| Field Name | The field name as it appears in the form code. |
| Field Selector | The field selector as it appears in the form code. |
| Attribute Type | Choose a type from the menu. |
| Consent Value | Identifies whether consent applies to the field. |
| Primary Identifier | Indicates that the field can be used to identify the data subject. We recommend you designate email address as the primary identifier. > [!NOTE] > **Important** > > You must pass a valid value for this field. |
| Consent Selection Identifier | Field Type | The type of element that signifies consent. |
| Field Name | The element name. |
| Field Selector | The field selector name in the form code for the checkbox or radio button. |
| Consent Value | Use the menu to choose the state of the radio button or checkbox that grants consent, either checked or unchecked. |
| Purpose | Enter a granular purpose for which the data subject is consenting to the use of their personal data, choose an existing one from the menu, or add a new one. For details on adding a new processing purpose see, [Adding a new processing or consent purpose](/v1/docs/importing-the-form-json-into-securiti#adding-a-new-processing-or-consent-purpose). |
| Form Submission Trigger | Form Trigger Type | The type of event that submits the form. - **Form Submit** The form submission is recorded when you submit the consent form. - **Button Click** The form submission is recorded only when you click a particular defined button. For instance, you can name the button as **Submit** or **Agree** etc. |
| Field Name | The name of the element that submits the form. |
| Purpose | Choose the purpose for which the form submission trigger grants consent. > [!NOTE] > **Note** > > The Purpose menu only appears if Securiti does not detect a consent selection identifier for a form. |
| Consent Expiration | Expiration Duration (in Months) |  |
9. Near the upper right corner of the page, click **Save** and then click **Publish**.

> [!NOTE]
> **Important**
> 
> You must redeploy your form consent code after making any changes in the form configuration.
10. Proceed to [Generating and embedding the form consent code](/v1/docs/generating-and-embedding-the-form-consent-code).

## Adding a new processing or consent purpose

You can add a new processing purpose or consent purpose from within the **Form Configuration** tab if it is not listed in the **Purpose** menu.

To add a new processing purpose:

1. In the Form Name section, navigate to the end of the Purpose menu items, and click **+ Add New Processing Purpose**, as shown below.

![Form consent interface showing options for processing purpose.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PC_HC_4.png)
2. In the **Add Processing Purpose** popup, type the processing purpose, and description. You can also enter **External ID** (optional), select **Processing Purpose Category**, and set translation languages.

After adding these details, click **Save**, as shown below.

![Form consent interface for email marketing with processing purpose and description fields.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FC_PP.png)

To add a new consent purpose:

1. In the **Consent Selection Identifier** section, navigate to the end of the Purpose menu items, and click **+ Add New Consent Purpose**, as shown below.

![Form fields for consent purpose selection, including add a new consent purpose and other options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PC_HC_5.png)
2. In the **Add Consent Purpose** popup, type the consent purpose, description, **External ID** (optional), set translation languages, and then click **Save**, as shown below.

![Form for adding consent purpose with options for translation and external ID.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FC_CP.png)

See [Configuring processing purposes and consent purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes) for information on building a library of processing purposes.

Cross-Site Request Forgery (CSRF) is when a malicious website tricks your data subjects into performing an action on another website where they are authenticated. For instance, it is like someone making your data subjects unintentionally do something on a website where they are logged into without their knowledge or consent.

## Related

- [Generating and embedding the form consent code](/generating-and-embedding-the-form-consent-code.md)
- [Configuring processing purposes and consent purposes](/configuring-processing-purposes-and-consent-purposes.md)
