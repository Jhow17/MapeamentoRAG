---
title: "Grant permissions and obtain credentials in SharePoint Online Cloud"
slug: "grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud"
updated: 2026-06-23T06:20:25Z
published: 2026-06-23T06:20:25Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in SharePoint Online Cloud

> [!NOTE]
> **Note**
> 
> Securiti lets you create multiple instances for all Microsoft 365 data systems, using the same credentials. Hence, removing any restrictions for checking uniqueness in case of duplicate connectors.

To grant Permissions and obtain credentials in SharePoint Online Self-hosted connector, perform the following:

#### Step 1 - Register an application in the Azure Portal.

> [!NOTE]
> **Note**
> 
> To enable the connector for SharePoint, you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring Permissions that allow it to access SharePoint resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(8).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(8).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti Connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose **Web** from the Select a platform meny and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(7).png)

> [!NOTE]
> **Note**
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the Authentication section.
  - Perform the following steps if you miss adding the redirect URL while registering an application.
    1. On the left sidebar, choose **Manage** > **Authentication (Preview)**.
    2. On the **Authentication (Preview)** page under the **Redirect URI Configuration** tab, click **Add Redirect URI**.

![redirect-URI-Config.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bd048f48-09d8-5760-6d9b-c62123ac8322(1).png)
    3. On the **Select a platform to add redirect URI** popup, click **Web**.

![select-web.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f3292fdc-49fb-7f10-f79f-4f3516c2e402(1).png)
    4. On the **Add Redirect URI** popup, add one of the redirect url as described in [app registration table](/v1/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud) above.
    5. Click **Configure**.

![add-URI.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85c0373a-15ed-454d-98ca-e7579a11911a(1).png)

It shows you the added redirect URI, as shown belo.

![URI-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8159182-a1bf-170f-4a30-fd27ffaf13ab(1).png)

#### Step 2 - Obtain authentication credentials.

Perform the following steps to obtain authentication credentials for connector activation:

1. **Obtain Client ID**
  1. On the left sidebar, click **Overview**.
  2. Record the Application (Client) ID by copying it.

![client-id-cld.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55f806dc-580f-0c2e-f427-166a4928dc8a.png)
2. **Obtain application secret:**
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **New client secret**.

![add-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-82c9d5d6-a9c2-1f76-c714-00a16c42af62.png)
  2. On the **Add a client secret** popup, add the following information:

![popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7dbae86c-75f9-9bc3-53a7-acb5feecccf9(1).png)
    - Enter a description for the secret, for example, “SharePoint Connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.
  3. Under the **Client secrets** tab, record the new client secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d(4).png)
3. **Obtain Tenant ID, Domain, and Tenant Name**
  1. On the top left, click **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation.

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(11).png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain.
  4. Record the **Tenant Name** for the Connector Activation.

**Tenant Name** is initial part of the domain. If *datasubjectrequest.onmicrosoft.com* is the domain. **datasubjectrequest** is the Tenant Name.

#### Step 3 - Configure SharePoint Online Cloud permissions

Perform the following steps to configure Microsoft 365 SharePoint Online Cloud permission:

1. **Configure Graph API Permissions:**
  1. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.

![add-perm-cld.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a6dba0e-6250-b808-4970-537cdfd55e8a.png)
  2. On the **Request API Permissions** page, click **Microsoft Graph** , then click **Application Permissions**.

![Microsoft-graph.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bee93d4a-d894-2e48-48ee-1985fd58ebbc(3).png) ![application-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ec0e1f3-defa-0212-ced5-a6462963c86a(3).png)
  3. Scroll down to **Select Permissions** section, expand the various areas, and mark the checkboxes for Graph API Permissions for the Connector as outlined in use cases and Permissions section in [Microsoft 365 SharePoint Online connectors](/v1/docs/microsoft-365-sharepoint-online-connectors).

![mark-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-febaf8d0-370d-7750-62b6-99a169ef3c13(3).png)
  4. When you have enabled the said Permissions, near the bottom of the Permissions box, click **Add Permissions**.

It redirects you to API Permissions page where you see the following Permissions.

> [!NOTE]
> **Note**
> 
> You can see different Graph API Permissions list depending on modules related Permissions you selected. For more information, refer to use cases and Permissions section in [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors).

![grap-perm-list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150fdbcb-bd62-edbc-f152-075bf2466d5e.png)
2. **Configure SharePoint API Permissions:**

> [!NOTE]
> **Note**
> 
> This SharePoint API Permissions are required for DSR Automation in the SharePoint Online Cloud connector
  1. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.

![add-perm-cld.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a6dba0e-6250-b808-4970-537cdfd55e8a.png)
  2. On the **Request API Permissions** page, click **Microsoft Graph** , then click **Application Permissions**.

![sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff8d6c52-fcdc-afcd-93cc-e33d41a6aabf(1).png)
  3. On the following page, perform the following steps:

![request-api.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26c5207c-7044-144c-cf8f-efec65870309.png)
    1. Click **Application Permissions** to access the required permission mentioned in use cases and Permissions section in [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors).
    2. Scroll down to **Permissions** section, expand the **Sites** section, and mark the checkbox for **Sites.Read.All**.
  4. Click **Add Permissions.**

It redirects you to **API Permissions** page where you see SharePoint permission added in the list as shown below.

> [!NOTE]
> **Note**
> 
> You can see different Graph API Permissions list depending on modules related Permissions you selected. For more information, refer to use cases and Permissions section in [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors).

![SP-API-list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d2be934-63e3-b582-d670-3ab9e55e6802.png)
3. **Grant admin consent:**
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.

![grant-admin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-325e39d9-ce55-aac3-ef92-d06317905d00.png)
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

![consent-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea71f4d7-a59c-2b0f-cdb6-618a4eeb23ff(5).png)

The API Permissions page appears with admin consent given to all permisisons as shown below.

![Final-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0d631f46-4363-02d4-d0e0-f8562336da8a.png)

Proceed to [Connecting Microsoft 365 SharePoint Online (Securiti-Cloud) with Securiti](/latest/docs/new-ui-activating-microsoft-365-sharepoint-online-securiti-hosted-connector).
