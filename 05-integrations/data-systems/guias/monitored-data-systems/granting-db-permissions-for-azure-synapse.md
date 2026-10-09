---
title: "Granting DB permissions for Azure Synapse"
slug: "granting-db-permissions-for-azure-synapse"
updated: 2025-10-30T19:27:23Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/granting-db-permissions-for-azure-synapse"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Granting DB permissions for Azure Synapse

Do the following to grant Azure Synapse connector database permissions.

1. Create login credentials for users in the master database:

```plaintext
CREATE LOGIN <username> WITH PASSWORD = ‘<password>’;
```
2. Create a new user in the database that you want to use:

```plaintext
CREATE USER <username> FROM LOGIN <username used above to create the login>;
```
3. Enable user to select or read from data from a table or view:

```plaintext
GRANT SELECT ON <table name> TO <username used above to create the user>;
```

> [!NOTE]
> **Note**
> 
> You can apply the SELECT permission to individual columns within a table.
4. To GRANT Read Permissions to all tables in specific SCHEMA:

```plaintext
GRANT SELECT ON SCHEMA::<schema name> TO <username>;
```
5. Proceed to [Acquire authentication credentials in Azure Synapse](/v1/docs/acquire-authentication-credentials-in-azure-synapse).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

## Related

- [Acquire authentication credentials in Azure Synapse](/acquire-authentication-credentials-in-azure-synapse.md)
- [Connecting Azure Synapse with Securiti](/activate-the-azure-synapse-connector-in-securiti.md)
