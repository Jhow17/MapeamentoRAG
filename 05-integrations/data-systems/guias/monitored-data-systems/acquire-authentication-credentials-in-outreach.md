---
title: "Acquire authentication credentials in Outreach"
slug: "acquire-authentication-credentials-in-outreach"
updated: 2026-07-13T08:05:04Z
published: 2026-07-13T08:05:04Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-outreach"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Outreach

1. Log in to the Outreach instance.
2. To request API access in Outreach, fill out the [form](https://www.outreach.io/product/platform/api), as shown below.

![Outreach_API_access_form.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1a1b3e1-412f-e047-ae07-1c9bd152383a.png)

Outreach support creates an application and generates the authentication credentials.
3. You can add comments in the form by providing support with the Callback URL and scopes required for Securiti to integrate Outreach. Or you can do this later after application details are generated.

| Callback URL | - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
| --- | --- |
| Minimum scopes | - audits.read - users.read - prospects.read - phoneNumbers.read - emailAddresses.read - accounts.read - calls.read - recipients.read - opportunities.read - mailboxes.read - mailings.read - snippets.read - personas.read - complianceRequests.all |
4. Record the **Client ID** and **Client Secret** (authentication credentials) you obtained earlier to use later.
5. Proceed to [Connecting Outreach with Securiti](/latest/docs/connecting-outreach-with-securiti).
