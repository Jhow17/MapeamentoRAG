---
title: "Acquire authentication credentials in Confluence Cloud"
slug: "acquire-authentication-credentials-in-confluence-cloud"
updated: 2026-09-21T10:40:14Z
published: 2026-09-21T10:40:14Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-confluence-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Confluence Cloud

Log in to [https://developer.atlassian.com/](https://developer.atlassian.com/).

1. Near the upper right corner of the page, select **User Menu > Developer console**.

![Developer_console.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05eb0e59-0bcf-dad3-0935-3c9540a50b18.png)
2. Click **Create** and select **OAuth 2.0 integration**, as shown below.

![Create_OAuth.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f91bb8c-ae08-7c79-ffde-dcdf3104ee29.png)

![Overview_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9da2ec4e-4a4d-5ee5-80b5-d28547b3aeb0.png)

Confluence displays the app overview page.
3. Choose **Permissions** in the left-hand menu of the developer dashboard.

![Permissions_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8974f69a-814d-5870-01ba-9d94ecd4fb02.png)
4. Click **Add** then **Configure** under the Action column for Confluence API, as shown below.

![Configure_Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a38fb536-515a-f410-d194-f1b60d90c92d.png)
5. Click **Edit** and add the following scopes in the **Classic scopes** section.
  - Read Confluence space summary.
  - Read Confluence detailed content
  - Read Confluence content summary.
  - Search Confluence content and space summaries.
  - Read user
  - Download content attachments. ![confluencecloud_classicscopes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e07c16a4-572c-7b71-cc5b-5727d8de6c68.png)
6. Add the following permission in the **Granular scopes** section and save.
  - **View space -** `read:space:confluence` ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-21 at 3.36.59 PM.png)
7. To run [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors), add the following permissions

> [!NOTE]
> **Important**
> 
> For entitlement scanning in Confluence Cloud connector, the below mentioned key considerations must be followed.
> 
> - The authenticated user needs the **Product Admin** role to access permissions on Confluence site content.
> - All users must make their email visibility public for accurate entitlement resolution during the inventory metadata scan. This requirement does not apply to the authenticated user with the Client ID and Secret.

In the **Granular scopes** section, add the below permissions:

Add the following permissions in the **Classic scopes** section:
  - read:content-details:confluence
  - read:permission:confluence
  - read:confluence-groups
  - read:confluence-content.permission
8. Once you've set the minimum permissions, select **Authorization** from the left-hand menu.
9. Click **Configure** for OAuth 2.0 (3LO) under Authorization type, as shown below.

![Authorization_Configure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a1b72864-61e2-f27a-675e-72cd6ccd08dc.png)
10. On the OAuth 2.0 configuration setup page, enter the URL you want to redirect to upon activation in the "Callback URL" field, as shown in the example below:

https://<*web portal*>/static/activateConnector.html

> [!NOTE]
> **Important**
> 
> Replace <*web portal*> with your environment URL.

Add the URL according to your environment. The list below shows redirect URLs for different regions.

![Callback_URL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d253f11c-5218-f14d-96b0-39ad2351c7a6.png)

Click **Save changes**
  - US cloud: `https://app.securiti.ai/static/activateConnector.html`
  - US1 cloud: `https://app1.securiti.ai/static/activateConnector.html`
  - Canada cloud: `https://app3.securiti.ai/static/activateConnector.html`
  - EU cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
  - Indonesia cloud: `https://app2.securiti.ai/static/activateConnector.html`
  - Australia cloud: `https://app4.securiti.ai/static/activateConnector.html`
  - UAE cloud: `https://app5.securiti.ai/static/activateConnector.html`
  - Mumbai cloud: `https://app6.securiti.ai/static/activateConnector.html`
  - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
  - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
  - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`
11. Click **Settings** on the developer dashboard.
12. Under Authentication details, record the **Client ID** and **Secret** to use later.

![Copy_Client_ID___Secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0ed397c3-638e-af72-3fde-fcd148442a0a.png)
13. Proceed to [Connecting Confluence Cloud with Securiti](/latest/docs/connecting-confluence-cloud-with-securiti).
