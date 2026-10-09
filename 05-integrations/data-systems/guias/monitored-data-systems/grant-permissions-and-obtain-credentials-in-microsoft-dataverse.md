---
title: "Grant permissions and obtain credentials in Microsoft Dataverse"
slug: "grant-permissions-and-obtain-credentials-in-microsoft-dataverse"
updated: 2026-07-20T20:16:27Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-microsoft-dataverse"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Microsoft Dataverse

> [!NOTE]
> **Note**
> 
> This procedure assumes you have admin access to Azure Portal and Power Apps to let Securiti to assign roles and permission to users required for Connector Activation.

Refer to the matching procedure below to grant Permissions and obtain Credentials in Microsoft Dataverse.

1. Register an application in the Azure portal.
2. Obtain authentication credentials.
3. Configure Microsoft Dataverse permissions. in Azure application
4. Assign Security roles to selected user for Dataverse .
5. Obtain other activation credentials in Power Apps
6. Assign required role to Dataverse app (only for Hashicorp authentication

### Step 1 - Register a Dataverse application in the Azure Portal.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(9).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(9).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti Connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose Web from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - US2 Cloud: `https://app.us2.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
5. Near the bottom of the page, click **Register**.

![register-app-MD.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e325c3c7-da7f-545e-4418-313938c82340.png)

When you click **Register**, it redirects you to the **Overview** page of the newly registered application.

> [!NOTE]
> **Note**
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the Authentication section.
6. Refer to the matching procedure if you miss adding the redirect URL while registering an application.
  1. On the left sidebar, choose **Manage** > **Authentication**.

![Screenshot_2024-08-23_at_2_02_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52d46981-45dc-d8ae-0349-6ccf62b190c2(4).png)
  2. On the **Authentication** page, click **Add a platform**.
  3. On the **Configure platforms** popup, click **Web**.

![Screenshot_2024-08-23_at_2_02_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa08c31b-c9de-c9c1-deb5-57fbc44cb6ed(4).png)
  4. On the following popup, add the **Redirect URl** from the above Table, and click **Configure**.

![Screenshot_2024-08-23_at_3_19_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c0b39c0-6210-8689-04e0-787c220b297c(2).png)

### Step 2 - Obtain OAuth authentication credentials

Perform the following steps to obtain authentication credentials for connector activation:

1. Obtain **Client ID** and **Tenand ID.**
  1. On the left sidebar, click **Overview**.
  2. Record the **Application (Client) ID** by clicking on **Copy to clickboard** icon.

You can also record **Tenant ID** here or in the next step below.

![Client-id-MD.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ccb4362-11be-d994-fb52-63ca8e4d61f9.png)
2. Obtain **Domain** or **Tenant ID.**
  1. On the top left, click **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation:

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(12).png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain.
3. Obtain **application secret**:
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **New client secret**.

![add-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f8e4fb7-70a7-09d7-0362-2f94e498e3cc.png)
  2. On the **Add a client secret** popup, add the following information:

![secret-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c55ef862-9a29-5011-4ab7-810b635ea6ac.png)
    - Enter a description for the secret, for example, “Dataverse Connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.
  3. Under the **Client secrets** tab, record the new client secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d(5).png)

### Step 3 - Configure Microsoft Dataverse permissions

Perform the following steps to configure Microsoft Dataverse in Azure app:

- **Configure Microsoft Dataverse Permissions:**
  1. Navigate back to your Microsoft Dataverse application in Azure portal.
  2. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.

![API_permission-MD.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-65bae81d-c1bf-dbb4-2188-818f7b7e4c81.png)
  3. On the **Request API Permissions** popup, perform the following steps to use Dataverse API:
    - On the **APIs my organization uses** popup, click **Application Permissions** tab.
    - Search Dataverse in the search field.
    - Click on the **Dataverse** API from the list.

![API-org.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8961f48c-4dbc-f03e-d4ec-9cf38822d934.png)
  4. On the **Dynamics CRM** APIs popup, perform the following steps to assign permission to the Dataverse app.
    1. Click **Delegated Permissions** tab.
    2. Mark the checkbox for **user_impersonation** permission from the **Select Permissions** list.
    3. Click **Add Permissions**.

![user-impersonation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0cefd6c0-674d-4b4f-8cde-6e6866b27d57.png)

It redirects you the API Permissions page, where you see the user_impersonation permission added under Dynamic CRM section.

![Permission_list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63993812-22af-d4dd-bb78-d3ca24f6271c.png)

### Step 4 - Assign Security role to the user

Perform the following steps to assign Security role to user using Power Apps account.

1. Go to your Power Apps account **Dashboard**.
2. On the top right, click **Settings** icon > **Advanced Settings**.

![adv-setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3470afa0-22a9-c9a4-c6a2-8b30d93ab90e.png)

It redirects you to the new web browser window.
3. On the **Dynamic CRM** page, click **Settings** menu icon.

![Dynamic-setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d19b5d4-e659-212a-e129-a4be4939b500.png)
4. From the **Settings** menu, click **Security**.

