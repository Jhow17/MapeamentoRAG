---
title: "Register an application in Shopify (Securiti-Cloud)"
slug: "register-an-application-in-shopify-securiti-hosted"
updated: 2026-09-11T11:43:35Z
published: 2026-09-11T11:43:35Z
canonical: "helpcenter.securiti.ai/register-an-application-in-shopify-securiti-hosted"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register an application in Shopify (Securiti-Cloud)

To integrate Securiti with Shopify for DSR Automation, you register an application and store within Shopify, and receive a Domain, Client ID, and Client Secret:

> [!NOTE]
> **Note**
> 
> You can skip steps 1-4 if you have an existing store.

1. Navigate to the Shopify Partners main website (https://www.shopify.com/partners) and click either **Join Now** button. ![C00278.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2e784592-ce61-d3c2-9e9c-a999b747670c.png)
2. On the Create an Account page, fill out the form and click **Create account**. ![C00279.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ee017eb-3cc0-b4ed-4484-4c3f93bf9387.png)
3. On the Add details page, fill out the form with your organization details and click **Proceed to Dashboard**. ![C00280.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4354c489-64a7-a526-2ab4-8cf8a59ce303.png)
4. On the Dashboard screen for your Shopify Partners profile, on the left sidebar click **Apps**.

![C00281.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f18d390e-f1dd-3145-225a-f5923065add5.png)
5. Click **Create app**.

![C00282.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1dd6055-d386-c7e6-ef99-8842f814b1d5.png)
6. On then Create app pop-up, apply the following settings and click **Create App**.

| App name | Any convenient name |
| --- | --- |
| App URL | - US Cloud: `https://app.securiti.ai` - US1 Cloud: `https://app1.securiti.ai` - Indonesia Cloud: `https://app2.securiti.ai` - Canada Cloud: `https://app3.securiti.ai` - Australia Cloud: `https://app4.securiti.ai` - UAE Cloud: `https://app5.securiti.ai` - India Cloud: `https://app6.securiti.ai` - EU Cloud: `https://app.eu.securiti.ai` - KSA Cloud: `https://app7.securiti.ai` - Qatar Cloud: `https://app8.securiti.ai` - Sovereign deployment: Consult the administrator of your Sovereign deployment |
| Allow-listed redirection URL(s) | - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

![C00283.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9395cba-965d-655e-1e6c-f6b261ca671d.png)
7. On the details page for your app, record the API key and the API secret key to use later.

![C00284.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-821ae352-d4a2-9a07-8fe8-8384c46644cc.png)
8. Click the App action menu and click **Install on development store**.

![C00285.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1a4da80-be64-0486-2d5b-836b31b788dc.png)
9. On the Install your App pop-up, select an existing store from the **Select a store** menu, or **Create a new development store** and click **Install app on store**, as shown below.

![C00310.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc71f386-2653-e716-f140-8578be19cfc7.png)
10. On the Add store page, in the Pick a store type area, mark the radio button for **Development store**, then click **Save**.

![C00287.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c53da1f7-09a3-a953-b05c-7ae3ded34947.png)

Shopify redirects you to the home page for your development store.
11. Record the store name to use later. You use this name as the domain/account ID when you activate the Connector in Securiti.

![C00288.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b3bb2d0-3081-54d4-4700-3050af007d0b.png)
12. Return to your new app’s details page.
13. From the App actions menu, click Install on development store.

![C00285.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1a4da80-be64-0486-2d5b-836b31b788dc.png)
14. On the Install your app popup, choose the development store you just created (in this example, DemoStore321619).

![C00286.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fffc15f7-efa8-2986-05bb-9ae61d25e215.png)
15. Proceed to [Connecting Shopify with Securiti (Securiti hosted)](/latest/docs/connecting-shopify-with-securiti-securiti-hosted).
