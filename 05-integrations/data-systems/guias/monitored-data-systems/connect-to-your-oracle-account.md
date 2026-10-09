---
title: "Connect to your Oracle Account"
slug: "connect-to-your-oracle-account"
updated: 2026-07-31T09:03:48Z
published: 2026-07-31T09:03:48Z
canonical: "helpcenter.securiti.ai/connect-to-your-oracle-account"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect to your Oracle Account

> [!WARNING]
> **Important**
> 
> You must have `SYSDBA` role to run security posture scans for Oracle Data system.

1. Open your Database system client (in the this case, it is that of Microsoft's Visual Studio running on the MacOS operating system).
2. Choose **OracleDB** from the available SQLTools configurations.

![ORCLS_SQLSELECT.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6ed99a7b-63bc-9582-b573-3181f07157d4.png)
3. Navigate to your networking Database settings (in this case, it is called **Connection Assistant**).

![ORCLS_CREDENTIALS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eec79756-c82c-a170-fcf7-a03f78e07c55.png)
4. Enter your Oracle Database settings and record these details to use later:

| Server Host | The server host IP for your Database (for example, *<128.X.X.1>*) |
| --- | --- |
| Port | The network access port address for your Database (for example, *<1583>*) |
| Database | The exact name of the Database you wish to link to Securiti (for example, *<ORCL>*) |
| Username | The username associated with accessing your Database (for example, *<MasterUser>*) |
| Password | The password associated with your Database user account (for example, *<pxsxwxrx>*) |
5. Click **Test Connection** and then **Save Connection** after you validate the Database access details.
6. Navigate to the final screen of the Connection Assistant and review your Database Credentials (in JSON format).

![ORCLS_CONNECTNOW.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bdc7727e-2476-b169-f90e-2fb8330171be.png)
7. Click **Connect Now**.

The Database is now accessible for linking to external applications such as Securiti.

![ORCLS_CONNECTED.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ebc63835-9e67-f889-7153-0a918e858ab2.png)
8. Proceed to [Connecting Oracle with Securiti](/latest/docs/connecting-oracle-with-securiti).
