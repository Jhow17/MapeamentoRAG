---
title: "Acquire credentials for Service Principal authentication"
slug: "obtain-credentials-for-service-principal-authentication"
updated: 2026-06-22T14:49:48Z
published: 2026-06-22T14:49:48Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-service-principal-authentication"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire credentials for Service Principal authentication

## Register the application in Microsoft Entra ID

You must register your application in Microsoft Entra ID to create a service principal. Follow the matching procedure below to create and register an application in Microsoft Entra ID.

1. Log in to [Azure portal](http://portal.azure.com).
2. On the Home page, select **Microsoft Entra ID**.
3. Click **Add** to add your Azure application.

![azuresql_addapplication.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16f74427-daf8-ff38-9dfd-c7c7d73eaee6(12).png)
4. Enter the application name and leave the other fields as default.
5. Click **Create**

See [Microsoft Entra's official documentation](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant#register-an-application-in-microsoft-entra-id), for more information. ![azuresql_registerapp_menu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3f559dc0-0f90-3763-0cca-c9a2fdcf25e8(12).png)

## Set up Microsoft Entra ID for SQL Server admin

You must add the Microsoft Entra ID as an admin Authentication method for your SQL Server to secure and manage access to your Azure SQL Database.

This step ensures that only users and applications authenticated through Entra ID can access your SQL Server. To add Microsoft Entra ID as an admin Authentication method.

1. In the left menu of the Azure portal, under the **Settings** section, click **Microsoft Entra ID**.
2. Under the **Microsoft Entra Admin**, obtain the App ID.
3. Under **Microsoft Entra Authentication only**, mark the checkbox for **Support only Microsoft Entra Authentication for this server**. ![azuresql_databasepermissions_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89e89ac2-5fe8-8e01-efad-23798cd3a99d.png)

## Set up networking and firewall rules

You must allowlist your IP address by adding it to the firewall rules, as the SQL server is not public. To add the client IP address to firewall rules, follow the steps below.

- In the **Networking** tab for your SQL server Instance, under the **Firewall rules**, add the IPv4 address that is used by the client to make Connection request. ![azuresql_firewall_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7f578037-dc0c-541f-9605-ccc23fcea7ee.png)

## Create a Service Principal for Microsoft Azure SQL Database

An Azure service principal is a security identity used by user-created apps, services, and automation tools to access specific Azure resources. A service principal works as a 'user identity' (login and password or Certificate) with a specific role, and tightly controlled Permissions to access your resources.

1. Create and register your application in Microsoft Entra ID as described in the section above.
2. Once registered, you must create a secret or upload a Certificate based on the following types of Authentication for your Connector.
  - Service Principal
  - Service Principal with Certificate
3. For Service Principal Authentication:
  1. From the left menu of the **Overview** page, select **Certificates & Secrets**
  2. On the right side of the page, click **Client secrets**.
  3. Click **New client secret** to add a new secret for Authentication.
  4. Enter the secret key name and click **Add**

Record the Azure client (Client ID and Secret) for the Service Principal. The **Client ID** is used as the username and the **Client secret** is used as a password in the Connection string while trying to connect to the Azure SQL server

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
openssl pkcs12 -export -password pass:"password" -legacy  -out client.pfx -inkey client.key -in client.crt
```
