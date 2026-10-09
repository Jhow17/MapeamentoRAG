---
title: "Intercom"
slug: "intercom-connectors"
status: "new"
updated: 2026-07-16T06:23:45Z
published: 2026-07-16T06:23:47Z
canonical: "helpcenter.securiti.ai/intercom-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Intercom

Intercom is a customer messaging and engagement platform that enables businesses to communicate with customers through chat, email, and other digital channels. By connecting Intercom with Securiti, organizations can efficiently locate and manage personal data for Data Subject Requests (DSR), helping streamline privacy request fulfillment and support compliance with data protection regulations.

Intercom falls under the category of [Monitored, Scanless data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Intercom (Securiti-Cloud) | DSR Automation |

### Supported authentication method

Securiti supports OAuth authentication method for Intercom.

### Prerequisites for configuring Intercom connector

#### 1. Developer account in Intercom

You must have a developer account to create an application and acquire authentication credentials.

#### 2. Create custom app in Intercom

Create an application in the Intercom instance to get the authentication credentials. For more information, see [Register an application in Intercom](/latest/docs/register-an-application-in-intercom).

#### 3. Assign redirect URLs

While creating a custom app in the Intercom, add the redirect URLs as per your region from the following:

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

### Connect Intercom connector with Securiti

This section covers the methods to integrate your Intercom with Securiti.

#### Steps to connect the Intercom connector with Securiti

To configure the Intercom (Securiti-Cloud) connector, perform the procedures in the following topics:

1. [Register an application in Intercom](/latest/docs/register-an-application-in-intercom).
2. [Connecting Intercom with Securiti](/latest/docs/connecting-intercom-with-securiti).

**Additional resources**

- [Fulfilling DSR requests for Intercom](/latest/docs/fulfilling-dsr-requests-for-intercom).
