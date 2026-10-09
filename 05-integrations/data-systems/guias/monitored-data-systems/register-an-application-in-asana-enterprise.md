---
title: "Register an application in Asana Enterprise"
slug: "register-an-application-in-asana-enterprise"
updated: 2026-07-04T22:20:36Z
published: 2026-07-04T22:20:36Z
canonical: "helpcenter.securiti.ai/register-an-application-in-asana-enterprise"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Register an application in Asana Enterprise

To integrate Securiti with Asana Enterprise for DSR automation, you first register your application with Asana to receive an API key. Asana Enterprise authenticates using Personal Access Tokens (PATs) or a Service Account Token.

> [!NOTE]
> **Note**
> 
> PAT and Service Account authentication differ from each other for data access.
> 
> - PATs restrict access to data visible to the account holder, excluding private projects, tasks, and other scopes.
> - A Service Account, however, grants access to all organizational data.

To register a new application in Asana Enterprise using PAT authentication:

1. Log in to your Asana account, https://app.asana.com/-/login.
2. On the top right side of the menu, click **Settings**.

![asanaenterprise_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-40af9fbb-4754-4553-34a4-ecee4cc79f8f.png)
3. From the **Apps** tab, click **Manage Developer Apps**.

![asanaenterprise_manage_developer_apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e1dd03ee-f5a5-9d40-de62-cb262ba07f10.png)
4. Under **Personal access tokens**, click **Create new token**.

![asanaenterprise_createnewtoken.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba712ba7-5c18-02de-8f47-12824cc54662.png)
5. Choose any name for the token and click the checkbox to agree to Asana API Terms, then click **Create token**.
6. Record the displayed token and store to use later when you activate the connector. The copied token is your API key.

![asanaenterprise_copytoken.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14f46200-2e24-8131-c447-af8e91244bea.png)

To register a new application in Asana Enterprise using Service Account Token authentication:

> [!NOTE]
> **Important**
> 
> You must be a super admin to add a service account. [Follow these steps to create a super admin](https://help.asana.com/hc/en-us/articles/14141552580635-Admin-and-super-admin-roles-in-Asana#gl-adding-admin) or add a new one.

1. Log in to Asana with your organizational admin account.
2. On the upper right corner, click on your profile photo and select **Admin Console** from the menu.

![asanaenterprise_admin_console.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-23e4a56f-5efd-c7fd-071c-6e22b1bd9127.png)
3. From your super admin account, navigate to the **Apps** tab in the admin console and click **Service Accounts**.

![asanaenterprise_manageapps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75385ab7-80e2-25d3-1b35-33f2e2f71048.png)
4. Click **Add Service Account** and save the access token for the created service account to use later when activating the connector.

![asanaenterprise_add_serviceaccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-96af24ef-f581-01c2-9696-80771fa09b2a.png)
