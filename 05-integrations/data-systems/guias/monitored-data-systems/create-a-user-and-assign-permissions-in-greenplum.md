---
title: "Create a user and assign permissions in Greenplum"
slug: "create-a-user-and-assign-permissions-in-greenplum"
updated: 2026-07-07T11:07:59Z
published: 2026-07-07T11:07:59Z
canonical: "helpcenter.securiti.ai/create-a-user-and-assign-permissions-in-greenplum"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a user and assign permissions in Greenplum

> [!NOTE]
> **Note**
> 
> This procedure assumes you have an existing Greenplum database Instance running in your environment and have create user rights to assign permissions.

To create a new user in the Greenplum database and assign Permissions:

1. Log in to your Greenplum database.
2. On the terminal, run the following commands to create a user.

```plaintext
CREATE USER user_securiti
ALTER USER user_securiti WITH ENCRYPTED PASSWORD 'somestrongpassword';
USE <dbname>
```
  - You can use a convenient username and a strong password in the command. In the above example, *user_securiti* is the username and *some-strong-password* is the password.
  - Add the Database name you want to include in the scanning by replacing <dbname>.
  - Save the **username**, **password**, and **Database name** to use later for connector activation.
3. Assign **read** permission to the Greenplum user and Database tables by running the **GRANT** command.

```plaintext
GRANT SELECT ON <schema>.<table_name> to user_securiti;
```

> [!NOTE]
> **Tip**
> 
> You can use this command to generate scripts for all tables in the Schema. See the example below:
> 
> ```plaintext
> select 'grant select on '||schemaname||'.'||tablename||' 
> to user_securiti;'                     
> from pg_tables where schemaname in ('public')
> order by schemaname, tablename;
> ```
> 
> Replace the Schema and user name as required.
4. Proceed to [Connecting Greenplum (Self-hosted) with Securiti](/latest/docs/connecting-greenplum-self-hosted-with-securiti), or [Connecting Greenplum (Securiti-Cloud) with Securiti](/latest/docs/connecting-greenplum-securiti-cloud-with-securiti).
