---
title: "Configure DSR automation setup"
slug: "microsoft-365-sharepoint-connectors-configure-dsr-automation-setup"
updated: 2026-06-23T06:24:24Z
published: 2026-06-23T06:24:24Z
canonical: "helpcenter.securiti.ai/microsoft-365-sharepoint-connectors-configure-dsr-automation-setup"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure DSR automation setup

If you have an existing SharePoint Online Cloud Data system connector instance and want to enable Robotic Automation, use the matching procedure below.

#### Step 1 - Enable DSR automation permissions

Make sure you selected DSR Automation Permissions while creating an application in Microsoft Entra ID. For more information, refer to [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud).

#### Step 2 - Configure the permission request in Classic SharePoint Admin Center

If you want to enable DSR Automation for SharePoint Online, you use the Classic SharePoint admin center to configure a permission request for the app you created in [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud). To get more clarity on the Robotic Automation and app-only Permissions in SharePoint Online, refer to [Using add-in only / app-only permissions with search queries in SharePoint Online](https://learn.microsoft.com/en-gb/archive/blogs/vesku/using-add-in-only-app-only-permissions-with-search-queries-in-sharepoint-online).

Perform the following steps to configure Permissions in Classic SharePoint Admin Center.

1. Browse to the following URL, where <tenant> is your Office 365 tenant name:

**https://*<tenant>*-admin.sharepoint.com/_layouts/15/appinv.aspx**

For example, if your Microsoft 365 default domain is **sometenant.onmicrosoft.com**, your tenant name is **sometenant** and you would browse to:

**https://sometenant-admin.sharepoint.com/_layouts/15/appinv.aspx**
2. In the Classic SharePoint admin center apply the following settings, then click **Lookup** as shown below.

| App Id | Enter the Application ID for the application you created in [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud). When you enter an Application ID, it automatically populates the application **Title**. |
| --- | --- |
| Title | It automatically populates when you enter the Applicationn ID. |
| App Domain | Enter your company’s tenant domain you recorded in [Grant permissions and obtain credentials in SharePoint Online Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-sharepoint-online-cloud). See the example below. *sometenant.onmicrosoft.com* |
| Redirect URL | Admin automatically populates the Redirect URL as you enter the App ID. |
| App's Permission Request XML | In the Permission Request XML box, copy and paste the following text: <AppPermissionRequests AllowAppOnlyPolicy="true"> <AppPermissionRequest Scope="http://sharepoint/content/tenant" Right="FullControl" /> </AppPermissionRequests> |

![permission_request_xml.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb9fd7e4-ce11-ab6c-9d4b-c7aa8714a964(1).png)

The admin center populates the title and the redirect URL for the application.
3. Click **Create**.

The admin center redirects you to authenticate the app.
4. Click **Trust It** as shown below.

![ODC-SP-Admin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f138b59e-93de-d3fd-5c8e-33f717c4e2b3(1).png)

#### Step 3 - Turn off DisableCustomAppAuthentication

> [!NOTE]
> **Note**
> 
> Skip this procedure if you do not want to enable Enhanced Robotic Automation for the SharePoint Connector.

SharePoint Connector requires the **DisableCustomAppAuthentication** script for activation. Otherwise, you'd run into the error message, as shown below.

> [!NOTE]
> **Note**
> 
> Refer to the help center documentation for Office365 connector activation. In particular, make sure that the required PowerShell scripts are executed. The Sharepoint API Token is not valid.

![Error_message_-_script.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c1dc396-0f07-1f93-a12d-776b423aba6f(1).png)

For more information, see [Stack Exchange article on SharePoint Online authorization issue](https://sharepoint.stackexchange.com/questions/284402/sharepoint-online-authorization-issue-token-type-is-not-allowed).

1. Download the PowerShell script.
2. Open the script in a text editor and replace **<tenantName>** with your Office 365 tenant name.

For example, if your Microsoft 365 default domain is **sometenant.onmicrosoft.com**, your tenant name is **sometenant**.
3. Execute the PowerShell script.
4. When prompted, authenticate with your Credentials.
5. Proceed to [Connecting Microsoft 365 SharePoint Online (Securiti-Cloud) with Securiti](/latest/docs/new-ui-activating-microsoft-365-sharepoint-online-securiti-hosted-connector).
