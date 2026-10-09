---
title: "Acquire authentication credentials in Oracle Autonomous Data Warehouse"
slug: "acquire-authentication-credentials-in-oracle-autonomous-data-warehouse"
updated: 2026-07-13T07:35:00Z
published: 2026-07-13T07:35:00Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-oracle-autonomous-data-warehouse"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Oracle Autonomous Data Warehouse

1. Log in to your Oracle Cloud Account.
2. Oracle Autonomous Data Warehouse uses **User**, **Password** , and Database Name aka **Database Identifier (DSN)** for Connector Activation.

Additionally, the Connector requires a configured wallet so you can access it remotely.
3. Access Activation parameters:
  1. Select **Overview > Autonomous Database > Create Autonomous Database**on the Oracle Cloud homepage, as shown below.

![create_db.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d415f12-9328-879e-7d58-4c5c8a985810.png)
  2. Choose your Username and Password (use them to activate the Connector).

ADMIN is the default username that you can change later.

![username_pwd.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55ed4ea4-50d5-3602-5d1f-2378bda0b43c.png)

Click **Create Autonomous Databse**.
  3. Record the Database Name to use later.

![db_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8b12c69e-7cee-88b9-987a-a6a4c6eeccd8.png)
4. Configure the wallet:
  1. On the Oracle Autonomous Data Warehouse dashboard, click **View Details**, as shown below.

![view_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e1cdc70f-8a50-56dd-5bed-60fd0ba72a55.png)
  2. On the following page, click **DB Connection** and see that the Wallet Type menu has the "Instance Wallet" option selected.

![db_connection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-41a08aea-4b4b-7d23-2beb-105ad0f565cc.png)

![download_wallet.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c069059b-a70b-cb5e-7413-a23b3c0dc464.png)

Click **Download Wallet**.
  3. On the following pop-up, set a password and click **Download** to download a zip file, as shown below.

![set_password.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1590145d-2cd9-40b1-dda4-b564c1a29466.png)

> [!NOTE]
> **Note**
> 
> The password's referred to as <*wallet_password*> for this example.
  4. In the wallet, take note of the files, as shown below:
    - ojdbc.properties
    - sqlnet.ora

![wallet_contents__filenames_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-175f7be8-adbc-f6cf-4c6d-8c76ee00b7e1.png)

> [!NOTE]
> **Note**
> 
> The wallet's referred to as *wallet_dbname.zip* for this example.
  5. Replace contents of the filenames mentioned in the above step with the following:
    - For **ojdbc.properties**:

```plaintext
# Connection property while using Oracle wallets.
#oracle.net.wallet_location=(SOURCE=(METHOD=FILE)(METHOD_DATA=(DIRECTORY=${TNS_ADMIN})))
# FOLLOW THESE STEPS FOR USING JKS
# (1) Uncomment the following properties to use JKS.
# (2) Comment out the oracle.net.wallet_location property above
# (3) Set the correct password for both trustStorePassword and keyStorePassword.
# It’s the password you specified when downloading the wallet from OCI Console or the Service Console.
javax.net.ssl.trustStore=${TNS_ADMIN}/truststore.jks
javax.net.ssl.trustStorePassword=<wallet_password>
javax.net.ssl.keyStore=${TNS_ADMIN}/keystore.jks
javax.net.ssl.keyStorePassword=<wallet_password>
```

> [!NOTE]
> **Note**
> 
> Replace <*wallet_password*> with the password that you created in Step 4.3.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(626).png)
    - For **sqlnet.ora**:

```plaintext
WALLET_LOCATION = (SOURCE = (METHOD = file) (METHOD_DATA = 
(DIRECTORY=“/home/appuser/connectors/custom_drivers/wallet_<datasource_id>_<db_name>“)))
SSL_SERVER_DN_MATCH=yes
```

> [!NOTE]
> **Note**
> 
> Replace <*datasource_id*> and <*db_name*> with your datasource id (available in the datasource URL during Activation), as shown below and Database name (Step 3.3).
  6. Once you've made respective changes to the files as outlined in steps above, copy and paste your wallet (zip file) in the following path:

```plaintext
/mnt/drivers/wallet_<datasource_id>_<db_name>/<wallet_dbname.zip>
```
5. Proceed to [Connecting Oracle Autonomous Data Warehouse with Securiti](/latest/docs/connecting-oracle-autonomous-data-warehouse-with-securiti).
