---
title: "Register a client in Zoho"
slug: "register-a-client-in-zoho"
updated: 2026-06-26T11:01:32Z
published: 2026-06-26T11:01:32Z
canonical: "helpcenter.securiti.ai/register-a-client-in-zoho"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register a client in Zoho

To integrate Securiti with Zoho for DSR Automation, you first register a client in Zoho and receive a client ID a client secret.

1. Navigate to [https://accounts.zoho.com/developerconsole](https://accounts.zoho.com/developerconsole) and click **Add Client ID** as shown below.

![C00333.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f17e6284-8962-d053-0732-bb1c435c6923.png)
2. In the Create Zoho Client ID box, apply the following settings.

| Client Name | Enter your organization name. |
| --- | --- |
| Client Domain | Enter your organization domain. |
| Authorized redirect URIs | - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
| Client Type | Choose **WEB Based**. |

![C00334.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ecdb6c9-2a72-7381-a157-2a60195d34a6.png)
3. Click **Create**. Zoho shows you the client ID and client secret it created, as shown below.

![C00335.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c3d4216-a935-99c4-ff0f-532fa2a311fd.png)
4. Record the client ID and client secret to use later.
5. Proceed to [Connecting Zoho CRM with Securiti](/latest/docs/connecting-zoho-crm-with-securiti).
