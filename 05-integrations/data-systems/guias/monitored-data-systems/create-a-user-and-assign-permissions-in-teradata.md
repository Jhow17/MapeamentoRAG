---
title: "Create a user and assign permissions in Teradata"
slug: "create-a-user-and-assign-permissions-in-teradata"
updated: 2026-06-28T11:02:01Z
published: 2026-06-28T11:02:01Z
canonical: "helpcenter.securiti.ai/create-a-user-and-assign-permissions-in-teradata"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a user and assign permissions in Teradata

> [!NOTE]
> **Note**
> 
> This procedure assumes you have an existing Teradata Database Instance running and have a create user rights to assign Permissions.

To create a new user in the Teradata Database and assign Permissions, perform the following steps:

1. Log in to your Teradata Database.
2. On the terminal, run the following commands to create a user.

```sql
CREATE USER securiti AS PERM=10e+09, PASSWORD=<some-strong-password>;
```
  - You can use the convenient username and strong password in the command. In above example, *testuser* is the username and *some-strong-password* is the password.
  - Save the **username** and **password** to use later for Connector Activation.
3. Assign **read** permission to the Teradata user by running the **GRANT** command.

```sql
GRANT SELECT ON <target-db> TO securiti;
```

> [!NOTE]
> **Note**
> 
> You can run the **GRANT** command once per Database you want to scan.
4. Proceed to [Connecting Teradata with Securiti](/latest/docs/connecting-teradata-with-securiti).
