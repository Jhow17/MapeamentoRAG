---
title: "Prerequisites and obtaining authentication credentials for Gmail (Securiti cloud)"
slug: "prerequisites-and-obtaining-authentication-credentials-for-gmail-securiti-cloud"
updated: 2026-06-23T10:15:53Z
published: 2026-06-23T10:15:53Z
canonical: "helpcenter.securiti.ai/prerequisites-and-obtaining-authentication-credentials-for-gmail-securiti-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites and obtaining authentication credentials for Gmail (Securiti cloud)

This topic contains information about the following:

1. Project Creation
2. Enabling APIs
3. Creating Google Workspace Service Account
4. Enabling Google Workspace Domain-Wide Delegation
5. Generating Service Account Key File for Activation

1. To create a project:
  1. Log in to [Google Developer Console](https://console.developers.google.com/apis/dashboard) with your Google Workspace admin.
  2. Near the upper left corner, select the project menu and click **New Project**, as shown below.

![new_project.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95496cb8-cb22-00be-815d-e957ef07e85d.png)
2. To enable APIs:
  1. On your project dashboard, click **Enable APIs & Services**.

![apis_services.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-18c945bc-44b6-26f5-00db-2cc46fef8172.png)

![enable_apis_services.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d48f3519-775f-b48d-680e-fcea826c9b2e.png)
  2. In the left-hand menu, select **Enabled APIs & services**.

It displays the API library under Google Workspace, as shown below.

![apis_library.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-53f95918-c807-eb2a-a3b1-064146a15476.png)

> [!NOTE]
> **Important**
> 
> Admin SDK API does not show by default in the API library. Search for it at the top using the library search bar.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(636).png)

Enable the following APIs for Google Workspace Gmail:
    - **Gmail API**
    - **Admin SDK API**
  3. Click an API card and on its API description page, click **Enable**, as shown below.

![enable_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d62d62f-4075-22c0-9f7d-17f81cd0eb77.png)
  4. Repeat the steps in 2(a-c) to enable other APIs.
3. Once you have enabled the APIs, use the matching procedure below to create a service account:
  1. Click the navigation menu (three horizontal bars) in the top left and select **IAM & Admin > Service Accounts**.

![service_accounts.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f8fc5cb7-575b-d087-84f2-ebce664116af.png)
  2. Click **Create service account**, enter a name for it and then click **Create And Continue**.

![create_service_account.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b79c1866-5286-82dc-d4c3-6c874f466dae.png)
  3. After that, in "Grant this service account access to project" area, choose **Owner** from the Role menu (for the purposes of this topic).

![choose_role.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a56d8dd2-df49-2d25-0051-9e6724c719f5.png)

Click **Done**
  4. On the following page, record the "O Auth 2 Client ID" for later use, as shown below.

![client_id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-15ee7927-095b-03fc-731d-996c4d5bad87.png)
4. Now, enable the Google Workspace Domain-wide Delegation as follows:
  1. On the [Admin console](/v1/docs/securiti-pods-and-elastic-pods) of your Google Workspace domain, click the navigation or main menu (three horizontal bars) in the top left and select **Security > Access and data control > API Controls**.

![domain_wide_delegation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58d3a732-95f1-8f3e-ab75-b8a65e39f5e5.png)
  2. On the card for Domain wide delegation, click **Manage Domain Wide Delegation**, then click **Add new**, as shown below.

![add_new.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2fe388d8-48af-389b-2dce-96d129688ee7.png)
  3. In the Client ID field, enter the information you recorded in step 3(d).
  4. In OAuth scopes (comma-delimited) field, enter the list of scopes for the application you want to grant access to and click **Authorize**.

![authorize_id_scopes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-069b0482-6172-e76e-a990-47421b0d7c61.png)

Enter the following scopes for Gmail (Google Workspace) application:

```plaintext
https://www.googleapis.com/auth/gmail.readonly,
https://www.googleapis.com/auth/admin.directory.customer.readonly,
https://www.googleapis.com/auth/admin.directory.resource.calendar.readonly,
https://www.googleapis.com/auth/drive.metadata.readonly,
https://www.googleapis.com/auth/admin.directory.domain.readonly,
https://www.googleapis.com/auth/drive.readonly,
https://www.googleapis.com/auth/calendar.readonly,
https://www.googleapis.com/auth/calendar.events.readonly,
https://www.googleapis.com/auth/admin.directory.user.readonly,
https://www.googleapis.com/auth/drive.photos.readonly,
https://www.googleapis.com/auth/admin.directory.group.readonly
```
5. To generate Service Account Key File:
  1. On the page for your service account, under Actions Column, click the three vertical dots and select **Manage keys**.

![manage_keys.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-199daa51-2d88-a142-23fd-7784627df78c.png)
  2. Now select **ADD Key > Create new key** and mark the radio button for **JSON** in Key type, as shown below.

![add_create_key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0706150e-016c-aec7-fc0d-b4dcde2328fa.png)

![key_type_json.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8bc3d9cf-679f-bbee-0ad8-04b652d60805.png)

Click **Create**. A file is downloaded on your system that you must store safely for the next step.
6. Proceed to [Connecting the Gmail (Google Workspace) (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-the-g-suite-gmail-google-workspace-with-securiti).
