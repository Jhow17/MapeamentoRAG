---
title: "Register an application in Zendesk Support (Self-hosted)"
slug: "register-an-application-in-zendesk-support-self-hosted"
updated: 2026-06-27T08:50:05Z
published: 2026-06-27T08:50:05Z
canonical: "helpcenter.securiti.ai/register-an-application-in-zendesk-support-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register an application in Zendesk Support (Self-hosted)

1. Log in to your Zendesk Administrator account.
2. On the left sidebar, click the gear icon for Settings.
3. In the Channels area, click **API**.
4. On the Zendesk API page, click the **OAuth Clients** tab.
5. Near the right side of the page, click **+** to create a new OAuth client.

![C00048.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a0843bb-cf9b-adc2-37a9-7830f7dc03ee(1).png)
6. Provide the necessary information in the following fields:

| Setting | Description |
| --- | --- |
| Client name | Specify the name of your client, displayed to Securiti when asked to grant access to your application. See an example below. *alpha1* |
| (Optional)Description | Provide a brief description of the client application to help understand the purpose. See an example below. |
| Company | Enter your Zendesk application name. |
| (Optional) Logo | Select an image (JPG or PNG) as logo that is displayed to Securiti during the Connection to visually represent your application. |
| Unique identifier | A system-generated identifier for the OAuth client used in API calls. This is reserved for internal usage and not visible to Zendesk users. By default, this is the same as the client name specified above. |
| Client kind | Select the client kind to **Confidential** for successful and secure Authentication. |
7. In the Redirect URLs box, enter one of the following URLs:
  - US Cloud: `https://app.securiti.ai/static/activateConnector.html`
  - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html`
  - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html`
  - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
  - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html`
  - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html`
  - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html`
  - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html`
  - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
  - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
  - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` ![C00049.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57a8f7b2-a300-f253-ce4e-92dd2ccd4ba5(1).png)
8. Click **Save**.

Zendesk alerts you to store the secret that it is about to show you. It only shows you the secret once. If you lose it, you must reset it. ![C00050.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5aa22095-86e2-0ab2-585c-bcca81ebd7a6(1).png)
9. Click **OK**.
10. Record the text in the Unique Identifier and Secret boxes to use later. ![C00051.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21344a55-5250-2339-52c3-a33d933b0b55(1).png)
11. Proceed to [Connecting Zendesk Support with Securiti (Self-hosted)](/latest/docs/connecting-zendesk-with-securiti-self-hosted).
