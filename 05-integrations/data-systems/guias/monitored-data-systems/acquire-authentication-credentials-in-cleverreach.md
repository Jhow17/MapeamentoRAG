---
title: "Acquire authentication credentials in CleverReach"
slug: "acquire-authentication-credentials-in-cleverreach"
updated: 2026-07-21T10:10:55Z
published: 2026-07-21T10:10:55Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-cleverreach"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in CleverReach

1. Log in to your CleverReach instance.
2. CleverReach uses Client Id and Client Secret for connector activation.

> [!NOTE]
> **Note**
> 
> You can register for a free account at [https://www.cleverreach.com/en/](https://www.cleverreach.com/en/). CleverReach sends you two emails to verify your account and the other with your login credentials (Customer ID, Login URL, Login Name, and Password).
3. Click the **Developer icon (</>)** near the top right corner of the CleverReach admin page and choose **Manage OAuth Apps**.

![CleverReach Dashboard view](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f9cd083-c9fd-3d91-b319-4720fe002391.png)
4. Click **Create OAuth App now** on the REST API page.

![REST API page](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6dab7b6-2866-3a7c-cf07-edc56f09b46e.png)
5. On the OAuth app creation popup, enter a name for your app and click **Create now**.

![New OAuth App creation](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8b056ff1-9a58-ae8b-d8dd-262825fe6e7c.png)

![Client ID &amp; Client Secret](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e073c427-a6f4-5632-318c-855360ae7d0e.png)

Record your **Client ID** and **Client Secret** to use later and click Save.

> [!NOTE]
> **Important**
> 
> Your Redirect URL is the app's default "all," as denoted by an asterisk (*). If you want to redirect the app to a particular URL after activation, you may enter it in the field.
6. Proceed to [Connecting CleverReach with Securiti](/latest/docs/connecting-the-cleverreach-with-securiti).
