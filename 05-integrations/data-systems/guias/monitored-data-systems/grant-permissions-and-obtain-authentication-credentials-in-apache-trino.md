---
title: "Grant permissions and obtain authentication credentials in Apache Trino"
slug: "grant-permissions-and-obtain-authentication-credentials-in-apache-trino"
updated: 2026-07-03T10:42:33Z
published: 2026-07-03T10:42:33Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-authentication-credentials-in-apache-trino"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain authentication credentials in Apache Trino

Apache Trino data systems require minimum permissions and authentication parameters to activate the connector in Securiti successfully.

Do the following to grant Trino connector minimum permissions and obtain credentials.

> [!NOTE]
> **Note**
> 
> We assume you have access to a running Apache Trino instance, or you have access to the instance's admin to acquire the required information before activating the connector.

1. To provide access to catalogs and tables to specific users using the GRANT command:

```plaintext
GRANT ( privilege [, ...] | ( ALL PRIVILEGES ) )
ON ( table_name | TABLE table_name | SCHEMA schema_name)
TO ( user | USER user | ROLE role )
[ WITH GRANT OPTION ]
```
2. To successfully execute the GRANT statement, specify privileges to the user, as shown below.

```plaintext
GRANT SELECT ON <TABLE> TO <USER> WITH GRANT OPTION;
```
3. Record the following for later use:
  - Host
  - Port
  - User
  - Password
  - Catalog
4. Proceed to [Connecting Apache Trino connector with Securiti](/latest/docs/activate-the-apache-trino-connector-in-securiti).

## Related

- [Connecting Apache Trino with Securiti](/activate-the-apache-trino-connector-in-securiti.md)
