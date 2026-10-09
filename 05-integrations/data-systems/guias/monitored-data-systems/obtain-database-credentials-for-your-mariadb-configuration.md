---
title: "Obtain database credentials for your MariaDB configuration"
slug: "obtain-database-credentials-for-your-mariadb-configuration"
updated: 2026-06-23T06:53:12Z
published: 2026-06-23T06:53:12Z
canonical: "helpcenter.securiti.ai/obtain-database-credentials-for-your-mariadb-configuration"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain database credentials for your MariaDB configuration

1. Open your Database's system client (in the this case, it is that of Microsoft's Visual Studio running on the MacOS operating system).
2. Choose **MariaDB** from the available SQLTools configurations.

![MariaDB_SelectDBType.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-69f2acb3-5f0d-772b-1345-59080a12192c(1).jpg)
3. Navigate to your networking Database settings (in this case, it is called **Connection Assistant**).

![MariaDB_SetupMariaDBConnection.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c3fbc2b-1997-6077-f4df-3a8c038db608(1).jpg)
4. Confirm your Database Connection settings and record the following details to use later:

| Server Host | The server host IP for your Database (for example, *<128.X.X.1>*) |
| --- | --- |
| Port | The network access port address for your Database (for example, <*1583*> |
| Database | The exact name of the Database you wish to link to Securiti (for example, <*DEMODATA*>) |
| Username | The username associated with accessing your Database (for example, <*Master*> |
| Password | The password associated with your Database user account (for example, <*pxsxwxrx*> |
5. Click **Test Connection** and then **Save Connection** after you verify the Database access details.
6. Navigate to the final screen of the Connection Assistant and review your Database Credentials (in JSON format).

![MariaDB_StartMariaDBConnection.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cdbee6af-7753-3971-3060-d139afe5873d(1).jpg)
7. Click **Connect Now**.

The Database is now accessible for linking to external applications such as Securiti.
8. Proceed to [Connecting MariaDB with Securiti](/latest/docs/connecting-mariadb-with-securiti).
