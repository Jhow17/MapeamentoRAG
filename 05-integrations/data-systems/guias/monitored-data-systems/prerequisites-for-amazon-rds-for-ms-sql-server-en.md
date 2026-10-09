---
title: "Prerequisites for Amazon RDS for Sql Server"
slug: "prerequisites-for-amazon-rds-for-ms-sql-server-en"
updated: 2026-07-01T19:44:15Z
published: 2026-07-01T19:44:15Z
canonical: "helpcenter.securiti.ai/prerequisites-for-amazon-rds-for-ms-sql-server-en"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Amazon RDS for Sql Server

> [!NOTE]
> Note
> 
> This procedure assumes that you already have a running Amazon RDS for Sql Server instance, which automatically creates a master user with administrative privileges.
> 
> 
> 
> However, the [Amazon RDS documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html#:~:text=When%20you%20create%20a%20DB%20instance) advises not to use the master user for application-level tasks such as connector integration. For security and compliance, it is recommended to create a separate user with only the minimum required privileges instead.

## Creating a new user and granting DB permissions for Microsoft SQL Server

To integrate SQL Server with Securiti and provide access to scan your databases, you must grant the necessary permissions.

To create a new user and grant DB permissions:

1. Create a SQL Server login with your password, for Securiti to connect and authenticate.

`CREATE LOGIN securiti WITH PASSWORD = '&lt;some-strong-password&gt;;`
2. Create a user within the specific database that you are granting access to. This step links the login you created earlier to a user in your database.

```plaintext
USE <DatabaseName>
CREATE USER securiti FOR LOGIN securiti
```

> [!NOTE]
> Note
> 
> Repeat the step to grant access to multiple databases.
3. Grant **SELECT** permission to scan all objects in the database. The command below provides access to scanning all objects in the "dbo" schema.

```plaintext
USE <DatabaseName> 
Grant select on SCHEMA :: [dbo] to securiti
```
4. Assign **Read-Only** Role.
  - Run the following command to provide read-only access to Securiti user.

`EXEC sp_addrolemember 'db_datareader', '&lt;readonly_user&gt;'`

## Obtain connector activation credentials

In your Amazon RDS environment, record the following to use later:

1. In **Aurora and RDS**, from the left menu, select **Databases**. Record your database name.
2. In the **Connectivity & security** tab, record the values for **Endpoint** and **Port**, as shown below. The endpoint is your host value and port number for SQL Server is 1433.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/prerequisites-for-amazon-rds-for-ms-sql-server-en-image-jwazbljj.png)
3. In the **Configuration** tab, under the **Availability** section, record your username, as shown below.

> [!NOTE]
> Note
> 
> It is not necessary to have an admin user for your Amazon RDS instance.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/prerequisites-for-amazon-rds-for-ms-sql-server-en-image-q6cy65kc.png)
4. From the left menu, select **Parameter groups** and in the **Parameters** section, search for SSL. Verify the SSL value from the **Value** field. SSL is off if the value is 0 and on if the value is set to 1, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/prerequisites-for-amazon-rds-for-ms-sql-server-en-image-vpfi23bf.png)
5. Proceed to [Connecting Amazon RDS for Sql Server with Securiti](/latest/docs/connecting-amazon-rds-for-ms-sql-server-with-sercuiti).
