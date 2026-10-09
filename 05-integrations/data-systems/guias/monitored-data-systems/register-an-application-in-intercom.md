---
title: "Register an application in Intercom"
slug: "register-an-application-in-intercom"
updated: 2026-07-10T04:23:17Z
published: 2026-07-10T04:23:17Z
canonical: "helpcenter.securiti.ai/register-an-application-in-intercom"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register an application in Intercom

To integrate Securiti with Intercom for DSR Automation, you first register an application within Intercom and record its client ID and client secret:

1. Log in to the Intercom [developer hub](https://app.intercom.com/admins/sign_in).
2. At the developer hub Your Apps screen, click **New app** as shown below.

![C00084.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b672e97-4571-a736-4e94-1fb2ec1e0256.png)

A “New App” box appears as shown below.

![C00083.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c4e8cc42-4186-0ebc-38b3-0ca185d21cbb.png)
3. Apply the following settings:

| App name | Enter any convenient name. We recommend that you use the word "Securiti" in the name to remind you that it is for the Securiti solution. |
| --- | --- |
| Workspace | Choose a workspace for the app. |
| Integration | Mark the radio button for **Internal Integration**. |
4. Click **Create App**.

Intercom opens the Authentication page as shown below.

![C00085.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1feafa75-9264-d032-ab45-8937fba730b9.png)
5. Near the upper right corner of the page, click **Edit**.
6. In the OAuth area, mark the checkbox for **Use OAuth** and enter the one of the following redirect URL as shown below:

![C00086.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7a35097-2c4b-65d0-7117-8e71c52cb372.png)
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
  - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`
7. Near the upper right corner of the page, click **Save**.
8. On the left sidebar, click **Configure > Basic Information**.
9. On the Basic information page, record the Client ID and Client Secret as shown below to use later.

![C00087.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ec1f9edc-d305-da37-05ab-7ec3ea53f303.png)
10. Proceed to [Connecting Intercom with Securiti](/latest/docs/connecting-intercom-with-securiti).
