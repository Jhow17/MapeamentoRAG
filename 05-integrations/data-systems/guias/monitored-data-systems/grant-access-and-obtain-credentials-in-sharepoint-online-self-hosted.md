---
title: "Obtain credentials for SharePoint Online (Self-hosted)"
slug: "grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted"
updated: 2026-06-23T05:43:36Z
published: 2026-06-23T05:43:36Z
canonical: "helpcenter.securiti.ai/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for SharePoint Online (Self-hosted)

If you want to obtain credentials to activate the SharePoint Online connector for selective sites access, skip this article and see [Obtain credentials for SharePoint Online with selective sites](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access).

> [!NOTE]
> **Note**
> 
> We assume you own your Microsoft 365 account and run a SharePoint Online Self-hosted Instance with admin privileges.

Perform the following procedures to grant permissions and obtain credentials in Azure Portal for SharePoint Online Self-hosted Connector.

#### Step 1 - Register an application in the Azure Portal.

> [!NOTE]
> **Note**
> 
> To enable the Connector for SharePoint, you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring Permissions that allow it to access SharePoint resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(6).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(6).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti Connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose **Web** from the Select a platform meny and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(5).png)

> [!NOTE]
> Note
> 
> Microsoft Entra ID lets you register the application without adding redirect URLs. If you miss adding redirect URLs, or need to add additional ones for use cases such as **Data Access Intelligence** using **IAM Metadata Sources** in Data Access Governance, you can update them later.
  - Perform the following steps if you miss adding the redirect URL while registering an application.
    1. On the left sidebar, choose **Manage** > **Authentication (Preview)**.
    2. On the **Authentication (Preview)** page under the **Redirect URI Configuration** tab, click **Add Redirect URI**.

![redirect-URI-Config.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bd048f48-09d8-5760-6d9b-c62123ac8322.png)
    3. On the **Select a platform to add redirect URI** popup, click **Web**.

![select-web.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f3292fdc-49fb-7f10-f79f-4f3516c2e402.png)
    4. On the **Add Redirect URI** popup, add one of the redirect url as described in [app registration table](/v1/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted) above.
    5. Click **Configure**.

![add-URI.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85c0373a-15ed-454d-98ca-e7579a11911a.png)

It shows you the added redirect URI, as shown belo.

![URI-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8159182-a1bf-170f-4a30-fd27ffaf13ab.png)
5. Proceed to Obtain Authentication Credentials.

#### Step 2 - Obtain activation parameters and authentication credentials

Perform the following steps to obtain Activation parameters and Authentication Credentials for Connector Activation:

#### A - Obtain activation credentials

> [!NOTE]
> **Note**
> 
> Tenant ID, Tenant name, and Domain are Activation parameters. You need to record them for both OAuth based and Certificate based authenticatons.

Refer to the matching procedure to obtain Activation Credentials.

1. On the top left, click **hamburger** icon.
2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
3. On the **Overview** page, record one of the following for later use in the Connector Activation:

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(9).png)
  - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
  - **Primary Domain** as Domain.
4. Record the **Tenant Name** from **Primary Domain** for the Connector Activation.

**Tenant Name** is initial part of the domain. See the examples below:
  - If *testdomain.onmicrosoft.com* is the domain. **testdomain** is the Tenant Name.
  - If *yourdomain.sharepoint.com* is the domain. **yourdomain** is the Tenant Name.

#### B - Obtain OAuth based credentials

Refer to the matching procedure to obtain OAuth based Credentials for SharePoint Online Connector.

1. **Obtain Application (Client) ID**
  1. On the left sidebar, click **Overview** and record the "Application (Client) ID" by clicking the **Copy to Clipboard** icon for later use.
  2. Record the **Application (Client) ID** by copying it.

![App-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-380d688d-8a16-923a-79ca-68ba2c757cb2.png)
2. **Configure application secret:**
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **New client secret**.

![new-client-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-538c9eb6-1506-8cd7-7078-29c593f87ca3(1).png)
  2. On the **Add a client secret** popup:
    - Enter a description for the secret, for example, “SharePoint Connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.

![client-secret-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c50e628-d758-5c26-73c8-8b84a5164fca.png)
  3. Under the **Client secrets** tab, copy the secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d(2).png)
  4. Record the new client secret to use it Connector Activation.

#### C - Obtain certificate based credentials

> [!NOTE]
> **Important**
> 
> Certificate based Credentials are required when accessing Sharepoint APIs in addition to the Microsoft Graph API. Currently Gencore Entitlements, Site Sharing settings, and Site to Hubsite relationships require the use of Certificate Credentials.
> 
> For more information on Certificate based Credentials requirements and use cases, see [Microsoft 365 SharePoint Online FAQs](/latest/docs/microsoft-365-sharepoint-online-faqs).

Perform the following procedures to obtain Certificate based Credentials for SharePoint Online.

1. Open the terminal (console) on your machine, and execute the following command

```plaintext
openssl req -x509 -newkey rsa:4096 -sha256 -keyout /users/john.doe/certificate/private-auth-key.pem -out /users/john.doe/certificate/public-auth-cert.pem -nodes -days 730
```

