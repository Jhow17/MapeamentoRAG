---
title: "Configuring standard messaging apps"
slug: "configuring-standard-messaging-app"
updated: 2026-04-28T02:32:07Z
published: 2026-04-28T02:32:07Z
canonical: "helpcenter.securiti.ai/configuring-standard-messaging-app"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring standard messaging apps

**Scenario**

As a Data Governance Officer, you're looking to make GenAI insights easily accessible to teams in their daily workflows. Switching to dedicated tools breaks focus and slows adoption. With the **Standard Apps** section, users can interact with GenAI pipelines directly through apps, such as Slack. This enables real-time queries and responses from your knowledge base.

In the **User Portal > Messaging Apps > Standard Apps** section, you can integrate messaging applications to interact with your GenAI pipelines. You can query your GenAI pipelines and retrieve information from your configured knowledge base directly.

Securiti currently supports integration with the following messaging applications:

- [Slack](/v1/docs/configuring-messaging-app-integrations#add-gencore-ai-to-slack)
- [Microsoft Teams](/v1/docs/configuring-messaging-app-integrations#add-genia-to-microsoft-teams)

To integrate your GenAI pipeline with your messaging app, on **Gencore AI**:

1. Add Gencore AI bot to your messaging app.
2. Integrate Gencore AI bot with the messaging app channel.
3. Link GenAI pipeline with Gencore AI bot.

### Add Gencore AI to Slack

To configure the Gencore AI bot on your Slack workspace:

1. On Slack, click **+ Add Apps**.
2. On the [Slack marketplace](https://slack.com/apps), search for and open Gencore AI bot.
3. Click **Open in Slack**. Securiti directs you to the relevant oauth page.
4. To allow Gencore AI slack bot to perform mentioned actions on your messaging app workspace, click **Allow**. Securiti directs you to the **Standard Apps** section with corresponding app listed as **Connected**.

![List of connected apps including Slack and Microsoft Teams with their statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/slack connected.png)

### Integrate Gencore AI bot with Slack channel

To integrate your Gencore AI bot with Slack channel:

1. To create a new channel in Slack, click **+Channels**.

![Slack-Channels.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57d6c95a-0baa-2596-4f70-7945d302ef7c(1).png)
2. Select **Create channel**.

![Slack-CreateChannelmain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5b37d28c-5c5b-6941-90e8-5f65e5aa69cd(1).png)
3. Provide the channel name.

![Slack-ChannelName.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b0d7b70f-8c8d-c32e-3495-976dfb008db0(1).png)
4. Select the visibility for the channel as **Private** or **Public**.

![Slack-Visibility.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-277b349b-0275-db21-0db1-8f3cb46b0839(1).png)
5. Click **Create**.
6. Add people to the created channel.

![Slack-AddPeople.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-412bbbb5-b151-a708-7dfe-803be44c25ad(1).png)
7. To link your GenAI pipeline with the Gencore AI bot, in the channel settings, click **Integrations**.

![Slack-integrationsTab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-23da79d7-e28f-bc97-1dd1-798c7bb861e6(1).png)
8. Click **Add an App**.

![SlackMP-Add_an_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-782c21ac-aac5-a12a-524f-0d4f13413fac(1).png)
9. Click the Gencore AI bot to add it to the Slack channel.

> [!NOTE]
> **Note**
> 
> Once the Gencore AI bot is integrated, it takes about 15 minutes before displaying the created Slack channel in the list of the channels in the **Messaging App Integrations** pipeline node.

### Link GenAI pipeline with Gencore AI bot

To link your GenAI pipeline with Gencore AI bot:

1. In the pipeline you want to link to the Slack channel, open the **Messaging App Integrations** node.
2. Enable the messaging app. In this case, **Slack**.

![Enable_Slack_toggle.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7d9d489c-6367-5ac2-fbf7-8fd6f9ec1f48(1).png)
3. Click **Channel** and select the created Slack channel from the list.

![Enabled slack toggle](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Enable toggle - Slack channel.png)
4. To save the details, click **Save and Continue**.
5. To disconnect the messaging app, click the toggle button adjacent to the app name you want to disconnect from.

![Settings interface showing Slack channel selection with toggle options and search functionality.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Slack channel - selected disconnected.png)

### Add Genia to Microsoft Teams

To configure Genia with your Microsoft Teams application:

1. Ensure a Team is created in your Microsoft Teams app.

> [!NOTE]
> **Note**
> 
> To learn how to create a Team, see [Create a Team](https://support.microsoft.com/en-au/office/create-a-team-from-scratch-in-microsoft-teams-174adf5f-846b-4780-b765-de1a0a737e2b).
2. Integrate Genia with a Microsoft Teams channel.
3. Link your GenAI pipeline with a Teams channel.

#### Integrate Genia with Microsoft Teams channel

To integrate Genia with Microsoft Teams application:

1. In your pipeline, open the **Messaging App Integrations** node.
2. Click **Add Messaging Service**. Securiti opens the **Settings > Gencore AI > User Portals** page.
3. On your User Portal, click **Options** (three dot menu) and choose **Edit**.
4. Select the **Messaging Apps** tab.
5. On **Microsoft Teams**, click **Connect**. Securiti directs your to Microsoft Teams.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4CSOGP87.png)
6. Click **Open**.

![Overview of the Genia app for Microsoft Teams, highlighting key features and functionalities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Genia app open(2).png)
7. In the popup, select the relevant team and click **Go**.

> [!NOTE]
> Important
> 
> Ensure you select the standard channel only as Securiti sends the first welcome message to the standard channel.

![Genia app interface showing channel selection options for users to choose from.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Genia - Select channel(1).png)

A welcome message from your app displays in your Microsoft Teams channel.

Meanwhile, for [direct conversation](/v1/docs/messaging-app-integrations#direct-message-configuration-for-microsoft-teams-apps) with your app, the following message displays in your chat with the app.

![Instructions for using the 'Get started' button and linking a pipeline for messaging.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/message - guidelines for direct messaging.png)
  - To get started with connecting to Securiti, click **Get Started.**
  - To provide feedback, click Have Feedback?
  - To contact support, click **Contact Support**.
  - To know more about the app, click **New to (App name)**.

![Welcome message from Genia for Microsoft Teams, highlighting features and account connection instructions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Welcome message from Genia - GS button.png)
8. To start connecting to Securiti, click ​**Get started**​​. When you click **​Get started**​​, you are taken to your browser to review and approve the required permissions.
9. On the ​Connect with **Securiti ​Gencore AI** page, click ​**Review Permissions​​**.

![Connect with Securiti Gencore AI and review Microsoft account permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Teams-reviewpermissions.png)
10. Select your Microsoft user account associated with the logged-in tenant. You can view a set of permissions required for this integration.
11. Click ​**Accept**​​. Once the permissions are accepted, you must log in to ​Securiti.
12. Click **Sign in to Securiti**.

![Sign in to Securiti account to connect with Microsoft Teams and various services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/teams-signintosecuriti.png)

> [!NOTE]
> **Note**
> 
> If you are logged in to Securiti already, the platform does not ask for a login.

Once logged in successfully, the confirmation message displays as **​Connected with Securiti Gencore AI​​**.

After you complete the permission flow, Securiti sends a confirmation message to the integrated Teams channel.

![Instructions for integrating GenAI pipelines into Microsoft Teams for streamlined communication.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/message after connecting(1).png)
13. In your Securiti tenant, go to apps list in your user portal settings. Securiti displays the status as **Connected**.

![Microsoft Teams shows 10 teams and 1 bot, both connected successfully.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/standard apps connected number(1).png)

> [!NOTE]
> **Note**
> 
> The badge displays the number of connected Teams apps (e.g., 1 Team Connected). This number updates when you add or remove Teams apps.
14. To connect more Teams apps, click the Options menu (three dots) and click **+ Connect more**. Follow the same process from Step 3.

![Interface showing app connections for Microsoft Teams and Slack with options to connect more.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/app options connect more.png)

> [!NOTE]
> **Note**
> 
> To connect the app for the first time, you must have the ​Admin User​​ role.

#### Link GenAI pipeline with Teams channel

To link your GenAI pipeline with your Teams channel:

1. Go to the **Messaging App Integration** node of the pipeline where you want to link Genia to the Teams channel.
2. Under the **Channel Configuration** tab, enable the **Microsoft Teams** toggle.
3. Click the **Channel** dropdown.
4. Select one or more channels for the connected app.

![Select General channel for Teams standard app](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MAI - select general channel(1).png)
5. Once the channel is selected, a welcome message is sent to the Teams app.

![Genia introduces herself and offers assistance regarding the RAG_133 topic.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/message after selecting channel(1).png)

#### Converse with GenAI pipeline in your channel

To start a conversation with Genia:

1. Tag Genia in your connected Teams channel and type your question.
2. Click **Post**. You receive the relevant response.

![Genia provides information about Weaviate and its capabilities in a chat interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ask-genia .png)

To learn how to configure direct messaging with your Microsoft Teams app, see ​[Direct messaging configuration​​](/latest/docs/messaging-app-integrations#direct-message-configuration-for-microsoft-teams-apps).

### Viewing pipeline connections

You can view your pipeline connections for your messaging apps by clicking the **Options** (three-dot) menu to the right of your connected apps.

To view the pipeline connections:

1. Click **Pipeline Connections**. Securiti displays the **Pipeline Connection Breakdown**.

![Interface showing app connections with options for Slack and Microsoft Teams.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline connections.png)
2. To view a connection’s status, click on the pipeline title.

![Overview of connected pipelines in the Securiti-Hosted Portal for Microsoft Teams.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline connection breakdown.png)

The expanded view displays the channels integrated with the pipeline.

![Overview of pipeline connections in Microsoft Teams, highlighting BURP_141 and its channels.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pipeline connection breakdown - pipeline expanded.png)

### Reauthorizing messaging apps

If your app requires reauthorization, the relevant icon displays with the app name. To reauthorize your messaging app:

1. Click on the ​**reauthorize** icon​​.

![Microsoft Teams interface showing connected teams and a warning icon for Standard App.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MI - reauthorize icon.png)
2. Click ​**Reauthorize**​​. Securiti directs you to the permissions page for the messaging app.

![Microsoft Teams interface showing reauthorization prompt and connection options for apps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MI - authorize expanded button.png)
  - For Slack, Securiti directs you to the Slack portal where you can reauthorize your app by clicking ​**Allow**​​.

![SlackCustomApp requests permission to access Gencore Messaging Integrations workspace features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CMS-CMSA Allow.png)
  - For Microsoft Teams, Securiti directs you to your Microsoft Teams account where you can verify your credentials and ​[integrate your app​](/latest/docs/configuring-messaging-app-integrations#integrate-genia-with-microsoft-teams-channel)​.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Messaging app integrations](/messaging-app-integrations.md)
- [Configuring custom messaging apps](/configuring-custom-messaging-apps.md)
