---
title: "Grant permissions and obtain credentials in Apache Presto"
slug: "grant-permissions-and-obtain-credentials-in-apache-presto"
updated: 2026-07-03T10:11:56Z
published: 2026-07-03T10:11:56Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-apache-presto"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Apache Presto

Apache Presto does not manage users or storage. It relies on the underlying data source or connectors for these functions. When configuring Presto with connectors, user credentials must have at least **SELECT** (Read) permissions for the database to execute queries.

Follow the steps below to provide permissions and obtain credentials for the connector.

1. Download the required JDBC driver for Apache Presto.
2. Grant **SELECT** permission for the database to query data from. For example to connect MySQL with Presto you must have this configuration file: `etc/catalog/mysql.properties` and ensure that the user `root` has **SELECT** permission on the database.

```plaintext
connector.name=mysql
connection-url=jdbc:mysql://host.docker.internal:3306
connection-user=root
connection-password=root
```

For more information, see [Presto documentation for supported connectors](/v1/docs/prerequisites-for-amazon-documentdb-connector).
3. Record the following information to use later:

| Parameter | Description |
| --- | --- |
| Host | Record the hosting address for your Apache Presto server. For example, `192.168.1.100`. |
| Port | Enter the port on which database service is available. For example, 3306 for MySQL. |
| User | Record the username required to authenticate the connection to the database. For example, "root". |
| Password | Record the password associated with the username for authentication. |
4. Proceed to [Connecting Apache Presto with Securiti](/latest/docs/activate-the-apache-presto-connector-in-securiti).

## Related

- [Connecting Apache Presto with Securiti](/activate-the-apache-presto-connector-in-securiti.md)
