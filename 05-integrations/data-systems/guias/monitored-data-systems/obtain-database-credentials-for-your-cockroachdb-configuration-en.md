---
title: "Obtain database credentials for your CockroachDB configuration"
slug: "obtain-database-credentials-for-your-cockroachdb-configuration-en"
updated: 2025-12-10T09:08:09Z
published: 2025-12-10T09:08:09Z
canonical: "helpcenter.securiti.ai/obtain-database-credentials-for-your-cockroachdb-configuration-en"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain database credentials for your CockroachDB configuration

1. Log in to your CockroachDB instance.
2. On the top right of your database cluster page, click **Connect** to test the database connection. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/obtain-database-credentials-for-your-cockroachdb-configuration-en-image-kq6mtk1o.png)
3. On the **Connect to <database>** pop-up, record the following credentials.

| **Parameter** | **Description** |
| --- | --- |
| Host | Under the **General connection string**, record the server host for your database from the connection string. If the General connection string is *postgresql://nisar:<ENTER-SQL-USER-PASSWORD>@****demo-cluster-00000.x00.aws-us-east-1.cockroachlabs.cloud****:****26257****/defaultdb?sslmode=verify-full*, the following value is the Host. *demo-cluster-00000.x00.aws-us-east-1.cockroachlabs.cloud* |
| Port | Under the **General connection string**, record the network access port address for your database. See the example below. *26527* |
| Database | The exact name of the database you wish to link to Securiti. See the example below. *defaultdb* |
| Username | Record the username associated with accessing your database and activating the connector. See the example below. *user123* |
| Password | Record the password for the user associated with accessing your database and activating the connector. See the example below. *pxsxwxrx* |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/obtain-database-credentials-for-your-cockroachdb-configuration-en-image-0qnvxit7.png)
4. Proceed to [Activate the CockroachDB connector in Securiti](/v1/docs/activate-the-cockroachdb-connector-in-securiti-en).