![Security.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a401cd8-f17d-5aaf-389a-7429ad3991f8.png)
5. On the **Security** page, click **Users**.

![Users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c3126f1-b18f-6cbe-7aff-7cb39c00d04a.png)
6. On the **Enabled Users** page, mark the checkbox for the **User** you want to select Dataverse Connector Activation.

![enabled_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b503c8e4-f089-6dfb-949f-26bdad606326.png)
7. On the top, click **MANAGE ROLES**.

![manage-roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ac4106b-f39a-d756-2f88-8f3e4e3f35b4.png)
8. Assign one of the following roles to the selected user.
  - Basic User (limited tables which have read access from this role will be scanned - Select this option if you want to scan those tables only) - predefined role. (Not recommended)

> [!WARNING]
> **Warning**
> 
> We do not ask you to select Basic User role as it provides limited scanning ability to tables with only read access.
  - System Administrator Role (All Tables permission) - predefined role (Recommended)
  - Custom Role (Recommended)

For more information on how to create a Custom Role, see [Create a custom Security role for Dataverse in the Dynamic CRM app](/latest/docs/create-a-custom-security-role-for-dataverse-in-the-dynamic-crm-app).

![assign-roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7300eb0-77d2-5daa-9392-eaa3c8677585.png)

### Step 5 - Obtain other activation credentials in Power Apps

Perform the following steps to obtain Host URL and Version for Connector Activation.

**Obtain Host URL and Version**

1. Log in to your [Power Apps account](https://make.powerapps.com/).
2. On the Dashboard at the top right, choose **Settings** icon. Select **Developer resources** from the menu.

![power-setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-423c61a4-b116-be3d-8e74-ac92195780bc.png)
3. On the **Developer resources** popup, copy the **Web API endpoint** URL. See the example below.

*https://org8bcf25c3.api.crm.dynamics.com/api/data/v9.2*
  - Record the **Host URL** by copying it from **Web API endpoint** URL. See the example below.

If "**https://org8bcf25c3.api.crm.dynamics.com**/api/data/v9.2" is the Web API endpoint URL. Copy the initial part of URL that follows the *crm.dynamics.com* format.
  - Record the **Version**. See the example below.

If *https://org8bcf25c3.api.crm.dynamics.com/api/data/****v9.2*** is the Web API endpoint URL. Copy v9.2 as a version.

![api-endpoint-url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05a1c498-912f-5c5e-6d7d-a1b0398ec83f.png)
4. Proceed to [Connect Microsoft Dataverse connector in](/latest/docs/connect-microsoft-dataverse-connector-with-securiti) Securiti if you don't want to use Hashicorp vault Authentication.

### Step 6 - Assign required role to Dataverse app (only for Hashicorp authentication)

You must also configure the Hashicorp OAuth Token along with assigning required role to Dataverse app in case of Hashicorp vault Authentication. For more information, see [Configure the Hashicorp OAuth token for Microsoft Dataverse](/latest/docs/optional-configure-the-hashicorp-oauth-token-for-microsoft-dataverse)

Perform the following additional steps to assign admin role to Dataverse app:

1. Log in to your [Microsoft Power Platform account](https://admin.powerplatform.microsoft.com/) with admin Credentials.
2. On the left sidebar, click **Environments**. It shows a list of all the active Environments (applications) associated with your admin account.
  1. Select the **Microsoft Dynamics 365 CRM Suite** Instance from the Environments list.
  2. On the top of the page, click **Settings**.

![leftside-custom.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc9e3644-e9ba-6216-af57-5f3ceeb39895.png)
3. On the Settings page, expand **Users + Permissions** and select **Application users**.

![application_users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f12b2574-0f1b-2556-3ff4-fd69e8756867.png)
4. On the **Application users** page, click **New app user**.

![new-app-user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5cbd406-7a95-1f0d-1543-4b7156052b63.png)
5. On the **Create a new App user** popup, configure the following settings:

| Setting | Description |
| --- | --- |
| App | Click **Add an app**, and select the app that you created to activate the Microsoft Dataverse Connector |
| Business unit | Select the **Business unit** or organization that is connected to the Microsoft Dataverse Instance. |
| Security roles | Click on **edit** icon to assign System Administrator or Custom Role if you created as a Security Role to this user. |

Click **Create** to create this user.

![create-spp-user.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-35f7b843-d0e1-25c8-da47-b6dd0fb063f9.jpg)
6. It redirects you to the Application users page where you can see the newly create user.

![list-app-users.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cb5148f9-0a20-e0f3-03b6-99a351022295.jpg)

> [!NOTE]
> **Note**
> 
> **App ID** corresponding to this user is similar to the **Client ID** of the app that you selected during user creation. By default, newly created users are in an active state. The new user must be in an active state to use the HashiCorp vault with Microsoft Dataverse
7. Proceed to [Connect Microsoft Dataverse with](/latest/docs/connect-microsoft-dataverse-connector-with-securiti) Securiti.
