---
title: "Grant permissions and obtain credentials in Zoho Recruit"
slug: "grant-permissions-and-obtain-credentials-in-zoho-recruit"
updated: 2026-06-27T08:07:59Z
published: 2026-06-27T08:07:59Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-zoho-recruit"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Zoho Recruit

Zoho Recruit Data system Connector uses a set of minimum Permissions and Activation parameters for Activation. Use the matching procedure below to activate the Connector in Securiti.

> [!WARNING]
> **Important**
> 
> We assume you have the setup running Zoho Recruit or access to its admin to enable necessary Permissions and obtain Activation Credentials.

1. Enable the following User role Permissions:
  - Modules.All.Read
  - Users.All.Read
  - Settings.All.Read
2. Log in to your [Zoho Developer Console](https://accounts.zoho.com/signin?servicename=AaaServer&amp;amp;context=&amp;amp;serviceurl=https%3A%2F%2Fapi-console.zoho.com%2Flogin).

> [!NOTE]
> **Note**
> 
> You can create a free trial account if you don't already have an active account.
> 
> Create a new API client by selecting the Web-based application on the page and following the below link.
> 
> [https://www.zoho.com/recruit/developer-guide/apiv2/register-client.html](https://www.zoho.com/recruit/developer-guide/apiv2/register-client.html)
3. On the Zoho API console page, select your application, and on the tab for Client Secret, record the following for later use:
  - Client ID
  - Client Secret ![Zoho_Recruit_Client_Id_and_Secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9e95537-1dab-62e7-d5d0-06b2c1c9b7a5.png)
4. Proceed to [Connecting Zoho Recruit with Securiti](/latest/docs/connecting-zoho-recruit-in-securiti).
