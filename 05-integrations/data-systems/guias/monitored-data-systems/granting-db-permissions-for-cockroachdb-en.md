---
title: "Granting DB permissions for CockroachDB"
slug: "granting-db-permissions-for-cockroachdb-en"
updated: 2025-12-10T09:06:26Z
published: 2025-12-10T09:06:26Z
canonical: "helpcenter.securiti.ai/granting-db-permissions-for-cockroachdb-en"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Granting DB permissions for CockroachDB

> [!NOTE]
> Note
> 
> - You must have a running CockroachDB instance with the privileges to create a user role and assign permissions.
> - You must provide connect permissions on all databases that require scanning.

Do the following to grant PostgreSQL connector database permissions.

1. For usage permission, enable:
  - pg_catalog
  - information_scheme
  - crdb_internal
  - all schemes on all databases that require scanning
2. Create a new user role by using the following command:

```plaintext
CREATE ROLE securiti WITH LOGIN PASSWORD '<some-strong-password>'
```
3. Grant `CONNECT` permission on each database by using the following command.on tables in each schema of every database:

```plaintext
GRANT CONNECT ON DATABASE <<database>> TO securiti;
-- use <<database>> to connect to database
```
4. Grant schema `USAGE` permission inside each database by using the following command.

```plaintext

```
5. Grant `SELECT` on all tables in the schema by using the following command.

```plaintext
GRANT SELECT ON ALL TABLES IN SCHEMA public TO securiti;
```
6. Proceed to [Obtain database credentials for CockroachDB configuration](/v1/docs/obtain-database-credentials-for-your-cockroachdb-configuration-en).
