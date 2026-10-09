---
title: "Configure DSR automation setup"
slug: "configure-dsr-automation-setup"
updated: 2026-06-16T07:14:34Z
published: 2026-06-16T07:14:34Z
canonical: "helpcenter.securiti.ai/configure-dsr-automation-setup"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure DSR automation setup

If you have an existing OneDrive Data system connector Instance and want to enable Robotic Automation, use the matching procedure below.

#### Step 1 - Enable DSR automation permissions

Make sure you selected DSR Automation Permissions while creating an application in Microsoft Entra ID.

#### Step 2 - Configure the permission request in Classic SharePoint Admin Center

If you want to enable DSR Automation forOneDrive, you use the Classic SharePoint admin center to configure a permission request for the app you created in [Grant permissions and obtain credentials in OneDrive Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-onedrive-cloud). To get more clarity on the Robotic Automation and app-only Permissions in OneDrive refer to [Using add-in only / app-only permissions with search queries in SharePoint Online](https://learn.microsoft.com/en-gb/archive/blogs/vesku/using-add-in-only-app-only-permissions-with-search-queries-in-sharepoint-online).

Perform the following steps to configure Permissions in Classic SharePoint Admin Center.

1. Browse to the following URL, where <tenant> is your Office 365 tenant name:

**https://*<tenant>*-admin.sharepoint.com/_layouts/15/appinv.aspx**

For example, if your Microsoft 365 default domain is **sometenant.onmicrosoft.com**, your tenant name is **sometenant** and you would browse to:

**https://sometenant-admin.sharepoint.com/_layouts/15/appinv.aspx**
2. In the Classic SharePoint admin center apply the following settings, then click **Lookup** as shown below.

| App Id | Enter the Application ID for the application you created in [Grant permissions and obtain credentials in OneDrive Cloud](/v1/docs/grant-permissions-and-obtain-credentials-in-onedrive-cloud). When you enter an Application ID, it automatically populates the application **Title**. |
| --- | --- |
| Title | It automatically populates when you enter the Applicationn ID. |
| App Domain | Enter your company’s tenant domain you recorded in [Grant permissions and obtain credentials in OneDrive Cloud](/v1/docs/grant-permissions-and-obtain-credentials-in-onedrive-cloud). See the example below. *sometenant.onmicrosoft.com* |
| Redirect URL | Admin automatically populates the Redirect URL as you enter the App ID. |
| App's Permission Request XML | In the Permission Request XML box, copy and paste the following text: *<AppPermissionRequests AllowAppOnlyPolicy="true"> <AppPermissionRequest Scope="http://sharepoint/content/tenant" Right="FullControl" /> </AppPermissionRequests>* |

![permission_request_xml.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eb9fd7e4-ce11-ab6c-9d4b-c7aa8714a964.png)

The admin center populates the title and the redirect URL for the application.
3. Click **Create**.

The admin center redirects you to authenticate the app.
4. Click **Trust It** as shown below.

![ODC-SP-Admin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f138b59e-93de-d3fd-5c8e-33f717c4e2b3.png)

#### Step 3 - Turn off DisableCustomAppAuthentication

> [!NOTE]
> **Note**
> 
> Skip this procedure if you do not want to enable Enhanced Robotic Automation for the OneDrive Connector.

OneDrive connectors require the **DisableCustomAppAuthentication** script for Activation. Otherwise, you'd run into the error message, as shown below.

> [!NOTE]
> **Note**
> 
> Refer to the help center documentation for Office365 Connector Activation. In particular, make sure that the required PowerShell scripts are executed. The Sharepoint API Token is not valid.

![Error_message_-_script.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c1dc396-0f07-1f93-a12d-776b423aba6f.png)

See this StackExchange article for more information:

[https://sharepoint.stackexchange.com/questions/284402/sharepoint-online-au](https://sharepoint.stackexchange.com/questions/284402/sharepoint-online-au)[thorization-issue-token-type-is-not-allowed)](http://Details at https://sharepoint.stackexchange.com/questions/284402/sharepoint-online-authorization-issue-token-type-is-not-allowed))

1. Download the PowerShell script from [this link](/privaci-utils/connectors/sharepoint_online/DisableCustomAppAuthentication.ps1).
2. Open the script in a text editor and replace **<tenantName>** with your Office 365 tenant name.

For example, if your Microsoft 365 default domain is **sometenant.onmicrosoft.com**, your tenant name is **sometenant**.
3. Execute the PowerShell script.
4. When prompted, authenticate with your Credentials.

#### Step 4 - Add a site collection administrator

If you want to enable DSR Automation for OneDrive, you must add a site collection administrator for all your OneDrive tenant accounts. If you do not want to enable Enhanced Robotic Automation for the OneDrive Connector, skip this procedure.

> [!NOTE]
> **Important**
> 
> The site collection administrator script may take a week to take effect to serve DSR.

Perform the following steps to add a site collection administrator

1. Download the PowerShell script from [this link](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti_form_extractor(1).zip).
2. Execute the PowerShell script.
3. When prompted, enter the following information:

| User principal name | The admin user for the tenant, for example, **admin@contoso.onmicrosoft.com**. |
| --- | --- |
| Tenant name | Your Office 365 tenant name, for example, if your domain is "if the tenant is contoso.onmicrosoft.com" your tenant name is **contoso**. |
| User principal name for the user to be added as a Site admin for all OneDrive accounts | This user need not be an admin of any sort and need not have a license assigned. It can just be an internal temporary user of the system. We recommend creating a new temp user for this activity. |
4. After you execute the script, it shows the output on the same directory where the script is executed from, as shown in the example below.

```plaintext
User UPN:  https://securititest-admin.sharepoint.com
Tenant name: securititest
User UPN to add:  testuser2@securititest.onmicrosoft.com
Going to run against <4> users
Handling user 1
Updated secondary administrator for: https://securititest-my.sharepoint.com/personal/sana_securititest_onmicrosoft_com
Handling user 2
Updated secondary administrator for: https://securititest-my.sharepoint.com/personal/mrehan_securititest_onmicrosoft_com
Handling user 3
Updated secondary administrator for: https://securititest-my.sharepoint.com/personal/ameer_securititest_onmicrosoft_com
Handling user 4
Updated secondary administrator for: https://securititest-my.sharepoint.com/personal/mayur_securititest_onmicrosoft_com
Assigned User as Site Collection to 4 OneDrive for Business user profiles.
```

Once you have added the site collection administrator, you can verify it from the SharePoint admin site, as shown in the examples below.

The Site collection admin view before running the script, containing only that user:

![site_collection_owners1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ad159b8-ac5e-268a-a59f-a379f179812f.png)

After running the script, the same view now shows the added user:

![site_collection_owners2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cc7bc14d-36a9-9a9f-a4f8-cd017071b876.png)

#### Step 5 - Add a secondary admin for all new OneDrives

After you create a site collection administrator as described in Add a site collection administrator procedure above, you add that administrator as a secondary admin for all new OneDrives as described below.

1. In the SharePoint admin center, choose **user profiles**, then click **My Site Settings** as shown below.

![my_site_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-afc08e14-c452-3ff6-65d8-d255ba6bfc8e.png)
2. Click on **setup my sites** and in the settings page find **My site secondary admin**.
3. Add the admin user in the Secondary Admin box, and mark the checkbox for **Enable My Site secondary admin**.
4. Proceed to [Connecting the OneDrive (Securiti-Cloud) data system](/latest/docs/new-ui-connecting-microsoft-365-onedrive-cloud-with-securiti).
