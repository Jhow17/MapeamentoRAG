---
title: "Messaging app integrations"
slug: "messaging-app-integrations"
updated: 2026-01-27T04:32:13Z
published: 2026-02-09T22:00:18Z
canonical: "helpcenter.securiti.ai/messaging-app-integrations"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Messaging app integrations

In the **Messaging App Integrations** node, you can connect your pipeline with the channels and configure direct messaging with following messaging apps:

- **Slack**
- **Microsoft Teams**

## Prerequisites

To integrate your messaging app with your GenAI pipeline, you must have an active account on the messaging app portal.

## Adding a messaging service

To add a messaging service:

1. In the **Messaging App Integration**, click **Add messaging service**.

![Add messaging service in messaging app integration node](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Messaging app integrations - Add messaging service.png)

The **Messaging Integrations** settings display where you can configure the messaging app. To learn how to integrate GenAI pipeline to your messaging app workspace, see [Configuring Messaging Integrations](/v1/docs/configuring-messaging-app-integrations).
2. Once the messaging service is configured, go back to your pipeline and open **Messaging App Integrations**. The messaging service is listed.

## Channel configuration

Securiti displays the **Channel Configuration** tab by default. To connect your pipeline to a messaging app:

1. In the **Channel Configuration** tab, click the toggle to enable the messaging app service you want to connect to.

![messaging app integration node - enabled standard app](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Channel config - enable app standard.png)
2. To link your pipeline to a channel:
  1. Click the **Channel** dropdown and select the channel where the Gencore AI bot is integrated.
  2. Manually type the **Channel ID**. To find the channel ID, click in the **Channel** field and scroll down to find the channel ID. You can link your pipeline to multiple channels.

You can click **Refresh** to refresh the channel list. ![messaging integrations node refresh button](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/mai - channels refresh.png)

Your app is integrated in your Slack channel.

![CMS-CMSA_integrated_in_channel_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70a8dd28-e95d-d207-9d9d-ab3587706a1b(1).png)
    - ![messaging integrations node channels selected](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/mai - channels selected.png)
3. To save the details, click **Save and Continue**.

## Reauthorizing messaging apps

If your app requires reauthorization, a reauthorization icon appears next to the app name. To reauthorize your messaging app:

1. Click the ​**Reauthorize**​​ icon​.

![Microsoft Teams interface showing options for channels and app settings with reauthorize icon](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Reauth icon.png)
2. On the ​**Reauthorization required**​ popup, click ​**Reauthorize**​​. Securiti directs you to the permissions page for the messaging app.

![Microsoft Teams interface showing reauthorization prompt and channel selection options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Reauth button.png)
  - For Slack, Securiti directs you to the Slack portal where you can reauthorize your app by clicking ​**Allow**​​.
  - For Microsoft Teams, Securiti directs you to your Microsoft Teams account where you can verify your credentials and ​integrate your app​​.

## Direct messaging configuration

You can configure direct messaging with your apps:

- [Direct message configuration for Slack apps](/v1/docs/messaging-app-integrations#direct-message-configuration-for-slack-custom-apps)
- [Direct message configuration for Microsoft Teams apps](/v1/docs/messaging-app-integrations#direct-message-configuration-for-microsoft-teams-custom-apps)

### Direct message configuration for Slack custom apps

To configure direct messaging for your custom Slack app:

1. Click **Direct Message Configuration** tab.
2. In the **Direct Message Configuration** tab, click the toggle to enable direct messaging with your app.

![Configuration settings for integrating Slack and Microsoft Teams with direct messaging options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Direct messaging slack.png)
3. To ask a query, message your app directly in your messaging app.

![CMS-Direct_Message_Answered.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f98f4301-e37e-58af-89a9-342ac713b655(1).png)

### Direct message configuration for Microsoft Teams apps

To configure direct messaging for your custom Microsoft Teams app:

> [!NOTE]
> **Note**
> 
> To enable direct messaging for Microsoft Teams app, you must configure required settings on your Developer Portal and ensure the app is installed in the personal scope in Teams. For more information, see [Creating custom Microsoft Teams apps](/v1/docs/creating-custom-microsoft-teams-apps).

1. In the **Messaging App Integration** node of your GenAI pipeline, click **Direct Message Configuration** tab.
2. Click the toggle to enable direct messaging with your app and click **Enterprise**.
3. To select the enterprise, click ​**Enterprise**​​.

![Select enterprise in channels](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Genia-direct messaging-select enterprise.png)

> [!NOTE]
> Important
> 
> The ​**Enterprise**​​ denotes the customer's Microsoft tenant name. If Teams relate to different tenants, each tenant appears as a separate **Enterprise** and you can select multiple enterprises. If all teams belong to the same tenant, only one **Enterprise** is shown.
4. To ask a query, on Microsoft Teams, select the app and converse with your app directly.

![Direct chat with app](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/direct chat with app.png)

#### In-chat guidance messages

You may receive the following messages to ensure direct messaging:

- ​If the **authentication is not completed**​​, the following message displays guiding you to complete the integration process.

![Instructions for using the 'Get started' button and linking a pipeline for messaging.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/message - guidelines for direct messaging(1).png)
- ​​If the **authentication is complete​​, however, the pipeline is not connected** for direct messaging, the following message displays indicating how to link the pipeline.

![Instructions for linking a pipeline for Direct Messaging in Securiti tenant.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Auth complete but pipeline not integrated.png)

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Configuring standard messaging apps](/configuring-standard-messaging-app.md)
- [Configuring custom messaging apps](/configuring-custom-messaging-apps.md)
