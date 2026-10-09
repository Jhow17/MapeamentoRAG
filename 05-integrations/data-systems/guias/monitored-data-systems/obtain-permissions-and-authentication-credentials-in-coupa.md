---
title: "Obtain permissions and authentication credentials in Coupa"
slug: "obtain-permissions-and-authentication-credentials-in-coupa"
updated: 2026-07-07T06:33:37Z
published: 2026-07-07T06:33:37Z
canonical: "helpcenter.securiti.ai/obtain-permissions-and-authentication-credentials-in-coupa"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permissions and authentication credentials in Coupa

Coupa data systems use Oauth 2.0 authentication method to activate the connector. Do the following to generate client credentials.

> [!NOTE]
> **Important**
> 
> You have to reconfigure any existing Coupa connectors using the OAuth 2.0 authentication you previously activated via the Legacy authentication method.

1. Log in to your Coupa account with the admin credentials.
2. On the setup tab, click **Oauth Connect**.
3. Click **Create** to create the app.
4. On the following page, select **Client credentials** from the Grant type menu. Enter the required information and enable all *read* scopes.
5. You can view the created app, as shown below. Record the **Identifier** (client id) and **Secret** (client secret) values for later use.

![client_id_secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4989ebda-8ce5-63a6-b29d-973050a43b00.png)
6. Proceed to [Connecting Coupa (Self-hosted) with Securiti](/latest/docs/connecting-coupa-self-hosted-with-securiti).
