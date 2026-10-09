---
title: "Prerequisites for Microsoft Fabric connector"
slug: "prerequisites-for-microsoft-fabric-connector"
updated: 2026-05-25T21:22:12Z
published: 2026-05-25T21:22:12Z
canonical: "helpcenter.securiti.ai/prerequisites-for-microsoft-fabric-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Microsoft Fabric connector

You must fulfil the following prerequisites before proceeding with connecting Microsoft Fabric with ​Securiti:

## 1. Register an application in Microsoft Entra ID

You must register an application in Microsoft Entra ID to authenticate with Microsoft Fabric. To register your application:

1. Log in to [Azure portal](https://portal.azure.com) with your Azure administrator account.
2. On the Azure homepage, under **Azure Services**, click **App registrations**.

![Microsoft Azure portal displaying App registrations and resource management options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_appregistrations.png)
3. Click ➕ **New registration** to register your application.
4. On the **Register an application** modal, provide values for the following fields:

| Setting | Description |
| --- | --- |
| Name | Enter the name of your application, such as “FabricSecuriti” |
| Supported account types | Select the **Single tenant** account type from the list to let the accounts in organizational directory only. |
| Redirect URI (optional) | Select **Web** and enter your redirect URI. - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

![Register an application in Microsoft Azure, selecting account types and redirect URI options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_applicationsettings.png)
5. Click **Register.**

## 2. Acquiring authentication credentials

To record the application credentials required for authentication:

1. In the **Overview** page for your application, record the **Client ID** and **Tenant ID**, as shown below.

![Overview of app registration with essential IDs highlighted for user reference.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_clientandtenantID.png)
2. From the left menu, select **Manage > Certificates & Secrets**, as shown below.
3. In the **Clients** section, click **New client secret** to generate the client secret for your application.
4. On the **Add a client secret** dialog, enter the description and expiration time for the secret.
5. Click **Add.**

![Adding a client secret in Azure with description and expiration settings displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_addclientsecret.png)
6. Copy the value of the generated client secret, immediately.

![Azure portal displaying client secrets and their expiration details for application management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_clientsecretvalue.png)

## 3. Assigning API permissions

Include the following API permissions in your registered application to discover Microsoft Fabric data.

1. From the left menu, select **Manage > API Permissions**.
2. On the **Configured permissions** page, click **Add a permission**.

![Admin consent settings for API permissions with an option to add permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_addpermission.png)
3. Select the APIs mentioned in the next step and choose **Delegated permissions** for the selected API.
4. Use the table below to understand the APIs and their required permissions to include in your application.

| API | Delegated permissions |
| --- | --- |
| **Azure Storage** | `user_impersonation` |
| **Power BI Service** | - **App**: `App.Read.All` - **Capacity**: - `Capacity.Read.All` - `Capacity.ReadWrite.All` - **Code & Fabric Extensions:** - `Code.AccessFabric.All` - `Fabric.Extend` - `Fabric.Extend.IframeSandbox` - **Connections:** - `Connection.Read.All` - `Connection.ReadWrite.All` - `Connection.Reshare.All` - **Content:** - `Content.Create` - **Gateway:** - `Gateway.Read.All` - `Gateway.ReadWrite.All` - **Item (General Fabric items):** - `Item.Execute.All` - `Item.ExternalDataShare.A`ll - `Item.Read.All` - `Item.ReadWrite.All` - `Item.Reshare.All` - **Item Metadata:** - `ItemMetadata.Read.All` - `ItemMetadata.ReadWrite.All` - **Lakehouse:** - `Lakehouse.Read.All` - `Lakehouse.ReadWrite.All` - **OneLake (Storage Layer permissions):** - `OneLake.Read.All` - `OneLake.ReadWrite.All` - **Organizational Apps:** - `OrgApp.Read.All` - `OrgApp.ReadWrite.All` - **Storage Accounts:** - `StorageAccount.Read.All` - `StorageAccount.ReadWrite.All` - **Tenant:** - `Tenant.Read.All` - `Tenant.ReadWrite.All` - **Warehouse:** - `Warehouse.ReadWrite.All` - **Workspace:** - `Workspace.Read.All` - `Workspace.ReadWrite.All` |
| **Microsoft Graph** | **Users:** - `User.Read` - `User.Read.All` - `Directory.Read.All` |

![Requesting API permissions for Azure Storage with user impersonation option selected.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_AzurestorageAPI_permissions.png)

![Requesting API permissions for Microsoft Graph and Azure Storage in MSFabric interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_graphAPI_permissions.png)

![Requesting API permissions for Power BI with highlighted permission options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_powerbi_permissions.png)

## 4. Granting admin consent for permissions

You must grant **admin consent** for all configured permissions before activating the connector. To grant admin consent:

1. After adding all permissions, under the **Configured permissions**, click **Grant admin consent for <Your Organization>**, as shown below.
2. On the confirmation popup, click **Yes**.

![Admin consent confirmation prompt for permissions in Securiti, Inc. application settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_adminconsent.png)
3. Ensure that all permissions show **Granted**.

## 5. Adding a service principal to an allowed security group

To enable Microsoft Fabric access through a service principal, add the service principal to a security group and assign that group to the required workspace.

### 5.1. Create or select a security group

Create a dedicated security group, or use an existing one, to control which service principals can access Fabric resources.

1. Log in to the **Microsoft Entra admin center**, as shown below.

![Microsoft Azure interface displaying Microsoft Entra ID and resource management options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_entraIDapp.png)
2. Navigate to **Identity > Groups > All groups**, as shown below.

![Overview page of Securiti, Inc. showing tenant information and group details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_groups.png)
3. From the Groups **Overview** page, click **New group** or open an existing group, as shown below.

![Overview of groups showing total groups and their categories in a management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_groupsoverview.png)

![Overview of group management interface with a highlighted 'New group' button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_newgroupbutton.png)
4. Configure the group with the following settings:
  - **Group type**: Security
  - **Membership type**: Assigned (recommended)
5. Enter a name and description.
6. Click **Create**, as shown below.

![Form for creating a new group with fields for type, name, and description.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_creategroup_settings.png)

### 5.2. Adding the service principal as a group member

Add the service principal to the security group so it inherits the group’s permissions.

1. Open the security group.
2. Select **Members > Add members**.
3. Search for your application under **Enterprise applications**. Ensure you select the **Enterprise application** (service principal), not the App registration object.
4. Select the application.
5. Click **Add**, as shown below.

![Creating a new security group and adding members in the application interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_Addmembers.png)

### 5.3. Verifying group membership

Confirm that the service principal is successfully associated with the security group.

1. In the **Microsoft Entra admin center**, select **Enterprise applications**.
2. Select your application.
3. Navigate to **Users and groups**.
4. Confirm that the security group appears in the assignment list, as shown below.

![Interface for managing users and groups in MS Fabric application settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_groupverification.png)

### 5.4. Assigning the security group to a Fabric workspace

Grant the security group access to the required Fabric workspace so the service principal can operate within it.

1. Sign in to the Microsoft Fabric portal.
2. Open **Workspaces**.
3. Select the target workspace.
4. Open **Workspace access**, as shown below.

![Workspace management interface showing options for accessing and managing workspaces.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_workspaceaccess.png)
5. Add the security group or service principal and assign the appropriate role.

The service principal now inherits access to the workspace through the security group.

## 6. Enabling service principal for Fabric APIs

You must enable service principals to use the Fabric APIs. Add the registered application as a service principal to each Fabric workspace that you want Securiti to scan.

To enable service principal for using APIs:

1. Log in to [Microsoft Fabric admin portal](https://app.powerbi.com/admin-portal/tenantSettings?experience=fabric-developer).
2. From the left menu, select **Tenant Settings**.

![Admin portal settings for Microsoft Fabric, highlighting tenant settings and user permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabrid_tenantsettings.png)
3. Scroll down to the following tenant settings:
  - **Service principals can call Fabric public APIs**
  - **Allow service principals to create and use profiles**
4. Activate the **Enabled** toggle for both settings, as shown below.
5. Choose one of the following when setting to Enabled:

![Settings for service principals to call APIs and create user profiles in admin portal.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fabric_enableserviceprincipal.png)
  - **Enabled for the entire organization**
  - **Enabled only for specific security groups**

When choosing the latter, add your application’s service principal to the allowed security group.

Proceed to [Activate the Microsoft Fabric (Self-hosted) connector in Securiti.](/latest/docs/activate-microsoft-fabric-self-hosted-connector-in-securiti)
