---
title: "Grant permissions and obtain credentials for Microsoft Dynamics 365 Finance and Operations"
slug: "grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en"
updated: 2026-07-10T19:49:53Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials for Microsoft Dynamics 365 Finance and Operations

> [!NOTE]
> Note
> 
> This procedure assumes you have admin access to Azure Portal and Microsoft Dynamics 365 Finance and Operations (F&O) to let Securiti to assign roles and permission to users required for connector activation.

## Register a Dynamics 365 F&O application in the Azure Portal

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-l7ki4dbh.png)
3. On the **App registrations** page, click **+ New registration** ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-76rsxufi.png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti connector." |
| Supported Account types | Choose **Accounts in this organization directory only - Single Tenant**. |
| Redirect URl | Choose Web from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - US2 Cloud: `https://app.us2.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
5. Near the bottom of the page, click **Register**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-bg8hfq1b.png)
  - When you click **Register**, it redirects you to the **Overview** page of the newly registered application.

> [!NOTE]
> Note
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the authentication section. For more information, see [Microsoft documentation.](https://learn.microsoft.com/en-us/entra/identity-platform/how-to-add-redirect-uri)

## Obtain OAuth authentication credentials

Perform the following steps to obtain authentication credentials for connector activation:

1. **Obtain Client ID and Tenant ID**
  1. On the left sidebar, click **Overview**.
  2. Record the following by clicking on the **Copy to Clickboard** icon.
    - **Application (Client) ID**
    - **Tenant ID**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-uszspvxz.png)
2. **Obtain application secret:**
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **New client secret**.
  2. On the **Add a client secret** popup, add the following information:
    - Enter a description for the secret, for example, “Dynamics F&O secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-kanqviiy.png)
  3. Under the **Client secrets** tab, record the new client secret by clicking **Copy to Clipboard** in front of **Value**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-afyk4prq.png)

## Configure Dynamics ERP permissions

Perform the following steps to configure Dynamics ERP permissions in the Azure app:

1. In the left sidebar, select **API permissions** and click **Add a permission**.
2. On the **Request API permissions** popup, search and select **Dynamics ERP**.
3. Under the **Dynamics ERP**, click **Delegated Permissions**.
4. Under the **Delegated Permissions**, search for and mark the `Odata.FullAccess` permission checkbox. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-a3pa95wq.png)
5. Click **Add permission**. It takes you to the API permissions page, where you can see a list of selected permissions.
6. On the **API permissions** page, click **Grant admin consent for <your tenant>**.
7. On the **Grant admin consent confirmation** popup, click **Yes**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/grant-permissions-and-obtain-credentials-in-microsoft-dynamics-365-finance-and-operations-en-image-90ow0pky.png)
8. Proceed to [Assign roles to the Dynamics 365 user](/latest/docs/assign-roles-and-permissions-to-dynamics-365-fo-user).
