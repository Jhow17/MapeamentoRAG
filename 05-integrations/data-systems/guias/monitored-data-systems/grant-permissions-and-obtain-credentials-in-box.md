---
title: "Grant permissions and obtain credentials in Box"
slug: "grant-permissions-and-obtain-credentials-in-box"
updated: 2026-07-30T08:35:24Z
published: 2026-07-30T08:35:24Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-box"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Box

> [!NOTE]
> **Note**
> 
> You must have an admin role to ensure full access to all files and folders. A connector authorized by a co-admin can't access files and folders that are exclusively available to the admin or other co-admin users.

To create a custom app in Box and assign the required permissions:

1. Create a Box developer account using your main Box account.
2. Log in with your main account to access the Box dashboard.
3. Near the bottom of the page, click **Dev Console**.

Then select **Create New App > Custom App**.

![Box_create_custom_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36fdd2d4-17cd-33f4-b2ea-8d713ee9aea4.png)
4. On the Custom App popup, mark the radio button for **User Authentication (OAuth 2.0)**.

Click **Create App**.
5. Under the Configuration tab, record the **Client ID** and **Client Secret** to use later.

![Box_client_id_and_secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-24c9dc01-f3a9-a56a-5d46-3c7c8ee3fd50.png)
6. Enter the appropriate URL in the Box custom app to change the OAuth 2.0 redirect URI that matches your Securiti tenant, as shown below.

| Cloud | URL |
| --- | --- |
| US | `https://app.securiti.ai/static/activateConnector.html` |
| US1 | `https://app1.securiti.ai/static/activateConnector.html` |
| Canada | `https://app3.securiti.ai/static/activateConnector.html` |
| EU | `https://app.eu.securiti.ai/static/activateConnector.html` |
| Indonesia | `https://app2.securiti.ai/static/activateConnector.html` |
| Australia | `https://app4.securiti.ai/static/activateConnector.html` |
| UAE | `https://app5.securiti.ai/static/activateConnector.html` |
| Mumbai | `https://app6.securiti.ai/static/activateConnector.html` |
| Sovereign deployment | `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

![redirect_URIs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1bdcfb7-0683-8f6c-d878-334ea92d4eed.png)
7. Select the following permissions:
  1. In the **Advanced Features** section of the Configuration tab, mark the checkbox for **Make API calls using the as-user header**.

![Box_API_checkbox.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cbbb005f-5a99-f97e-4cda-6824cfbb250f.png)

> [!NOTE]
> **Note**
> 
> You can scan other users' files when you've enabled the option.
  2. In the **Application Scopes** area, enable the following permissions:

For more information, see [Scopes - Box Developer Documentation](https://developer.box.com/guides/api-calls/permissions-and-errors/scopes/).
    - Manage users
    - Manage groups
    - Manage enterprise properties (required in addition to "Suppress notification" scope to suppress download email notifications).
    - Read all files and folders stored in Box (if not already marked).
    - Write all files and folders stored in the Box.

![permission-Securiti-for-Box.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e46b64d5-6e76-af2b-ada2-7ac57f6dc1d6.png)
8. (Optional) To **suppress the notifications** that Box would otherwise send to every file owner when Securiti downloads their files for scanning:
  1. Visit the [Box customer support site](http://https://support.box.com/hc/en-us) and submit a request for them to enable the "Suppress notification" scope. Include in your request the Client ID and Client Secret you created.

For more information, see [Box documentation on suppress notifications](https://developer.box.com/guides/api-calls/suppress-notifications/).
  2. Wait for Box customer support to enable the "Suppress notification" scope before proceeding.
9. (Optional) To use enhanced DSR Automation using full scan for your data, you must enable the `enterprise_content` scope for your Box application. For more information, see [Enable the enterprise_content scope in Box](/latest/docs/enable-the-enterprise-content-scope-in-box)
10. Proceed to [Connecting Box (Self-hosted) with Securiti](/latest/docs/connecting-box-self-hosted-connector-with-securiti) or [Connecting Box (Securiti-Cloud) with Securiti](/latest/docs/connecting-box-securiti-cloud-with-securiti).

## Related

- [Enable the enterprise_content scope in Box](/enable-the-enterprise-content-scope-in-box.md)
