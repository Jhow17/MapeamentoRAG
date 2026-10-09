---
title: "Configuring DSR email notification templates"
slug: "configuring-dsr-email-notification-templates"
updated: 2026-05-07T09:23:28Z
published: 2026-05-07T09:23:28Z
canonical: "helpcenter.securiti.ai/configuring-dsr-email-notification-templates"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring DSR email notification templates

Securiti offers pre-built content for notification templates in the Data Subject Rights module. You can modify templates for the emails that Securiti sends out to data subjects to notify them of status changes in their DSR requests. You can also modify the translated versions that Securiti sends according to the language settings of the DSR form or the data subject's geographic location.

1. Do one of the following to open the notification templates page for Data Subject Rights:
  - In the Data Subject Rights module, choose **Settings > Notification Templates**.
  - In Securiti Dashboard View open **Settings** and choose **Data Subject Rights** from the left-hand side menu, then choose **Notification Templates**.
2. Near the upper right corner of the page, click **Language** (globe icon) and choose the language in which you want to view or modify the template, as shown below.

![langiages_in_notification_templates.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4aa45994-3b88-9bb3-379c-5630a23d54af(1).png)

> [!NOTE]
> Note
> 
> Changes made to a notification template in one language do not automatically appear in other language versions. After updating and publishing a template, you must manually review and update each translation to maintain consistency across supported languages.
3. In the list near the left edge of the page, click the card for the message template you want to modify.

![notification_templates.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b35affb2-79bb-f9b6-bd7d-66fa204364ca(1).png)
4. You can change the email subject or add some additional text.
5. Use the tools on the page to edit and format the body text of the template to suit your needs:

> [!NOTE]
> **Note**
> 
> The image above the body text is the company logo you uploaded on while configuring a DSR Form. For more information, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms). Additionally, you cannot attach a hyperlink directly to a particular piece of the text within notification templates. If you want to include a hyperlink, you can place it anywhere in the template but not directly behind a specific piece of text.
  - Use the formatting toolbar to apply body text formats or choose variables to embed in the body text of the message.

![Screenshot_2024-03-01_at_1_01_13_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5df80304-8271-cf34-3099-41aa48d7350c(1).png)
6. Once done, click **Save** to save the template in draft form. Then, click **Publish** to use the customized notification template.

> [!NOTE]
> **Note**
> 
> Only published templates can be used; if the template is in draft form, it cannot be used.

You can also view how a template appears when published and preview it as an email.

![publish_template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6aaca9b-8643-5f0c-753a-78d835da835d(1).png)

To revert changes made to a template and restore it to the pre-built content provided by Securiti, at the upper right corner, click **Revert**.

![Screenshot_2024-03-01_at_1_01_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59f64a6b-655c-380f-ec88-ebb2c3ef4fdc(1).png)

> [!WARNING]
> **Important**
> 
> The Message Notification template is structured on top of [Customer messaging templates](/v1/docs/creating-and-editing-messaging-templates). The [Message] variable within the template retrieves the message sent by a DSR owner to the data subject from the DSR Workbench using a customer messaging template.
> 
> ![Screenshot_2025-04-29_at_2_03_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da1d7b9d-ed6b-2b89-c413-9e7435c300f8(1).png)
> 
> Each time a DSR owner sends a message to the data subject, they receive an email containing the message content and a "View Message" link. They can click on the link to access Privacy Central and respond to the message.
> 
> ![Screenshot_2024-01-10_at_10_30_02_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-126cb8d5-c492-df82-ce91-b4ec346e1a8a(1).png)

### Exporting and importing notification templates

You can now export and import notification templates between environments using CSV format. This lets you reuse templates across environments or tenants instead of updating them manually in each one.

You can export one or all templates in selected languages, then import them into another environment to update existing templates and maintain consistency.

After each export or import, Securiti sends you an email with a CSV attachment:

- **For exports**: A CSV file containing all notification templates in the selected language.
- **For imports**: A CSV file listing which templates were successfully imported and which were skipped, along with the reason.

To export notification templates:

1. In the Data Subject Rights module, choose Settings > Notification Templates.
2. In the upper-right corner, click Export.
3. On the Export Templates page, select the templates you want to export and choose the export language:
  1. To export templates in all available languages, select All Languages.
  2. To export specific languages, select Only Selected Languages, then pick from the menu.
4. Click Export.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(254).png)

Securiti sends you an email with a download link. Click the link to download a CSV file containing notification templates.

> [!NOTE]
> **Note**
> 
> - The Description column (including its content) is always in English in the exported file.
> - The exported CSV includes column headers in English, regardless of the selected export language.
> - When you select Only Selected Languages option on the pop up , Securiti pre-selects the default language configured at the global level in the Language menu. You can add more languages before exporting the templates.

Once you have exported templates, you can import them into a different environment or tenant.

#### CSV template guidelines for import

When you export notification templates, the downloaded CSV file serves as the template for imports. Follow these rules:

- Do not change or rename column headers.
- Do not modify the **Used-For** column, as it defines the template’s purpose and, together with the **Locale** column, acts as the unique identifier for determining which templates are updated during import.
- The **Used-For**, **Locale**, **Title**, **Subject**, and **Body** columns must not be empty in the CSV file. If any of these are empty, the import will fail.
- You should only update the content in the **Title**, **Subject**, and **Body** columns in the CSV.
- Changes to the **Description** column are ignored during import, and the default value is used.

To import a template(s):

1. In the Data Subject Rights module, choose Settings > Notification Templates.
2. In the upper-right corner, click Import.
3. Drag and drop or upload the CSV and click Import.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(255).png)

> [!NOTE]
> **Note**
> 
> The maximum file size for import is 100 MB.

After the import completes, Securiti sends you an email with a CSV attachment. The file lists which templates were updated and which were skipped, along with the reason.
