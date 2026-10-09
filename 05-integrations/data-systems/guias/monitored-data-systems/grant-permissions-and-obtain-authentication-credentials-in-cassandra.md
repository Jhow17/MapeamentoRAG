---
title: "Grant permissions and obtain authentication credentials in Cassandra"
slug: "grant-permissions-and-obtain-authentication-credentials-in-cassandra"
updated: 2026-07-06T02:30:48Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-authentication-credentials-in-cassandra"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain authentication credentials in Cassandra

Cassandra data systems use minimum permissions and activation parameters to activate the connector in Securiti.

> [!NOTE]
> **Important**
> 
> We assume you have a Cassandra instance running. Or that you have access to its admin to obtain required permissions and activation parameters.

## Granting permissions

Use the matching procedure below:

1. To create a role:

```plaintext
CREATE ROLE securiti 
WITH PASSWORD = '<some-strong-password>' 
AND LOGIN = true;
```
2. To grant SELECT permissions on all keyspaces you want to scan:

```plaintext
GRANT SELECT ON KEYSPACE <<keyspace_name>> TO securiti
```
3. To grant SELECT permission for each Table:

```plaintext
GRANT SELECT ON TABLE <<keyspace_name>>.<<table_name>> TO securiti
```
4. Record these parameters for later use.
  - Host
  - Port
  - User
  - Password
  - Database
5. Proceed to [Connecting Cassandra with](/latest/docs/connect-cassandra-with-securiti) Securiti.
