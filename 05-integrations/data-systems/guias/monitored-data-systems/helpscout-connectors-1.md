---
title: "HelpScout"
slug: "helpscout-connectors-1"
status: "new"
updated: 2026-07-16T06:20:49Z
published: 2026-07-16T06:20:52Z
canonical: "helpcenter.securiti.ai/helpscout-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# HelpScout

HelpScout is a cloud-based customer support platform that helps organizations manage customer conversations, shared inboxes, and knowledge bases. By connecting HelpScout with Securiti, organizations can efficiently locate and manage personal data for Data Subject Requests (DSR), helping streamline privacy request fulfillment and support compliance with data protection regulations.

HelpScout falls under the category of [Monitored, Scanless data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| HelpScout (Securiti-Cloud) | DSR Automation |

### Supported authentication method

Securiti supports OAuth authentication method for HelpScout.

### Prerequisites for configuring HelpScout connector

#### 1. Create custom app in HelpScout

Create a custom app in the HelpScout instance to get the authentication credentials.

#### 2. Assign redirect URLs

While creating a custom app in the HelpScout, add the redirect URLs as per your region from the following:

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

### Connect HelpScout connectors with Securiti

This section covers the methods to integrate your HelpScout with Securiti.

#### Steps to connect the HelpScout connector with Securiti

To configure the HelpScout (Securiti-Cloud) connector, perform the procedures in the following topics:

1. [Register an application in HelpScout](/latest/docs/register-an-application-in-helpscout).
2. [Connecting HelpScout with Securiti](/latest/docs/connecting-helpscout-with-securiti).

**Additional resources**

- [Fulfilling DSR requests in HelpScout](/latest/docs/fulfilling-dsr-requests-in-helpscout).
