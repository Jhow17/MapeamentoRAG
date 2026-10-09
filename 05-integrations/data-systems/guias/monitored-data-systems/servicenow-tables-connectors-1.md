---
title: "ServiceNow Tables"
slug: "servicenow-tables-connectors-1"
status: "new"
updated: 2026-09-21T10:14:52Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/servicenow-tables-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# ServiceNow Tables

ServiceNow Tables provide structured storage for enterprise data such as incidents, requests, users, and configuration items within the ServiceNow platform. By connecting ServiceNow Tables with Securiti, organizations can discover and classify sensitive data through Sensitive Data Intelligence (SDI) and efficiently locate personal data for Data Subject Requests (DSR), helping strengthen data governance and privacy compliance.

ServiceNow falls under the category of [Monitored, Structured data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| ServiceNow Tables (Self-hosted) | - Sensitive Data Intelligence (Discovery Scan) - DSR Automation using SQL queries |

### Supported pod types

ServiceNow Tables support following pod types:

- Securiti standard Pod.
- ePods

### Supported authentication method

For ServiceNow Tables, following authentication methods are supported:

- Basic
- OAuth 2.0
- OAuth JWT

### Supported items for Classification scans

Securiti supports following items for classification purposes.

- Databases
- Tables

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring ServiceNow Tables connector

#### 1. ServiceNow instance

You must have access to a running ServiceNow instance. If you do not manage the instance, coordinate with your ServiceNow administrator to obtain the required permissions and authentication details.

#### 2. REST API permissions

If you are using Basic authentication method, you must assign the minimum required REST API permissions to the user account used for connector activation. Ensure the required tables are accessible through web services and have read access.

#### 3. OAuth application (OAuth authentication only)

If you are using OAuth authentication, verify that the OAuth 2.0 plugin is active and configure an OAuth application with the appropriate Redirect URL for your Securiti deployment.

#### 4. OAuth application (OAuth JWT authentication only)

If you are using OAuth JWT authentication, configure an OAuth JWT application using the private key certificate.

For more information, see [Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables](/latest/docs/obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow).

#### 5. Additional configuration for non-admin users (if applicable)

If you are activating the connector with a non-admin account using OAuth authentication, assign the required roles and configure the necessary table exceptions to support OAuth token generation.

#### 6. Use cases and permissions for ServiceNow

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation |  | **For admin user:** - `snc_platform_rest_api_access` - **Can read** enabled on required tables - **Allow access to this Table via web services** enabled on required tables **For non-admin user:** - `admin` - `snc_platform_rest_api_access` - `snc_read_only` Add following properties in ***sys_properties.list*** for non-admin users using OAuth: - `glide.security.snc_read_only_role.tables.exempt_create` - `glide.security.snc_read_only_role.tables.exempt_write` - `glide.security.snc_read_only_role.tables.exempt_delete` **For JWT OAuth user:** - `itil` - `snc_platform_rest_api_access` Select the **useraccount** in the OAuth scope during application registration. | These role lets Securiti read the tables and views in ServiceNow Files for classification purposes. This role also fetch personal data through APIs for DSR Automation. |

### Connect ServiceNow Tables with Securiti

To configure the ServiceNow Tables connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).
3. If you are using non-admin role, see [Configuration steps for non-admin users in ServiceNow Tables](/latest/docs/configuration-steps-for-non-admin-users-in-servicenow-tables).
4. [Grant permissions and obtain credentials in ServiceNow Tables](/latest/docs/grant-permissions-and-obtain-credentials-in-servicenow-tables) or [Obtain authentication credentials using OAuth JWT authentication in ServiceNow Tables](/latest/docs/obtain-authentication-credentials-using-oauth-jwt-authentication-servicenow).
5. [Connecting ServiceNow Tables with Securiti](/latest/docs/connecting-servicenow-tables-with-securiti).
6. [Configuring discovery scans in ServiceNow Tables](/latest/docs/configuring-discovery-scans-in-servicenow-tables).

**Additional resources**

- [Fulfilling DSR requests in ServiceNow Tables](/latest/docs/fulfilling-dsr-requests-in-servicenow-tables).
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
