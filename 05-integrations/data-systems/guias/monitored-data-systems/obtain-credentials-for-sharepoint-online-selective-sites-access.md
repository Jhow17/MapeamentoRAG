---
title: "Obtain credentials for SharePoint Online Selective Site(s) Access"
slug: "obtain-credentials-for-sharepoint-online-selective-sites-access"
updated: 2026-06-23T05:53:53Z
published: 2026-06-23T05:53:53Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-sharepoint-online-selective-sites-access"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for SharePoint Online Selective Site(s) Access

If you want to obtain credentials to activate the SharePoint Online connector without selective sites, skip this article and see [Obtain credentials for SharePoint Online (Self-hosted)](/latest/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted).

To activate the SharePoint Online Self-hosted Connector with Selective Sites Access in Securiti, Microsoft requires you to create two applications in the Azure portal.

1. The first is a **Selective Sites Access** application, which connects directly with Securiti, and is used to scan only the SharePoint sites that you explicitly authorize.
2. The second is a **Full Control** application, which doesn't connect with Securiti. But it is required of your tenant to fetch all available SharePoint sites and grant access to the Selective Sites Access application for the specific sites you choose.

Together, these two applications enable secure and controlled Integration between Microsoft 365 SharePoint Online and Securiti. For more information on the various Selective Sites Access features, see [SharePoint Online FAQs](/latest/docs/microsoft-365-sharepoint-online-faqs).

![Final-selective.svg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-636713fe-3340-91da-26e0-50035fe56f82.svg)

#### Prerequisites

- You must **own** a Microsoft 365 account and run a SharePoint Online account with **admin** privileges.
- You must have access to the **Azure portal** to create applications and assign required permissions.
- You must have **Postman** installed on your system.
- You must have an **OpenSSL** or equivalent program installed on your system to generate certificates and keys if [entitlement scans](/latest/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted) are required with selective access.

#### Required Microsoft Entra ID applications

The following table lists the two Microsoft Entra ID applications required for this setup, and explains their purpose in connector activation and scanning.

| Aspect | Selective Sites Access application | Full Control Provisioning application |
| --- | --- | --- |
| Purpose and who uses it | You can use it to activate the SharePoint connector in ​Securiti and scan only sites that have been explicitly granted. | SharePoint admin can use it to enumerate sites, get site IDs, and grant per-site access through API calls to the Selective Sites application. ​​Securiti ​​ does not use or access this application. |
| Permission scope | Microsoft Graph application permission: ​ - `Sites.Selected​​` You might need additional permissions separately if other modules are enabled. | Microsoft Graph application permission: ​ - `Sites.FullControl.All​​` |
| Default access | No site access by default. `Sites.Selected `provides zero access until an admin grants per-site permissions to this app. | Tenant-wide rights under Sites.FullControl.All, but used only to grant per-site permissions to the Selective Sites app. Not used for connector activation or scanning. |
| How site access is granted | Gains access to a target site only after an explicit per-site permission grant is applied to this app by the Full Control Provisioning App (admin-run API calls). | Admin uses this app to grant the “Selective Sites Access” app per-site permissions. Its purpose is to enable the “Selective Sites Access” app, not to access content itself. |
| Used for connector activation | Yes, operates only on explicitly authorized sites (depends on the CSV uploaded during activation). | No, used solely for granting and managing permissions; not used by Securiti for activation or scanning. |

#### Credentials required for each Azure application

The following Table lists the Credentials required for each application and its role.

| Azure application type | Applicable Credentials | Purpose |
| --- | --- | --- |
| Selective Sites Access application | - Tenant Name - Tenant ID - OAuth-based Credentials - Application (Client) ID - Client Secret - Certificate-based Credentials (Recommended) - Certificate ThumbPrint - Private Key | These Credentials are required for Connector Activation as the Selective sites access application connects with Securiti. |
| Full Control application | - Application (Client) ID - Client Secret | These Credentials are not required for activating the Connector in Securiti. They are only used in Postman to generate an access Token for the Full Control application. The access Token lets the Full Control application connect to Microsoft Graph, so you can fetch all SharePoint sites and grant access to the Selective Sites Access application |

#### 1. First application - Selective Sites Access application

> [!WARNING]
> **Important**
> 
> You must complete all the procedures to complete the process for obtaining credentials and assigning permission

Perform the following procedures to create the Selective Sites Access application and obtain Credentials.

1. Register the Selective Sites Access application in Azure
2. Obtain authentication credentials
3. Configure Selective Sites Access application permissions

#### Register the Selective Sites Access application in the Azure

