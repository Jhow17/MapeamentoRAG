---
title: "Configure your local Sybase ASE database for synchronization"
slug: "configure-your-local-sybase-ase-database-for-synchronization"
updated: 2026-08-19T08:10:05Z
published: 2026-08-19T08:10:05Z
canonical: "helpcenter.securiti.ai/configure-your-local-sybase-ase-database-for-synchronization"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure your local Sybase ASE database for synchronization

1. Open your database system client (in this case it is BeaverDB running on the MacOS operating system).
2. Navigate to and select **Sybase jConnect** from the "Select your Database" section of the Connection setup process (BeaverDB shown, other clients may list this setting under a different title).

![Sybase_Setup_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-761fc953-5ea2-4985-1f51-b7a467e55bc4.png)
3. Navigate to your networking database settings as shown below (in this case, it is called SQL Server Connection Settings).![Sybase_Setup2_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b0c1914a-5d93-bb64-5efd-6883861ebc94.png)
4. Confirm your database connection settings and record the following information to use later:

| Server Host | The server host IP for your Database (for example, <*128.X.X.1*>) |
| --- | --- |
| Port | The network access port address for your Database (for example, <*5000*> |
| Database | The exact name of the Database you wish to link to Securiti (for example, <*DEMODATA*>) |
| Username | The username associated with accessing your Database (for example, <*Master*>) |
| Password | The password associated with your Database user account (for example, <*pxsxwxrx*>) |
5. Click **Test Connection** and then **Finish** after you verify the database access details.

The database is now accessible for linking to external applications such as Securiti.
6. Proceed to [Connect Sybase ASE connector with Securiti](/latest/docs/connect-sybase-ase-connector-with-securiti).
