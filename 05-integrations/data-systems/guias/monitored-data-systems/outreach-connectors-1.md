---
title: "Outreach"
slug: "outreach-connectors-1"
status: "new"
updated: 2026-07-16T07:28:14Z
published: 2026-07-16T07:28:16Z
canonical: "helpcenter.securiti.ai/outreach-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Outreach

Outreach is a sales engagement platform that helps organizations manage customer communications, automate outreach, and streamline sales workflows. By connecting Outreach with Securiti, organizations can efficiently locate and manage personal data for Data Subject Requests (DSR), helping streamline privacy request fulfillment and support compliance with data protection regulations.

Outreach falls under [Monitored, structured data systems](/latest/docs/managing-data-system-connectors).

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Outreach (Securiti-Cloud) | DSR Automation using APIs |

### Supported authentication methods

Securiti supports OAuth authentication method for Outreach connector.

### Prerequisites for configuring Outreach Self-hosted connector

#### 1. Outreach account

You must have access to an Outreach instance to request API access and configure an OAuth application for the connector.

#### 2. Outreach application

You must request API access from Outreach. Once approved, Outreach provides an OAuth application and the authentication credentials required for connector activation.

#### 3. OAuth configuration

Configure the OAuth application with the appropriate Callback URL for your Securiti deployment.

For more information, see [Acquire authentication credentials in Outreach](/latest/docs/acquire-authentication-credentials-in-outreach).

#### 4. Use case and permissions

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - DSR automation using APIs | N/A | Add the following scopes: - `audits.read` - `users.read` - `prospects.read` - `phoneNumbers.read` - `emailAddresses.read` - `accounts.read` - `calls.read` - `recipients.read` - `opportunities.read` - `mailboxes.read` - `mailings.read` - `snippets.read` - `personas.read` - `complianceRequests.all` | These permissions let Securiti read the files in Outreach to build the Personal Data Index for DSR Automation. |

### Connect Outreach with Securiti

To configure the Outreach (Securiti-Cloud) connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Outreach](/latest/docs/acquire-authentication-credentials-in-outreach).
2. [Connecting Outreach with Securiti](/latest/docs/connecting-outreach-with-securiti).
3. [Configuring General permissions for Outreach](/latest/docs/configuring-general-permissions-for-outreach).

#### Additional resources

- [Fulfilling DSR request for Outreach](/latest/docs/fulfilling-dsr-request-for-outreach).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