> [!NOTE]
> **Note**
> 
> To enable the Connector for SharePoint, you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring Permissions that allow it to access SharePoint resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(7).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(7).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name for your Azure application. See the example below. *"Selective Sites Access App"* |
| Supported Account types | Choose **Accounts in this organization directory** from the menu. |
| Redirect URl | Choose **Web** from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(6).png)

> [!NOTE]
> **Note**
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the Authentication page. For more information, see [Microsoft documentation](https://learn.microsoft.com/en-us/entra/identity-platform/how-to-add-redirect-uri).
5. Proceed to Obtain Authentication Credentials.

#### Obtain authentication credentials for Selective Sites Access application

1. **To obtain OAuth Credentials (Client ID and Secret):**
  1. On the left sidebar, click **Overview.**
  2. On the **Overview** page under the **Essentials**, record the **Application (Client) ID** by clicking the "Copy to Clipboard" icon for later use.

![cop-clientid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b1d47e5-9fe5-2565-22d0-8dda9e1b0c86.png)
  3. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**.
  4. On the **Certificates & secrets** page, click **+ New client secret**.
  5. On the **Add a client secret** popup, enter a description for the secret, for example, “Client Secret for selective sites access application”, and choose an expiration term. We recommend one year.
  6. Click **Add** to add the secret to the list.

![secret-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-96787d63-de7e-2c93-da7e-d06f84e8d974.png)
  7. Under the **Client secrets** tab, record the new client secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7825bf3-8068-3c58-8288-2f8889e5f077.png)
2. **To obtain Certificate-based Credentials (Recommended):**

> [!NOTE]
> **Note**
> 
> - Certificate based Credentials are required for [Data Inventory Syncs and Entitlement scans](/v1/docs/configuring-data-inventory-sync-for-sharepoint-online-self-hosted).
> - When using Certificate-based Credentials, you must first obtain OAuth Credentials and then configure the certificates, since both are required for Connector Activation.
> 
> For more information on Certificate based Credentials requirements and use cases, see [Microsoft 365 SharePoint Online FAQs](/v1/docs/microsoft-365-sharepoint-online-faqs).

You must create public and private keys before generating a Certificate in the Azure portal. To generate keys and generate a Thumbprint Certificate:
  1. Open the terminal (console) on your machine, and execute the following command

```plaintext
openssl req -x509 -newkey rsa:4096 -sha256 -keyout /users/john.doe/certificate/private-auth-key.pem -out /users/john.doe/certificate/public-auth-cert.pem -nodes -days 730
```

