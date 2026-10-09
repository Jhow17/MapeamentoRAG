---
title: "Grant permissions and obtain credentials in Apache HBase"
slug: "grant-permissions-and-obtain-credentials-in-apache-hbase"
updated: 2026-07-03T09:48:19Z
published: 2026-07-03T09:48:19Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-apache-hbase"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Apache HBase

The HBase data systems require minimum permissions and authentication credentials to activate the connector in Securiti.

> [!NOTE]
> **Note**
> 
> We assume you have an Apache HBase instance running on your machine or you have access to the admin (superuser) to configure necessary permissions.

Use **GRANT** syntax to grant HBase minimum DB permissions.

1. To manage user access to HBase database tables:

```plaintext
grant '<user-or-principal-or-group>','<permissions>','<table>
```
2. To create, for example, a policy that grants "user1" read and write permissions on the table "usertable":

```plaintext
grant 'user1','RW','usertable'
```

> [!NOTE]
> **Note**
> 
> You can use the GRANT syntax similarly to grant CREATE and ADMIN rights.
3. Record the following information to use later:
  - Host
  - Port
  - User
  - Password
  - User principal in the case of Kerberos.
4. Proceed to [Connecting Apache HBase with Securiti](/latest/docs/connecting-apache-hbase-with-securiti).

## Related

- [Connecting Apache HBase with Securiti](/activate-the-apache-hbase-connector-in-securiti.md)
