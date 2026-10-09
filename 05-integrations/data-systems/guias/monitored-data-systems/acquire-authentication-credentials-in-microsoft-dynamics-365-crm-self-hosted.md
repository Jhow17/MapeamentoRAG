---
title: "Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Self-hosted)"
slug: "acquire-authentication-credentials-in-microsoft-dynamics-365-crm-self-hosted"
updated: 2026-07-28T11:09:54Z
published: 2026-07-28T21:00:00Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-microsoft-dynamics-365-crm-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Microsoft Dynamics 365 CRM Suite (Self-hosted)

> [!NOTE]
> **Note**
> 
> Securiti lets you create multiple instances for all Microsoft 365 data systems, using the same Credentials. Hence, removing any restrictions for checking uniqueness in case of duplicate connectors.

Microsoft Dynamics 365 CRM Suite supports the following authentication methods to connect and authenticate with Securiti.

| Authentication method | Authentication Credentials |
| --- | --- |
| OAuth | - Account - Directory (or Tenant) ID - Client ID - Client Secret |

Follow the procedure below to acquire your Microsoft Dynamics 365 CRM Suite authentication credentials.

### Register OAuth application on Azure

1. Visit [portal.azure.com](https://portal.azure.com/)
2. Select **Azure Active Directory > App registrations** on the Azure admin console, as shown below.

![azure_active_directory.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1925fa3-80ff-fdbd-c258-ce8d33bcd786.png)

![app_registrations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e7e51810-260b-d4fa-075b-459bbb12e4fb.png)
3. Click **New registration**, as shown below.

![new_registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5139fe33-51cd-1e37-d8f9-067ccfbfeb65.png)
4. On the **Registration an application** page, apply these settings.

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti Connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose Web from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - US2 Cloud: `https://app.us2.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

![enter_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ee801e98-79c8-7095-e1ea-166c8daf2570.png)

Click **Register.**
5. On the following page, under **Essentials**, record the "Application (client) ID", as shown below.

You can record the Tenant ID in this step or in the next step below.

![essentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36069e0d-4c53-4598-f94d-ebaa096643cc.png)
6. Obtain **Tenant ID or Domain:**
  1. On the top left, click **hamburger** icon.
  2. On the left sidebar, click **Microsoft Entra ID**.

It opens the **Overview** page.
  3. On the **Overview** page, record one of the following for later use in the Connector Activation:

![Entria-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ea08cd0-f2eb-6d0d-6b9f-0db29a1f2976(1).png)
    - **Tenant ID**

> [!NOTE]
> **Note**
> 
> Tenant ID is also referred to as Directory ID or Organization ID in Microsoft.
    - **Primary Domain** as Domain.
7. Select **Certificate & secrets** in the left-hand menu and click **New client secret**.

![certificates_and_secrets.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4ed5901-fbb7-a684-d005-c3ce5d057845.png)
8. To the right, enter a description and an expiry date on the flyout menu, as shown below.

![new_client_description___expiry_date.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e10a51dd-a673-fb1d-ebeb-6ee1fc1f0889.png)

Click **Add.**
9. Record the client secret value to use later, as shown below.

![client_secret_value.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f4ad313-32c2-b5b4-86d7-5b809dd87aeb.png)

### Configure OAuth application permissions

1. On the Azure homepage, select **API Permissions** and then **Add a permission** under Configured Permissions, as shown below.

![api_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b8c2627-5aa6-8adb-c574-d79be2cc1de5.png)
2. To the right, select **Microsoft Graph > Delegated Permissions** on the flyout menu, as shown below.

![request_api_permissions_flyout_menu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b124b3bc-1f12-0e6f-0e3e-d59944ef3cf0.png)

![microsoft_graph_delegated_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-13927cf8-9eb8-ded9-6464-30bd12f05c1d.png)
3. From the list of Permissions, select **User.Read**, as shown below.

![user_read.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a8c5802-83f3-259a-5482-e945fd0f1d0e.png)

Click **Add Permissions.**
4. Now select **Dynamics CRM** on the "Request API Permissions" flyout menu, and in the list of Permissions, choose and add **user_impersonation**, as shown below.

![dynamics_crm_card.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2deb5d1a-f136-1509-58c8-c3e06c16195e.png)

![user_impersonation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36b884cb-14a1-74b6-b118-d5dbcd6f47c6.png)
5. Under Configured Permissions, click **Grant admin consent for *<application name>***, as shown below.

![grant_admin_consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f5538ae-4c98-04ef-9a2c-ab4cc232050b.png)

Proceed to [Configure the user in the Power Platform app for Self-hosted connector](/latest/docs/configure-the-user-in-the-power-platform-app).
