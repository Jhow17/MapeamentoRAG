---
title: "Salesforce Customer Data Platform"
slug: "salesforce-customer-data-platform-connectors"
status: "new"
updated: 2026-07-31T11:05:29Z
published: 2026-07-31T11:05:42Z
canonical: "helpcenter.securiti.ai/salesforce-customer-data-platform-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Salesforce Customer Data Platform

The Salesforce Customer Data Platform connector in Securiti enables integration with Marketing Cloud to access and manage customer data across its services using both APIs. It allows organizations to discover and govern personal data, while supporting automated Data Subject Requests (DSR) such as access and deletion to help ensure compliance with privacy regulations.

Salesforce Customer Data Platform falls under the [Monitored, structured data systems](/latest/docs/managing-data-system-connectors) category.

### Supported Connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Salesforce Customer Data Platform (Self-hosted) | - DSR Automation using APIs and SQL queries - Discovery Scan |

### Supported authentication methods

For the Salesforce Customer Data Platform connector, OAuth-based authentication is supported

### Prerequisites for configuring the Salesforce Customer Data Platform connector

#### 1. Salesforce Customer Data Platform instance

You must have a Salesforce Customer Data Platform instance running on your Salesforce account.

#### 2. Admin access in Salesforce Customer Data Platform

You must be an administrator to grant permissions to the user in Salesforce Customer Data Platform.

#### 3. Add OAuth scopes in Salesforce Customer Data Platform application

Add the following OAuth scopes to enable OAuth settings in the Salesforce Customer Data Platform application:

- `Access the identity URL service (id, profile, email, address, phone)`
- `Manage Data Cloud Identity Resolution (cdp_identityresolution_api)`
- `Manage user data via APIs (api)`
- `Perform ANSI SQL queries on Data Cloud data (cdp_query_api)`
- `Perform requests at any time (refresh_token, offline_access)`

For more information on the OAuth scopes, see [Grant permissions and obtain authentication credentials in the Salesforce Customer Data Platform](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-the-salesforce-customer-data-platform).

#### 4. Use cases and permissions for Salesforce Customer Data Platform

This section covers use cases and permissions required for the Salesforce Customer Data Platform connector.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | N/A | Assign the following user-level permission to the Salesforce Customer Data Platform user: - `(Legacy) Data Cloud User` | This permission lets Securiti to discover and scan Salesforce Customer Data Platform objects for classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect Salesforce Customer Data Platform with Securiti

To configure the Salesforce Customer Data Platform connector, perform the following procedures in sequence:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. [Grant permissions and obtain authentication credentials in the Salesforce Customer Data Platform](/latest/docs/grant-permissions-and-obtain-authentication-credentials-in-the-salesforce-customer-data-platform).
3. [Connecting Salesforce Customer Data Platform with Securiti](/latest/docs/connecting-salesforce-customer-data-platform-with-securiti).
4. [Configure discovery scans in Salesforce Customer Data Platform](/latest/docs/configure-discovery-scans-in-salesforce-customer-data-platform).

**Additional resources**

- [Fulfilling Salesforce Customer Data Platform DSR requests](/latest/docs/fulfilling-salesforce-customer-data-platform-dsr-requests).
