---
title: "Create a ServiceNow instance and obtain credentials (Yokohama release)"
slug: "create-a-servicenow-instance-and-obtain-credentials-yokohama-release"
updated: 2026-06-11T15:02:21Z
published: 2026-06-11T15:02:21Z
canonical: "helpcenter.securiti.ai/create-a-servicenow-instance-and-obtain-credentials-yokohama-release"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a ServiceNow instance and obtain credentials (Yokohama release)

> [!NOTE]
> **Note**
> 
> - You must have a running ServiceNow Instance and an admin role to create the application registry.
> - This procedure applies to the ServiceNow Yokohama release only. We assume that you have already opted for the Yokohama release.

Perform the following procedures before activating the ServiceNow Connector in Securiti.

- [Access the connecting instance in ServiceNow](/v1/docs/create-a-servicenow-instance-and-obtain-credentials-yokohama-release)
- [Verify the OAuth configuration for your instance](/v1/docs/create-a-servicenow-instance-and-obtain-credentials-yokohama-release)
- [Create ServiceNow app and obtain credentials](/v1/docs/create-a-servicenow-instance-and-obtain-credentials-yokohama-release)

#### Access the connecting instance in ServiceNow

In order to link your ServiceNow account with the Securiti application, you create a dedicated Instance to initiate the Connector Activation process:

1. Log in to your [developer account](https://developer.servicenow.com/dev.do#!/home) in ServiceNow.
2. On the home page, click **Start building** to access the Instance dashboard.

![access-instance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d4e65dd9-76a0-d639-522f-e9e3bd6573a4.png)

It redirects you to the Instance admin dashboard

![instance-dash.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a1bbdd6-e59e-4d84-a80f-761a80f575d6.png)

#### Verify the OAuth configuration for your instance

Perform the following steps to verify OAuth Configuration for your Instance.

> [!NOTE]
> **Note**
> 
> When using Automation Policy with the Cloud Connector, Securiti does not require any additional Permissions for ServiceNow. However, access to tables for operations like ticket creation and updates is governed by the Permissions set by your ServiceNow Administrator in ServiceNow.

1. On the top navigation in ServiceNow Instance dashboard, click **All**.
2. In the search bar, search for the **Plugins**.
3. Under the **System Definition**, click **Plugins**.

![search-plugin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba06cb4b-e443-c0f8-07da-761912c6e529.png)
4. On the **Search your licensed applications and plugins** page, search **OAuth 2.0**.
5. Under the **Installed** tab in the **Family plugins** section, verify that **OAuth 2.0** plugin is active and up to date.

![image2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-128d5d85-4e3c-d213-b0ed-da46cc4d1705.png)

#### Create ServiceNow app and obtain credentials

> [!WARNING]
> **Important**
> 
> You must have a System Administrator or higher role to activate and integrate the ServiceNow Connector with Securiti. We recommend you use the Self-hosted version of the ServiceNow Data system to use a non-admin role with Securiti.

1. On your ServiceNow Instance in the top navigation in, click **All**.
2. In the search filter, Search for **Application Registry**.
3. Under the **System OAuth**, choose **Application Registry**.

![search-app-registry.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b35b1a42-18c5-1e61-bcdc-d28dfe420766.png)
4. On the top right of the **Application Registries** page, click **New**.

![click-new.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4f1560c4-7ded-1709-d44d-eece0729d26b.png)
5. On the OAuth application page, click on **Create an OAuth API endpoint for External Clients** link.

![click-oauth-link.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-240f95ca-e6bc-6b40-1de9-a5278792934b.png)
6. On the **Applications Registries New Record** page, apply the following settings:

| Setting | Description |
| --- | --- |
| Name | Enter an appropriate name for your application. |
| Client ID | Client ID is automatically generated in the ServiceNow application. |
| Client Secret | Client Secret is automatically generated in the ServiceNow application. |
| Redirect URL | - US Cloud: `https://app.securiti.ai/static/activateConnector.html` - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html` - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html` - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html` - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html` - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html` - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html` - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html` - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
  - Click **Submit**.

![add-credentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a74da270-7cd9-f5ec-fc97-4aec547e13ce.png)
7. On **Application Registries** page, choose the newly created ServiceNow application.

![click-new-cred.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6dca9e44-be0e-ed94-3d34-532adf243628.png)
8. On the **Application Registries <Your ServiceNow Application>** page, record the following for Connector Activation:
  - **Client ID**
  - **Client Secret**.

![record-credentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-530fc20e-41f1-a03a-4e23-a82a0cd1f0ac.png)
9. From the top URL, record the Instance id to use it later for Connector Activation.

If the URL is *https://****dev1234****.service-now.com/now/nav/ui/classic/params/target/*

**dev1234** is Instance id.
10. Proceed to [Connecting ServiceNow with Securiti](/latest/docs/connecting-servicenow-with-securiti), or [Connecting ServiceNow (Legacy) with Securiti](/latest/docs/connecting-servicenow-legacy-with-securiti).
