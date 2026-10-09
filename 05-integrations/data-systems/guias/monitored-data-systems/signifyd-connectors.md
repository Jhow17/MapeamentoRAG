---
title: "Signifyd"
slug: "signifyd-connectors"
status: "new"
updated: 2026-08-11T09:03:42Z
published: 2026-08-11T09:03:49Z
canonical: "helpcenter.securiti.ai/signifyd-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Signifyd

Signifyd is an end-to-end Commerce Protection Platform that leverages its Commerce Network to maximize conversion, automate customer experience, and eliminate fraud and consumer abuse risk for retailers. Incoming orders are contextualized with intelligence from its merchant network, evaluated for fraud risk, and accepted or rejected in real time. It covers the full shopper journey from account creation and checkout through to returns and chargeback management.

The Signifyd connector lets you integrate with Securiti to discover and govern order, transaction, and shopper identity data processed across your commerce protection workflows.

Signifyd (Securiti Cloud) falls under the Monitored, scanless data systems category. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Signifyd (Securiti Cloud) | - DSR Automation using APIs |

### Supported authentication methods

- Signifyd (Securiti Cloud) supports Basic authentication method, using username and password.

### Prerequisites for configuring Signifyd connector

#### 1. Admin access

You must have admin access in Signifyd to reveal API key to authenticate your connector.

For more information, see [Acquire authentication credentials in Signifyd](/latest/docs/acquire-authentication-credentials-in-signifyd).

#### 2. Use cases and permissions for Signifyd

This table covers use cases and permissions required for Signifyd (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) | N/A | - Access to reveal **API Keys** in Signifyd Web Application. | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Signifyd (Securiti Cloud) connector with Securiti

To configure the Signifyd connector, perform the procedures in the following topics:

1. [Acquire authentication credentials in Signifyd](/latest/docs/acquire-authentication-credentials-in-signifyd).
2. [Connect Signifyd connector with Securiti](/latest/docs/connect-signifyd-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for Signifyd](/latest/docs/fulfilling-dsr-requests-for-signifyd)

If you are using enhanced DSR processing as described in [Understanding enhanced DSR request processing](https://helpcenter.securiti.ai/docs/understanding-identifiers-for-dsr-request-processing), see [Signifyd data element types for enhanced DSR processing](/latest/docs/signifyd-data-element-types-for-enhanced-dsr-processing) for a list of the data element types supported as identity PD.
