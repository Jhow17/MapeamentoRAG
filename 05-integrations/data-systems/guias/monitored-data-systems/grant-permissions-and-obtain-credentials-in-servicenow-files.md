---
title: "Grant permissions and obtain credentials in ServiceNow Files"
slug: "grant-permissions-and-obtain-credentials-in-servicenow-files"
updated: 2026-07-14T06:25:00Z
published: 2026-07-14T06:25:00Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-servicenow-files"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in ServiceNow Files

This document contains information about the following:

1. (Optional) Verify the OAuth Configuration for your Instance in ServiceNow.
2. (Optional) Configure Instance settings for ServiceNow.
3. REST API Access permission.

> [!NOTE]
> **Note**
> 
> Before proceeding with Authentication, we assume you have a ServiceNow Instance running or have access to the app's admin to obtain the necessary Permissions for activating the Connector.
> 
> If you are not the admin, see [Configuration steps for non-admin users in ServiceNow Files](/latest/docs/configuration-steps-for-non-admin-users-in-servicenow-files) on assigning roles and creating Table exceptions.

> [!WARNING]
> **Important**
> 
> Steps 1 and 2 apply only when you want to activate the Connector using the OAuth-based Authentication method.

1. To verify the OAuth Configuration for your Instance:
  1. On the left sidebar, search for the Plug-ins section and click **Plug-ins**.

![ServiceNow_PlugIn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-29d54707-e540-f265-9396-6a9ab5678b32(1).png)
  2. On the list of potentially installable plug-ins for your system, search for **OAuth 2.0**.

![ServiceNow_PlugIn1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2555b160-2635-02b1-2a67-b551edb259ad(1).png)
  3. Verify that the status for the OAuth 2.0 plug-in is displaying an **Active** message.

![ServiceNow_PlugIn2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25f6b1c3-a11c-6f13-7731-daa229565b84(1).png)
2. To configure Instance settings:
  1. Navigate back to the **System Administration** page.

![ServiceNow_SYSAdmin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d03be335-9de4-396a-4ee4-afb792e284a3(1).png)
  2. In the left sidebar, search for "**OAuth**", which then shows the **Application Registry**. Click **New** on the top bar to create the required OAuth-based application for Connector Activation.

![ServiceNow_InstanceList.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08a31fed-d474-853b-edbf-791da47cb16b(1).png)
  3. Click **Create an OAuth API endpoint for External Clients**.

![ServiceNow_NewOAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22133d19-5ac0-b2fc-5a35-e9c5e071cf9f(1).png)
  4. Apply the following settings and click **Submit**:

| Name | Enter an appropriate name for your application. |
| --- | --- |
| Client ID | A Client ID is automatically generated after you start the application creation process. |
| Client Secret | A Client Secret is automatically generated after you complete the application creation process. |
| Redirect URL | - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

![ServiceNow_NewOAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f4af20b-c17a-1035-d5d5-767d362dc16c(1).png)

After you create the OAuth application, ServiceNow redirects you to the **Application Registry**, where you can see the newly created application as shown below:

![ServiceNow_OAuthEnd.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0bb52c1-8c04-0717-764d-63221b0c3a54(1).png)
  5. Click the highlighted application (in this case, "*DemonstrativeExample*").

ServiceNow redirects you to the details page for your new application.
  6. Record the **Client ID** and newly generated **Client Secret** to use later.

> [!NOTE]
> **Note**
> 
> We recommend you increase the Refresh Token Lifespan to "*864,000,000*."

![ServiceNow_ExistingOAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a15a24e-0776-e838-de96-fabb688dcb21(1).png)
3. > [!WARNING]
> **Important**
> 
> After you have changed Permissions, it may take some time to reflect.

To configure minimum Permissions (REST API Access):
  1. On the ServiceNow dashboard, in the left-hand menu, select **Organization > Users**. Then in the "User ID" Column, select a user by clicking on it.

![organization_users.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-94f5a2cb-ca3d-032e-1f73-94e326174827.png)
  2. Near the bottom of the page, select the "Roles" tab and click **Edit**.

![roles_edit.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7c54026-17ed-5a2f-d78d-dcf860f98b1c.png)
  3. On the Edit Members page, from "Collection", search and select <***snc_platform_rest_api_access***> and add it to the Roles List on the right.

![assign_role.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83ca3eac-06cf-a5d2-c3b1-4a37091e3d8b.png)

Click **Save**
  4. On the dashboard, in the left-hand menu, select **System Definition > Tables**.

In the right side window, select a Table by clicking its label.

![tables_label.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d7a45644-6986-b6d3-8570-81ad3828ba6c.png)
  5. On the following page, select the "Application Access" tab, then mark the checkboxes for **Can read** and **Allow access to this Table via web services**.

![access_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-514d4eb8-4042-eef9-d5ef-4f13ff91d9b4.png)

Repeat the step if you have more than one Table.
  6. (Optional) If you have previously enabled access controls for a Table(s), you have to assign that role to the user

Repeat the steps in <***3a***> and <***b***>, and this time, in Collection, search and select the Table name(s) for which you have created the access control, as shown in the example below. Then save your changes.

![access_controls.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-df85d4cb-1f51-754f-9b2e-6d7093b66180.png)

![assign_role_to_the_user.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6154c26-0a1a-10fe-3a0a-bc54e352feca.png)
4. Proceed to [Connecting ServiceNow Files with Securiti](/latest/docs/connecting-servicenow-files-with-securiti).
