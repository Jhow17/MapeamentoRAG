---
title: "Magento"
slug: "magento-connectors"
status: "new"
updated: 2026-07-20T17:29:03Z
published: 2026-07-20T21:00:01Z
canonical: "helpcenter.securiti.ai/magento-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Magento

Magento is an open-source e-commerce platform that provides businesses with the tools to build, manage, and scale online stores. It offers a flexible and feature-rich environment for managing product catalogues, orders, customer accounts, and payments.

The Magento connector lets you integrate your Magento environment with Securiti to discover and govern customer and commerce data processed across your online store, including order records, customer profiles, and payment information.

Magento falls under the category of monitored, scanless data systems. For more information, see [data systems classification](/latest/docs/managing-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Magento (Securiti Cloud) | - DSR Automation using APIs |

### Supported authentication methods

- Magento (Securiti Cloud) supports Basic authentication method, using username and password.

### Prerequisites for configuring Magento connector

#### 1. Admin access

You must have admin access in Magento to obtain Token and Domain to authenticate your connector.

For more information, see [Obtain the access token in Magento](/latest/docs/obtain-the-access-token-in-magento).

#### 2. Use cases and permissions for Magento

This table covers use cases and permissions required for Magento (Securiti Cloud) connectors.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| Data Subject Request (DSR) | N/A | - Access to obtain **Access Token** and **Domain URL** from the **available APIs** in Magento Application. | These permissions let Securiti read the files and databases. These permissions also build the Personal Data Index for DSR Automation. |

### Steps to connect Magento (Securiti Cloud) connector with Securiti

To configure the Magento connector, perform the procedures in the following topics:

1. [Obtain the access token in Magento](/latest/docs/obtain-the-access-token-in-magento).
2. [Connect Magento connector with Securiti](/latest/docs/connect-magento-connector-with-securiti).

#### Additional resources

- [Fulfilling DSR requests for Magento](/v1/docs/fulfilling-dsr-requests-for-magento)

A token is a small piece of data, typically in the form of a string, that serves as an authentication or authorization mechanism. It is used to verify the identity of a user or application and grant access to specific resources or functions. Tokens are commonly used for security and access control in API interactions.

Domain is a logical or thematic grouping of related data assets. Domains are used to categorize and organize data assets based on their subject matter or the business context they belong to. For example, you might have a Finance domain that includes data related to financial transactions, reports, and analysis, or a Human Resources domain that encompasses data related to employee information, payroll, and HR processes.
