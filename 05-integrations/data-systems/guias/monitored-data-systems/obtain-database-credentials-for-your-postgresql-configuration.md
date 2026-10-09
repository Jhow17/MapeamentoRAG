---
title: "Obtain database credentials for your PostgreSQL configuration"
slug: "obtain-database-credentials-for-your-postgresql-configuration"
updated: 2026-05-29T05:36:03Z
published: 2026-05-29T05:36:03Z
canonical: "helpcenter.securiti.ai/obtain-database-credentials-for-your-postgresql-configuration"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain database credentials for your PostgreSQL configuration

1. Open your Database system client (in the this case, Microsoft's Visual Studio running on MacOS).

![PostgreSQL_CreateConnect.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ecc769cb-a597-57b5-8d84-ed90ca932047(2).png)
2. Choose PostgreSQL from the available SQLTools configurations.

![PostgreSQL_CreatePGSQL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1f775aa-b3ac-7265-24b4-2e8f518d9106(2).png)
3. Navigate to your networking Database settings (in this case, it is called Connection Assistant).
4. Confirm your Database Connection settings and record the following details to use later:

| Server Host | The server host IP for your Database (for example, <*128.X.X.1*>) |
| --- | --- |
| Port | The network access port address for your Database (for example, <*1583*>) |
| Database | The exact name of the Database you wish to link to Securiti (for example, <*DEMODATA*>) |
| Username | The username associated with accessing your Database (for example, <*Master*> |
| Password | The password associated with your Database user account (for example, <*pxsxwxrx*> |

![PostgreSQL_ConfigurePGSQL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-616ac4c9-9e99-7167-df96-8b90ec41a2a5(2).png)
5. Click **Test Connection** and then **Save Connection** after you verify the Database access details.
6. Navigate to the final screen of the Connection Assistant and review your Database Credentials (shown in .json format).

![PostgreSQL_ConnectPGSQL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e9d425e-4204-66fb-547b-aacf618f149d(2).png)
7. Click **Connect Now**.

The Database is now accessible for linking to external applications such as Securiti.
8. Proceed to [Activate the PostgreSQL connector in Securiti](/latest/docs/activate-the-postgresql-connector-in-securiti), [(New UI) Connecting PostgreSQL (self-hosted) with Securiti](/latest/docs/new-ui-connecting-postgresql-self-hosted-with-securiti), or [(New UI) Connecting PostgreSQL Cloud (Securiti Cloud) with Securiti](/latest/docs/new-ui-connecting-postgresql-cloud-securiti-cloud-with-securiti).
