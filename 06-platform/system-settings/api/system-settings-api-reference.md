---
title: "System Settings API reference"
slug: "system-settings-api-reference"
description: "System Settings APIs for managing users, roles, permissions, organizations, MFA, API keys, sessions, password policies, tenant settings, and tags in Securiti."
updated: 2026-08-31T12:50:28Z
published: 2026-08-31T12:50:28Z
canonical: "helpcenter.securiti.ai/system-settings-api-reference"
area: platform
modulo: system-settings
tipo: api
data_captura: 2026-10-08
---

# System Settings API reference

The System Settings API reference provides programmatic access to the system-level configurations of your Securiti tenant. Using these REST APIs, you can automate and manage several actions without performing these actions manually through the Securiti platform.

See the table below for the major categories that the API supports:

| Category | Description |
| --- | --- |
| OAuth | Covers the authentication flow for generating access tokens used in OAuth 2.0 based API authentication for the System Settings APIs. |
| Users | Covers the complete lifecycle management of user accounts, including creating, fetching, updating, and deleting users, exporting users, querying roles with filters, and managing user preferences and saved filters. |
| Roles and Permissions | Covers the management of roles and permissions, including fetching, creating, updating, and deleting roles, and generating and managing API keys for Simple and OAuth 2.0 authentication. |
| Organizations | Covers the management of organizations and organization units, including adding, editing, and importing organizations. |
| MFA | Covers multi-factor authentication management, including enabling, disabling, verifying, and managing MFA settings for users. |
| Sessions and Password | Covers session and password policy management, including fetching active user sessions and configuring password settings and message digest preferences. |
| General Settings | Covers tenant-level configurations, including updating general tenant settings, fetching supported languages, and managing tag categories and tag values. |

The System Settings API is a REST API that accepts and returns data in JSON format. It supports two authentication methods: Simple API Key authentication using `X-API-KEY`, `X-API-SECRET`, and `X-TIDENT` headers, and OAuth 2.0 authentication using an access token. The API is available across all the supported regions, and also supports custom server URLs for on-premises deployments. A Postman collection is available for local testing and integration.

Use the System Settings [REST API documentation](https://securiti-doc-router.securiti.ai/modules/system-settings/apidocs/index.html) to explore and test System Settings APIs, and review HTTP endpoints, JSON request and response formats, query parameters, API schemas, authentication methods, and sample API requests.
