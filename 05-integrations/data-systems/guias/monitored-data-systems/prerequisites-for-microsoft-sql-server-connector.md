---
title: "Prerequisites for Microsoft SQL Server connector"
slug: "prerequisites-for-microsoft-sql-server-connector"
updated: 2026-06-22T18:34:27Z
published: 2026-06-22T18:34:27Z
canonical: "helpcenter.securiti.ai/prerequisites-for-microsoft-sql-server-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Microsoft SQL Server connector

This topic covers the following prerequisites for connecting Microsoft SQL Server with Securiti.

- [Creating a new user and granting DB permissions for Microsoft SQL Server](/v1/docs/prerequisites-for-microsoft-sql-server-connector)
- [(Optional) Using Kerberos authentication](/v1/docs/prerequisites-for-microsoft-sql-server-connector)

> [!WARNING]
> **Important**
> 
> You must have `sysadmin` role to run security posture scans for Microsoft SQL Server Data system.

Follow the procedures in the sequence below to create a new user and grant DB Permissions for Microsoft SQL Server.

#### Creating a new user and granting DB permissions for Microsoft SQL Server

> [!NOTE]
> Note
> 
> To integrate SQL Server with Securiti and allow Securiti to scan your databases, you must create a SQL Server login and grant the required read-only permissions on the target database.

To create a new user and grant DB Permissions:

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
3. Grant `CONNECT` permission to create a connection with the Database. The command below provides access to connect the database with the `securiti` user.

```plaintext
USE <DatabaseName>
GRANT CONNECT TO securiti;
```
4. Grant `SELECT` permission to scan all objects in the Database. The command below provides access to scanning all objects in the "dbo" Schema.

```plaintext
GRANT SELECT ON SCHEMA::[dbo] TO <UserName>;
-- Example.
-- GRANT SELECT ON SCHEMA::[dbo] TO securiti;.
```
5. Run the following command to provide read-only access to Securiti user.

```plaintext
EXEC sp_addrolemember 'db_datareader', '<UserName>';
-- example.
--EXEC sp_addrolemember 'db_datareader', 'securiti';.
```

#### (Optional) Using Kerberos authentication

To use Kerberos Authentication for your SQL Server Connector, ensure that you have installed Active Directory (AD) on the windows where SQL Server is set up.

Record the following values to use later during the Connector Activation process.

- (Optional) **Kerberos Configuration file**: The Kerberos Configuration file (krb5.conf) is used to define the realms, domain mappings, and server details required for secure Authentication via Kerberos in the SQL Server Connector Activation process in Securiti.
- **Kerberos Realm**: The Kerberos realm corresponds to the Active Directory domain in which the machine is registered. You can record this value from the Kerberos config file under the "[realms]" section.

You can also run the below command on your machine to check domain.

```plaintext
echo %USERDNSDOMAIN%
```

See an example below for realm name.

*SQL.COM*
- **Service Principle Name** : Service Principle Name is the SPN that is registered against the active directory user. To check the SPNs against a specific user you can execute the following command on your machine.

```plaintext
setspn -L EXAMPLE\User  (setspn -L Domain\Username)
```

See an example below for Service Principle Name where the value following the slash is the Fully Qualified Domain Name (FQDN).

*MSSQLSvc/EC2AMAZ-S8AQ7PH.example.com:1433*
- **Kerberos Key Distribution Center (KDC)**: Record the public IP address for your KDC server. See an example below.

*13.60.225.50*
- **Keytab file**: The keytab file stores pairs of Kerberos principals and encrypted keys that are derived from Kerberos password. It can be generated or it is provided by your Kerberos administrator. The keytab file uses **.keytab** file extension.
- **Keytab principal**: The Keytab principal is the identity used for Kerberos Authentication. If the principal is the same as the SQL Server service, use the service principal's SPN. Alternatively, if using AD user principal use the format below.

*user@REALM*

Proceed to [Connecting Microsoft SQL Server with Securiti](/latest/docs/new-ui-connecting-sql-server-self-hosted-with-securiti).
