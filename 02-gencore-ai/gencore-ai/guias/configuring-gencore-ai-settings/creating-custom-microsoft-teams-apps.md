---
title: "Creating custom Microsoft Teams apps"
slug: "creating-custom-microsoft-teams-apps"
updated: 2026-04-27T04:25:53Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/creating-custom-microsoft-teams-apps"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Creating custom Microsoft Teams apps

To create a custom Microsoft Teams messaging app, you must:

1. [Create and configure a bot app](/latest/docs/creating-custom-microsoft-teams-apps#create-and-configure-a-bot-app).
2. [Configure the Azure AD application](/latest/docs/creating-custom-microsoft-teams-apps#configure-the-azure-ad-application).
3. [Create a Client/Bot Secret](/latest/docs/creating-custom-microsoft-teams-apps#creating-a-clientbot-secret).
4. [Create a custom Microsoft Teams app in Securiti](/latest/docs/creating-custom-microsoft-teams-apps#create-a-microsoft-teams-custom-app-in-securiti).
5. [Create and configure the Microsoft Teams App in your Developer Portal](/latest/docs/creating-custom-microsoft-teams-apps#create-microsoft-teams-app-in-developer-portal).
6. [Publish the app to your organization](/latest/docs/creating-custom-microsoft-teams-apps#publish-microsoft-teams-app-to-your-organization).
7. [Integrate custom Microsoft app with Securiti](/latest/docs/creating-custom-microsoft-teams-apps#integrating-custom-microsoft-app-with-securiti).

### Create and configure a bot app

To create a bot application:

1. Go to the [Bot](https://dev.teams.microsoft.com/bots) section in the Microsoft Developer Portal. This section lists all existing bot applications.

1. ![Dev_Portal_-_Bot_Updated_Removed_QA_and_masked_Creds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5b91247d-e78b-abc5-f49b-2bf8fb3a6bbb(2).png)
2. To create a new bot:

Once the bot is created, you can access it in the [Bot Framework Portal](https://dev.botframework.com/bots) from the list of all available bots.
  1. Click **New Bot**.

![129_CMA_Updated_Dev_Portal_AddNewBot_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-784b4e43-189d-0952-23e7-7141f85f6da5(2).png)
  2. Enter a name for your bot and click **Add**.

![Bot_name_Enter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd087f8f-4dec-007e-f303-7b2b759a4282(2).png)
3. Select your bot from the list of available bots and go to the **Settings** section.
4. Upload your Bot Logo.
5. To configure the Messaging Endpoint, in the **Messaging Endpoint** field, enter the **Application Bot Configuration URL**. To see the **Application Bot Configuration URL**, see [Create Microsoft Teams Custom App in Securiti](/v1/docs/creating-custom-microsoft-teams-apps#create-microsoft-teams-custom-app-in-securiti).

This endpoint receives all webhook events related to the bot, such as mentions or when an event triggers a dialog box. Securiti's backend service listens to these webhook events and processes them, accordingly.

![129_Updated_Bot_profile_Config_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6a948b43-65b6-4fa4-a178-81854df6132a(2).png)

Once the Messaging endpoint is configured, the next step is to set up the Azure AD application.

### Configure the Azure AD application

To configure the Azure AD application:

1. On [Azure Portal’s Application Registration](https://portal.azure.com/#view/Microsoft_AAD_RegisteredApps/ApplicationsListBlade) page, click **Manage Microsoft App ID and Password**.

Under **Manage Microsoft App ID and Password**, there is an app ID, which is the value to be placed in the Client ID and Bot ID in your Securiti tenant:
  - Copy this app ID as Client ID and paste it in the [Client ID](/v1/docs/creating-custom-microsoft-teams-apps#create-microsoft-teams-custom-app-in-securiti) field.
  - Copy this app ID as Bot ID and paste it in the [Bot ID](/v1/docs/creating-custom-microsoft-teams-apps#create-microsoft-teams-custom-app-in-securiti) field.

![Manage_MS_App_ID_and_pswd.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-942acb35-fef1-212e-813a-b36d5e98c63b(2).png)
2. In Azure Active Directory (AD), search for your application by providing the ID provided in the bot handle. This ID, also referred to as the client_id or bot_id in this case, will be the same for both the bot and the Azure AD application.
3. On the **Branding & Properties** section, upload the bot logo. The logo should be in the png format with dimensions 192x192 pixels.

![129_Updated_Branding_properties_logo.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bdb83fb6-b0ea-fb49-0b3c-dde77b7b4abf(2).png)
4. To set up permissions, navigate to the **API Permissions** page and add the **Microsoft Graph API permissions**:

![129_Updated_MS_Azure_API_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac8d842a-e46a-0272-261b-2e6d5d8c44cb(2).png)
  - **Required Application level permissions**:

| Permission | Description |
| --- | --- |
| ChannelSettings.ReadWrite.All | Get list of channels, read specific channel information, update channel descriptions |
| Organization.Read.All | Read organization details (name, ID, tenant info) |
| Team.ReadBasic.All | Read team information (name, ID, primary channel) where the app is installed |
| User.ReadBasic.All | Read user information given the user identifier |
  - **Required Delegated level permissions**

    - General permissions:

| Permission | Description |
| --- | --- |
| offline_access | Maintain access when user is not actively signed in, enables refresh token functionality |
| User.Read | Read signed-in user's profile informatin |
    - Permissions for connecting with Private and Shared channels:

| Permission | Description |
| --- | --- |
| ChannelMessage.Send | Send a new message to channel on behalf of private bot user (required for private, and shared channels) |
| ChannelMessage.Read.All | Read messages in channels and manage webhook subscriptions for message notifications on behalf of the private bot user |
| ChannelMessage.ReadWrite | Edit the message send on behalf of private bot user |

> [!NOTE]
> Important
> 
> Do not click Grant admin consent for org.
  - ![129_Updated_Request_API_permissions_-_Deleg_and_appl.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d9cdd9e-d6d6-2dcc-8556-db6e60884590(2).png)
5. To **set up authentication**:
  1. Go to the **Authentication** page.
  2. Under **Supported account types**, select **Multitenant**.
  3. Under **Platform configurations**, click **Add a platform** and choose **Single-page application (SPA)**.
  4. In the **Redirect URLs** field, enter `{BASE_URL}` (for example, `https://app.securiti.ai/`) and click **Configure**.

![Configuration settings for Azure application authentication and supported account types overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Azure Authentication section.png)

With these configurations, the Azure AD application is set up by providing the necessary settings and permissions. Return to the [Bot](https://dev.teams.microsoft.com/bots) section in the Microsoft Developer Portal to continue the setup process.

### Creating a Client/Bot Secret

In the Bot section:

1. Select **Client secrets**.

![129_Updated_Client_Secrets_Bot_section_copy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f3879aa-c207-644e-1985-ec7c6dd2d958(2).png)
2. Click **Add a client secret for your bot** and add a client secret.
3. Secure the credentials for upcoming steps.

Next, [create your Microsoft Teams custom app in Securiti](/v1/docs/creating-custom-microsoft-teams-apps#create-microsoft-teams-custom-app-in-securiti).

### Create a Microsoft Teams custom app in Securiti

To create Microsoft Teams custom app:

1. In the **Custom Apps** section, click **Add Custom App**.
2. Select **Microsoft Teams**.

![CMA1-_Main_MS_Teams_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-af84ab63-2817-3b0d-f21e-e34a7f50acd2(2).png)
3. Enter a name for you custom app.

![CMA2_App_Name_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1e34418-f28e-b098-6737-773cf30c588a(2).png)
4. Click **Save & Continue**.

![CMA2_Save_and_Cont_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-350dd5c3-2ddb-b7da-0dab-5eabfe5898f6(2).png)
5. In **Application Credentials**, enter the following information:

To get the **App ID**, see [Create Microsoft Teams Application in Developer Portal](/v1/docs/creating-custom-microsoft-teams-apps#create-microsoft-teams-app-in-developer-portal).

To get the **Client ID**, see [Configure the Azure AD Application](/v1/docs/creating-custom-microsoft-teams-apps#configure-the-azure-ad-application).

To get the **Client Secret**, see [Creating a Client/Bot Secret](/v1/docs/creating-custom-microsoft-teams-apps#creating-a-clientbot-secret).
  1. App ID
  2. Client ID
  3. Client Secret

![Custom_App_-_MS_Teams_App_Client_ID_Secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fef97487-44e5-8015-a07b-275af3f1f0fc(2).png)
6. In **Bot Credentials**, enter the following information:

To get the **Bot Secret**, see [Creating a Client/Bot Secret](/v1/docs/creating-custom-microsoft-teams-apps#creating-a-clientbot-secret).

To get the **Bot ID**, see [Configure the Azure AD Application](/v1/docs/creating-custom-microsoft-teams-apps#configure-the-azure-ad-application).

![CMA_Bot_Credentials_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3aa52b0-2b16-0488-e47a-a670558ce49a(2).png)
  1. Bot Name. This bot name will be tagged in conversations. Therefore, it is important to keep it consistent with your Microsoft Teams custom app name in the [Developers Portal](/v1/docs/creating-custom-microsoft-teams-apps#create-microsoft-teams-app-in-developer-portal).
  2. Bot ID
  3. Bot Secret
7. Click **Save and Continue**. Securiti displays the **Application Bot Configuration URL**.

![CMA_Bot_and_app_Creds_Save_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6d42f0c-9a0f-0d6e-7529-87c27123c26d(2).png)
8. Copy the **Application Bot Configuration** and add it in the [Bot Management section](/v1/docs/creating-custom-microsoft-teams-apps#create-and-configure-a-bot-app) after you select your Bot.

![Application bot config URL](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CMA-App Bot Config URL(1).png)
9. In the **Welcome Banner Configuration**, add the additional information for your app as a welcome message and links or buttons for customer contact.

![133_Welcome_Banner_Config.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4fc3ebd2-f406-b8a1-e748-f9be16f81b48(4).png)
  - **Title**: Add the title of your welcome message.
  - **Description**: Add a description for your custom app.
  - **Feedback Link**: Optionally add a link for feedback regarding your custom app.
  - **Support Link**: Optionally add a link for providing support to your app users.
  - **SignUp Link**: Optionally add a link to sign up for your custom app.
10. To save the details, click **Save and Add**.

### Create Microsoft Teams app in Developer Portal

To create a Microsoft Teams application:

1. Navigate to the [Microsoft Developer Portal App](https://dev.teams.microsoft.com/apps) section.
2. Click **New App** and provide an app name.

![129_Updated_Custom_-_New_App.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f43704b2-1b50-0442-8faf-9cdb14b06d7e(2).png)
3. Once the app is created:
  1. In the **Branding** section, upload the Teams application logo. The logo should be in the png format with dimensions 192x192 pixels.

![129_Updated_new_app_-_logo.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4417181f-3bc1-6d1e-ab43-291df93cb931(2).png)
  2. In the **Configure** section, open the **Basic Information** page. Here, you can view and edit key details about the app, such as the full app name, description, developer information, and privacy URLs related to your application.

Developer information, App URLs and description are required fields.
  3. Use this App ID in your Securiti tenant in App ID field.

![129_Updated_New_Team_-_Basic_info_and_app_id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da2b326c-2e89-7290-3874-a5b10c1f88c0(2).png)
  4. After configuring the bot application, update the **Application (Client) ID** with **Bot ID**.

![129_Updated_Application_client_ID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9b55629-b6da-bf15-82e6-979a866d37b3(2).png)
  5. Navigate to the **App Features** section from the sidebar and select the Bot feature.
  6. In the **Identify your bot** field:
    1. Choose the option to select an existing bot.
    2. Select the bot app that we just configured. Additionally, make sure to select the required fields as shown in the figure below. ![Advanced_-_Select_bot_label.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59464bd9-124c-c7a5-8ba2-c48c2b3fcef3(2).png)

You can use the Microsoft Teams app by previewing the app in the teams or publishing it.

To [enable direct messaging](/v1/docs/messaging-app-integrations#direct-message-configuration-for-microsoft-teams-apps) for your app, select **Personal** in scopes:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(115).png)

### Publish Microsoft Teams app to your organization

To publish your Microsoft Teams app to your organization:

1. In the Developer Portal, click **Publish to org**.

![129_Updated_Publish_to_org_-_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a773bfcf-9cd7-3822-1864-8136d847f8d8(2).png)
2. Click **Publish your app**. In [Microsoft Teams admin centre](https://admin.teams.microsoft.com/policies/manage-apps), the app is listed pending approval.

![129_Updated_Publish_your_appLabelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3d74ee0c-5dd7-b1cb-d555-d85897e42a9e(2).png)
3. In **Org wide settings**, ensure to enable permissions under **Custom Apps**.

![MS_Teams_Admin_Center_-_Custom_Apps_reqs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-15406055-97dc-c098-6f67-c73ee40027b0(2).png)

When the app is submitted, a success message displays.

![129_Updated_Published_Genia_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f6a5138-b34a-bfbb-fda8-8d0a1fb571cf(2).png)

### Integrating custom Microsoft App with Securiti

To see how to integrate your custom Microsoft app with Securiti, see [Configuring Messaging App Integrations](/v1/docs/configuring-messaging-app-integrations).
