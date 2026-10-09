---
title: "Granting DB permissions for Oracle"
slug: "granting-db-permissions-for-oracle"
updated: 2026-07-31T09:03:06Z
published: 2026-07-31T09:03:06Z
canonical: "helpcenter.securiti.ai/granting-db-permissions-for-oracle"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Granting DB permissions for Oracle

Do the following to grant Oracle Connector Database Permissions.

1. To create session permission for the user:

```plaintext
CREATE USER securiti IDENTIFIED BY "<some-strong-password>";
GRANT CREATE SESSION TO securiti;
```
2. To SELECT privileges on schemes requiring scan:

```plaintext
CREATE PROCEDURE grant_select(
    schema_name VARCHAR2, 
    grantee VARCHAR2)
AS   
BEGIN
    FOR r IN (
        SELECT owner, table_name 
        FROM all_tables 
        WHERE owner = schema_name
    )
    LOOP
        EXECUTE IMMEDIATE 
            'GRANT SELECT ON '||r.owner||'.'||r.table_name||' to ' || grantee;
    END LOOP;
END;
```

Then execute this once per Schema (owner or user):

```plaintext
EXEC grant_select('<<schema_name_all_caps>', 'SECURITI')
```

> [!NOTE]
> **Note**
> 
> Replace **<<schema_name_all_caps>>** with the actual Schema name.
3. To make sure the user has SELECT Permissions on the system view:

```plaintext
SELECT USERNAME FROM SYS.ALL_USERS ORDER BY USERNAME
```

You must assign *SELECT* Permission on *ALL_USERS* due to the following reasons:
  - Oracle JDBC driver checks ALL-USERS view internally when you initialize a Connection with Securiti.
  - *SELECT* permission on *ALL_USERS* helps you in retrieving schemas accessible to the authenticated user.
4. Proceed to [Connect to your Oracle Account](/latest/docs/connect-to-your-oracle-account)
