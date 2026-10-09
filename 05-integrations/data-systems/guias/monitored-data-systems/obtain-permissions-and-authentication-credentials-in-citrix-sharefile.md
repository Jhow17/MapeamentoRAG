---
title: "Obtain permissions and authentication credentials in Citrix ShareFile"
slug: "obtain-permissions-and-authentication-credentials-in-citrix-sharefile"
updated: 2026-07-30T10:00:46Z
published: 2026-07-30T10:00:46Z
canonical: "helpcenter.securiti.ai/obtain-permissions-and-authentication-credentials-in-citrix-sharefile"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permissions and authentication credentials in Citrix ShareFile

ShareFile data systems use admin permissions and ShareFile client id and secret to activate the connector successfully. Use the matching procedure below.

> [!NOTE]
> **Note**
> 
> We assume you have a ShareFile instance running to establish a connection with the ShareFile server. We also assume you are an admin with access to "account-wide users", "folders", and "files" (including **<*File Boxes*>**, **<*Sent Items*>**, and **<*e-signed documents*>**) before proceeding with connector activation.

1. Visit [Create API Key in ShareFile](https://api.sharefile.com/ApiKeys/Create)
2. Log in to the ShareFile account as an admin by clicking "Click here to log in."

> [!NOTE]
> **Note**
> 
> If you do not see the below page, proceed to the next step.

![log_in.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ede497a-4bb2-a49b-6755-a41742f950a6.png)
3. Enter your company domain in the Subdomain field, e.g., "securiti253", and click **Continue**. Then enter your email address and password.

![app_domain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5fc7f6e2-0dc9-6e24-2e17-6a37fc05be6c.png)

![email_password.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78fcf248-e9cd-2d06-957f-4020367cf133.png)

Click **Sign In**
4. > [!NOTE]
> **Important**
> 
> Do not use the "ShareFile" or any other ShareFile application name when creating the app. Otherwise, you won't be able to proceed with app creation.

On the following page, click **Create New**. ShareFile displays the API Key Generator page where you can enter the application name, description, and the redirection URI in their respective fields for your app.

| Redirect URLs | Use the information below to add the redirect URL that applies. - US cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
| --- | --- |

![api_key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf78947e-d568-0982-0bbe-bd34ae6ce2a4.png)

Click **Generate Api Key** to create the app.
5. For your app, record the **Client Id** and **Client Secret** information next to it for later use.

![client_id_secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4bf5da2a-d378-c646-9126-e9bf574d3c57.png)
6. Proceed to [Connecting Critix Sharefile with Securiti](/latest/docs/connecting-critix-sharefile-with-securiti).
