---
title: "Prerequisites for Trello connectors"
slug: "prerequisites-for-trello-connectors"
updated: 2026-06-28T14:32:35Z
published: 2026-06-28T14:32:35Z
canonical: "helpcenter.securiti.ai/prerequisites-for-trello-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Trello connectors

To establish a successful Connection in Securiti, Trello data systems use an API key and app Token for the Connector. Use the matching procedure below.

1. > [!NOTE]
> **Note**
> 
> We assume you have a Trello Instance running or you are the admin of your Trello account. That way you can select or configure required Permissions before activating the Connector.

To create a Power Ups Integration:
  1. Log in to [Trello Power Ups account](https://trello.com/power-ups/admin/)
  2. In the upper right corner of the page, click **New**

![new_powerUp_integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ecf48d38-0eb8-73b5-c3f5-b5b5ea6c2e60.png)
  3. On the application details page, enter a name for the app and apply other settings to suit. You can leave the **Iframe Connector URL field** blank.

![app_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ffba276-48da-09aa-cd4d-cc1fc9f26cd0.png)
  4. In the left sidebar, select **API key**. On the right side pane, record the API key for later use.

![api_key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4a29b57-889c-79fb-9232-2ab2bb5598ad.png)
  5. Also, on the right side pane, click **Token** in the following text:

*Most developers will need to ask each user to authorize your application. If you are looking to build an application for yourself, or are doing local testing, you can manually generate a* ***Token***.

It redirects you to [Trello's authorization page](http://https://trello.com/1/authorize?expiration=never&amp;amp;scope=read,write,account&amp;amp;response_type=token&amp;amp;name=Server%20Token&amp;amp;key=5f74bf4503c6651924cb61ecca66ae14).
  6. Click **Allow** and record the app Token for later use.

![app_token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75447404-bbaa-fbe2-ddf0-3775cd1b2182.png)
2. Proceed to [Connecting Trello with Securiti](/latest/docs/connecting-trello-with-securiti).
