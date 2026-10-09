---
title: "Obtain permissions and authentication credentials in IBM Netezza"
slug: "obtain-permissions-and-authentication-credentials-in-ibm-netezza"
updated: 2026-07-09T06:40:51Z
published: 2026-07-09T06:40:51Z
canonical: "helpcenter.securiti.ai/obtain-permissions-and-authentication-credentials-in-ibm-netezza"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permissions and authentication credentials in IBM Netezza

IBM Netezza data systems use minimum permissions and activation parameters to activate the connector in Securiti.

> [!NOTE]
> **Important**
> 
> We assume you have an IBM Netezza instance running. Or that you have access to its admin to obtain required permissions and activation parameters.

Use the matching procedure below.

1. ```plaintext
CREATE USER <username> WITH PASSWORD <some strong password>
```

For more information, see [Creating database users](https://www.ibm.com/docs/en/netezza?topic=npsdugr-creating-database-users-1).
2. To grant Select privileges on a database:

```plaintext
GRANT SELECT ON <DatabaseName>.<ALL|SchemaName>.<TABLE|TableName> TO user1;
```

"ALL" in the permission shows access to all schemas in a database. Or you can specify a single Schema to access only that Schema instead of ALL.

"Table" means all the Tables within a Database. Or you can grant access to a Table by replacing the Table name with the placeholder Table.
3. Record these parameters for later.
  - Host
  - Port
  - User
  - Password
  - Database
4. Proceed to [Connecting IBM Netezza with Securiti](/latest/docs/connecting-ibm-netezza-with-securiti).
