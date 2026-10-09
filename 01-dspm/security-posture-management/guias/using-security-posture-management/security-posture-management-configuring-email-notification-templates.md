---
title: "Configuring email notification templates"
slug: "security-posture-management-configuring-email-notification-templates"
updated: 2026-01-28T06:54:32Z
published: 2026-01-28T06:54:32Z
canonical: "helpcenter.securiti.ai/security-posture-management-configuring-email-notification-templates"
area: dspm
modulo: security-posture-management
tipo: guia
data_captura: 2026-10-06
---

# Configuring email notification templates

You can modify templates for the emails that Securiti sends out:

- From the Assessments module to clients and vendors in response to requests for assessments in the Assessment Automation module
- From the Data subject Rights module to data subjects to notify them of status changes in their DSR requests in the Data subject Rights module
- From the Policy center in response to a policy match
- From the Sensitive Data Intelligence module in response to discovery scan completion

You can also modify the translated versions that Securiti sends according to the language settings of the DSR form or the data subject's geographic location.

For the Assessments module, you can also create new templates for vendor assessment invitations by cloning existing ones and modifying them to suit.

1. Do one of the following to open the notification templates page for the module of interest:
  - In the module, choose **Settings > Notification Templates** or **Settings > Email Notification Templates**.
  - In Securiti Dashboard View open **Settings** and choose *<Module name>* from the left-hand side menu, then choose **Notification Templates**.
2. In the list near the left edge of the page, click the card for the message template you want to modify.

![notification_templates_all_messages_panel.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f63fb759-a89c-b2fa-e4b3-5903c468bd66(9).png)
3. Near the upper right corner of the page, click **Language** (globe icon) and choose the language in which you want to view or modify the template, as shown below.

![RN_notification_template_localization.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8318cf52-fa7c-461c-8053-43e9f654f3ef(9).png)
4. Use the tools on the page to edit and format the body text of the template to suit your needs:
  - Use the formatting toolbar to apply body text formats such as paragraph types and character formatting.

![notification_templates_formatting_toolbar.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2595119e-b7f1-a6aa-0e58-e226e8bc7400(9).png)
  - Use the Variables menu to choose variables to embed in the body text of the message.

![notification_template_variables_menu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47975598-6db6-0a54-0cea-02cd66e12956(9).png)
5. (Optional) For Assessments, you can remove the Securiti logo, and configure it to your liking for all assessment system notification templates:
  1. On the Notification Template for Assessments page, select the desired notification template from the All Messages list.
  2. In the Logo and Branding area, click either **Remove Logo** or **Upload**.

![Remove_or_Upload_logo.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81ed5dd7-0f37-7bee-4bc6-ffa26bd5177d(9).png)

In the case of the latter, a popup asks you to select the image you want to upload.
6. (Optional) Also, for Assessments, you can remove footer branding by Securiti. Near the upper right corner of the page, enable the **Hide Securiti Branding** toggle.

![Screenshot_2025-04-28_at_3_30_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf287b9f-c098-dd4f-c451-f2edd7386e26(9).png)

Securiti shows you a popup confirming if you want to Hide Securiti Branding.

![Screenshot_2025-04-28_at_3_31_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cdc08f16-f190-2ce3-38cb-4e98c75fe593(9).png)

Click **Save**

![Screenshot_2025-04-28_at_3_32_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f821851-c1bd-f0ae-27df-6e9f1ec48ff7(9).png)

> [!NOTE]
> **Note**
> 
> This applies to all tenants with internal and/or vendor assessment modules enabled.
> 
> Also, Hide Securiti Branding removes branding from all preconfigured assessment emails, such as risks, flags, reassessment, export, reminder, etc.
7. As you work on the template, click **Save** near the upper right corner of the page to save your work so you don't lose your changes.

Saving creates a draft of the template but does not put it into effect. The template is marked with a "Draft" badge in the templates list.
8. If you want to discard all your changes and start over, near the upper right corner of the page click **Revert** to revert to the previous version.
9. When you are ready to put your changes into effect, near the upper right corner of the page click **Publish**.

### Discovery scan email notification templates

You can clone and delete the email notification templates that you can use in discovery scan responses when you configure the discovery scans. You can do this for structured, unstructured, and streaming data systems.

#### Cloning an email notification template

1. In Securiti, go to **Sensitive Data Intelligence**. Choose **Discovery Scans** > **Email Notification Templates**.
2. Click the options icon and click **Clone Template**. The cloned email notification template appears.

![cloneEmailTemplate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14a2bde3-3e7c-c315-1dbc-5b7bbe722f2c(9).png)
3. To save your changes, near the upper right corner of the page, click **Save**, and then click **Publish**.

> [!NOTE]
> **Note**
> 
> You can make changes to both system and custom email notification templates.

#### Deleting an email notification template

1. In Securiti, go to **Sensitive Data Intelligence**. Choose **Discovery Scans** > **Email Notification Templates**.
2. Click the options icon and click **Delete**.

![deleteEmailNotificationTemplate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-798827ed-873b-5bfc-9e93-88aea2a1e59f(9).png)
3. When you are ready to put your changes into effect, near the upper right corner of the page click **Save**.

> [!NOTE]
> **Note**
> 
> You cannot delete any system email notification template.