In the above command, replace the */users/john.doe/Certificate/* with the appropriate path on your local machine where you want to store the generated Certificate files.

> [!NOTE]
> **Note**
> 
> We recommend using OpenSSL to generate the self-signed Public key (Certificate) and Private key. The keys generated by the command have a two-year validity.
2. Enter the following information after running the command.

| Parameter | Description |
| --- | --- |
| Country name | Enter the 2-letter code for country name. See the example below. *US* |
| State or Province name | Enter the full name of State or Province. See the example below. *New York* |
| Locality name | Enter the locality name can be either city name or location within city. See the examples below: - *New York* - *Southern Park* |
| Organization name | Enter your organization name in place of *ABC*. See the example below *Securiti* |
| Organizational unit name | Enter your Organizational unit name in place of XYZ. See the example below. *Data systems* |
| Common name | Enter a convenient common name in place of www.xyz.abc to identify your Certificate keys such as your name, company name, and server name. See the examples below. - www.securiti.ai - John Doe |
| Email address | Enter the email address you want to use for the Certificate keys. *admin@securiti.ai* |

![terminal-Sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6406ff5f-720a-1735-5219-52bf90371f4d.png)
3. Press enter to download the Certificate files.
4. Record the Public key (Certificate) and Private key downloaded in your local machine for later use.

The keys are generated in the same path you have opened in the terminal once you supply information to the specified parameters. See an example below.

The path */users/john.doe/Certificate/* contains two **public-auth-cert.pem** and **private-auth-key.pem.** files for the generated keys.
5. On the left sidebar, choose **Certificates & secrets** > **Certificates** > **Upload Certificate**.

![Add-certificate-Sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-51c17bec-31df-a1f3-f5a4-2a74a1c95c4b.png)
6. On the **Upload Certificate** popup, add the following information.

| Parameter | Description |
| --- | --- |
| Upload a Certificate | Upload a public key Certificate generated earlier. See the example for file format. *ca.crt* |
| Description | Enter a description for the purpose of public key Certificate. |

Click **Add**.

![certificate-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3c9e04e-5df9-83ec-693c-9a1bd8b61983.png)
7. Record the following information once the Public key (Certificate) is uploaded.

![record-thumbprint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fde178b0-ce08-d964-5bed-0f6602972450.png)

> [!NOTE]
> **Important**
> 
> The private key file and Certificate thumbprint are required for configuring Entitlement Scan for Microsoft 365 SharePoint Online Connector. Save this informaton to use for Connector Activation.
  - On the **Certificates & secrets** page, record the **Thumbprint** as the Certificate to use it for Connector Activation.

#### Step 3 - Configure SharePoint Online Self-hosted permissions.

Perform the following steps to configure Microsoft 365 SharePoint Online Self-hosted Permissions in Azure Portal:

1. **Configure Graph API Permissions:**
  1. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.

![add_graph_permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a9a830b-ffc8-4ef3-ee4e-e511e13f70d7.png)
  2. On the **Request API Permissions** page, click **Microsoft Graph** , then click **Application Permissions**.

![Microsoft-graph.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bee93d4a-d894-2e48-48ee-1985fd58ebbc(2).png)

![application-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2ec0e1f3-defa-0212-ced5-a6462963c86a(2).png)
  3. Scroll down to **Select Permissions** section, expand the various areas, and mark the checkboxes for Graph API Permissions for the Connector as outlined in use cases and Permissions section in [Permissions and use cases for connecting to SharePoint Online without limiting the connector’s access to sites](/latest/docs/microsoft-365-sharepoint-online-connectors).

![mark-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-febaf8d0-370d-7750-62b6-99a169ef3c13(2).png)
  4. When you have enabled the said Permissions, near the bottom of the Permissions box, click **Add Permissions**.

It redirects you to API Permissions page where you see the following Permissions.

> [!NOTE]
> **Note**
> 
> You can see different Graph API Permissions list depending on modules related Permissions you selected. For more information, see use cases and Permissions section (Without selective sites acess) in [Microsoft 365 SharePoint Online](/latest/docs/microsoft-365-sharepoint-online-connectors).

![graph-perm-wo-admin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-699bdf37-e545-03ad-27e7-10295b150c3d.png)
2. **Configure SharePoint Online Permissions (Only for Data Access Governance):**

> [!NOTE]
> **Note**
> 
> This procedure is only required for registering REST API application. You can skip this procedure if you do not want to register REST API application in Classic SharePoint.
  1. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.

![add_graph_permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a9a830b-ffc8-4ef3-ee4e-e511e13f70d7.png)
  2. On the **Request API Permissions** page, click **Microsoft Graph** , then click **Application Permissions**.

![sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff8d6c52-fcdc-afcd-93cc-e33d41a6aabf.png)
  3. On the following page, perform the following steps:

![sharepoint-app-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0b08f38-5a2f-51c5-7062-c6d9c1d71bfb.png)
    1. Click **Application Permissions** to access the required permission mentioned in [Permissions and use cases for connecting to SharePoint Online without limiting the connector’s access to sites](/latest/docs/microsoft-365-sharepoint-online-connectors) for SharePoint.
    2. Scroll down to **Permissions** section, expand the **Sites** section, and mark the checkbox for **Sites.FullControl.All**.
  4. Click **Add Permissions.**

It redirects you to **API Permissions** page where you see SharePoint permission added in the list as shown below.

![sp-wo-admin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bae3af3c-d9ba-ea83-b63c-5cb24827e240.png)
3. **Grant admin consent:**
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.

![grant-consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca0fe711-5e78-2827-ec31-7bdcc2b76f1e.png)
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

![consent-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea71f4d7-a59c-2b0f-cdb6-618a4eeb23ff(4).png)

The API Permissions page appears with admin consent given to all permisisons as shown below.

![final-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-79e5859b-f45d-6210-45d5-0575f535d90e.png)
4. Proceed to [Connecting Microsoft 365 SharePoint Online (Self-hosted) with Securiti](/latest/docs/new-ui-connecting-microsoft-365-sharepoint-online-self-hosted-with-securiti).
