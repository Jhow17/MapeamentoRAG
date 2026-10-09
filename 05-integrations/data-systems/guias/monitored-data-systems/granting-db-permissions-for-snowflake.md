---
title: "Granting DB permissions for Snowflake"
slug: "granting-db-permissions-for-snowflake"
updated: 2026-08-10T11:24:16Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/granting-db-permissions-for-snowflake"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Granting DB permissions for Snowflake

Do the following to grant Snowflake connector Database Permissions.

> [!NOTE]
> **Note**
> 
> - Securiti does not push data through workflows into Snowflake data systems. Therefore, we do not require "write" Permissions for Authentication and Activation of the connector.
> - If you use a firewall or proxy with your Snowflake account, allowlist all URLs and port combinations returned by the command below.
> 
> SELECT SYSTEM$ALLOWLIST()

1. Snowflake requires you to grant **MONITOR** and **USAGE** privileges to schemas or tables for the role assigned to the user. It helps with metadata discovery and scanning of data.

You can verify by running <*show grants to role devrole*> and <*show grants on Database DB1*> queries in the Snowflake portal, replacing "devrole" with that user's role and "DB1" with the Database name you want to scan.

```sql
CREATE ROLE ro_securiti
GRANT SELECT on <<schema>>.<<table>> TO ROLE ro_securiti

GRANT USAGE, MONITOR
  ON DATABASE <<database_a>>
  TO ROLE ro_securiti;

GRANT USAGE, MONITOR
  ON SCHEMA <<database_a>>.<<schema_1>>
  TO ROLE ro_securiti;

GRANT SELECT
  ON ALL TABLES IN SCHEMA <<database_a>>.<<schema_1>>
  TO ROLE ro_securiti;

GRANT USAGE, MONITOR
  ON WAREHOUSE <<warehouse_1>>
  TO ROLE ro_securiti;
```
2. To assign a role to the user:

```sql
GRANT ROLE ro_securiti TO USER securiti
```
3. To set the user role as default:

```pgsql
ALTER USER securiti
   SET default_role = ro_securiti;
```
4. Proceed to [Acquire authentication credentials in Snowflake](/latest/docs/acquire-authentication-credentials-in-snowflake).