In the above command, replace the */users/john.doe/Certificate/* with the appropriate path on your local machine where you want to store the generated Certificate files.

> [!NOTE]
> **Note**
> 
> We recommend using OpenSSL to generate the self-signed Public key (Certificate) and Private key. The keys generated by the command have a two-year validity. Consult the [Microsoft documentation](https://devblogs.microsoft.com/microsoft365dev/client-secret-expiration-now-limited-to-a-maximum-of-two-years/) for guidelines on creating and rotating secrets.
  2. Enter the following information after running the command.

> [!NOTE]
> **Note**
> 
> Enter a value for each parameter and ensure it is unique. This uniqueness is crucial for generating a distinct Certificate and key for every app registration setup. Without unique parameters, the generated Certificate and key are not be unique.

| Parameter | Description |
| --- | --- |
| Country name | Enter the 2-letter code for the country name. See the example below. *US* |
| State or Province name | Enter the full name of the State or Province. See the example below. *New York* |
| Locality name | Enter the locality name can be either a city name or a location within a city. See the examples below: - *New York* - *Southern Park* |
| Organization name | Enter your organization name in place of *ABC*. See the example below *Securiti* |
| Organizational unit name | Enter your Organizational unit name in place of XYZ. See the example below. *Data systems* |
| Common name | Enter a convenient common name in place of www.xyz.abc to identify your Certificate keys, such as your name, company name, and server name. See the examples below. - www.securiti.ai - John Doe |
| Email address | Enter the email address you want to use for the Certificate keys. *admin@securiti.ai* |

![terminal-Sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6406ff5f-720a-1735-5219-52bf90371f4d(1).png)

After running the command, you see two keys generated from the specified path in your operating system.
  3. Once you are done adding the above information, press enter to download the Certificate files
    - The keys are generated in the same path you have opened in the terminal once you supply information to the specified parameters. See an example below.

The path */users/john.doe/Certificate/* contains two **public-auth-cert.pem** and **private-auth-key.pem.** files for the generated keys.

| Key type | Recording purpose |
| --- | --- |
| Public Key | Record the Public key to use it for generating the Azure Certificate, as described below in uploading the Certificate. |
| Private Key | Record the Private key to use it for Connector Activation using Certificate-based Credentials. |
  4. To generate an Azure Certificate, on the left sidebar, choose **Certificates & secrets** > **Certificates** > **Upload Certificate**.

![Add-certificate-Sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-51c17bec-31df-a1f3-f5a4-2a74a1c95c4b(1).png)
  5. On the **Upload Certificate** popup, add the following information.

| Parameter | Description |
| --- | --- |
| Upload a Certificate | Upload a public key Certificate generated in **Record the Public key**. See the example for the file format. *ca.crt* |
| Description | Enter a description for the purpose of the public key Certificate. |

Click **Add**.

![Public-Key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a01dafc-2831-6613-b678-3991e70ed3ab.png)
  6. Record the Thumbprint Certificate once the Public key is uploaded.

![Thumbprint_certificate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0e41a62-1cc3-9cc3-d85c-e02b967fe3d3.png)

> [!WARNING]
> **Important**
> 
> The private key file and Certificate thumbprint are required for configuring the Entitlement Scan for Microsoft 365 SharePoint Online Connector. Save this information to use for Connector Activation.
    - On the **Certificates & secrets** page, record the **Thumbprint** as the Certificate to use for Connector Activation.

> [!NOTE]
> **Note**
> 
> The displayed value of Thumprint is not complete. Make sure to copy the complete value of Thumbprint Certificate.
3. **To obtain Tenant ID and Tenant Name:**
  1. On the top left, click the **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation:

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(10).png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
  4. Record the **Tenant Name** from the **Primary Domain** for the Connector Activation.

**Tenant Name** is the initial part of the domain. If *testdomain.onmicrosoft.com* is the domain. **testdomain** is the Tenant Name.

#### Configure the Selective Sites Access application permissions.

Perform the following steps to configure the Selective Sites Access application Permissions:

1. **Configure Graph API Permissions:**
  1. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.
  2. On the **API Permissions** page, click **Add a permission**.
  3. On the **Request API Permissions** popup, click **Microsoft Graph**, then click **Application Permissions**.

![graph-api-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a9f2accd-fbb8-f3b1-147a-976a19f2c2c0.png)

![graph-application.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-44d9cce1-fcf3-8d75-8083-498c8ba8d8b0.png)
  4. Scroll down to the **Select Permissions** section, and mark the checkbox for **Sites.Selected** permission, as shown below.

For more information on other use cases, see [Microsoft 365 SharePoint Online connectors](/v1/docs/microsoft-365-sharepoint-online-connectors).

![sites_perm-graph.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85d172e0-fcd8-a5ea-2067-98609dbc8d8c.png)
2. **Configure SharePoint API Permissions:**

> [!NOTE]
> **Note**
> 
> This procedure is only required for Entitlement Scan. You can skip this procedure if you do not want to run Entitlement scans. For more information on use cases, see Permissions section for selective sites in [Microsoft 365 SharePoint Online connectors](/v1/docs/microsoft-365-sharepoint-online-connectors).
  1. On the **API Permissions** page, click **Add a permission** to open the **Request API Permissions** popup.
  2. On the **Request API Permissions** page, click **SharePoint** > **Application Permissions**.

![sharepoint-api_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1efde3d-8d47-3dba-7596-0790410600c7.png)
  3. Under the **Application Permissions**, expand the **Sites** section, and mark the checkbox for **Sites.Selected**.

![SP-siteselected.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-053fdd29-5f50-fc9e-47e2-1653521134b7.png)
  4. Click **Add Permissions.**

![SP-API_SS_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e1fb68ac-039e-a0ab-1380-0d56efe49698.png)

It redirects you to the **API Permissions** page.
3. **Grant admin consent:**
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

![Grant-admin-consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e7dc081-b5ff-2567-d03e-c1d5ad3600e0.png)

The API Permissions page appears with admin consent given to all Permissions, as shown below.

![granted_permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a1675134-19fe-cc95-b6dc-1e539325f016.png)
4. Proceed to Full control application registration.

> [!NOTE]
> **Note**
> 
> You must also create **Full Control application** as described in the procedure below. **Selective Sites Access** application doesn't have access to SharePoint sites. It depends on the Full Control application to access those sites.

#### 2. Obtain authentication credentials for full control application

> [!NOTE]
> **Note**
> 
> You don't connect this application to Securiti. This application is used at your end for read access to SharePoint sites. This application provides full control privileges and is responsible for granting Permissions to Selective Sites access application for accessing specific sites.

Full control application covers the following procedures:

1. Register a full control application in Azure
2. Obtain authentication credentials for the Postman access token
3. Configure Full Control application permissions

#### 1. Register a full control application in Azure

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(7).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(7).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Full Control application." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Redirect URI is not required for the Full Control Application. |

Near the bottom of the page, click **Register**.

![register-fullcontrol.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-28dc9d27-308d-2340-eb21-4850320062f8.png)
5. Proceed to Obtain Authentication Credentials in Microsoft SharePoint Online Cloud.

#### Step 2 - Obtain authentication credentials for the Postman token

Perform the following steps to obtain the Authentication Credentials to use later for Postman:

1. **Obtain Application (Client) ID**
  1. On the left sidebar, click **Overview.**
  2. On the **Overview** page, record the **Application (Client) ID** by clicking the "Copy to Clipboard" icon for later use in the Postman access Token.

![Full-Clientid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4a83dce-6327-22a7-0e9c-6ae8c651a54d.png)
2. **Configure application secret:**
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**.
  2. On the **Certificates & secrets** page, click **New client secret**.
  3. Click **Add** to add the secret to the list.
  4. On the **Add a client secret** popup, enter a description for the secret, for example, “Full Control app secret for Postman”, and choose an expiration term. We recommend one year.

![full-secret-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d1e0fc2-ee6a-6d66-21e8-7ef5e82f2113.png)
  5. Under the **Client secrets** tab, record the new client secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

Record it for later use in the Postman access Token.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d(3).png)
3. Proceed to Configure Full control application permissions.

#### 3 - Configure Full Control application permissions.

Perform the following steps to configure Full Control application Permissions:

1. **Configure Graph API Permissions:**
  1. In the left-hand navigation pane, select **API Permissions**.
  2. On the **API Permissions** page, click **Add a permission**.
  3. On the **Request API Permissions** right side panel, click **Microsoft Graph** > **Application Permissions**.

![Full-GraphAPI.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c91b77c1-027b-ebbd-23fc-f4fbf1925a7b.png)
  4. Search and mark the checkbox for the **Sites.FullControl.All** permission.

![full-app-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0fe07582-2fe4-b4a2-863f-ee21178c3014.png)
  5. Click **Add Permissions**.
2. **Grant admin consent:**
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

> [!NOTE]
> **Note**
> 
> Grant admin consent is required to access the sites collection through Postman.

![Full-grant-consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc8b8230-9c31-ed50-feaa-14516dc9bf6d.png)
3. Proceed to Grant sites access to Selective Sites Access application

#### 3. Grant sites access to Selective Sites Access application

To grant site access to Selective Sites Access application:

1. Get access token for full control application credentials
2. GET API call to fetch sites list
  1. Record Site IDs for sites you want to give access
3. For each site recorded, make Post API calls to grant permissions to the site with token fetch.

Perform the following procedure to fetch the sites in Full control application through Postman and assign Permissions.

#### Get an access token for the Full Control application credentials

1. Log in to your Postman application.
2. On the top, click **New** > **Collection** to create a new collection in SharePoint Workspace.

![Collection-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca25e693-67e3-6bc3-765b-6ac1d3f78374.png)
3. On the new collection page, add the following information:
  1. Enter a convenient name for the collection. See the example below.

*SharePoint Collection*
  2. Click the **Authorization** tab.
  3. Select **OAuth 2.0** from the **Auth Type** menu.

![collection-name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2155cb9c-11a1-0f76-bee7-adf2b60c1c05.png)
  4. Scroll down to the **Configure New Token** section, and configure the following parameters.

| Parameters | Description |
| --- | --- |
| Token Name | Enter a name that helps you identify the app Token. See the example below. *SharePoint Full Control App Token* |
| Grant type | Select **Client Credentials** from the menu |
| Access Token URL | Add your Microsoft Entra ID domain to this URL and paste it here. See the example below. *https://login.microsoftonline.com/****<your-domain>****/oauth2/v2.0/Token* |
| Client ID | Enter the Client ID of the Full Control application you saved above in Step 2 - Obtain authentication credentials for Postman token. |
| Client Secret | Enter the Client Secret of the Full Control application you saved above in Step 2 - Obtain authentication credentials for Postman token. |
| Scope | Add the following URL to the Scope text field. *https://graph.microsoft.com/.default* |
| Client Authentication | Select **Send as Basic Auth Header** from the menu. |

