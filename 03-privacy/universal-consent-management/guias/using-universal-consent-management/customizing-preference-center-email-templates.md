---
title: "Customizing universal preference center email templates"
slug: "customizing-preference-center-email-templates"
updated: 2026-05-19T05:24:09Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/customizing-preference-center-email-templates"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Customizing universal preference center email templates

**Scenario**

As a Data Privacy Officer, you need consistent and compliant communication across all consent touchpoints, but managing separate emails for multiple preference centers can lead to duplication and inconsistency. For instance, if your organization operates multiple preference centers for different products or regions, maintaining separate email formats for consent updates or preference confirmations can create duplication and governance challenges. Securiti’s Email Templates library lets you create standardized templates and reuse them across preference centers, helping you maintain consistency, simplify management, and reduce operational effort while staying aligned with compliance and brand guidelines.

Securiti lets you build a library of email templates for your universal preference center, streamlining communication management between you and your data subjects. You can easily create, manage, and apply a single email template across multiple preference centers within your Securiti tenant, simplifying template management and ensuring consistency.

If you update the template, the changes made in that template are reflected across all the preference centers where that template is used. This way you don’t need to republish each preference center individually.

Use the following table to understand the Securiti roles and their permissions related to email templates:

| Role | Create/Edit Email Templates | View Email Templates |
| --- | --- | --- |
| Super Admin | Yes | Yes |
| Organization Admin | Yes | Yes |
| Module Owner | No | Yes |
| User | No | Yes |
| Operator | No | Yes |
| DPO | No | Yes |

You can create and customize the following types of email templates:

- Preference Center
- Double Opt-in Confirmation

## Creating a preference center email template

### 

To create a new email template for your preference center:

1. In Securiti, open **Universal Consent Management**, and choose **Advanced Settings > Email Templates**.
2. From the upper left corner of the **ALL TEMPLATES** left sidebar, click **New +** to create a new email template.
3. In the **New Template** popup, enter the template name, and click **Create Template**, as shown below.

![create_email_temp_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0196f8f-d297-b4f3-30b5-9b82aaec685e.png)![create_email_temp_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f1e4595-5f70-d5e2-c480-dffa7724819d.png)

> [!NOTE]
> **Note**
> 
> The **ALL TEMPLATES** sidebar displays 10 email templates, with pagination set at 10 email templates per page. To view more templates, near the lower right corner of the **ALL TEMPLATES** sidebar, click **Next** (> icon) and move to the next page.
4. To customize an email template:
  1. Near the upper left corner of the email template, click **Edit** (pencil icon) to edit the title and give a convenient name. Then click the check mark to save the name, as shown below.

![create_email_temp_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03957ac5-5638-87c5-5bd5-28e7e63ffa92.png)

![create_email_temp_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c835ce5-aad1-86c6-3edf-005c4b133935.png)
  2. Click **Upload Image**, navigate to a file containing your organization’s logo, and then click **Upload** again, as shown below.

![create_email_temp_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f912649-2883-aadd-7b87-7c720a4a833c.png)![create_email_temp_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c22fe4f0-1430-c27a-a10a-33a960926eff.png)

![create_email_temp_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1f55bc6-738a-9547-4828-0f14a1697cf7.png)

![create_email_temp_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b0c6a15b-8465-bd07-f0b8-95e9b3d03b8f.png)

> [!NOTE]
> **Note**
> 
> You can upload the logo for your email template in **PNG**, **GIF**, or **JPG** formats and remove or change it at any time.
  3. Add an appropriate email subject, as shown below.

![create_email_temp_9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b529c2ff-43a9-931d-aa29-07a52efbbc93.png)
  4. Use the tools in the **Body Text** section to customize the verbiage for your email template. Near the upper right corner of the **Body Text** section, click **Insert Variable +** to add the required variables, as shown below.

![create_email_temp_10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2a8f1d52-2d2f-867e-1618-98ed7c7068bf.png)![create_email_temp_11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-71c8531f-2fda-ebc3-6118-4831a3baaf55.png)

Use the following table to understand the use of variables in the email template:

| **Variable Name** | **Variable Syntax** | **Description** |
| --- | --- | --- |
| Visit Preference Center Button | `[[Visit-Preference-Center]]` | Lets you display a button that your data subjects can click directly from the email to access the preference center. |
| Preference Center Link | `[[Preference-Center-Link]]` | Lets you embed a link of your preference center in the email. |
| Preference Center Url | `[[Preference-Center-Url]]` | Lets you add a static URL of your preference center in the email, and you can further customize it. |
| Tenant Name | `[[Tenant-Name]]` | Lets you add your Securiti tenant name in the email. |
| Tenant Domain | `[[Tenant-Domain]]` | Lets you add your Securiti tenant domain in the email. |
  5. Add the label for the preference center button.
  6. Enter either the HEX code or a color name, such as Red, Blue, or Violet, to customize the button's background and text colors, as shown below.

![create_email_temp_12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dfd230f8-2627-c676-5298-717ac45a3386.png)
5. To save changes:
  1. Near the bottom of the template tab, click **Save**, or on from the upper right corner of the **UCM Preference Center Email Templates** page, click **Save**.

