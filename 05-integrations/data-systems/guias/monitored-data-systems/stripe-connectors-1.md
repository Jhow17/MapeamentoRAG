---
title: "Stripe"
slug: "stripe-connectors-1"
status: "new"
updated: 2026-08-11T09:08:55Z
published: 2026-08-11T09:09:00Z
canonical: "helpcenter.securiti.ai/stripe-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Stripe

Stripe is a cloud-based payments platform that provides software-driven solutions for processing online transactions and managing payment systems for both businesses and end-users. Widely adopted across e-commerce, SaaS, and marketplace platforms, it handles the full payments lifecycle, from checkout and invoicing through to subscription billing and revenue reconciliation.

The Stripe connector lets you integrate your Stripe environment with Securiti to discover and govern financial and transactional data stored across your Stripe account.

Stripe (Securiti Cloud) falls under the category of monitored, scanless data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Stripe (Securiti Cloud) | - DSR Automation using APIs - Workflow |

### Supported authentication methods

- For Securiti Cloud connector:
  - Stripe application-based authentication
    - API Key for authentication

### Prerequisites for configuring Stripe connector

#### 1. Admin access

You must have admin access in Stripe to reveal live key token to authenticate your connector.

For more information, see [Obtain the API Key in Stripe](/latest/docs/obtain-the-api-key-in-stripe-en).

#### 2. Use cases and permissions for Stripe

This table covers use cases and permissions required for Stripe (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) | N/A | - Access to reveal **Standard API Keys** in Stripe API Application: - **Secret API Key** | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Stripe (Securiti Cloud) connector with Securiti

To configure the Stripe connector, perform the procedures in the following topics:

1. [Obtain the API key in Stripe](/latest/docs/obtain-the-api-key-in-stripe-en).
2. [Connect Stripe connector with Securiti](/latest/docs/connect-stripe-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for Stripe](/latest/docs/fulfilling-dsr-requests-for-stripe).

An API key is a unique identifier used to connect to, or perform, an API call.
