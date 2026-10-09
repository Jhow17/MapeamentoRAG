---
title: "Creating and editing messaging templates"
slug: "creating-and-editing-messaging-templates"
updated: 2025-12-10T09:18:45Z
published: 2025-12-10T09:18:45Z
canonical: "helpcenter.securiti.ai/creating-and-editing-messaging-templates"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Creating and editing messaging templates

Securiti admins and DSR request owners can build and use a library of templates that simplify communication with data subjects while ensuring it is clear and consistent. You can use templates as-is, modify them on a case-by-case basis, and save modified versions as new templates.

Securiti has two types of messaging templates:

- **Customer messaging templates** are for when you are exchanging messages with data subjects while you are processing DSR requests. Securiti uses these templates for messages and emails to the data subject.
- **DSR messaging templates** are for when you are publishing final reports for DSR requests, or when you are declining DSR requests, specifically in the case of erasure requests. Securiti uses these templates for messages included with the final report it delivers to the data subject when you complete the processing of their DSR request.

You can also edit the templates that Securiti uses for email notifications. See [Configuring email notification templates](/v1/docs/configuring-dsr-email-notification-templates) for more information.

### Creating a new template

1. In Securiti, choose one of the following, depending on which type of template you want to work on:
  - **Settings > Data Subject Rights > Customer Messaging Templates**
  - **Settings > Data Subject Rights > DSR Messaging Templates**
2. Do one of the following:
  - In the Categories area, choose a category for the new template.
  - If there is not already an appropriate category, create one:
    1. Near the upper right corner of the page, click **+ Create Category**.
    2. Use the Create New Category popup to give the new category a name, then click **Save**.
3. Near the upper right corner of the page for the selected category, click **+ Create Template.**
4. On the template popup, apply the following settings to suit, as shown below:

| Template title | Click **Edit** (pencil icon) and give the template a descriptive name, then click the checkmark. |
| --- | --- |
| Subject | Type a subject line for the template. |
| Message | Type the message to the data subject. You can personalize the message by inserting variables from the Add Variable menu. |

> [!NOTE]
> **Note**
> 
> The message template displays a specific character limit for the template title, subject, and message fields that you need to craft.

![Simple_screenshot.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7982700-8599-840f-8166-a529486e9362.png)
5. On the popup, click **Save**.

### Cloning an existing template

To create a duplicate of an existing template that you can edit to suit:

1. If you haven't already done so, in Securiti, choose one of the following, depending on which type of template you want to work on:
  - **Settings > Data Subject Rights > Customer Messaging Templates**
  - **Settings > Data Subject Rights > DSR Messaging Templates**
2. Choose the category of the template you want to clone.
3. Near the right end of the card for the template you want to clone, choose **Options** (three dots) **> Clone**.
4. On the Clone Template popup, enter the name for the new template and choose a category for it. Then click **Save**.

### Editing an existing template

1. If you haven't already done so, in Securiti, choose one of the following, depending on which type of template you want to work on:
  - **Settings > Data Subject Rights > Customer Messaging Templates**
  - **Settings > Data Subject Rights > DSR Messaging Templates**
2. Choose the category of the template you want to edit.
3. Near the right end of the card for the template you want to edit, choose **Options** (three dots) **> Edit**.
4. On the template popup, edit the template to suit, then click **Save**.

### Deleting a template

1. If you haven't already done so, in Securiti, choose one of the following, depending on which type of template you want to work on:
  - **Settings > Data Subject Rights > Customer Messaging Templates**
  - **Settings > Data Subject Rights > DSR Messaging Templates**
2. Choose the category of the template you want to delete.
3. Near the right end of the card for the template you want to edit, choose **Options** (three dots) **> Delete**.
4. On the delete template popup, click **Yes** to confirm.

### Disable a DSR template

To disable a DSR template:

1. In Securiti, choose one of the following, depending on which type of template you want to work on:
  - **Settings > Data Subject Rights > Customer Messaging Templates**
  - **Settings > Data Subject Rights > DSR Messaging Templates**
2. Choose the category of the template you want to disable.
3. Select the template from the list and slide **Enabled** toggle to the left.

![DSR_Messaging_Templates_config.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-111cec04-caae-765f-b5e7-6e1c7d0084a1.png)

You can always enable these templates by sliding the Enabled toggle to the right.

In case of disabling customer messaging templates, you are unable to communicate with the Data Subjects while processing the DSR requests. This can result in irregular and inconsistent communication with data subjects.

![Screenshot_2025-02-25_at_5_45_24_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95091c8d-986f-deff-a374-9f43567f05b8.png)

Disabling DSR Messaging templates means that you are unable to incorporate messages that accompany the final report delivered to the data subject upon completion of their DSR request.

![Screenshot_2025-02-25_at_5_55_41_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d7ade16-b323-745f-698c-f2a402473227.png)

Likewise, you are not able to reject DSR subtasks unless the DSR message template, which provides the reasons for declining the request, is attached.

![Screenshot_2025-02-25_at_5_54_54_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9421f8e-6b23-bcdd-b86a-c72e5d4d4e83.png)
