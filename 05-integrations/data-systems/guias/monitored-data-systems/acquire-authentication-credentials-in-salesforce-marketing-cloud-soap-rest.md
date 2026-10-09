---
title: "Acquire authentication credentials in Salesforce Marketing Cloud (SOAP + REST)"
slug: "acquire-authentication-credentials-in-salesforce-marketing-cloud-soap-rest"
updated: 2026-07-31T11:13:40Z
published: 2026-07-31T11:13:40Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-salesforce-marketing-cloud-soap-rest"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Salesforce Marketing Cloud (SOAP + REST)

1. Log in to Salesforce Marketing Cloud.

> [!NOTE]
> **Note**
> 
> There are two schemas for Salesforce Marketing Cloud; REST and SOAP.
> 
> REST requires **Subdomain**, **Client id**, and **Secret** to activate the Connector.
> 
> In addition to "Subdomain", SOAP requires your SF Marketing Cloud login **Username** and **Password** to activate the connector.
2. On the dashboard, hover over your profile to access the "Settings" menu. Select **Setup > Apps > Installed Packages**.

![Settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-caa6cfe3-4a8f-f244-dbef-f23aaf8f8283.png)
3. On the following page, click **New** in the top-right corner, as shown below.

![Installed_Packages.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a03ed181-b5a0-ad15-46bc-6883da53f424.png)
4. In the Name field, assign a package name. Click **Save**.

![Package_Details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ca87304-6623-32cb-818e-08ef362bb3c2.png)
5. Under Components, click **Add Component** and select **API Integration**.

![Add_Component.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a0931f4f-1122-fe3f-a5fe-5c40f628fcc1.png)

![Component_API_Integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5564445b-8f6e-4f1c-54cf-8d79d1784b9d.png) Click **Next** to proceed.
6. Choose "Integration Type" as **Server-to-Server**, and click **Next**.

![Component_Server-to-Server.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39a6e60a-d9d6-5eac-701e-237a2e46c8d3.png)
7. Under **Scope**, select all the Scopes, as shown below. Then click **Save**.

![Select_Scope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-daa89e9a-557b-6f15-1f9b-6ad0660532ef.png)

![Scope_List.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cb8a3f6c-4e98-7af4-3e3f-8eeba00c3dc9.png)
8. For Subdomain:

> [!NOTE]
> **Note**
> 
> In SF Marketing Cloud (SOAP), use **Username** + **Password** instead.
  1. Go to **Administration > Setup > Installed Packages** and select the package with the "API Integration component" (created in the previous step).

The integrations details page displays your **Authentication Base URI**, **Client id**, and **Secret**.
  2. Obtain the **Subdomain** (for connector activation) from Authentication Base URI *https://SUBDOMAIN.auth.marketingcloudapis.com/*, as shown below.

![Activation_creds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bd7215e0-d5ef-9718-d53d-caa98356e647.png)
9. Copy and save the auth creds for later use.

> [!NOTE]
> **Note**
> 
> If you enter invalid creds, an error message is displayed that restricts Connector Activation.

For Authentication of SOAP web services, you must enable the username and password security setting. To enable:

1. Under the "Setup" menu on the left, select **Security > Security Settings > Username and Logins**.
2. Choose **Enable Username and Password for Web Services** from the list, as shown below.

![Enable_User_Password.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a5944127-a585-e7dc-8252-4b0de3b7a0b1.png)
3. Next, enable **API User** property in the Setup by selecting **Users > General Settings** (of the selected user), and toggle API User to **Yes**.

![Users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2b2c24c1-8902-48df-6e20-7140e0b1ea9a.png)
4. Proceed to [Connecting Salesforce Marketing Cloud (REST) with Securiti](/latest/docs/connecting-salesforce-marketing-cloud-rest-with-securiti), or [Connecting Salesforce Marketing Cloud (SOAP) with Securiti](/latest/docs/connecting-salesforce-marketing-cloud-rest-with-securiti).
