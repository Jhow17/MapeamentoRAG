---
title: "Using Database secrets engine for dynamic credentials"
slug: "using-database-secrets-engine-for-dynamic-credentials"
updated: 2026-01-23T16:20:15Z
published: 2026-01-23T16:20:15Z
canonical: "helpcenter.securiti.ai/using-database-secrets-engine-for-dynamic-credentials"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Using Database secrets engine for dynamic credentials

> [!WARNING]
> **Important**
> 
> Database secrets engine for dynamic credentials is supported for SQL connectors only.

HashiCorp's Database secrets engine enables dynamic generation of database credentials, providing security for your credentials. With this setup, instead of static usernames and passwords, the system dynamically generates credentials for each session based on configured roles, providing more secure and traceable access to databases. Each service accesses the database with unique credentials, simplifying auditing and tracking specific access instances. HashiCorp vault's internal revocation system ensures credentials are invalidated promptly after expiration. See [HashiCorp's documentation on databases](https://developer.hashicorp.com/vault/docs/secrets/databases), for more information.

Database secrets engine for dynamic credentials is supported for the following SQL connectors in Securiti.

- [Amazon RDS for MySQL](/latest/docs/amazon-rds-for-mysql-connectors)
- [MySQL](/latest/docs/mysql-connectors)
- [PostgreSQL](/latest/docs/postgresql-connectors-1)
- [SQL Server](/latest/docs/microsoft-sql-server-connectors)

To use the Database secrets engine for your credentials.

1. In your vault CLI, run the following command to enable the database engine.

```bash
vault secrets enable database
```
2. Run the following commands to add connections to the databases for which roles are required. To do so, run the commands below depending on your database type.

Replace `{{HOST}}`, `{{PORT}}`, `{{USERNAME}}`, and `{{PASSWORD}}` with the actual database details. Connection is successful if all the provided values are correct and the vault has access to the configured database.

> [!WARNING]
> **Important**
> 
> We recommend you create connection strings according to your parameters for a successful connection. See [connection strings reference](/v1/docs/securiti-pods-and-elastic-pods), for more information.
  - **Amazon RDS for MySQL**:

```bash
vault write database/config/mysql-db \
  plugin_name=mysql-database-plugin \
  allowed_roles="mysql-role" \
  connection_url="{{username}}:{{password}}@tcp({{HOST}}:{{PORT}})/" \
  username="{{USERNAME}}" \
  password="{{PASSWORD}}"
```
  - **MySQL**:

```bash
vault write database/config/mysql-db \
  plugin_name=mysql-database-plugin \
  allowed_roles="mysql-role" \
  connection_url="{{username}}:{{password}}@tcp({{HOST}}:{{PORT}})/" \
  username="{{USERNAME}}" \
  password="{{PASSWORD}}"
```
  - **PostgreSQL**:

```bash
vault write database/config/postgres-db \
  plugin_name=postgresql-database-plugin \
  allowed_roles="postgres-role" \
  connection_url="postgresql://{{username}}:{{password}}@{{HOST}}:{{PORT}}/" \
  username="{{USERNAME}}" \
  password="{{PASSWORD}}"
```
  - **SQL Server**:

```bash
vault write database/config/mssql-db \
  plugin_name=mssql-database-plugin \
  allowed_roles="mssql-role" \
  connection_url="sqlserver://{{username}}:{{password}}@{{HOST}}:{{PORT}}/" \
  username="{{USERNAME}}" \
  password="{{PASSWORD}}"
```
3. Create roles for "allowed_role" field, for the vault to generate temporary database credentials using the command below. Roles are used to create new users in a connected database for dynamic credentials.

In the commands above, "creation_statements" are executed to create credentials each time you request them from the vault. "default_ttl" sets the time period (TTL) for which the vault grants a lease for credentials. "max_ttl" limits how long you can request credentials, ensuring access is not extended indefinitely.
  - **Amazon RDS for MySQL**:

```bash
vault write database/roles/mysql-role \
  db_name=mysql-db \
  default_ttl="1h" \
  max_ttl="2h" \
  creation_statements="CREATE USER '{{name}}'@'%' IDENTIFIED BY '{{password}}';GRANT SELECT ON *.* TO '{{name}}'@'%';"
```
  - **MySQL**:

```bash
vault write database/roles/mysql-role \
  db_name=mysql-db \
  default_ttl="1h" \
  max_ttl="2h" \
  creation_statements="CREATE USER '{{name}}'@'%' IDENTIFIED BY '{{password}}';GRANT SELECT ON *.* TO '{{name}}'@'%';"
```
  - **PostgreSQL**:

```bash
vault write database/roles/postgres-role \
  db_name=postgres-db \
  default_ttl="1h" \
  max_ttl="2h" \
  creation_statements="CREATE ROLE \"{{name}}\" WITH LOGIN PASSWORD '{{password}}' VALID UNTIL '{{expiration}}';\        
   GRANT pg_read_all_data TO \"{{name}}\";"
```
  - **SQL Server**:

```bash
vault write database/roles/mssql-role \
    db_name=mssql-db \
    creation_statements="CREATE LOGIN [{{name}}] WITH PASSWORD = '{{password}}';\
        CREATE USER [{{name}}] FOR LOGIN [{{name}}];\
        GRANT SELECT ON SCHEMA::dbo TO [{{name}}];" \
    default_ttl="1h" \
    max_ttl="24h"
```

Replace DB_NAME with the database name for which the newly created user needs access.
4. Once the roles are configured, use the following command to dynamically generate a new set of credentials for accessing the database:

```bash
vault read database/creds/<role-name>
```

Replace <role-name> with the specific role created for each database type (e.g., postgres-role for PostgreSQL, mysql-role for Amazon RDS for MySQL and MySQL, and mssql-role for SQL Server). This command provides the temporary username and password for the specified database.
