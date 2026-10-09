---
title: "Creating an Entra ID app and obtain credentials for Microsoft 365"
slug: "create-an-entra-id-app-and-obtain-credentials-for-microsoft-365"
updated: 2026-03-10T08:16:17Z
published: 2026-03-10T08:16:17Z
canonical: "helpcenter.securiti.ai/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Creating an Entra ID app and obtain credentials for Microsoft 365

> [!WARNING]
> Importqant
> 
> Skip this procedure if you plan to connect Microsoft 365 applications using automatic authentication.

To connect your Microsoft 365 application using manual authentication, you must create a single Entra ID application, obtain credentials, and assign permissions based on module use cases.

## Create an Entra ID application

> [!NOTE]
> Note
> 
> To enable the Connector for Microsoft 365, you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring Permissions that allow it to access SharePoint resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com) admin console.
2. On the Home page under the Azure services section, click **App registrations**.
3. On the **App registrations** page, click **+ New registration**
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name for your Azure application. See the example below. "Selective Sites Access App" |
| Supported Account types | Choose **Accounts in this organization directory (<organization> only - Single tenant)** from the menu. |
| Redirect URl | Choose Web from the Select a platform menu and enter the redirect URL that applies: US Cloud: https://app.securiti.ai/static/activateConnector.html US1 Cloud: https://app1.securiti.ai/static/activateConnector.html Canada Cloud: https://app3.securiti.ai/static/activateConnector.html EU Cloud: https://app.eu.securiti.ai/static/activateConnector.html Indonesia Cloud: https://app2.securiti.ai/static/activateConnector.html Australia Cloud: https://app4.securiti.ai/static/activateConnector.html UAE Cloud: https://app5.securiti.ai/static/activateConnector.html Mumbai Cloud: https://app6.securiti.ai/static/activateConnector.html KSA Cloud: https://app7.securiti.ai/static/activateConnector.html Qatar Cloud: https://app8.securiti.ai/static/activateConnector.html Sovereign deployment: https://<sovereign_deployment_portal_host>/static/activateConnector.html |
5. Near the bottom of the page, click **Register**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-an-azure-app-and-obtain-credentials-image-2l270u8l.png)

> [!NOTE]
> Note
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the Authentication page. For more information, see Microsoft documentation.
6. Proceed to Obtain Authentication Credentials.

## Obtain authentication credentials

For manual authentication, you must record the Application ID, Application Secret, and Tenant ID. To obtain these authentication credentials, perform the following steps:

1. On the left sidebar, click **Overview**.
2. On the **Overview** page under the Essentials, record the **Application (Client) ID** and **Tenant ID** by clicking the "Copy to Clipboard" icon for later use. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-an-azure-app-and-obtain-credentials-image-6odtmzdp.png)
3. In the left-hand navigation pane for the newly created application, choose **Manage > Certificates & secrets**.
4. On the **Certificates & secrets** page, click **+ New client secret**.
5. On the **Add a client secret** popup, add the following details, as shown below.
  1. Enter a description for the secret, for example, “Client Secret for selective sites access application.”
  2. Choose an expiration term. We recommend one year.
  3. Click **Add** to add the secret to the list. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-an-azure-app-and-obtain-credentials-image-3b3xd97m.png)
6. Under the **Client secrets** tab, record the new client secret by clicking Copy to Clipboard in front of **Value**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-an-azure-app-and-obtain-credentials-image-tij7tbr4.png)

## Assign permissions to the Entra ID application

> [!NOTE]
> Note
> 
> Before assigning permissions to the Entra ID application, review the required permissions and purposes described in the Permissions section under Prerequisites. Understanding these requirements ensures that you assign only the necessary permissions for the Microsoft data systems you plan to connect.
> 
> For more information, see

1. In the left navigation pane, under **Manage**, click **API permissions**.
2. On the **API permissions** page, click **Add a permission**.
3. In the **Request API permissions** window, select **Microsoft Graph**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-an-azure-app-and-obtain-credentials-image-8qfg7yrh.png)
4. Choose **Application permissions**, based on your use case, then click **Add permissions** after selecting the required permissions, as described in [Permissions and use cases section in Microsoft 365](/latest/docs/microsoft-365#permissions-and-use-cases). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-an-azure-app-and-obtain-credentials-image-iyknvpfy.png)
5. It redirects you to the **API permissions** page. Click **Add a permission** again.
6. In the **Request API permissions** window, select **SharePoint**.
7. Choose **Application permissions**, based on your use case, then click **Add permissions** after selecting the required permissions described in the [Permissions and use cases section in Microsoft 365](/latest/docs/microsoft-365#permissions-and-use-cases).
8. Once completed, you are redirected to the **API permissions** page, where both Microsoft Graph and SharePoint permissions are listed.
9. On top of the API Permissions name Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.
10. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

> [!NOTE]
> Note
> 
> You might see different permissions based on the use cases required for Microsoft 365 applications you want to select in the authentication process.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-an-azure-app-and-obtain-credentials-image-i35c0j3j.png) The API Permissions page appears with admin consent given to all Permissions.
11. Proceed to [Connect the Microsoft 365 apps using manual authentication.](/latest/docs/connect-microsoft-apps-using-manual-authentication)