![get-access-token.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-93a7be45-742c-f13f-fede-02b403398b3f.png)
  5. Click the **Get New Access Token**.
  6. On the **Get new access Token** popup, click **Proceed**.
  7. On the **MANAGE ACCESS TOKENS** popup, click **Use Token**.

![Use-Token-btn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-80602e5c-cbc0-7889-2721-da251f17c609.png)

#### GET API call to fetch the sites list

1. On the left sidebar, click on your newly created SharePoint collection, and select **Add a request** from the menu.

![add-request.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-89bfc9c3-f44a-749d-77fa-c1cb63f4a8df.png)
2. On the **New Request** page, configure the following information:
  1. Add the following URL in the **GET** field to list all the sites in your SharePoint account

*https://graph.microsoft.com/v1.0/sites?top=9999*
  2. Under the **Auth** tab, select the **Inherit auth from parent** from the **Auth Type** menu.
  3. On the top right, click **Send**.

![GET-request.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b3ea84b-2541-f94a-a893-72460e410d3b.png)
  4. It gets all the listed sites in your SharePoint account, as shown below. Save the **Site ID** to record for later use in creating the sites list CSV file.

![list-of-sites.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba02091c-8794-c98a-52cd-b988eb730344.png)

#### Make Post API calls to grant permissions to each site

