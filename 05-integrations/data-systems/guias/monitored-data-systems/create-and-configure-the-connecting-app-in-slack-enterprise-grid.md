---
title: "Create and configure the connecting app in Slack Enterprise Grid"
slug: "create-and-configure-the-connecting-app-in-slack-enterprise-grid"
updated: 2025-10-31T06:51:43Z
published: 2025-11-03T07:34:02Z
canonical: "helpcenter.securiti.ai/create-and-configure-the-connecting-app-in-slack-enterprise-grid"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create and configure the connecting app in Slack Enterprise Grid

In order to link your Slack Enterprise Grid account with the Securiti application, you create an application to facilitate the Connector Activation process:

> [!NOTE]
> **Important**
> 
> You must be an Org Owner to install the app or activate the Connector.

1. Log in to the Slack API website at <*https://api.slack.com/apps*>.

Slack redirects you to the **Your Apps** dashboard.
2. Click **Create an App**.

![create_app_button.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bcc48c11-8ada-94a3-d22e-4185aa18c653.png)
3. On the pop-up, select the **From Scratch** option.

![createapp_scratch.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a268fadb-a847-a12b-4eeb-5959ac4a8ec6.png)
4. Enter an appropriate **App Name** and select your desired **Slack Workspace** for syncing to the Securiti app, then click **Create App**.

![app_name_workspace.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03d29020-ed3e-d926-485b-6fa07e34af8c.png)
5. Scroll down to **App Credentials** on the **Basic Information** page and record the following details for later use:

![Slack_AppBasicInfo.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57bedf5a-9202-b831-e1b8-5f67902ba42d.png)

![app_credentials_slackent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-04b51209-0225-ebbd-e7b7-87d61911468c.png)
  - App ID
  - Client ID
  - Client Secret
6. In the left sidebar, click **OAuth and Permissions**.

![addnew_redirecturl_slackent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75ea73ce-76b7-460e-21cc-52f0bbb79eb7.png)

> [!NOTE]
> **Important**
> 
> Securiti requires special scopes and APIs to access data for the Slack Enterprise Grid Connector, named as Discovery APIs. To access the Discovery API, an **Org Owner** must send an email to **email exports@slack.com** with a support request, such as "enable the Discovery APIs for Securiti and add discovery scopes to the app *AXXXXXXXXX*” where *AXXXXXXXXX* is the app ID you acquired in step 5. The Slack team promptly enables access after verifying the email address matches the owner of the organization.
7. Configure the following settings in the **OAuth and Permissions** section:

| Redirect URLs | Click **Add New Redirect URL** and add one of the following URLs according to the environment being used, click **Add**: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` Click **Save URLs** once done. ![saveurls_slackent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca6ca869-b68c-730a-123a-747ad4dd6389.png) |
| --- | --- |
| User Token Scopes | > [!NOTE] > **Note** > > - As previously mentioned in the prerequisites, you must contact the Slack team to enable these scopes. Only a member of Slack corporation can add the Discovery scopes. > - The Discovery Token is an org level Token. To add the discovery scope(s) after confirmation from the Slack team. 1. In **OAuth & Permissions** under **Features**, scroll down to the **Scopes** section. 2. Under the **User Token Scopes**, the **discovery:read** is shown as the Discovery scope ![scopes_slackent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7976ed83-4ec6-f6e6-6c9c-6e083ece9ef2.png) |
8. As the right Permissions and OAuth redirect URLs have been configured for the app, you must activate the app distribution.

> [!NOTE]
> **Important**
> 
> This is a necessary step to make your app installable on multiple workspaces, or at the org level.

To activate app distribution:
  1. In the left navigation panel under **Settings**, click **Manage distribution** and scroll down to the **Share your App with Other Workspaces** where list of steps with check marks are displayed.
  2. To get the last required checkmark, click **Remove Hard Coded Information** and mark the **Share your App with Other Workspaces** checkbox.

Slack enables the **Activate Public Distribution** button.

![laststep_tick_slackent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-676f7774-5a58-d487-426d-32f8496b65fa.png)
9. Proceed to [Activate the Slack Enterprise Grid connector in Securiti](/v1/docs/activate-the-slack-enterprise-grid-connector-in-securiti).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
