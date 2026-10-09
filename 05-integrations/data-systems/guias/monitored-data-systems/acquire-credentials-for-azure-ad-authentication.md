---
title: "Acquire credentials for Azure AD authentication"
slug: "acquire-credentials-for-azure-ad-authentication"
updated: 2026-06-12T10:42:51Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/acquire-credentials-for-azure-ad-authentication"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire credentials for Azure AD authentication

> [!WARNING]
> Important
> 
> Before starting the configuration, You must have the following required permissions and roles:
> 
> - Azure / Microsoft Entra ID
>   - To assign the Azure SQL Microsoft Entra Admin, the account must have **Owner**, **Contributor**, or **User Access Administrator** permissions on the Azure SQL Server resource (or its resource group).
>   - If Identity Syncing is enabled, the managed identity may require the **Directory Readers** role or Microsoft Graph permissions such as `User.Read.All` to look up users in Microsoft Entra ID.
> - Azure SQL Database
>   - To provision new database users from Microsoft Entra ID, you must connect using the designated **Microsoft Entra Admin** account or an account with the `ALTER ANY USER` permission.

## Prerequisites

Before initiating with the Azure AD authentication configuration, you must have following prerequisites fulfilled:

- You must have Azure SQL Database instance on Azure portal.
- You must have a Microsoft Entra ID (Azure AD) tenant, with the target user or group already created. For more information, see [Create a user and grant DB permissions](/latest/docs/create-a-user-for-azure-sql-server).
- You must enable Entra authentication on the relevant SQL server instance.
- You must enable Appliance ip under Security > Networking.

## Create Azure SQL Server

1. Log in to the [Azure Portal](https://portal.azure.com/), and search for Azure SQL Server.
2. If you don’t have Azure SQL Server created, then create one by selecting any of the following authentication methods as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-12 at 3.34.32 PM.png)
  - **Use Microsoft Entra-only authentication**
  - **Use both SQL and Microsoft Entra authentication**

## Add Client IP address to firewall rules

1. Go to Azure SQL server instance, and search Networking.
2. Under **Firewall rules**, Add IPv4 address which you will be using to make connection request, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-12 at 3.07.21 PM.png)

## Enable System assigned managed identity

1. Go to SQL Server in your Azure portal.
2. Open **Security** > **Identity**, and enable the **System assigned managed identity** status as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-12 at 12.58.01 PM.png)

## Record the System assigned managed identity

1. Go to SQL Server in your Azure portal.
2. Open **Settings** > **Properties**, and record the **System assigned managed identity**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-12 at 3.16.14 PM.png)

## Grant Permissions to the server

1. In the Azure portal, open **Microsoft Entra ID** service (formerly known as Azure Active Directory)
2. From the left side menu, click **Roles and Admin** section, and open **Directory Readers** permission, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-12 at 3.23.50 PM.png)
3. On the Assignments page, click **Add Assignments**, and assign the permission to your SQL Server.

## Provision the Entra User in the Database

1. Open a query editor such as **Azure Data Studio**, **SQL Server Management Studio (SSMS)**, or the **Azure Portal Query Editor**.
2. Connect to the target database using the Microsoft Entra Admin account configured earlier.
3. Verify that you are connected to the target database (not the `master` database).
4. Run the following command to create the user:

```plaintext
CREATE USER [user.name@yourdomain.com] FROM EXTERNAL PROVIDER;
```

Proceed to [Connecting Microsoft Azure SQL Database with Securiti](/latest/docs/connecting-microsoft-azure-sql-database-with-securiti).
