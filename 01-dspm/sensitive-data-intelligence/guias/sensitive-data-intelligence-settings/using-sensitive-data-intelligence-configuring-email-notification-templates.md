---
title: "Configuring email notification templates"
slug: "using-sensitive-data-intelligence-configuring-email-notification-templates"
updated: 2026-07-06T14:41:24Z
published: 2026-07-06T14:41:24Z
canonical: "helpcenter.securiti.ai/using-sensitive-data-intelligence-configuring-email-notification-templates"
stale: true
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring email notification templates

You can modify templates for the emails that Securiti sends out:

- From the Assessments module to clients and vendors in response to requests for assessments in the Assessment Automation module
- From the Data subject Rights module to data subjects to notify them of status changes in their DSR requests in the Data Subject Rights module
- From the Policy center in response to a policy match
- From the Sensitive Data Intelligenec module in response to discovery scan completion

You can also modify the translated versions that Securiti sends according to the language settings of the DSR form or the data subject's geographic location.

For the Assessments module, you can also create new templates for vendor assessment invitations by cloning existing ones and modifying them to suit.

1. Do one of the following to open the notification templates page for the module of interest:
  - In the module, choose **Settings > Notification Templates** or **Settings > Email Notification Templates**.
  - In Securiti Dashboard View open **Settings** and choose *<Module name>* from the left-hand side menu, then choose **Notification Templates**.
2. In the list near the left edge of the page, click the card for the message template you want to modify.
3. Near the upper right corner of the page, click the **Language** (globe icon) and choose the language in which you want to view or modify the template, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/notifiLaguage.png)
4. Use the tools on the page to edit and format the body text of the template to suit your needs:
  - Use the formatting toolbar to apply body text formats such as paragraph types and character formatting. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/notify_formatingtoolbar(1).png)
  - Use the Variables menu to choose variables to embed in the body text of the message.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/templateVariables.png)
5. (Optional) For Assessments, you can remove the Securiti logo, and configure it to your liking for all assessment system notification templates:
  1. On the Notification Template for Assessments page, select the desired notification template from the All Messages list.
  2. In the Logo and Branding area, click either **Remove Logo** or **Upload**.

In the case of the latter, a popup asks you to select the image you want to upload.
6. (Optional) Also, for Assessments, you can remove footer branding by Securiti. Near the upper right corner of the page, enable the **Hide Securiti Branding** toggle.

![Screenshot_2025-04-28_at_3_30_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf287b9f-c098-dd4f-c451-f2edd7386e26(8).png)

Securiti shows you a popup confirming if you want to Hide Securiti Branding.

![Screenshot_2025-04-28_at_3_31_04_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cdc08f16-f190-2ce3-38cb-4e98c75fe593(8).png)

Click **Save.**

![Screenshot_2025-04-28_at_3_32_01_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f821851-c1bd-f0ae-27df-6e9f1ec48ff7(8).png)

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

1. In Securiti, open **SensitiveData Intelligence** and choose **Discovery Scans** > **Email Notification Templates**.
2. Click the options icon and click **Clone Template**. The cloned email notification template appears.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cloneTemplate.png)
3. To save your changes, near the upper right corner of the page, click **Save**, and then click **Publish**.

> [!NOTE]
> **Note**
> 
> You can make changes to both system and custom email notification templates.

### Deleting an email notification template

1. In Securiti, open **SensitiveData Intelligence** and choose **Discovery Scans** > **Email Notification Templates**.
2. Click the options icon and click **Delete**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deleteTemplate.png)
3. When you are ready to put your changes into effect, near the upper right corner of the page click **Save**.

> [!NOTE]
> **Note**
> 
> You cannot delete any system email notification template.

### 

Data elements are associated with different languages that depend on different global localities. Securiti is continuously adding support for different languages for the detection/classification of sensitive data.
