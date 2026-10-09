---
title: "Grant permissions and obtain credentials in OneDrive Cloud"
slug: "grant-permissions-and-obtain-credentials-in-onedrive-cloud"
updated: 2026-09-30T10:28:46Z
published: 2026-09-30T10:28:46Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-onedrive-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in OneDrive Cloud

> [!NOTE]
> **Note**
> 
> Securiti lets you create multiple instances for all Microsoft 365 data systems, using the same Credentials. Hence, removing any restrictions for checking uniqueness in case of duplicate connectors.

Refer to the matching procedure below to grant Permissions and obtain Credentials in OneDrive Cloud Connector.

1. Register an application in the Azure portal.
2. Obtain authentication credentials.
3. Configure Microsoft 365 OneDrive permissions.

#### Step 1 - Register an application in the Azure Portal.

> [!NOTE]
> **Note**
> 
> To enable the Connector for OneDrive, you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring Permissions that allow it to access OneDrive resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(3).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(3).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti Connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose Web from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - US2 Cloud: `https://app.us2.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(2).png)

> [!NOTE]
> **Note**
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the Authentication section.
5. Refer to the matching procedure if you miss adding the redirect URL while registering an application.
  1. On the left sidebar, choose **Manage** > **Authentication**.

![Screenshot_2024-08-23_at_2_02_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52d46981-45dc-d8ae-0349-6ccf62b190c2(1).png)
  2. On the **Authentication** page, click **Add a platform**.
  3. On the **Configure platforms** popup, click **Web**.

![Screenshot_2024-08-23_at_2_02_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa08c31b-c9de-c9c1-deb5-57fbc44cb6ed(1).png)
  4. On the following popup, add the **Redirect URl** from the above Table, and click **Configure**.

![Screenshot_2024-08-23_at_3_19_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c0b39c0-6210-8689-04e0-787c220b297c(1).png)

#### Step 2 - Obtain authentication credentials.

Perform the following steps to obtain Authentication Credentials for Connector Activation:

1. **Obtain Client ID:**
  1. On the left sidebar, click **Overview**.
  2. Record the **Application (Client) ID** by copying it.

![ODC-client-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1517a8d9-9687-16d6-7a1a-84993c8ecae4.png)
2. **Obtain application secret:**
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **New client secret**.

![ODC-Client-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-87853a8e-6a76-482a-4489-dfa2b4165226.png)
  2. On the **Add a client secret** popup, add the following information:

![popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7dbae86c-75f9-9bc3-53a7-acb5feecccf9.png)
    - Enter a description for the secret, for example, “OneDrive Connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.
  3. Under the **Client secrets** tab, record the new client secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d(1).png)
3. **Obtain Tenant ID, Domain, and Tenant Name.**
  1. On the top left, click **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation:

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(6).png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain.
  4. Record the **Tenant Name** from **Primary Domain** for the Connector Activation.

**Tenant Name** is the initial part of the domain. If *testdomain.onmicrosoft.com* is the domain. **testdomain** is the Tenant Name.

#### Step 3 - Configure OneDrive Cloud permissions

Perform the following steps to configure OneDrive Cloud permission:

1. **Configure Graph API Permissions:**

![ODC-Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c3bf675-9d75-2946-127c-1cb6ccc6d7e4.png)
  1. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.

![ODC-add-api-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d7f6186-6a09-7391-f45b-b80f02341f5e.png)
  2. On the **Request API Permissions** page, click **Microsoft Graph** , then click **Application Permissions**.

![Microsoft-graph.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bee93d4a-d894-2e48-48ee-1985fd58ebbc(1).png)

![application-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ec0e1f3-defa-0212-ced5-a6462963c86a(1).png)
  3. Scroll down to **Select Permissions** section, expand the various areas, and mark the checkboxes for Graph API Permissions for the Connector as outlined in use cases and Permissions section in [Microsoft 365 OneDrive connectors](/v1/docs/microsoft-365-onedrive-connectors).

![mark-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-febaf8d0-370d-7750-62b6-99a169ef3c13(1).png)
  4. When you have enabled the said Permissions, near the bottom of the Permissions box, click **Add Permissions**.

It redirects you to API Permissions page where you see the following Permissions.

> [!NOTE]
> **Note**
> 
> You can see different Graph API Permissions list depending on modules related Permissions you selected. For mor information, see use cases and Permissions section in [5. Use cases and permissions for Microsoft 365 OneDrive](/v1/docs/microsoft-365-onedrive-connectors).
2. **Grant admin consent:**
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.

![ODC-grant-admin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b16f629-863c-3512-fab5-3892e3a9451d.png)
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

![consent-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea71f4d7-a59c-2b0f-cdb6-618a4eeb23ff(1).png)

The API Permissions page appears with admin consent given to all permisisons as shown below.

> [!NOTE]
> **Note**
> 
> You can see different Graph API Permissions list depending on modules related Permissions you selected. For more information, see use cases and Permissions section in [Use cases and permissions for Microsoft 365 OneDrive](/latest/docs/microsoft-365-onedrive-connectors).

![ODC-Permissions-final.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d468cc7d-224c-d2ce-c457-262341046fa1.png)

Proceed to [Connecting the OneDrive (Securiti-Cloud) data system](/latest/docs/new-ui-connecting-microsoft-365-onedrive-cloud-with-securiti).
