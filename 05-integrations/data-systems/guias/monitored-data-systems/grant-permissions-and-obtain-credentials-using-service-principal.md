---
title: "Grant Permissions and obtain credentials using Service Principal for Power BI Service"
slug: "grant-permissions-and-obtain-credentials-using-service-principal"
updated: 2026-07-31T09:45:47Z
published: 2026-07-31T09:45:47Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-using-service-principal"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant Permissions and obtain credentials using Service Principal for Power BI Service

> [!WARNING]
> Important
> 
> Securiti release 1.143 replaces manual admin authentication for the Power BI Service with Service Principal–based authentication. To create or reconfigure the Power BI Service connector using the Service Principal account, you must follow the procedure described in this article.

Follow the steps mentioned in this article to obtain Power BI data system connector authentication credentials using a Service Principal.

## Prerequisites

We assume you are an admin before creating or modifying a Power BI Service app so you can configure the required application scope(s).

## Register an application and record credentials

The Power BI Service Data system requires Client ID and Secret to establish a successful Connection in Securiti

1. In the [Azure Portal](https://portal.azure.com/?l=en.en-us), log in to your admin account.
2. On the homepage, search and click **App registrations**.

![search-app-reg.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bc5eaa23-f4a6-55c6-b6f8-200e9eb37a5a.png)
3. On the **App registration** page, click **New registration**.

![new-reg.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05c16f5a-04eb-d0bd-3505-c660fce1f7eb.png)
4. On the **Register an application** page, apply the following settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name for your Power BI app. |
| Supported Account types | Mark the radio button for Single tenant or multi-tenant as per your requirement. |
| Redirect URl | Choose **Web** from the Select a platform menu and enter the redirect URL that applies: - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
5. Click **Register**, It redirects you to the Overview page where Credentials are available.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(9).png)
6. On the **Overview** page, record the following Credentials for Connector Activation.
  - Directory (Tenant) ID
  - Application (Client) ID

![appid-tenid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3c9f58a2-eac8-b9e2-792d-a3c102c16e4e.png)
7. **Configure application secret:**
  1. In the left sidebar for the newly created application, choose **Manage** > **Certificates & secrets**. On the "Certificates & secrets" page, click **+ New client secret**.

![add-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3361b409-cc16-cf4d-4019-16f1c95d2129.png)
  2. On the **Add a client secret** popup:
    - Enter a description for the secret, for example, “Power Bi Connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list.

![secret-popupo.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b19f74c-33b7-5aed-4c86-a192afd0a0b1.png)
  3. Under the **Client secrets** tab, copy the secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-client-secret1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fbc72dd-7b7a-7e06-05e6-52303921fb0d(6).png)
  4. Record the new client secret to use in the Connector Activation.

## Create a Security Group

> [!NOTE]
> Note
> 
> Power BI does not allow you to add an individual Service Principal directly to the admin settings; it must be part of a security group.

To create a Security Group:

1. In the [Azure Portal](https://portal.azure.com/?l=en.en-us), go to **Microsoft Entra ID** > **Groups** > **New Group.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-23 at 4.20.51 PM.png)
2. In the Group Type section, select **Security** as a type.
3. In the Group Name section, type a group name such as **PowerBI-Service-Principals.**
4. In the **Add Members** section, search and select the application name you used while registering an application.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 8.40.35 AM.png)
5. Select **Create**, and your group is created.

## Enable the Service Principal access in Power BI

> [!NOTE]
> Note
> 
> A Power BI administrator must enable the tenant-level setting to let these identities to use the APIs.

1. In the [Power BI](https://app.powerbi.com/) service, go to **Settings** > **Admin Portal** > **Tenant Settings.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 8.44.58 AM.png)
2. In the **Tenant Settings** section, scroll down to **Admin API settings.**
3. Expand **Service principals can access read-only admin APIs**, toggle to **Enabled.**
  1. From the **Apply to** section, select **Specific security group** and choose the group you created earlier.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 8.52.24 AM.png)
4. Expand **Enhance admin APIs responses with detailed metadata**, toggle to **Enabled.**
  1. From the **Apply to** section, select **Specific security group** and choose the group you created earlier.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 8.56.16 AM.png)
5. Click **Apply.**

> [!NOTE]
> Note
> 
> It may take upto 15 minutes for the required changes to be propagated.

## Grant workspace access and permissions

To grant service principal access to see specific reports or datasets:

1. In the [Power BI](https://app.powerbi.com/) workspace, click **Manage access**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 8.59.40 AM.png)
2. On the Manage access tab, click **Add people or groups.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 9.02.09 AM.png)
3. Search for your **Application Name** or the **Security Group** that you configured earlier in this article.
4. Assign a role to the selected option, and click **Add.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 9.05.21 AM.png)

> [!WARNING]
> Important
> 
> You must have at least Contributor role for most API tasks like refreshing datasets or uploading reports.

> [!NOTE]
> Tip
> 
> If your application needs to read information about users in your tenant (and not just Power BI data), you must change the permissions in the [Azure Portal](https://portal.azure.com/?l=en.en-us):
> 
> 1. Go to **App Registrations** > Your App > **API permissions.**
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 9.12.22 AM.png)
> 2. Click **Add a Permission** > **Microsoft Graph.**
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 9.17.40 AM.png)
> 3. Select **Application permissions**, and search for `User.Read.All`**.**
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 9.16.29 AM.png)
> 
> 
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-25 at 9.19.08 AM.png)
> 4. Click **Add permissions,** and **Grant admin consent for (your tenant).**

For more information, see Microsoft’s [Embed Power BI content with service principal and an application secret](https://learn.microsoft.com/en-us/power-bi/developer/embedded/embed-service-principal?tabs=azure-portal).

Proceed to [Connecting Power BI Service with Securiti](/latest/docs/connecting-power-bi-service-with-securiti).
