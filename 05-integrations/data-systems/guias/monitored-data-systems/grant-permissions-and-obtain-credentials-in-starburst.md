---
title: "Grant permissions and obtain credentials in Starburst"
slug: "grant-permissions-and-obtain-credentials-in-starburst"
updated: 2026-07-15T06:58:42Z
published: 2026-07-15T06:58:42Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-starburst"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Starburst

Starburst data systems require minimum Permissions and Authentication parameters to activate the Connector in Securiti successfully.

Do the following to grant Starburst connector minimum permissions and obtain credentials.

> [!NOTE]
> **Note**
> 
> We assume you have access to a running Starburst Instance, or you have access to the instance's admin to acquire the required information before activating the connector.

1. To provide access to catalogs and tables to specific users using the GRANT command:

```sql
GRANT ( privilege [, ...] | ( ALL PRIVILEGES ) )
ON ( table_name | TABLE table_name | SCHEMA schema_name)
TO ( user | USER user | ROLE role )
[ WITH GRANT OPTION ]
```
2. To successfully execute the GRANT statement, specify privileges to the user, as shown below.

```sql
GRANT SELECT ON <TABLE> TO <USER> WITH GRANT OPTION;
```
3. Record the following for later use:
  - Host
  - Port
  - User
  - Password
  - Catalog
4. Proceed to [Connecting Starburst with Securiti](/latest/docs/connecting-starburst-with-securiti).
