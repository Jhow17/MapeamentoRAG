---
title: "Grant permissions and obtain credentials in Microsoft Teams"
slug: "grant-permissions-and-obtain-credentials-in-microsoft-teams"
updated: 2026-09-21T21:00:01Z
published: 2026-09-21T21:00:01Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-microsoft-teams"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Microsoft Teams

> [!WARNING]
> **Important**
> 
> We assume you own your Office 365 account and run a Microsoft Teams Instance with admin privileges.

Use the procedure below to grant Permissions and obtain Credentials in Microsoft Teams connector for successful Activation in Securiti.

#### Step 1 - Register an application in the Azure Portal.

> [!NOTE]
> **Note**
> 
> To enable the connector for Microsoft Teams, you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring Permissions that allow it to access Team resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(10).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(10).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti Connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose Web from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - US2 Cloud: `https://app.us2.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(8).png)

> [!NOTE]
> **Note**
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the Authentication section.
5. Refer to the matching procedure if you miss adding the redirect URL while registering an application.
  1. On the left sidebar, choose **Manage** > **Authentication**.

![Screenshot_2024-08-23_at_2_02_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52d46981-45dc-d8ae-0349-6ccf62b190c2(5).png)
  2. On the **Authentication** page, click **Add a platform**.
  3. On the **Configure platforms** popup, click **Web**.

![Screenshot_2024-08-23_at_2_02_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa08c31b-c9de-c9c1-deb5-57fbc44cb6ed(5).png)
  4. On the following popup, add the **Redirect URl** from the above Table, and click **Configure**.

#### Step 2 - Obtain authentication credentials

This section cover the steps to obtain authentication credentials of Microsoft Teams connector for the following supported Authentication Types.

**Client Secret**

Perform the following steps to obtain authentication credentials for connector activation using **Client Secret** as **Authentication** **Type**:

1. **Obtain Tenant ID or Domain**
  1. In the Azure Portal, on the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  2. On the **Overview** page, record the **Tenant ID** for later use in the connector activation, as shown below.

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(5).png)
2. **Obtain Client ID**
  1. On the left sidebar, click **Overview**.
  2. Record the Application (Client) ID by copying it

![OneDrive-Appid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6979b37b-edaf-2307-0d86-34e9b8f979fa.png)
3. **Obtain application secret:**
  1. In the left-hand navigation pane for the newly created application, select **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **New client secret**.

![Onedrive-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3495f611-7b04-f7fb-24c0-db31d33fb404.png)
  2. On the **Add a client secret** popup, add the following information:
    - Enter a description for the secret, for example, “OneDrive connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.

![add-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d84065c5-55f2-f582-7058-988b0070fe02.png)
  3. Under the **Client secrets** tab, record the new client secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d.png)

**Client Certificate**

Perform the following steps to obtain authentication credentials for connector activation using **Client Certificate** as **Authentication** **Type**:

1. **Obtain Tenant ID or Domain**
  1. In the Azure Portal, on the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  2. On the **Overview** page, record one of the following for later use in the connector activation, as shown below.

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(5).png)
    - **Tenant ID**.

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** to be used as Tenant Name. For example; 'contoso' will be the Tenant Name for the domain 'contoso.onmicrosoft.com'.
2. **Obtain Client ID**
  1. In the Azure portal, from the left sidebar, click **Overview**.
  2. Record the **Application (Client) ID** by copying it, as shown below.

![OneDrive-Appid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6979b37b-edaf-2307-0d86-34e9b8f979fa.png)
3. **Obtain Certificate**
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
| Organization name | Enter your organization name in place of *ABC*. See the example below Securiti |
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
> The private key file and Certificate Thumbprint are required for configuring Entitlement Scan for Microsoft 365 SharePoint Online connector. Save this information to use for connector activation.
    - On the **Certificates & secrets** page, record the **Thumbprint** as the Certificate to use it for connector activation.

#### Step 3 - Configure Microsoft Teams Self-hosted permissions.

Perform the following steps to configure Microsoft Teams Self-hosted Permissions in Azure Portal:

1. **Configure Graph API Permissions:**
  1. In the left-hand navigation pane, select **API Permissions** and click **Add a permission**.

![API-Perm-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7943028a-6ffb-ac75-1cee-ff9443d77acf.png)
  2. On the **Request API Permissions** page, click **Microsoft Graph** , then click **Application Permissions**.

![API-perm-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-45246fc3-e56d-b90d-3919-868e7a7a8189.png)

![Appliacation_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d5d28de-22b1-8d06-84aa-51003ca75f40.png)
  3. Scroll down to **Select Permissions** section, expand the various areas, and mark the checkboxes for following Microsoft Graph API Application Permissions:

![mark-permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-febaf8d0-370d-7750-62b6-99a169ef3c13(4).png)
    - Users.Read.All
    - Team.ReadBasic.All
    - Channel.ReadBasic.All
    - ChannelMessage.Read.All
    - Chat.ReadBasic.All
    - Chat.Read.All
    - TeamMember.Read.All
    - ChannelMember.Read.All
  4. When you have enabled the said Permissions, near the bottom of the Permissions box, click **Add Permissions**.

It redirects you to API Permissions page where you see the following Permissions.

![NG-perm-list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f490df7-c7fe-33ca-033e-f09a5954e11f.png)
2. **Grant admin consent:**
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.

![Add-consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60905644-e961-66e3-f243-f62401189652.png)
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

![Grant-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3bd8030-1983-0106-8fc4-188033f2799f.png)

The API Permissions page appears with admin consent given to all permisisons as shown below.

![Final-perm-list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-190d2834-6e13-19b2-f46d-b52922000ea4.png)
3. Proceed to [Connecting Microsoft Teams with Securiti](/latest/docs/new-ui-creating-microsoft-teams-self-hosted-connector-instance).
