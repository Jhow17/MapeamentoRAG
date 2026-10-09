---
title: "Obtain authentication credentials and grant permissions in Outlook Cloud"
slug: "obtain-authentication-credentials-and-grant-permissions-in-outlook-cloud"
updated: 2026-06-23T06:36:48Z
published: 2026-06-23T06:36:48Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-and-grant-permissions-in-outlook-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials and grant permissions in Outlook Cloud

> [!NOTE]
> **Note**
> 
> Securiti lets you create multiple instances for all Microsoft 365 data systems, using the same Credentials. Hence, removing any restrictions for checking uniqueness in case of duplicate connectors.

Perform the following steps to obtain Credentials and assign Permissions in Azure portal for the Cloud connectors:

#### Step 1 - Register an application in the Azure Portal.

> [!NOTE]
> **Note**
> 
> To enable the Connector for Outlook , you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring Permissions that allow it to access Outlook resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(5).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(5).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti Connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose **Web** from the Select a platform meny and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(4).png)

> [!NOTE]
> **Note**
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the Authentication section.
5. See the procedure below if you miss adding the redirect URL while registering an application.
  1. On the left sidebar, choose **Manage** > **Authentication**.

![Screenshot_2024-08-23_at_2_02_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52d46981-45dc-d8ae-0349-6ccf62b190c2(3).png)
  2. On the **Authentication** page, click **Add a platform**.
  3. On the **Configure platforms** popup, click **Web**.

![Screenshot_2024-08-23_at_2_02_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa08c31b-c9de-c9c1-deb5-57fbc44cb6ed(3).png)
  4. On the following popup, add the **Redirect URl** from the above Table, and click **Configure**.

![edit-redirect-url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9dd25b12-2692-fa8a-2d2f-ca1f051f3fa4(1).png)

#### Step 2 - Obtain authentication credentials.

Perform the following steps to obtain Authentication Credentials for Connector Activation:

1. **Obtain Client ID:**
  1. On the left sidebar, click **Overview**.
  2. On the Overview page, record the **Application (Client) ID** by following the steps below.
    1. Hover on the right side of **Application (client) ID**.

**Copy to clipboard** icon appears..
    2. Click Copy to clipboard icon to save the **Application (client) ID**.

![client-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-69fe4aa0-42bf-c357-9495-6af13e237a36(1).png)
2. **Obtain application secret:**
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **New client secret**.

![plus-client-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-369d74fd-c5b1-972c-699d-c4e625ab1688(1).png)
  2. On the **Add a client secret** popup, add the following information:
    1. Enter a description for the secret, for example, “Outlook-secret.”
    2. Choose an expiration term. We recommend one year.
    3. Click **Add** to add the secret to the list.

![secret-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9d1fbff9-0661-cc3e-5361-9587d09b6ddc(1).png)
  3. Under the **Client secrets** tab, record the new client secret by clicking **Copy to clipboard** in front of **Value**, as shown below.

> [!NOTE]
> **Note**
> 
> **Copy to clipboard** icon appears only once. If you are unable to copy the Client secret, it requires to you create a new Client secret to save it for later use.

![copy-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-652051c3-5b18-147e-a800-c2238f24ea47(1).png)
3. **Obtain Tenant ID or Domain**
  1. On the top left, click **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation.

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(8).png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain.

#### Step 3 - Configure permissions for Outlook Cloud

Perform the following steps to configure Permissions for Outlook Cloud Connector:

1. **Configure Graph API Permissions:**
  1. On the Outlook application left sidebar, click **API Permissions** and choose **Add a permission** > **Microsoft Graph** API.

![request-graph-api.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c84e5e38-4c3a-7094-b98e-579ff9684015(1).png)
  2. On the **Request API Permissions** popup, click **Application Permissions**.

![application-pemissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-900df581-ce4d-08c7-2934-d845a0179f61(1).png)
  3. To select the Permissions, perfrom the following steps in the Select Permissions section.
    1. Search the permission by its name.
    2. Mark the check box for each Permissions you search.

See the list of Permissions required for SDI and DSR modules. For more information on modules use cases, see [Permissions and use cases section in Microsoft Outlook connectors](/v1/docs/microsoft-365-outlook-connectors).
      - User.Read.All
      - Mail.Read
      - Reports.Read.All
      - User.ReadBasic.All
    3. Click **Add permisisons** when you select all the permisisons.

![select-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ebb66eda-183a-9eaa-7f70-d31019797309(1).png)

It redirects you to API Permissions page where you see the Permissions you selected.
2. **Grant admin consent:**
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.

![grant-admin-cloud.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b95ff34-77c4-38bc-b507-22234f85df49.png)
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

![consent-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea71f4d7-a59c-2b0f-cdb6-618a4eeb23ff(3).png)

The API Permissions page appears with admin consent given to all permisisons as shown below.

> [!NOTE]
> **Note**
> 
> You can see different Graph API Permissions list depending on Outlook Connector types and modules you selected. For more information on use cases and Permissions section in [Use cases and permissions for Microsoft 365 Outlook](/latest/docs/microsoft-365-outlook-connectors).

![final-perms-outlook-cloud.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-863d0c1d-1be3-43d5-3a72-9ae713d5c5e1.png)

Proceed to [Connecting Microsoft 365 Outlook (Securiti Cloud) with Securiti](/latest/docs/new-ui-activating-microsoft-365-outlook-securiti-cloud-connector-with-securiti).
