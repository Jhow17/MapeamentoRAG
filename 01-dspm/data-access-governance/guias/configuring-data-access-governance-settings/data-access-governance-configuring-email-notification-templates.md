---
title: "Configuring email notification templates"
slug: "data-access-governance-configuring-email-notification-templates"
updated: 2026-08-18T10:27:24Z
published: 2026-08-18T10:27:24Z
canonical: "helpcenter.securiti.ai/data-access-governance-configuring-email-notification-templates"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Configuring email notification templates

You can modify templates for the emails that Securiti sends out:

- From the Assessments module to clients and vendors in response to requests for assessments in the Assessment Automation module
- From the Data subject Rights module to data subjects to notify them of status changes in their DSR requests in the Data Subject Rights module
- From the Policy center in response to a policy match
- From the Sensitive Data Intelligence module in response to discovery scan completion

You can also modify the translated versions that Securiti sends according to the language settings of the DSR form or the data subject's geographic location.

For the Assessments module, you can also create new templates for vendor assessment invitations by cloning existing ones and modifying them to suit.

1. Do one of the following to open the notification templates page for the module of interest:
  - In Securiti Dashboard View open **System** **Settings** and choose ***Assessments*** from the left-hand side menu, then choose **Notification Templates**.
2. In the list near the left edge of the page, click the card for the message template you want to modify.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 12.20.09 PM.png)
3. Near the upper right corner of the page, click **Language** (globe icon) and choose the language in which you want to view or modify the template, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 12.26.53 PM.png)
4. Use the tools on the page to edit and format the body text of the template to suit your needs:
  - Use the formatting toolbar to apply body text formats such as paragraph types and character formatting.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 12.28.52 PM.png)
  - Use the Variables menu to choose variables to embed in the body text of the message.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 12.30.28 PM.png)
5. (Optional) For Assessments, you can remove the Securiti logo, and configure it to your liking for all assessment system notification templates:
  1. On the Notification Template for Assessments page, select the desired notification template from the All Messages list.
  2. In the Logo and Branding area, click either **Remove Logo** or **Upload**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 12.32.09 PM.png)

In the case of the latter, a popup asks you to select the image you want to upload.
6. (Optional) Also, for Assessments, you can remove footer branding by Securiti. Near the upper right corner of the page, enable the **Hide Securiti Branding** toggle.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FR3UAEF8.png)

Securiti shows you the Hide Securiti Branding confirmation popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AGJX9E2A.png)

Click **Save**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 1.02.30 PM (1).png)

> [!NOTE]
> **Note**
> 
> This applies to all tenants with internal and vendor assessment modules enabled.
> 
> Also, "Hide Securiti Branding" removes branding from all preconfigured assessment emails, such as risks, flags, reassessment, export, reminder, etc.
7. As you work on the template, click **Save** near the upper right corner of the page to save your work so you don't lose your changes.

Saving creates a draft of the template but does not put it into effect. The template is marked with a "Draft" badge in the templates list.
8. If you want to discard all your changes and start over, near the upper right corner of the page click **Revert** to revert to the previous version.
9. When you are ready to put your changes into effect, near the upper right corner of the page click **Publish**.

### Discovery scan email notification templates

You can clone and delete the email notification templates that you can use in discovery scan responses when you configure the discovery scans. You can do this for structured, unstructured, and streaming data systems.

### Cloning an email notification template

1. In Securiti, go to **System Settings**. Choose **Discovery Scan** **Notification Templates**.
2. Click the options icon and click **Clone Template**. The cloned email notification template appears.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-09 at 1.05.17 PM.png)
3. To save your changes, near the upper right corner of the page, click **Save**, and then click **Publish**.

> [!NOTE]
> **Note**
> 
> You can make changes to both system and custom email notification templates.

### Deleting an email notification template

1. In Securiti, go to **Sensitive Data Intelligence**. Choose **Discovery Scans** > **Email Notification Templates**.
2. Click the options icon and click **Delete**.

![deleteEmailNotificationTemplate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-798827ed-873b-5bfc-9e93-88aea2a1e59f(11).png)
3. When you are ready to put your changes into effect, near the upper right corner of the page click **Save**.

> [!NOTE]
> **Note**
> 
> You cannot delete any system email notification template.
