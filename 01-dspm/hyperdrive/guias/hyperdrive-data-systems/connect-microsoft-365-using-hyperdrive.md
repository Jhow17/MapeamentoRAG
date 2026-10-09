---
title: "Connecting Microsoft 365 using Hyperdrive"
slug: "connect-microsoft-365-using-hyperdrive"
updated: 2026-07-31T07:58:20Z
published: 2026-07-31T07:58:20Z
canonical: "helpcenter.securiti.ai/connect-microsoft-365-using-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft 365 using Hyperdrive

This topic covers both automatic and manual authentication methods to connect Microsoft 365 applications with Securiti

> [!NOTE]
> Note
> 
> You must have global admin access in the Microsoft Azure portal connect Microsoft 365 applications using automatic authentication.

## Creating a data system instance

1. Log in to Securiti with your admin credentials.
2. On the left navigation, choose **Settings > Data Systems**.
3. On the top right of the **Data Systems** page, click **+Add Integration**.
4. On the **Basic Information** tab, apply the following settings:
  1. Add an **Instance Name**.
  2. (Optional) Add a Description.
  - (Optional) Enable the **Hyperdrive mode** toggle to use dynamic compute scaling for data scans through the Securiti Outpost deployment.

> [!NOTE]
> Note
> 
> If the feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> 
> Securiti recommends you to use Hyperdrive mode. This option automatically increases compute capacity for large or complex scans and scales back during lighter scans.
  - Click **Create and Continue**.

## Choosing Microsoft 365 Applications

- On the **Applications** page, mark the checkboxes for Microsoft applications you want to include for authentication and scanning.
- (Optional) Under the **Application Settings**, enable the **Fetch Sensitive Labels** toggle to fetch labels for each file.

> [!NOTE]
> Note
> 
> - This option is applicable to Microsoft 365 SharePoint Online and OneDrive.
> - This option increases the processing time because it fetches labels per file for the selected data system.

![Selection of Microsoft 365 applications with options to discover data and configure settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/choose apps.png)
- (Optional) Under the **Application Settings**, enable the **Activity Analysis** toggle to enable audit log analysis.

> [!NOTE]
> Note
> 
> - Audit log analysis is activated for past 180 days and incremental data scans.
> - Requires access to Microsoft Purview audit logs and Office 365 Management Activity API. For more information, see [Microsoft 365](/latest/docs/microsoft-365).
- Click **Save and Continue**.

## 

It takes you to the Authentication page.

## Authenticating the data system instance

Securiti offers two options to authenticate the Microsoft 365 data system instance:

- For automatic authentication, Securiti creates an Entra ID application and assign permissions automatically once admin provides consent for authentication.
- For manual authentication, you must create an Entra ID application and assign the required permissions to run the supported features successfully. For more information, see [Create an Entra ID application and assign permissions](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365).

**Automatic**

### Microsoft 365 automatic authentication interactive demo

You can watch the following demo video to understand the configuration process for M365 connector’s automatic authentication:

