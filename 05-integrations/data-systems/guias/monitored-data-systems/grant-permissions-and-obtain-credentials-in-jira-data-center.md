---
title: "Grant permissions and obtain credentials in Jira Data Center"
slug: "grant-permissions-and-obtain-credentials-in-jira-data-center"
updated: 2026-08-03T04:57:47Z
published: 2026-08-03T04:57:47Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-jira-data-center"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Jira Data Center

To integrate Jira with Securiti, first create and assign the required permissions to the Jira app so it can access the necessary resources.

You can then obtain credentials through one of the following authentication methods:

- [OAuth-based authentication](/v1/docs/grant-permissions-and-obtain-credentials-in-jira-data-center#obtain-authentication-credentials)
- [Personal Access Token (PAT) based authentication](/v1/docs/grant-permissions-and-obtain-credentials-in-jira-data-center#obtain-authentication-credentials)

## Create a Jira app and assign permissions

To create an app in Jira Data Center and grant permissions in Jira Data Center:

1. On the Jira dashboard, near the upper right corner, select **Settings > Applications**. ![settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-475615ca-b9a0-95e5-d653-ed6100774316.png)
2. Enter the password if prompted, and in the left sidebar, select **Application links**.
3. On the **Create link** popup, mark these radio buttons:
  - In 'Application Type' > **External application**.
  - In 'Direction' > **Incoming** ![radio_buttons.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7394e268-4883-2ccb-7733-6924bb23e919.png)Click **Continue**
4. On the following page, enter an app name and provide the 'redirect URL.' Choose that applies from the table below.

| Cloud | URL |
| --- | --- |
| US | `https://app.securiti.ai/static/activateConnector.html` |
| US1 | `https://app1.securiti.ai/static/activateConnector.html` |
| Canada | `https://app3.securiti.ai/static/activateConnector.html` |
| EU | `https://app.eu.securiti.ai/static/activateConnector.html` |
| Indonesia | `https://app2.securiti.ai/static/activateConnector.html` |
| Australia | `https://app4.securiti.ai/static/activateConnector.html` |
| UAE | `https://app5.securiti.ai/static/activateConnector.html` |
| Mumbai | `https://app6.securiti.ai/static/activateConnector.html` |
| Sovereign deployment | `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
5. Near the bottom of the page, in the 'Application Permissions' section, from the **Permissions** menu choose **Read**. ![app_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd57ff2c-cb80-2edb-7eb5-eecb1f99852f.png)
6. Click **Save**.

## Obtain authentication credentials

Use one of the procedures below to obtain credentials with your chosen authentication method, either OAuth or Personal Access Token.

- To obtain credentials for the OAuth authentication method:
  1. Under **Credentials**, record the **Client ID** and **Client secret** for later use.

![id_and_secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7973f09a-1594-d002-a300-5c92ae20ee3e.png)
- To obtain credentials for the **Personal Access Token** authentication method:
  1. On the top right, click your **Avatar** icon, and choose **Profile**. ![Jira software dashboard displaying user profile options and project management features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/1-jira.png)
  2. On the **Profile** page in the left sidebar, click **Personal Access Tokens**.
  3. On the **Personal Access Tokens** page, click **Create token**. ![Jira interface showing personal access tokens and option to create a new token.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/2-jira.png)
  4. On the Create a personal access token page, configure the following settings:

| Setting | Description |
| --- | --- |
| Token Name | Enter a convenient name for the personal access token. See the example below. Se*curiti-ai-Token* |
| Optional) Expiry date | Enter the number of days for which the token expires. See the example below. *90* |
    - At the bottom of the **Create a personal access token** popup, click **Save**. ![Instructions for creating a personal access token with expiry settings and permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-654498e3-8360-6bb5-2dff-0c0c7d44f668.png)
  5. On the following popup, record the **token** by copying it.

> [!NOTE]
> Note
> 
> Copy the token immediately and store it securely; the full value appears only once and disappears after you close the dialog box.

![New personal access token creation with instructions to store it securely.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/4-jira.png)
  6. Proceed to [Connecting Jira Data Center (Self Hosted) with Securiti](/latest/docs/connecting-jira-data-center-self-hosted-with-securiti).
