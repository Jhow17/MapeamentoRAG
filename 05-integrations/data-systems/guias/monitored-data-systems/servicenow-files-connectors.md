---
title: "ServiceNow Files"
slug: "servicenow-files-connectors"
status: "new"
updated: 2026-07-14T07:25:38Z
published: 2026-07-14T07:26:13Z
canonical: "helpcenter.securiti.ai/servicenow-files-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# ServiceNow Files

ServiceNow is a SaaS platform that provides help desk and IT support for large-scale enterprises. The system itself is focused on the isolation of operational IT incidents and resolution of such incidents either through changing the basis of the problem or root cause analysis to prevent such incidents from occurring in the future.

ServiceNow falls under the category of [Monitored, Unstructured data systems](/latest/docs/getting-started-with-data-system-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| ServiceNow Files (Self-hosted) | - Sensitive Data Intelligence (Discovery Scan) - DSR Automation using full scan - Breach Analysis |

### Supported pod types

ServiceNow Files support Securiti standard Pod.

### Supported authentication method

For ServiceNow files, following authentication methods are supported:

- OAuth 2.0
- Basic

### Supported items for Classification scans

Securiti supports following items for classification purposes.

- Databases
- Tables

For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring ServiceNow Files connector

#### 1. ServiceNow instance

You must have access to a running ServiceNow instance. If you do not manage the instance, coordinate with your ServiceNow administrator to obtain the required permissions and authentication details.

#### 2. REST API permissions

If you are using Basic authentication method, you must assign the minimum required REST API permissions to the user account used for connector activation. Ensure the required tables are accessible through web services and have read access.

#### 3. OAuth application (OAuth authentication only)

If you are using OAuth authentication, verify that the OAuth 2.0 plugin is active and configure an OAuth application with the appropriate Redirect URL for your Securiti deployment.

#### 4. Additional configuration for non-admin users (if applicable)

If you are activating the connector with a non-admin account using OAuth authentication, assign the required roles and configure the necessary table exceptions to support OAuth token generation.

#### 2. Use cases and permissions for ServiceNow

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation |  | **For admin user:** - `snc_platform_rest_api_access` - **Can read** enabled on required tables - **Allow access to this Table via web services** enabled on required tables **For non-admin user:** - `admin` - `snc_platform_rest_api_access` - `snc_read_only` Add following properties in ***sys_properties.list*** for non-admin users using OAuth: - `glide.security.snc_read_only_role.tables.exempt_create` - `glide.security.snc_read_only_role.tables.exempt_write` - `glide.security.snc_read_only_role.tables.exempt_delete` | These role lets Securiti read the tables and views in ServiceNow Files for classification purposes. This role also fetch personal data through APIs for DSR Automation. |

### Connect ServiceNow Files with Securiti

To configure the ServiceNow Files connector, perform the procedures in the following topics:

1. If you haven't already done so, install and configure a Securiti pod as described in [Securiti pods](/v1/docs/pods-cluster-version-v128-and-later).
2. Activate your Self-hosted data system's connector on the pod as described in [Securiti pods](/latest/docs/pods-cluster-version-v128-and-later).
3. [Grant permissions and obtain credentials in ServiceNow Files](/latest/docs/grant-permissions-and-obtain-credentials-in-servicenow-files).

If you are using non-admin role, see [Configuration steps for non-admin users in ServiceNow Files](/latest/docs/configuration-steps-for-non-admin-users-in-servicenow-files).
4. [Connecting ServiceNow Files with Securiti](/latest/docs/connecting-servicenow-files-with-securiti).
5. [Configure discovery scans in ServiceNow Files](/latest/docs/configure-discovery-scans-in-servicenow-files).

**Additional resources**

- [Fulfilling ServiceNow Files DSR requests](/latest/docs/fulfilling-servicenow-files-dsr-requests).
