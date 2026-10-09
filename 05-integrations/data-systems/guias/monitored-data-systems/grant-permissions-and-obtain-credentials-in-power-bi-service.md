---
title: "Grant permissions and obtain credentials in Power BI Service"
slug: "grant-permissions-and-obtain-credentials-in-power-bi-service"
updated: 2026-07-31T09:44:34Z
published: 2026-07-31T09:44:34Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-power-bi-service"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Power BI Service

> [!WARNING]
> Important
> 
> Securiti release 1.143 replaces manual admin authentication for the Power BI Service with Service Principal–based authentication. To create or reconfigure the Power BI Service connector using the Service Principal account, you must follow the procedure described in [Grant Permissions and obtain credentials using Service Principal for Power BI Service](/latest/docs/optional-configure-the-service-principal-oauth-token-for-power-bi-service).

To create or reconfigure the Power BI Service connector using the Service Principal account, you must follow the procedure described below.

## Prerequisites

- We assume you are an admin before creating or modifying a Power BI Service app so you can configure required application scope(s).
- Power BI Service (Self-hosted) Data system uses the OAuth 2.0 Authentication method.
- You must configure `Tenant.Read.All` and `Dataset.Read.All` Permissions before activating the Connector.
- If the private link option is enabled, appliances should operate in the same network as the Private IP.
- We recommend you verify that the **Semantic Model Execute Queries REST API** option is enabled in the admin portal to ensure data is scanned from the tables during the Discovery scan. Note that this option is enabled by default.

## Scanning limitation

Securiti scans only the workspaces that the admin has access to, as it relies on admin-level Permissions. Personal workspaces not accessible to the admin are excluded from the scanning results.

To include Power BI workspaces in the scan, ensure they are shared with users in the organization and assigned one of the following roles:

- Viewer
- Member
- Contributor
- Admin

#### Register an application and record credentials

The Power BI Service Data system requires Client ID and Secret to establish a successful Connection in Securiti

1. Log in to your admin account Azure portal.
2. On the Azure Portal, search and click **App registrations**.

![search-app-reg.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bc5eaa23-f4a6-55c6-b6f8-200e9eb37a5a.png)
3. On the **App registration** page, click **New registration**.

![new-reg.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c16f5a-04eb-d0bd-3505-c660fce1f7eb.png)
4. On the **Register an application** page, apply the following settings, and click **Register**.

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name for your Power BI app. |
| Supported Account types | Mark the radio button for Single tenant or multi-tenant as per your requirement. |
| Redirect URl | Choose **Web** from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
  - ![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(9).png)

It redirects you to the Overview page where Credentials are available.
5. On the **Overview** page, record the following credentials for connector activation.
  - Directory Tenant) ID
  - Application (Client ID)

![appid-tenid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3c9f58a2-eac8-b9e2-792d-a3c102c16e4e.png)
6. Configure application secret:
  1. In the left sidebar for the newly created application, choose **Manage** > **Certificates & secrets**. On the **Certificates & secrets** page, click **+ New client secret**.

![add-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3361b409-cc16-cf4d-4019-16f1c95d2129.png)
  2. On the **Add a client secret** popup:
    - Enter a description for the secret, for example, “Power Bi Connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.

![secret-popupo.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b19f74c-33b7-5aed-4c86-a192afd0a0b1.png)
  3. Under the **Client secrets** tab, copy the secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d(6).png)
  4. Record the new client secret to use it Connector Activation.
7. Assign Permissions to the newly created Power Bi application:
  1. On the left sidebar, choose **API Permissions** > **Add Permission**.

![click-add-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19db09c6-10d5-8a7c-defd-1025bf7325a4.png)
  2. On the **Request API Permissions** popup, scroll down and select **Power BI Service**.

![Power-BI.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6bf28d0f-0dc8-8081-af41-7dfd235dc2bb.png)
  3. On the **Request API Permissions** popup, click **Delegated Permissions**.

![delegated-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-af5ef3e1-4de3-b240-948b-d09b987bd0c4.png)
  4. Under the **Select Permissions**, search and select the following permissions by marking the check boxes.
    - `Dataset.Read.All`
    - `Tenant.Read.All`

![select-permisisons.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-818a2446-2639-11b3-67d2-d6c7f08cd3c1.png)
  5. Click **Add Permissions**.
8. Grant admin consent.
  1. On top of the **API/ Permissions name** Table in the **API Permissions** page, click **Grant admin consent for *<yourOrganizationName>***.

![Grant-admin-consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48eee2b8-ed80-524d-2c4d-d3ef67479f1c.png)
  2. On the **Grant admin consent confirmation** popup, click **Yes** to confirm.

![consent-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea71f4d7-a59c-2b0f-cdb6-618a4eeb23ff(6).png)

The API Permissions page appears with admin consent given to all Permissions.
9. Proceed to [Connecting Power BI Service with Securiti](/latest/docs/connecting-power-bi-service-with-securiti).