[Embedded content](https://app.storylane.io/demo/rhgqqq0snafo?embed=inline)

Perform the following steps to authenticate the Microsoft 365 connector using automatic authentication:

1. On the **Authentication** page, select the **Output deployment** you configured earlier in [Configuring Securiti Outpost deployment](/latest/docs/full-saas-hyperdrive-deployment).
2. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data. For more information, see [Configuring PCS Destination](https://helpcenter.securiti.ai/latest/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> Note
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
3. Under **Azure Authentication**, click **+ Add Azure Application**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Outpost-select.png)
4. On the **Add Azure Application** popup, under **Step 1**, click the copy to clipboard icon to copy the device code.

> [!NOTE]
> Note
> 
> You must use the copied code imediately because it expires in 15 minutes.
5. Under **Step 2**, click on the **Microsoft Azure App Authorization Service** link. ![Instructions for adding an Azure application with a device code and authorization steps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/copy-code.png)
6. On the Microsoft Azure access page, paste the code you copied in the previous step, and click **Next**.

![Microsoft login prompt requesting a code for account access verification.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/enter-code.png) It redirects you to the login page.
7. Log in to your Azure portal account with admin access, and click **Continue**. Securiti creates an Azure app and redirects you to the **Add Azure Application** popup.
8. Once the Azure app is created successfully, click **Authorize Access** to assign the permissions. ![Successful Azure application authorization and creation process displayed in the configuration interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/azure-app-popup.png)

It takes you to the Microsoft Azure login page.
9. Log in to your Azure account, and click **Accept**. ![App permission request displaying various access rights and an 'Accept' button.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Permissions-pop.png)

Securiti creates two Entra ID applications during this process. For more information on the purpose of these applications, see the [section below](/latest/docs/connect-microsoft-365-using-automatic-authentication#automatic-creation-process-of-entra-id-applications).

It takes you to the Authentication page.
10. On the **Authentication** page, check if you have selected the Outpost deployment.
11. Click **Save Configuration and Continue.** It takes time to complete the Authentication process. Once authentication is complete, you can see the authentication statuses on the [**Authentication**](/latest/docs/using-authentication-statuses) page.

> [!WARNING]
> Important
> 
> While authenticating the connector, Securiti creates a permanent Entra ID application using a temporary Provisioner app owner by Securiti.

To understand the flow of how Securiti creates Entra ID applications, see the steps below:

1. Once Azure admin grants consent, Securiti uses Application 1 (temporary) with the following permissions:

| Permission | Purpose |
| --- | --- |
| `Application.ReadWrite.All ` | Creates app registrations. |
| `Directory.ReadWrite.All` | Creates a service principal. |
2. Securiti receives an access token that is valid for 1 hour.

This token is used immediately for provisioning, and no refresh token is stored.
3. Securiti Provisioner application creates permanent Application 2.

It creates app registration, service principal, secret, and certificate.
4. Once the admin grants consent for Application 2.

It reviews and approves M365 data access permissions. For more information on permissions assigned to Application 2, see the [permissions section in Microsoft 365](/latest/docs/microsoft-365#permissions-and-use-cases).

Provisioning is complete, and the provisioner application is no longer used; the access token expires after 60 minutes, and no renewal is possible.

### Comparison between the provisioner app and the permanent app.

| Features | Application 1 - Securiti Provisioner | Application 2- Securiti-Microsoft365-DS-{ID} (Permanent) |
| --- | --- | --- |
| Purpose | Create application 2 using device code flow | Data discovery and governance |
| Owned by | Securiti | Your organization |
| Lifetime | 60 minutes | Until deactivated |
| Access | App management only | M365 data (read-only) |
| Management | None | Cannot modify apps |
| Security | We guarantee: - Access token expires in 60 minutes - No refresh token stored - Requires an active admin session - Cannot access M365 data | Your organization manages it |
| Authentication method | Not applicable, as this application is not used for authentication | - OAuth-based credentials (Encrypted Secret) - Certificate-based credentials |

**Manual**

Perform the following steps to authenticate the Microsoft 365 connector using the manual authentication.

1. On the **Authentication** page, select the **Output deployment** you configured earlier in [Configuring Securiti Outpost deployment](/latest/docs/full-saas-hyperdrive-deployment).
2. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data. For more information, see [Configuring PCS Destination](https://helpcenter.securiti.ai/latest/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> Note
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
3. Under **Azure Authentication**, click **+ Add Azure Application**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Outpost-select.png)
4. On the **Authentication** page under **Pod Configuration**, choose your Outpost deployment.
5. Under **Azure Authentication**, click **+ Add Azure Application**.
6. On the bottom right of the **Add Azure Application** popup, click **Add Manually**. ![Instructions for adding an Azure application with a device code and authorization steps.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/click-add-manually.png)
7. On the **Add Azure Application** popup, add the authentication credentials you recorded earlier in the [Creating an Entra ID app and obtaining credentials for Microsoft 365](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365)

| Parameter | Description |
| --- | --- |
| Tenant ID | Enter your Tenant ID, which follows the specified string format. See the example below. *0a1b01a1-ab1b-1a1a-b0b0-101010ab1a01* |
| Application ID | Enter the Application ID you recorded earlier. Application ID uses a string value. See the example below. *12345678-abcd-1234-efgh-123456abcdef* |
| Application Secret | Enter the Client Secret you recorded earlier. The Client Secret uses a string value. See an example below. *aB8C~Dsr.10yXyu~a4VAAAAp8ZRTJBA.zlAcy~* |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connect-microsoft-apps-using-manual-authentication-image-rb9pt4bb.png)
8. Click **Save and Continue**. It takes you back to the Authentication page.
9. On the Authentication page, click **Save Configuration and Continue**. It takes time to establish the connections with all the Microsoft apps selected in the configuration process. M2M authentication

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/connectors-new-ui-template-1).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using authentication statuses (Hyperdrive)](/latest/docs/using-authentication-statuses-hyperdrive)

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft 365 OneDrive (self-hosted)

- [Configure data inventory sync for Microsoft 365 applications (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive)
- [Create discovery scans for Microsoft 365 (Hyperdrive)](/latest/docs/create-discovery-scans-for-microsoft-365-hyperdrive)
- [Configure Activity Analysis for Microsoft 365 (Hyperdrive)](/latest/docs/configure-activity-analysis-for-microsoft-365-hyperdrive)
