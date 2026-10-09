---
title: "Register an application in Asana"
slug: "register-an-application-in-asana"
updated: 2026-05-29T10:07:07Z
published: 2026-05-29T10:07:07Z
canonical: "helpcenter.securiti.ai/register-an-application-in-asana"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register an application in Asana

To integrate Securiti with Asana for DSR automation, you first register your application with Asana to receive a client ID and a client secret.

To register a new application in Asana:

1. Navigate to [https://app.asana.com/0/developer-console](https://app.asana.com/0/developer-console) and click **Add New Application**.

![C00009.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-229993ca-da49-e052-4bae-35c5fc1a5c95.png)
2. In the Create new app box, enter a name for the app, mark the "I agree" checkbox and click **Create App** as shown below.

![C00010.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48c1fb1f-89f8-1b40-9215-19aea07dd341.png)

Asana creates a new app and redirects you to its configuration page.
3. Click the **Settings** tab.
4. In the App Website box, enter the following URL as shown below:

![C00011.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-88ea59ba-345b-c717-803b-cd3411daea44.png)
  - US cloud: `https://app.securiti.ai`
  - US1 cloud: `https://app1.securiti.ai`
  - Indonesia Cloud: `https://app2.securiti.ai`
  - Canada Cloud: `https://app3.securiti.ai`
  - Australia Cloud: `https://app4.securiti.ai`
  - UAE Cloud: `https://app5.securiti.ai`
  - India Cloud: `https://app6.securiti.ai`
  - EU cloud: `https://app.eu.securiti.ai`
  - KSA cloud: `https://app7.securiti.ai`
  - Qatar Cloud: `https://app8.securiti.ai`
  - Sovereign deployment: Consult the administrator of your Sovereign deployment
5. Click **Save Changes**.
6. Click the **Authorization** tab.
7. In the Redirect URL box, enter one of the following URLs as shown below:

![C00012.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55d113c2-5979-53d0-db2e-f9f886ee7115.png)
  - US cloud: `https://app.securiti.ai/static/activateConnector.html`
  - US1 cloud: `https://app1.securiti.ai/static/activateConnector.html`
  - Canada cloud: `https://app3.securiti.ai/static/activateConnector.html`
  - EU cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
  - Indonesia cloud: `https://app2.securiti.ai/static/activateConnector.html`
  - Australia cloud: `https://app4.securiti.ai/static/activateConnector.html`
  - UAE cloud: `https://app5.securiti.ai/static/activateConnector.html`
  - Mumbai cloud: `https://app6.securiti.ai/static/activateConnector.html`
  - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
  - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
  - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`
8. Record the Client ID and Client Secret to use later.
9. Click **Add**.
