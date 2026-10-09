---
title: "Create a ServiceNow instance and obtain credentials"
slug: "create-a-servicenow-instance-and-obtain-credentials"
updated: 2026-06-11T15:02:01Z
published: 2026-06-11T15:02:01Z
canonical: "helpcenter.securiti.ai/create-a-servicenow-instance-and-obtain-credentials"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a ServiceNow instance and obtain credentials

> [!NOTE]
> **Note**
> 
> If you are using the ServiceNow Xanadu release or an earlier version, perform the following procedures before activating the ServiceNow connector in Securiti.

- [Create a connecting instance in ServiceNow](/v1/docs/create-a-servicenow-instance-and-obtain-credentials)
- [Verify OAuth configuration for your instance](/v1/docs/create-a-servicenow-instance-and-obtain-credentials)
- [Create a ServiceNow app and obtain credentials](/v1/docs/create-a-servicenow-instance-and-obtain-credentials)

#### Create a connecting instance in ServiceNow

In order to link your ServiceNow account with the Securiti application, you create a dedicated Instance to initiate the Connector Activation process:

1. Visit the following link to sign up for Personal Developer Instances (PDI).

<[*https://signon.service-now.com/x_snc_sso_auth.do?pageId=sign-up*](https://signon.service-now.com/x_snc_sso_auth.do?pageId=sign-up)>

![sign_up.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d8040111-948f-5574-ea39-e5585dca78ae.png)
2. Once you've signed up, near the upper right corner of the [page](https://developer.servicenow.com/dev.do#!/home), click **Request Instance**.

![request_instance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e70e5e4-18d8-3368-b302-e6162001f281.png)
3. On the Request an Instance popup, for the latest version, select "Utah" otherwise choose your preferred version.

> [!NOTE]
> **Note**
> 
> It may take some time to set up your Instance.

![latest_version.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a169c065-5086-9c8e-89e1-0eecdfd1b225.png)

![setting_up.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-201c1caf-529a-65aa-22f9-6df3ca8d7eb7.png)
4. Now, click **Start Building** which opens up the Instance page in a new browser tab.

![start_building.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0eb38985-e215-49b1-164b-9f496fc40581.png)

> [!NOTE]
> **Note**
> 
> Check your email inbox for login Credentials from ServiceNow.

#### Verify OAuth configuration for your instance

Perform the following steps to verify OAuth Configuration for your Instance.

> [!NOTE]
> **Note**
> 
> When using Automation Policy for the Cloud Connector, Securiti does not require any additional Permissions for ServiceNow. However, access to tables for operations like ticket creation and updates is governed by the Permissions set by your ServiceNow Administrator in ServiceNow.

1. On the left sidebar, search for the Plug-ins section and click **Plug-ins**.

![ServiceNow_PlugIn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-29d54707-e540-f265-9396-6a9ab5678b32.png)
2. On the list of potentially installable plug-ins for your system, search for **OAuth 2.0**.

![ServiceNow_PlugIn1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2555b160-2635-02b1-2a67-b551edb259ad.png)
3. Verify that the status for the OAuth 2.0 plug-in is displaying an **Active** message.

![ServiceNow_PlugIn2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25f6b1c3-a11c-6f13-7731-daa229565b84.png)

#### Create a ServiceNow app and obtain credentials

> [!NOTE]
> **Important**
> 
> You must have System Administrator or higher role to activate and integrate the ServiceNow Connector with Securiti. We recommend you use the Self-hosted version of the ServiceNow Data system to use a non-admin role with Securiti.

1. Navigate back to the **System Administration** page.

![ServiceNow_SYSAdmin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d03be335-9de4-396a-4ee4-afb792e284a3.png)
2. In the left sidebar, search for **OAuth** which then shows the **Application Registry**. Click **New** on the top bar to create the required OAuth-based application for Connector Activation.

![ServiceNow_InstanceList.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08a31fed-d474-853b-edbf-791da47cb16b.png)
3. Click **Create an OAuth API endpoint for External Clients**.

![ServiceNow_NewOAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22133d19-5ac0-b2fc-5a35-e9c5e071cf9f.png)
4. Apply the following settings and click **Submit**:

| Name | Enter an appropriate name for your application. |
| --- | --- |
| Client ID | A Client ID is automatically generated in the ServiceNow application. |
| Client Secret | A Client Secret is automatically generated in the ServiceNow application. |
| Redirect URL | - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

![ServiceNow_NewOAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1f4af20b-c17a-1035-d5d5-767d362dc16c.png)

After you create the OAuth application, ServiceNow redirects you to the **Application Registry** where you can see the newly created application as shown below:

![ServiceNow_OAuthEnd.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0bb52c1-8c04-0717-764d-63221b0c3a54.png)
5. Click the highlighted application (in this case, *DemonstrativeExample*).

ServiceNow redirects you to the details page for your new application.
6. Record the **Client ID** and newly generated **Client Secret** to use later.

> [!NOTE]
> **Note**
> 
> We recommend you increase the Refresh Token Lifespan to *864,000,000*.

![ServiceNow_ExistingOAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a15a24e-0776-e838-de96-fabb688dcb21.png)
7. Proceed to [Connecting ServiceNow with Securiti](/latest/docs/connecting-servicenow-with-securiti), or [Connecting ServiceNow (Legacy) with Securiti](/latest/docs/connecting-servicenow-legacy-with-securiti).