![create_email_temp_13.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f462251-161e-8d8f-81c2-c04a1d73b16f.png)
  2. On the **Update Template** popup, click **Update Template** to save your changes, as shown below.

![create_email_temp_14.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f07a038b-9291-2933-ff1a-6ec6e2b625ef.png)
6. To preview your changes, from the upper right corner of the template, click Preview, as shown below.

![create_email_temp_15.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d7a05677-86b7-5ae5-acb4-ca08c8b49ca0.png)

![create_email_temp_16.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f21bedd4-2e91-e0df-62bc-1c80d619e8bf.png)

> [!NOTE]
> **Note**
> 
> You can preview the email template at any time while working on it.
7. To delete an email template, click **Options** (three dots), and select **Delete**, as shown below.

![create_email_temp_17.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-676f10f2-7a03-7b6b-e9bb-44542d4d965b.png)![create_email_temp_18.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-35dd145d-126f-a203-0fef-e856b5d2735b.png)
8. To filter out a specific email template, from the upper left corner of the **UCM Preference Center Email Templates** page, enter the email template title in the search bar, as shown below.

![create_email_temp_19.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c725cfbf-e8cf-8501-320e-a30d78e713f5.png)

## Creating a double opt-in email template

To create a new double opt-in email template:

1. In Securiti, open Universal Consent Management, and choose **Advanced Settings** **> Email Templates**.
2. Near the upper left corner of the **ALL TEMPLATES** left sidebar, click **New** **+** to create a new email template, as shown below.

![Email template creation interface showing options for double opt-in confirmation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_1.png)
3. On the **New Template** popup, select **Template Type** as **Double Opt In Confirmation**, enter the template name, and click **Create Template**, as shown below.

![Creating a new email template for double opt-in confirmation with specified details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_2.png)
4. To customize an email template:
  1. Near the upper left corner of the email template, click **Edit** (pencil icon) to edit the title and give a convenient name. Then click the checkmark to save the name, as shown below.

![Email template management interface showing double opt-in email details and options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_3.png)
  2. Click **Upload Image**, from the **Upload** popup, browse to the file containing your organization’s logo, and then click **Upload** again to upload the logo, as shown below.

![Upload dialog for email template with logo file and confirmation message.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_4.png)
  3. In the **Email Subject** text field, add an appropriate subject line.
  4. Use the toolbar located at the top of the **Body Text** section to customize the verbiage for your email template. Near the upper right corner of the **Body Text** section, click **Insert Variable +** to add the required variables, as shown below.

![Email template for double opt-in confirmation with subject and body text sections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_5.png)

Use the following table to understand the use of variables in the email template:

| **Variable Name** | **Variable Syntax** | **Description** |
| --- | --- | --- |
| Visit Preference Center Button | `[[Visit-Preference-Center]]` | Lets you display a button that your data subjects can click directly from the email to access the preference center. |
| Preference Center Link | `[[Preference-Center-Link]]` | Lets you embed a link of your preference center in the email. |
| Confirm Preferences | `[[Confirm-Preferences]]` | Lets you display a button that your data subjects can click directly from the email to access the confirmation message page. |
| Confirm Preference URL | `[[Confirm-Preference-Url]]` | Lets you embed a link of your confirmation message page in the email. |
| Preference Center Url | `[[Preference-Center-Url]]` | Lets you add a static URL of your preference center in the email, and you can further customize it. |
| Link Expiration | `[[Link-Expiration]]` | Lets you add preference center link expiration time. |
| Tenant Name | `[[Tenant-Name]]` | Lets you add your Securiti tenant name in the email. |
| Tenant Domain | `[[Tenant-Domain]]` | Lets you add your Securiti tenant domain in the email. |
  5. Add the label for the confirm button.
  6. Enter either the HEX code or a color name, such as Red, Blue, or Violet, to customize the button's background and text colors, as shown below.

![Email template for double opt-in confirmation with highlighted button and links.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_6.png)
5. To save changes, near the bottom of the template tab, click **Save**, or on from the upper right corner of the **Email Templates** page, click **Save,** as shown below.

![Email template for double opt-in confirmation with subject and body text details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_7.png)
6. On the **Update Template** popup, click **Update Template** to save your changes, as shown below.

![Template update prompt for email preferences with options to confirm or cancel changes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_8.png)
7. To preview your changes, from the upper right corner of the template, click **Preview**, as shown below.

![Email template for confirming preferences with links for consent management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_9.png)
8. To delete an email template, from the **ALL TEMPLATES** left sidebar, click **Options** (three dots), and select **Delete**, as shown below.

![Email template for double opt-in confirmation with subject and body text details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_email_template_10.png)

## Related

- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Customizing your universal preference center](/customizing-your-preference-center.md)
- [Configuring the UAE PDPL privacy notice template](/configuring-the-uae-pdpl-privacy-notice-template.md)
- [Configuring the Brazil LGPD privacy notice template](/configuring-the-brazil-lgpd-privacy-notice-template.md)
