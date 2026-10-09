---
title: "Grant permissions and obtain credentials in Domo"
slug: "grant-permissions-and-obtain-credentials-in-domo"
updated: 2026-07-21T10:20:43Z
published: 2026-07-21T10:20:43Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-domo"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Domo

The Domo data system requires client id and secret to establish a successful connection in Securiti

> [!NOTE]
> **Important**
> 
> We assume you are an admin before creating a Domo app so you can configure required application scope(s).

1. Log in to [Domo Developer Portal](https://developer.domo.com/manage-clients).

> [!NOTE]
> **Note**
> 
> If you do not have an account, you can sign up for a free Domo developer trail at [this link](https://www.domo.com/start/developer).
2. On the Manage Clients page, click **Create a client** and configure these details:

Click **Create**
  - Enter an app name
  - Enter a description for your app
  - In the **Application Scope**, mark the checkbox for **Data**

![create_client.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad1fdd8b-6753-dc6f-cf79-aef814f70f00.png)

![client_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-484a769a-ab59-6156-c1f1-4b6797d66d22.png)
3. On the following page, record the **Client Id** and **Client Secret** for later use.

![client_id_and_secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5eced7f1-c68a-5586-96f1-417a710741e1.png)
4. Proceed to [Connecting Domo with Securiti](/latest/docs/new-ui-connecting-domo-with-securiti).
