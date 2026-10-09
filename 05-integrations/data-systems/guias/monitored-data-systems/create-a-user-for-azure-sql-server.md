---
title: "Create a user and grant DB permissions"
slug: "create-a-user-for-azure-sql-server"
updated: 2026-06-22T14:49:43Z
published: 2026-06-22T14:49:43Z
canonical: "helpcenter.securiti.ai/create-a-user-for-azure-sql-server"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a user and grant DB permissions

> [!NOTE]
> Note
> 
> To integrate Azure SQL Server with Securiti and allow Securiti to scan your databases, you must create a SQL Server login and grant the required read-only permissions on the target database.

1. Create a Server Login on the master database to create a new user.

```plaintext
-- Connect to the 'master' database
CREATE LOGIN <LoginName> WITH PASSWORD = '<some-strong- password>';
-- example.
-- CREATE LOGIN securiti WITH PASSWORD = 'StrongPassword@123';.
```
2. Create a user within the specific Database that you are granting access to. This step links the login you created earlier to a user in your Database.

> [!NOTE]
> Note
> 
> You must be in master database while creating a user otherwise you get an error.

```plaintext
USE <DatabaseName>;
CREATE USER <UserName> FOR LOGIN <LoginName>;
-- Example
-- USE CustomerDB;.
-- CREATE USER securiti FOR LOGIN securiti;.
```
3. Grant SELECT permission to scan all objects in the Database. The command below provides access to scanning all objects in the "dbo" Schema.

```plaintext
GRANT SELECT ON SCHEMA::[dbo] TO <UserName>;
-- Example.
-- GRANT SELECT ON SCHEMA::[dbo] TO securiti;.
```
4. Run the following command to provide read-only access to Securiti user.

```plaintext
EXEC sp_addrolemember 'db_datareader', '<UserName>';
-- example.
--EXEC sp_addrolemember 'db_datareader', 'securiti';.
```
5. Proceed to [Acquire authentication credentials for Microsoft Azure SQL Database](/v1/docs/prerequisites-for-microsoft-azure-sql-database).
