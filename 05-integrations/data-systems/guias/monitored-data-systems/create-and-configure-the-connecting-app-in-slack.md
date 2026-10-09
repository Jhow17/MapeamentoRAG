---
title: "Create and configure the connecting app in Slack"
slug: "create-and-configure-the-connecting-app-in-slack"
updated: 2026-07-15T06:40:49Z
published: 2026-07-15T06:40:49Z
canonical: "helpcenter.securiti.ai/create-and-configure-the-connecting-app-in-slack"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create and configure the connecting app in Slack

> [!NOTE]
> **Note**
> 
> The procedure requires you to be a Full Member of Slack to create and install the app or activate the Connector.

The following Table explains the modules related Permissions in the Slack application.

| Modules | Permissions | Use case |
| --- | --- | --- |
| Sensitive data Intelligence | **channels:history** | Views messages and other content in a user’s public channels, private channels, direct messages, and group direct messages. |
| **channels:read** | Views basic information about public channels in a workspace. Securiti asks it for both Connector Activation and data scanning. |
| **groups:history** | Views messages and other content in a user’s public channels, private channels, direct messages, and group direct messages. |
| **groups:read** | Views basic information about a user’s private channels. Securiti asks it for both Connector Activation and data scanning. |
| **im:read** | Views basic information about a user’s direct and group direct messages Securiti asks it for both Connector Activation and data scanning. |
| **im:history** | Views messages and other content in a user’s public channels, private channels, direct messages, and group direct messages. |
| **mpim:read** | Views basic information about a user’s direct and group direct messages Securiti asks it for both Connector Activation and data scanning. |
| **mpim:history** | Views messages and other content in a user’s public channels, private channels, direct messages, and group direct messages. |
| **users:read** | Views the list of users in the workspace |
| **users.profile:read** | Views the profile information for each user in the workspace. |
| **files:read** | Views files shared in channels and conversations that a user has access to. |
| Slack Workflow Node | **channels:write** | Manages a user’s public channels and create new ones on a user’s behalf and includes the channel details in the Workflow |
| **chat:write** | Sends messages on a user’s behalf and Include the user's direct messages in the Workflow. |
| **files:write** | Lets you upload, edit, and delete files on a user’s behalf and includes the files and conversation in the Workflow. |
| **groups:write** | Manages a user’s private channels and create new ones on a user’s behalf and includes the private channels content in Workflow. |
| **im:write** | Starts direct messages with people on a user’s behalf and includes the user's content in the Workflow. |
| **mpim:write** | Starts group direct messages with people on a user’s behalf and includes the group's messages information in the Workflow. |
| **search:read** | Performs a DSR search for profiles, messages, and channel content in the workspace. |
| Data Subject Rights (DSR) Automation |

**Create a connecting app in Slack**

In order to link your Slack account with the Securiti application, you create an application to facilitate the Connector Activation process:

1. Log in to the [Slack API website](https://api.slack.com/apps).

Slack redirects you to the **Your Apps** dashboard.
2. On the **Your Apps** page, click **Create an App**.

![step-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c86dcc1e-e5da-d2da-be3c-12dc1d0420b3.png)
3. On the **Create an app** pop-up, select the **From Scratch** option.

![step-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ed192041-9e73-5ea0-de51-dd207de03281.png)
4. Enter an appropriate **App Name** and select your desired Slack **Workspace** from the menu for syncing to the Securiti app, then click **Create App**.

![step-4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ec01181c-e519-1f6c-4364-2b860cb1e40c.png)
5. On the **Basic Information** page, scroll down to **App Credentials** , and record the following details for later use:

![step-5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6b2267ed-bb50-2de8-878f-f1dbe1d9b38d.png)
  - App ID
  - Client ID
  - Client Secret
6. In the left sidebar, click **OAuth and Permissions**.

![step-6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5018506-daca-d4bb-f429-18e425b920ad.png)
7. **Configure OAuth and Permissions**

Configure the following settings in the **OAuth and Permissions** section:

| Redirect URLs | Click **Add New Redirect URL** and add one of the following URLs according to the environment being used, click **Add**: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` Click **Add** > **Save URLs** once done. ![step-7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8d3f106-67a9-aba3-ef3b-bfdf47d613ab.png)![step7a-slackPro-final.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5eacbd8b-7f02-9a03-3c49-f1346f5ad8ea.png) |
| --- | --- |
| User Token Scopes (Optional) | Scroll down to the **User Token Scopes** under the **Scopes** section, and click **Add an OAuth Scope**. > **Note** > > Slack requires you to add the scopes in User Token because user's content acess is required. To get more information on difference between Bot Token and User Token scopes, refer to [Slack documentation](https://api.slack.com/quickstart#scopes). ![step-7b.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-94530ad2-fb48-e0d7-c9e0-dca124b954f9.png) Add the following OAuth scopes: - **channels:history** - **channels:read** - **files:read** - **groups:history** - **groups:read** - **im:history** - **im:read** - **mpim:history** - **mpim:read** - **search:read** (For [DSR Automation](/latest/docs/dsr-automation-in-data-system-connectors)) - **users:read** - **users.profile:read** ![step-7c.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a771cb9d-48b9-491e-61e4-af1abda5e6b7.png) |
| User Token scope to use the Connector with Securiti workflows, also enable the following scopes: | > **Note** > > You must add the following User Scopes to include the data in Workflow Node module. - **channels:write** - **chat:write** - **files:write** - **groups:write** - **im:write** - **mpim:write** |
8. Proceed to [Connecting Slack (Self-hosted) with Securiti](/latest/docs/connecting-slack-self-hosted-with-securiti) or [Connecting Slack (Securiti-Cloud) with Securiti](/latest/docs/connecting-slack-securiti-cloud-with-securiti).
