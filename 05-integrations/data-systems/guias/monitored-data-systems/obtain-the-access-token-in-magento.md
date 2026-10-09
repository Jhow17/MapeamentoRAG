---
title: "Obtain the access token in Magento"
slug: "obtain-the-access-token-in-magento"
updated: 2026-07-20T20:07:59Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/obtain-the-access-token-in-magento"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain the access token in Magento

To integrate Securiti with Magento for DSR Automation, you first obtain the access Token and domain in Magento that you apply in Securiti.

1. Log in to Magento with your admin Credentials.
2. In Magento, navigate to **System > Extensions > Integrations**.
3. Click **Add New Integration**.
4. On the New Integration page Integration Info tab, apply the following settings:

| Name | Enter a convenient name for the Integration. |
| --- | --- |
| Email | Leave blank. |
| Callback URL | Enter one of the following URLs: - US Cloud: `https://app.securiti.ai` - US1 Cloud: `https://app1.securiti.ai` - Indonesia Cloud: `https://app2.securiti.ai` - Canada Cloud: `https://app3.securiti.ai` - Australia Cloud: `https://app4.securiti.ai` - UAE Cloud: `https://app5.securiti.ai` - India Cloud: `https://app6.securiti.ai` - EU Cloud: `https://app.eu.securiti.ai` - KSA Cloud: `https://app7.securiti.ai` - Qatar Cloud: `https://app8.securiti.ai` - Sovereign deployment: Consult the administrator of your Sovereign deployment |
| Identity link URL | Leave blank. |
| Your Password | Enter your Magento admin password. |

![Magento_new_integration_info.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b6996505-d66a-33ce-962b-d06920f869a9.png)
5. In the Basic Settings area near the left side of the page, click the **API** tab.
6. In the Available APIs area, from the Resource Access menu choose **All** as shown below.

![API_choose_All.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff706f0a-bde5-43c4-79ae-906014cd3cdc.png)
7. Near the upper right corner of the page, click **Save**.
8. On the Integrations page, click the **Activate** link for the new Integration you just created.
9. Click **Allow** as shown below.

![Click_Allow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e8b32790-f56f-6850-88bd-0d1e5c287144.png)

Magento shows you the Integration tokens for the new Integration as shown below.

![Magento_shows_integration_tokens.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fc0588f4-b0d1-616c-526e-2e0bc1b2ae2e.png)
10. Record the Access Token to use later.
11. Near the upper right corner of the page, click **Done**.
12. In the URL bar for the tab with the Magento console, record the domain portion of the URL as shown below to use later.

![domain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-17d0f526-d218-194f-fd12-7ceb30498a73.png)
13. Proceed to [Connect Magento connector with Securiti](/latest/docs/connect-magento-connector-with-securiti).
