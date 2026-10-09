---
title: "Acquire credentials for Basic authentication"
slug: "prerequisites-for-microsoft-azure-sql-database"
updated: 2025-12-19T12:40:42Z
published: 2025-11-19T10:05:15Z
canonical: "helpcenter.securiti.ai/prerequisites-for-microsoft-azure-sql-database"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire credentials for Basic authentication

To connect Microsoft Azure SQL Database with Securiti and perform data scanning, you must do the following.

- Create Azure SQL server and Database
- Set up networking and firewall rules
- Create Service Principal

Follow the procedure below to create SQL sever and service principal for your Microsoft Azure SQL Database.

### Create the SQL Server and SQL Database

1. Log into Azure portal.
2. Type and search **SQL Server** in the search box.
3. Click **Create**.
4. On the **Create SQL Database Server** page, in the **Basic** tab, enter values to suit for **Subscription** and **Server details** fields. Enter your server name.

![azuresql_serverbasictab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba68bbc0-ac62-7301-ed0d-4425ffebe6d1.png)
5. In the **Overview** page, record the following to use later for connector authentication, as shown below.
  - Resource group name
  - Server name
  - Subscription ID
  - Resource name

![Overview of Azure SQL database settings including resource group and subscription details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azuresqldatabase_creds.png)
6. In the **Authentication** section, choose an Authentication method. Select one of the following options. We recommend you choose the **Microsoft Entra-only** Authentication.

![azuresql_createserverauth_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f11edd8d-6198-5877-353f-7def76d51478.png)

> [!NOTE]
> **Note**
> 
> In case of **Use both SQL and Microsoft Entra-only Authentication**, you must add username and password details for your Server. It is also required for Basic Authentication Credentials in Connector Activation.
  - Use Microsoft Entra-only Authentication
  - Use both SQL and Microsoft Entra-only Authentication
7. Click **Review + create** to create a Azure SQL Server.
8. Record the user and password for **Basic** Authentication.

| Credential | Description |
| --- | --- |
| User | User is SQL server admin username which you set while creating a Azure SQL server. You can record it while creating an Azure SQL Server. Otherwise you can follow the below procedure to obtain admin username 1. On the left sidebar under the **Settings**, click **Connection strings**. 2. On the **Connection strings** page under the **JDBC** tab in the **JDBC (SQL Authentication)** section, record the username. From the SQL Authentication information, extract the User ID. If User ID = testusera101, use **testusera101** as User in Connector Activation. ![JDBC_SQL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc88621c-6ccb-c110-d196-a9f7570fc775.png) |
| Password | Password is confidential, you must record it while creating a Azure SQL server above. |

### Registering application in Microsoft Entra ID

You must register your application in Microsoft Entra ID to create a service principal. Follow the matching procedure below to create and register an application in Microsoft Entra ID.

1. Log into [Azure portal](http://portal.azure.com).
2. On Home page, select **Microsoft Entra ID**.
3. Click **Add** to add your Azure application.

![azuresql_addapplication.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16f74427-daf8-ff38-9dfd-c7c7d73eaee6(12).png)
4. Enter the application name and leave other fields as default.
5. Click **Create**

See [Microsoft Entra's official documentation](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant#register-an-application-in-microsoft-entra-id), for more information.

![azuresql_registerapp_menu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f559dc0-0f90-3763-0cca-c9a2fdcf25e8(12).png)

### Set up Microsoft Entra ID for SQL Server Admin

You must add the Microsoft Entra ID as an admin Authentication method for your SQL Server for securing and managing access to your Azure SQL Database.

This step ensures that only users and applications authenticated through Entra ID can access your SQL Server. To add Microsoft Entra ID as an admin Authentication method.

1. In the left menu of Azure portal, under the **Settings** section, click **Microsoft Entra ID**.
2. Under the **Microsoft Entra Admin**, obtain the App ID.
3. Under **Microsoft Entra Authentication only**, mark the checkbox for **Support only Microsoft Entra Authentication for this server**.

![azuresql_databasepermissions_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89e89ac2-5fe8-8e01-efad-23798cd3a99d.png)

### Set up networking and firewall rules

You must allowlist your IP address by adding it to the firewall rules as the SQL server is not public. To add client IP address to firewall rules, follow the step below.

- In the **Networking** tab for your SQL server Instance, under the **Firewall rules**, add IPv4 address that is used by the client to make Connection request.

![azuresql_firewall_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f578037-dc0c-541f-9605-ccc23fcea7ee.png)

### Creating Service Principal for Microsoft Azure SQL Database

An Azure service principal is a security identity used by user-created apps, services, and automation tools to access specific Azure resources. A service principal works as a 'user identity' (login and password or Certificate) with a specific role, and tightly controlled Permissions to access your resources.

1. Create and register your application in Microsoft Entra ID as described in the section above.
2. Once registered, you must create a secret or upload a Certificate based upon the following types of Authentication for your Connector.
  - Service Principal
  - Service Principal with Certificate
3. For Service Principal Authentication:
  1. From the left menu of the **Overview** page, select **Certificates & Secrets**
  2. On the right side of the page, click **Client secrets**.
  3. Click **New client secret** to add a new secret for Authentication.
  4. Enter the secret key name and click **Add**

Record the Azure client (Client ID and Secret) for the Service Principal. The **Client ID** is used as the username and the **Client secret** is used as a password in Connection string while trying to connect to the Azure SQL server

![azuresql_newclientsecret_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c86df8b-cecd-8028-91fb-df5c95589929(12).png)
4. For Service Principal Certificate Authentication:
  1. In case you do not have a Certificate file already, follow the below procedure to create a Certificate.
    1. Run the below openssl command on your console.

```plaintext
openssl req -subj '/CN=myclientcertificate/O=Securiti.ai, Inc./ST=CA/C=US' \ -new -newkey rsa:4096 -sha256 -days 730 -nodes -x509 -keyout client.key -out client.crt
```
    2. Save your .pem, .cer or .crt Certificate file. Upload this Certificate in Azure portal.
    3. Record the password your Certificate is signed with, for later use.
  2. From the left menu of the **Overview** page, select **Certificates and Secrets**
  3. On the right side of the page, click **Certificates**.
  4. Click **Upload Certificate** to add a Certificate in .pem or. crt format.

![azuresql_uploadcert.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2bab358e-3098-a758-b748-408fbacda2f5.png)
  5. To upload the Certificate for your Connector in Securiti, use the .pfx format. Run the command below to convert your Certificate in .pfx format.

Use your password for .pfx Certificate.

```plaintext
openssl pkcs12 -export -password pass:"password" -legacy  -out client.pfx -inkey client.key -in client.crt
```
