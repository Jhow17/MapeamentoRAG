---
title: "Hubspot"
slug: "hubspot-connectors"
status: "new"
updated: 2026-09-30T10:33:35Z
published: 2026-09-30T10:33:49Z
canonical: "helpcenter.securiti.ai/hubspot-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Hubspot

HubSpot is a cloud-based customer relationship management (CRM) platform that helps organizations manage marketing, sales, customer service, and business operations. By connecting HubSpot with Securiti, organizations can efficiently locate and manage personal data for Data Subject Requests (DSR), helping streamline privacy request fulfillment and support compliance with data protection regulations.

HubSpot falls under the category of [Monitored, Scanless data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Hubspot (Securiti-Cloud) | DSR Automation |

### Supported authentication method

Securiti supports OAuth authentication method for Hubspot.

### Prerequisites for configuring Hubspot connector

#### 1. Developer account in Hubspot

You must have a developer account in the Hubspot to add redirect URLs. If you don’t have a developer account already, see [Register a Hubspot developer account](/latest/docs/register-a-hubspot-developer-account).

#### 2. Add redirect URLs in the Hubspot app

Based on the supported regions, add from the following URLs:

- US Cloud: <[https://app.securiti.ai/static/activateConnector.html](https://app.securiti.ai/static/activateConnector.html)>
- US1 Cloud: <[https://app1.securiti.ai/static/activateConnector.html](https://app1.securiti.ai/static/activateConnector.html)>
- EU Cloud: <[https://app.eu.securiti.ai/static/activateConnector.html](https://app.eu.securiti.ai/static/activateConnector.html)>
- Indonesia Cloud: <[https://app2.securiti.ai/static/activateConnector.html](https://app2.securiti.ai/static/activateConnector.html)>

#### 2. Assign redirect URLs

While creating a custom app in the HubSpot, add the redirect URLs as per your region from the following:

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

#### 3. Use cases and Permissions

Use the table below for permissions and use cases for Hubspot.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| DSR Automation using APIs | N/A | Add the following scopes in the Hubspot app: automation - `business-intelligence` - `content` - `crm.lists.read` - `crm.objects.companies.read` - `crm.objects.contacts.read` - `crm.objects.deals.read` - `crm.objects.owners.read` - `crm.schemas.companies.read` - `crm.schemas.contacts.read` - `crm.schemas.deals.read` - `files` - `forms` - `Integration-sync` - `social` | These permissions let Securiti read the files Hubspot to build the Personal Data Index for DSR Automation. |

### Connect Hubspot connector with Securiti

To configure the Hubspot (Securiti-Cloud) connector, perform the procedures in the following topics:

1. If you don’t have developer account, see [Register a Hubspot developer account](/latest/docs/register-a-hubspot-developer-account).
2. [Register an application in Hubspot](/latest/docs/register-an-application-in-hubspot).
3. [Connecting Hubspot with Securiti](/latest/docs/connecting-hubspot-with-securiti).
4. [Configuring General permissions for Hubspot](/latest/docs/configuring-general-permissions-for-hubspot).

**Additional resources**

- [Fulfilling DSR requests for Hubspot](/latest/docs/fulfilling-dsr-requests-for-hubspot).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
