---
title: "Grant permissions and obtain credentials in Microsoft 365 Lists"
slug: "grant-permissions-and-obtain-credentials-in-microsoft-365-lists"
updated: 2026-07-31T06:12:25Z
published: 2026-07-31T06:12:25Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-microsoft-365-lists"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Microsoft 365 Lists

Use the matching procedure below to grant Permissions and obtain Credentials in Microsoft 365 Lists Connector for successful Activation in Securiti.

> [!WARNING]
> **Important**
> 
> We assume you own your Microsoft 365 account and run a Microsoft Lists Instance with admin privileges.

Microsoft 365 Lists uses the following Credentials for Connector Activation:

- Tenant Name
- Domain or Account ID
- Client ID
- Certificate Thumbprint
- Private Key

#### Minimum API permissions for Microsoft 365 Lists

The minimum API Permissions required for the APIs used in this Connector are as follows:

**Graph APIs:**

- Sites.Read.All
- User.Read.All
- Files.Read.All
- Group.Read.All

**SharePoint APIs:**

- Sites.Read.All

Refer to the section below to configure Permissions and acquire Credentials in the Microsoft 365 Lists app.

#### Creating an app in Microsoft 365 Lists

1. Login to [Microsoft Entra ID](https://entra.microsoft.com) with an admin account.

> [!NOTE]
> **Note**
> 
> Azure Active Directory (Azure AD) is now Microsoft Entra ID. Refer to the [official documentation](https://learn.microsoft.com/en-us/entra/fundamentals/new-name) to read about this announcement.
2. **Obtain Tenent ID, Domain, and Tenant Name**
  1. On the top left, click **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation:

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(4).png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain.
  4. Record the **Tenant Name** from **Primary Domain** for the Connector Activation.

**Tenant Name** is initial part of the domain. If *testdomain.onmicrosoft.com* is the domain. **testdomain** is the Tenant Name.
3. Follow the procedure below to register your app and acquire **Client ID** .
  1. On the same page, under the **Identity** menu, expand the **Applications** menu and click **App registrations**.

![m365lists_newss.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e3bba4e9-4dcd-4dd7-f6f3-453554078934.png)
  2. Click **New registrations** to register a new application.

![M365lists_newregister_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5b136ff-3b61-42ed-ecea-04e68b6d5343.png)
  3. Set appropriate values to the following inputs.

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Microsoft Lists Connector." |
| Supported Account types | Choose a supported account according to your requirement. For example, choose **Accounts in this organization directory** for single tenant usage. |
| Redirect URI | Choose Web from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - US2 Cloud: `https://app.us2.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
  4. Near the bottom of the page, click **Register**. Microsoft Entra ID displays page for your new application.

![M365lists_register_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-daf91be5-16b3-d6e6-77c8-3a28b5f7dee4.png)
  5. From the **Overview** tab of the registered application, record the following Credentials for later use.

![M365lists_clientID_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85c16ca7-21cb-bb19-21fe-a68a5a9cbe8e.png)
    - Application (Client) ID as Client ID
4. Follow the procedure below to generate the self-signed Public key (Certificate) and Private key which are needed for the application secret.
  1. Open the terminal (console) on your machine, and execute the following command

```plaintext
openssl req -x509 -newkey rsa:4096 -sha256 -keyout private-auth-key.pem -out public-auth-cert.pem -nodes -days 730
```

> [!NOTE]
> **Note**
> 
> We recommend using OpenSSL to generate the self-signed Public key (Certificate) and Private key. The keys generated by the command have a two-year validity. Consult the [Microsoft documentation](https://learn.microsoft.com/en-us/azure/key-vault/secrets/tutorial-rotation-dual?tabs=azure-cli) for guidelines on creating and rotating secrets.
  2. Enter the following information after running the command.

> [!NOTE]
> **Note**
> 
> Enter a value for each parameter and ensure it is unique. This uniqueness is crucial for generating a distinct Certificate and key for every app registration setup. Without unique parameters, the generated Certificate and key will not be unique.

![M365lists_certcommand_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-614939c4-a57b-2545-d62d-ccc5a84160d3.png)
    - Country name (e.g., 2-letter code = US)
    - State or Province name (e.g., full name = New York)
    - Locality name (e.g., city = New York)
    - Organization name (e.g., company = Securiti)
    - Organizational unit name (e.g., section = Platform)
    - Common name (e.g., fully qualified hostname = www.securiti.ai)
    - Email address (e.g., securiti@admin.com)
  3. Record the Public key (Certificate) and Private key for later use.

The keys are generated in the same path you have opened in the terminal once you supply information to the specified parameters. See an example below.

The path */users/john.doe/Certificate/* contains two **public-auth-cert.pem** and **private-auth-key.pem.** files for the generated keys.
  4. Click **Add a Certificate or secret** to configure the application secret.

![M365lists_addcert_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bc61ecd2-f891-0cd6-180d-cc1093f2c550.png)
  5. In the **Certificates & secrets** tab, select **Certificates** and click **Upload Certificate** to upload the Public key (Certificate) generated in the previous steps. It opens another window to select a Public key (Certificate) from your machine.

![M365lists_uploadcert_9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-43d9b669-59d3-c55f-3c94-788947e1a250.png)
  6. Record the following information once the Public key (Certificate) is uploaded.

![M365lists_thumbprint_10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad274dfa-718f-4484-5d09-035c390d4dbe.png)
    - Thumbprint as Certificate Thumbprint
5. Click **API Permissions** to add the necessary Permissions to the registered application

![M365lists_addpermissions_11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-520761f6-b742-054c-2230-187dd865317b.png)
6. Follow the procedure below to configure the Graph API Permissions.
  1. From the left navigation menu, click **API Permissions** to add the necessary Permissions to the registered application.
  2. On the **Request API Permissions** page, select **Microsoft Graph** from the list and configure the following Graph API Permissions as **Application Permissions** type.

![M365lists_graphpermissions_12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-805526b6-e97c-e5f4-5041-b420b6b75492.png)
    - Sites.Read.All
    - User.Read.All
    - Files.Read.All
    - Group.Read.All
  3. Click **Add Permissions** after selecting all the required Permissions.
7. Follow the procedure below to configure the SharePoint Permissions.
  1. Add SharePoint Permissions by clicking **API Permissions**.
  2. On the **Request API Permissions** page, select **SharePoint** from the list.
  3. Add the following Permissions as **Application Permissions** type.

![M365lists_sharepointpermissions_13.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57f4cd8b-234c-e1e5-cdbe-c6ca68893e7c.png)
    - Sites.Read.All
  4. Click **Add Permissions** to add these Permissions.
8. Click on **Grant admin consent** to grant admin privileges to the Permissions once all the stated Permissions are added.

![M365lists_grantconsent_14.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3b0b656-5ae5-edc2-c47a-e5e628988b6d.png)
9. Proceed to [Connect Microsoft 365 Lists connector with Securiti](/latest/docs/connecting-microsoft-365-lists-connector-with-securiti).