1. On the left sidebar, click options (**three dots**) > **Add request**.

![post-add-request.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-29f3fcf4-023e-475f-4005-2df6fbab6082.png)
2. Choose **POST** from the request menu. ![post-request-option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ebe8071-59ab-f476-a3d0-9fea331376f9.png)
3. In the **POST** field, paste the following URL, including the Site ID generated from the Fetch the list of sites mentioned above. See the example below.

*https://graph.microsoft.com/v1.0/sites/****<site-id>****/Permissions*
4. You can set permissions for each site by updating the request body for the above API based on the use case.

| Use case | Value in POST request body |
| --- | --- |
| Discovery scan (SDI) and Inventory scan | "`roles": "read"​​` |
| Entitlements Scan | `​"roles": "fullcontrol"` |
| Files Quarantine | `"roles": "write"` |

To set permission for each site:
  1. On the POST request page, choose **body** > **raw** > **JSON**.

![Json-site-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-705b0f26-74e0-65d2-5dba-3a0ce02a064d.png)
  2. Paste the following code into the request body.

```plaintext
{
 "roles": ["write"],
 "grantedToIdentities": [{
   "application": {
     "id": "Add your application's client ID",
     "displayName": "Sharepoint Test App"
   }
 }]
}
```
  3. Change the role to read, write, or fullcontrol depending on the following use cases quarantine policy.

![read_permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74359010-8f61-31e1-31d0-9e30793879fa.png)
    - For file quarantine, add “**write**” in the role.
    - For those without quarantine access, add “**read**” in the role.
    - For entitlement scans, add "**Full Control**" in the role.
  4. Replace the **Add your application's client ID** text in the request body with the Client ID generated above in Obtain authentication Credentials of Selective Sites Access application.
5. Click **Send**.

It generates the following response.

![send-btn-post.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8e1dad42-5146-b40d-151d-0239916093f7.png)
6. Repeat the POST request procedure for each site you want add in the CSV file.

#### 4. Creating a CSV file for sites generated from Postman

> [!WARNING]
> **Important**
> 
> We assume you have completed the procedures mentioned above. We recommend you add 100 Site IDs for each CSV file. You must enter the Side ID for each entry on a new line.

1. Create a list of SharePoint sites and enter the Site ID generated in Fetch sites through GET request in Postman for each entry in the CSV file.
2. Follow the following format for each entry. Each contains a single Column Site ID with quotes, as shown in the example below.

![csv-format.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5219bcfb-2658-129c-2e72-5fed70eb6f7d.png)

Each site ID has the three elements separated by commas. The three elements are in the following sequence: hostname, siteGUID, webGUID.

```plaintext
yourdomain.sharepoint.com,2481752e-e36e-41c1-84b4-5b887b68c8a4,1bf6a54a-aa7f-4db0-81d7-a3f754bcb53a
```
3. Save the CSV file to use it later for connector activation.

#### Connector activation credentials

Once you complete registration and assign Permissions in both Azure applications, make sure you have the following Credentials:

- OAuth and Certificate-based Credentials.
- CSV file for granted sites you created.

Proceed to [Connecting Microsoft 365 SharePoint Online (Self Hosted) with Securiti](/latest/docs/new-ui-connecting-microsoft-365-sharepoint-online-self-hosted-with-securiti).
