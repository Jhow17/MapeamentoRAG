---
title: "Microsoft 365 SharePoint Online"
slug: "microsoft-365-sharepoint-online"
updated: 2026-09-21T09:38:08Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/microsoft-365-sharepoint-online"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 SharePoint Online

This section describes the Data Access Governance features supported for Microsoft 365 SharePoint Online and the steps to configure these functionalities.

## Supported Data Access Governance Feature Sets

The following is the list of the features supported for Microsoft 365 SharePoint Online:

### Access Intelligence

- Privilege Analysis
  - Site, Sub-site, and File-level permissions granularity
- Activity Analysis
  - Site Collection, Folders, and File-level user activity
- Supported Credential Vault for Sharepoint Access Scan :
  - HashiCorp

### Access Control

- Site-level user and group access provisioning. Note that Access Control Policies for SharePoint are supported for Self-hosted SharePoint Connectors.

### Cross Border Transfer Policies

- Based on Data Access Location and Data Location

> [!NOTE]
> Note
> 
> If Data Access Governance features for Microsoft 365 SharePoint Online are not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Example Supported Use Cases

The supported example use cases include:

**Access Intelligence**

- Identify and report on which SharePoint users and user groups have access to Sites and what their permissions are on those Sites
- Identify and report on which SharePoint users and user groups have access to files and what their permissions are on those files
- Identify and report on files containing sensitive data that are shared with every internal user in your organization
- Identify and report on users whose access to a file comes via file sharing and those whose access is granted through group assignment, role assignment, and other permissions mechanisms
- Identify and report on Sites that allow external sharing of data, and what type of external access can be configured for those Sites
- Identify and report access to Files shared via link anonymously
- Identify sensitive data with over-abundant access, causing risk when users leverage Microsoft Copilot

## Configuring SharePoint Data Access Governance

This section describes the SharePoint Privilege Analysis Configuration process

### Pre-requisites

#### Permissions for SharePoint Access Intelligence Privilege and Activity Analysis

Refer to the below permissions for Azure application and SharePoint application.

| Application API Domain | Permission Required | What Securiti uses this permission for | Microsoft Documentation |
| --- | --- | --- | --- |
| SharePoint | Sites.FullControl.All | Required for Privilege Analysis. Lets Securiti read the Sites related information. Lets the app to have full control of all site collections without a signed in user. | [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesfullcontrolall) |
| Microsoft Graph | Sites.Read.All | Required for Privilege Analysis. Lets Securiti read all Sharepoint Sites, SubSites in the system to gather Privilege Analysis | [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesreadall) |
| Sites.FullControl.All | Required for Privilege Analysis and for SharePoint sharing-link collection during Access Scans. Lets Securiti read the Sites related information and have full control of all site collections without a signed-in user. Without this permission, Microsoft Graph omits the webUrl and shareId fields on sharing-link permissions, so sharing links (anonymous, organization-wide, and specific-people) cannot be resolved and are skipped during the scan. | [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference#sitesfullcontrolall) |
| User.Read.All | Required for Privilege Analysis. Lets Securiti read information on sharepoint users assigned to Sites, Libraries, Files | [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference#userreadall) |
| AuditLogsQuery-SharePoint.Read.All | > [!NOTE] > **Note** > > Note that the Privilege Analysis permissions listed above must be granted alongside the Activity Analysis permissions. Required for Activity Analysis. Lets Securiti read information on user and application activity in your tenant. | [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference#auditlogsquery-sharepointreadall) |
| AuditLogsQuery-Entra.Read.All | Required for Activity Analysis. Lets Securiti read information on user and application activity in your tenant. | [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference#auditlogsquery-entrareadall) |
| AuditLogsQuery-Endpoint.Read.All | Required for Activity Analysis. Lets Securiti read information on user and application activity in your tenant. | [Microsoft Documentation](https://learn.microsoft.com/en-us/graph/permissions-reference#auditlogsquery-endpointreadall) |
| Microsoft Office 365 Management API | ActivityFeed.Read | Required for Activity Analysis. Lets you retrieve activity data from the Office 365 Management Activity API, including user actions and operational events across Microsoft 365 services. | [Microsoft Documentation](https://learn.microsoft.com/en-us/office/office-365-management-api/get-started-with-office-365-management-apis) |
|  | ActivityFeed.ReadDlp | Required for Activity Analysis. Lets you retrieve Data Loss Prevention (DLP) activity events, including policy matches and sensitive data handling actions across Microsoft 365 services. | [Microsoft Documentation](https://learn.microsoft.com/en-us/office/office-365-management-api/get-started-with-office-365-management-apis) |

> [!NOTE]
> Note
> 
> Securiti currently uses the Microsoft Graph API as the default source for Activity Analysis logs ingestion. We recommend using the Microsoft Office 365 Management API for improved data consistency. You can enable it by granting the required permissions.
> 
> To view the Activity Analysis data, you must turn auditing on in the Microsoft Purview portal. Audit logging is turned on by default for Microsoft 365 organizations. However, when setting up a new Microsoft 365 organization, you should verify the auditing status for your organization. For more information, see [Microsoft Documentation](https://learn.microsoft.com/en-us/purview/audit-log-enable-disable?tabs=microsoft-purview-portal). If this feature for Microsoft 365 SharePoint Online is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

#### Authentication for Access Intelligence Scans using Microsoft Graph and Sharepoint API permissions

This section describes the prerequisite steps to configure authentication credentials Access Intelligence Scans using Microsoft Graph and Sharepoint API permissions.

****Step 1 - Register an application in the Azure Portal****

> [!NOTE]
> **Note**
> 
> To enable the connector for SharePoint, you need to register an application in Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring permissions that allow it to access SharePoint resources.

1. Log in to your [Microsoft Azure](https://azure.microsoft.com/en-us/get-started/azure-portal/v1/docs/securiti-pods-and-elastic-pods) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91(11).png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40(11).png)
4. On the **Registration an application** page, apply these settings:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name, for example, "Securiti connector." |
| Supported Account types | Choose **Accounts in this organization directory**. |
| Redirect URl | Choose **Web** from the Select a platform many and enter the redirect URL that applies: - US cloud: `https://app.securiti.ai/static/activateMetadataSource.html` `https://app.securiti.ai/static/activateConnector.html` - US1 cloud: `https://app1.securiti.ai/static/activateMetadataSource.html` `https://app1.securiti.ai/static/activateConnector.html` - Canada cloud: `https://app3.securiti.ai/static/activateMetadataSource.html` `https://app3.securiti.ai/static/activateConnector.html` - EU cloud: `https://app.eu.securiti.ai/static/activateMetadataSource.html` `https://app.eu.securiti.ai/static/activateConnector.html` - Indonesia cloud: `https://app2.securiti.ai/static/activateMetadataSource.html` `https://app2.securiti.ai/static/activateConnector.html` - Australia cloud: `https://app4.securiti.ai/static/activateMetadataSource.html` `https://app4.securiti.ai/static/activateConnector.html` - UAE cloud: `https://app5.securiti.ai/static/activateMetadataSource.html` `https://app5.securiti.ai/static/activateConnector.html` - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateMetadataSource.html` `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |

Near the bottom of the page, click **Register**.

![reg-app-azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c39ddae9-2bf3-f4d7-6474-abbef245ce0d(10).png)

> [!NOTE]
> **Note**
> 
> If you miss adding the redirect URL, Azure lets you register the application. You can add a redirect URL by accessing the authentication section.
5. Refer to the matching procedure if you miss adding the redirect URL while registering an application.
  1. On the left sidebar, choose **Manage** > **Authentication**.

![Screenshot_2024-08-23_at_2_02_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52d46981-45dc-d8ae-0349-6ccf62b190c2(6).png)
  2. On the **Authentication** page, click **Add a platform**.
  3. On the **Configure platforms** popup, click **Web**.

![Screenshot_2024-08-23_at_2_02_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa08c31b-c9de-c9c1-deb5-57fbc44cb6ed(6).png)
  4. On the following popup, add the **Redirect URl** from the above table, and click **Configure**.

![Screenshot_2024-08-23_at_3_19_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c0b39c0-6210-8689-04e0-787c220b297c(4).png)
6. Proceed to Obtain authentication credentials.

****Step 2 - Obtain activation parameters and authentication credentials****

Perform the following steps to obtain activation parameters and authentication credentials for connector activation:

**A - Obtain activation credentials**

> [!NOTE]
> **Note**
> 
> Tenant name and Domain are activation parameters. You need to record them for both OAuth based and Certificate based authenticatons.

Refer to the matching procedure to obtain activation credentials.

1. Log in to your [Microsoft admin account](https://azure.microsoft.com/en-us/get-started/azure-portal).
2. On the left sidebar, choose **Settings** > **Domains**.

![Domains.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eca42f96-fd9c-9d1b-4dbc-4bb811e741d3.png)
3. Record the **Tenant Name** and **Domain** for the connector activation.
  - **Domain** is the primary domain for your Microsoft Entra ID account. See the example below.

*datasubjectrequest.onmicrosoft.com.*

> [!NOTE]
> **Important**
> 
> You must confirm primary domain from Microsoft Entra ID details and use that domain here.
  - **Tenant Name** is initial part of the domain. If *datasubjectrequest.onmicrosoft.com* is the domain. **datasubjectrequest** is the Tenant Name.

![domain-tenant-sp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-499877df-3a5f-5aa4-df10-e5b17f5f9251.png)

**B - Obtain OAuth based credentials**

Refer to the matching procedure to obtain OAuth based credentials for SharePoint Online connector.

**Obtain Application (Client) ID**

1. On the left sidebar, click **Overview** and record the "Application (Client) ID" by clicking the **Copy to Clipboard** icon for later use.
2. Record the Application (Client) ID by copying it.

![App-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-380d688d-8a16-923a-79ca-68ba2c757cb2(1).png)

**C - Obtain certificate credentials**

> [!NOTE]
> **Important**
> 
> Certificate credentials are required when accessing Sharepoint APIs in addition to the Microsoft Graph API. Currently Gencore Entitlements, Site Sharing settings, and Site to Hubsite relationships require the use of certificate credentials.

Refer to the matching procedure to obtain certificate based credentials for SharePoint Online.

1. Open the terminal (console) on your machine, and execute the following command

```plaintext
openssl req -x509 -newkey rsa:4096 -sha256 -keyout private-auth-key.pem -out public-auth-cert.pem -nodes -days 730
```

> [!NOTE]
> **Note**
> 
> We recommend using OpenSSL to generate the self-signed Public key (certificate) and Private key. The keys generated by the command have a two-year validity. Consult the [Microsoft documentation](/v1/docs/securiti-pods-and-elastic-pods) for guidelines on creating and rotating secrets.
2. Enter the following information after running the command.

> [!NOTE]
> **Note**
> 
> Enter a value for each parameter and ensure it is unique. This uniqueness is crucial for generating a distinct certificate and key for every app registration setup. Without unique parameters, the generated certificate and key will not be unique.

![terminal-Sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6406ff5f-720a-1735-5219-52bf90371f4d(2).png)
  - Country name (e.g., 2-letter code = US)
  - State or Province name (e.g., full name = New York)
  - Locality name (e.g., city = New York)
  - Organization name (e.g., company = Securiti)
  - Organizational unit name (e.g., section = Platform)
  - Common name (e.g., fully qualified hostname = www.securiti.ai)
  - Email address (e.g., securiti@admin.com)
3. Record the Public key (certificate) and Private key for later use in uploading the certificate.

The keys are generated in the same path you have opened in the terminal once you supply information to the specified parameters. See an example below.

The path */users/john.doe/certificate/* contains two **public-auth-cert.pem** and **private-auth-key.pem.** files for the generated keys.
4. On the left sidebar, choose **Certificates & secrets** > **Certificates** > **Upload certificate**.

![Add-certificate-Sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-51c17bec-31df-a1f3-f5a4-2a74a1c95c4b(2).png)
5. On the **Upload certificate** popup, add the following information.

| Parameter | Description |
| --- | --- |
| Upload a certificate | Upload a public key certificate generated in **Record the Public key**. See the example for file format. *ca.crt* |
| Description | Enter a description for the purpose of public key certificate. |

Click **Add**.

![certificate-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3c9e04e-5df9-83ec-693c-9a1bd8b61983(1).png)
6. Record the following information once the Public key (certificate) is uploaded.

![record-thumbprint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fde178b0-ce08-d964-5bed-0f6602972450(1).png)

> [!NOTE]
> **Important**
> 
> The private key file and certificate thumbprint are required for configuring Entitlement scan for Microsoft 365 SharePoint Online connector. Save this informaton to use for connector activation.
  - On the **Certificates & secrets** page, record the **Thumbprint** as the certificate to use it for connector activation.

****Step 3 - Configuring your Azure Graph Application and Sharepoint API permissions and enable Activity Data Collection****

- **Configure Graph API permissions.**
  1. In the Manage area of the navigation pane for the connector page, click **API permissions** as shown below.

![graph_api_permissions1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f1af5b5d-1b1a-de0b-b8ec-ca6997f3a203(2).png)
  2. On the API permissions page, click **Add a permission**.

![graph_api_permissions2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba425a80-9b45-943d-3f39-b616407b175d(2).png)
  3. On the Request API permissions page, click **Microsoft Graph**.

![graph_API_permissions3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b085b423-b306-b40d-3f98-b9a0c5c0ee45(2).png)
  4. Click **Application Permissions**.

![graph_API_permissions4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3bdf84c3-5246-5a7d-a96d-61ca78cf080f(2).png)
  5. On the Select Permissions page for Microsoft Graph, expand the various areas and mark the checkboxes for the permissions given below for the connector

Refer to SharePoint permissions table above for more understanding of the permissions uses and explanations.
    - Sites.Read.All
    - Group.Read.All
    - User.Read.All
  6. Near the bottom of the Request API permissions box, click **Add permissions**.
  7. Near the bottom of the **API permissions** page, click **Grant admin consent for <yourOrganizationName>**. Click **Yes** to confirm.

![grant-consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca0fe711-5e78-2827-ec31-7bdcc2b76f1e(1).png)

**Configure SharePoint Online permissions:**

1. In the left-hand navigation pane, select **API permissions** and click **Add a permission**.

![add_graph_permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a9a830b-ffc8-4ef3-ee4e-e511e13f70d7(1).png)
2. On the **Request API permissions** page, click **Microsoft Graph** , then click **Application Permissions**.

![sharepoint.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff8d6c52-fcdc-afcd-93cc-e33d41a6aabf(2).png)
3. On the following page, perform the following steps:

![sharepoint-app-perm.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0b08f38-5a2f-51c5-7062-c6d9c1d71bfb(1).png)
  1. Click **Application permissions** to access the required permission mentioned in Microsoft 365 SharePoint Online connectors for SharePoint.Microsoft 365 SharePoint Online connectors
  2. Scroll down to **Permissions** section, expand the **Sites** section, and mark the checkbox for **Sites.FullControl.All**.
4. Click **Add Permissions.**

It redirects you to **API permissions** page where you see SharePoint permission added.

**Enabling Activity Data Collection (Only required for Activity Analysis using M365 Management API)**

To start collecting activity data, you must enable subscriptions for the required activity feeds in your Microsoft 365 environment.

**Ensure the following activity types are enabled:**

You must call the following three endpoints individually to begin data collection for each category.

> [!NOTE]
> Note
> 
> Replace {{tenant_id}} with the customer's specific Microsoft 365 Tenant ID.

- **SharePoint & OneDrive Activity** Captures file-level and site-level user activities such as access, sharing, downloads, and modifications.

```plaintext
https://manage.office.com/api/v1.0/{{tenant_id}}/activity/feed/subscriptions/start?contentType=Audit.SharePoint
```
- **Microsoft Entra (Azure AD) Activity**

Captures identity and directory-level events such as logins, user updates, and authentication activities.

```plaintext
https://manage.office.com/api/v1.0/{{tenant_id}}/activity/feed/subscriptions/start?contentType=Audit.AzureActiveDirectory
```
- **Data Loss Prevention (DLP) Events**

Captures sensitive data handling events, including policy matches and violations across Microsoft 365 services.

```plaintext
https://manage.office.com/api/v1.0/{{tenant_id}}/activity/feed/subscriptions/start?contentType=DLP.All
```

For more information you can see [Office365 Management Activity API reference](https://learn.microsoft.com/en-us/office/office-365-management-api/office-365-management-activity-api-reference). These activity feeds provide the data required for Activity Analysis in Securiti.

> [!NOTE]
> Note
> 
> **Initial Data Availability**
> 
> - After enabling activity collection, it may take up to 12 hours for the first activity data to appear in Securiti.
> - During this time, no activity logs will be visible in the Activity Explorer.
> 
> **Data Retention**
> 
> - Microsoft retains activity data for 7 days only.
> - Data older than 7 days is permanently deleted and cannot be retrieved.
> 
> **No Historical Backfill**
> 
> - Activity data is only collected after enabling the integration.
> - Historical logs (prior to setup) are not available.
> 
> **Scan Scheduling and Data Gaps**
> 
> - Securiti Activity Analysis runs on autoscan jobs with a 7-day cadence, while Microsoft retains activity data for only 7 days.
> - Misalignment, delays, or execution gaps can lead to permanent data loss and incomplete results.
> - Ensure scans are scheduled and monitored carefully to avoid exceeding this retention window.

****Step 4 - Connector Activation and Scans Configuration****

To configure SharePoint Privilege Analysis, There are some prerequisites:

**Prerequisites**

1. [You must have a configured Data System connector for Sharepoint](/v1/docs/microsoft-365-sharepoint-online-connectors).
  - Access Intel supports both Customer Self-Hosted Connectors and Securiti Cloud Hosted Connectors.
2. If you want to use Vault Credentials for configuring connector as a Metadata source, you must have to follow the steps stated in step 4B **(Configuring Vault Credentials for using Connectors as a Metadata Source)**.
3. You must have [performed a Discovery Scan](https://helpcenter.securiti.ai/docs/configure-discovery-scans-in-microsoft-365-sharepoint-online) on your selected scope of your Sharepoint Account.

OR

Perform an Inventory Sync. Note that if you want to get visibility into the users' access to data elements, then you must perform a discovery scan. If you want file-level access visibility, then you must perform an inventory sync.
4. Supported Authentication for Access Intelligence Scans
  - Oauth using an Azure Application with Microsoft Graph API and SharePoint permissions (Client ID, Client Thumbprint, and Private key used for authentication)

For **Configuring Access Intelligence Privilege and Activity Analysis for SharePoint with and using IAM Metadata Sources** step 1 to 3 are same as stated above in pre-requisites.

#### Configuring Access Intelligence Privilege and Activity Analysis for SharePoint using IAM Metadata Sources

****Step 4 A - Configuring your Sharepoint Access Scans for Access Intelligence****

**1. Configure an IAM Metadata Source for your data system**

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SF5Z1E26.png)
2. Click **IAM Metadata Sources**. This opens the IAM Metadata Sources page.
3. Near the upper right corner of the page, click **+New IAM Metadata Source**.
4. On the **New IAM Metadata Source** popup:

> [!NOTE]
> **Note**
> 
> Note that if you configure a Metadata Source using the ClientID, Certificate Thumbprint, and Certificate, and the scanning exceeds more than one hour, you may encounter this error:
> 
> ```plaintext
> "error_description":"Invalid JWT token. The token is expired."}}
> ```
> 
> To avoid this scenario, see [Microsoft documentation](https://learn.microsoft.com/en-us/entra/identity-platform/configure-token-lifetimes) to increase the lifespan of the token.
  1. Enter the **Connection Name**. For example, SharePoint Metadata Source.
  2. Select the SharePoint in **Source Type** if you want to create a metadata source for SharePoint Cloud. If you want to create a metadata source for SharePoint (Self-Hosted), select SharePoint On Prem. Note that for SharePoint Onprem you must have a pod configured, before creating the metadata source.
  3. Enter the **Tenant ID**.
  4. In the Authentication Details area, select oAuth2.0 as Authentication Type.
  5. Enter the **Client ID** and **Certificate** **Thumbprint**.
  6. Upload the Private Key File. .pem file format is supported.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(49).png)
  7. Click Create **New IAM Metadata source**.

**2. Configure an Access Scan Definition for your data system**

1. In Securiti, open **Data Access Governance**, then from the left menu bar choose **Settings>Access Scan Definitions**.
2. Near the upper right corner of the page, click **+ New Access Scan Definition**.
3. On the New Access Scan Definition popup:

1. Enter the **Name** for the Access Scan Definition.
2. Select **Microsoft 365 SharePoint Online** for Securiti Cloud Hosted SharePoint in **Data System** to scan for IAM related metadata.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7IDFD0NT.png)
3. Enter the **Tenant ID**.
4. In the Source of Credentials and Connectivity for Access Intelligence Scans section, select one of the following:

**IAM Metadata Sources** : Select this option if you want to use a configured IAM metadata source to retrieve IAM and RBAC metadata.

**Data System Connector** : Select this option if the data system connector will act as the source of credentials and connectivity.
5. If you select **IAM Metadata Sources**, choose the required metadata source in the Metadata Sources field. If you have not configured a **metadata source**, click **+ New IAM Metadata Source** to create one.

> [!NOTE]
> **Note**
> 
> You can create multiple ASDs for the same data system type (e.g., multiple SharePoint ASDs). However, you cannot create two ASDs for the same account/configuration, the same combination of Tenant ID and Client ID. Attempting to do so returns an "ASD already exists" error.

1. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
2. In the **Privilege Analysis Configuration** area, choose what access metadata you want to collect for SharePoint. These options let you align scan execution with business goals and can help reduce scan duration for large SharePoint environments.

The available options are:

**Default behavior**

If you do not select any option in the Privilege Analysis Configuration area, Securiti will only gather the **SharePoint Site Level Permissions for Users and Groups**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-W0WX9PGL.png)

> [!NOTE]
> **Note**
> 
> These scoping options control what privilege metadata is collected during the access scan. Selecting more options provides deeper visibility but may increase scan time, especially for large SharePoint deployments.

![System settings interface showing discovery scan selection and associated connectors options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/step.png)

In the **Privilege Analysis Configuration** area, under **Discovery Scan Id Selection**, select one or more discovery scans to limit the access scan to specific SharePoint Online (Self-Hosted) sites, as shown below.

> [!NOTE]
> **Note:**
> 
> The menu shows only discovery scans whose provider type matches the ASD.
> 
> When a Discovery Scan scope is configured, Securiti only validates the top-level SharePoint Sites present in the Discovery Scan configuration. It then includes those top-level Sites, and automatically any sub-sites those Sites may have, in the scan.
> 
> Note that sub-sites that are configured by themselves in the Discovery Scans are not included in the scan. In other words, if your Discovery Scan scope configuration contains a sub-site (for example, subsiteA under siteA), Securiti will not include it in the scan. If you want to include a sub-site in the scope, you must add its top-level site (siteA) to the Discovery Scan scope. Note that, when this is done, due to the nature of the selection, all other sub-sites will also get selected for scanning e.g., when siteA is added to the Discovery Scan in order to scan subsiteA, not only will subsiteA get selected for scanning, but all other sub-sites of siteA will also be scanned.
  - **Individual File Level Permissions** Collect permission assignment information for every file and folder in the Document Libraries of each Site in the SharePoint account. This provides detailed file-level access visibility across the account.
  - **Sharing Link Permissions** Collect file and folder sharing link information, including links shared anonymously or with external users.
3. (Optional) In the **Scan Configuration section**:

Select **Auto Scan** if you want the system to automatically scan or re-scan access information weekly.

Select **Activity Analysis** if you want to enable scanning of the selected data system for activity logs. This lets you analyze user activity and access events associated with the data system.

Select **Specify time periods** to exclude for running scans and mark the required hours and weekdays during which scans should not run.
4. Click **Add Definition**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TZZZGYIX.png)

**3. Enable the Access Intelligence Scan**

Enable the Access Intelligence Scan toggle on the Data System Connector Page. Navigate to the **Permissions** tab of the Connector. Enable the Access Intelligence Scan button to link the ASD with the data system connector.

**4. Launching the Access Scan**

On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.

Click the three dots option, and select the **Scan Now** option.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(50).png)

#### Configuring Access Intelligence Privilege and Activity Analysis for SharePoint without using IAM Metadata Sources

For **Configuring Access Intelligence Privilege and Activity Analysis for SharePoint without using IAM Metadata Sources** steps 1 to 4 are same as stated above in pre-requisites.

****Step 4B - Configuring your Sharepoint Access Scans for Access Intelligence****

To configure Access Scans for Access Intelligence, you must:

1. In Securiti, open **Data Access Governance,** from the left menu bar, click **Settings**.
2. Click **Access Scan Definitions**. This opens the Access Scan Definitions (ASDs) page.
3. Near the upper right corner of the page, click **+ New Access Scan Definition**.
4. On the New Access Scan Definition popup:
  1. Enter the **Name** for the Access Scan Definition.
  2. Select **Microsoft 365 SharePoint Online Onprem** in the **Data System** menu. For more information, see [Configuring Access Intelligence Scans without using IAM Metadata Sources](/latest/docs/access-intelligence-scans-without-using-iam-metadata-sources).
  3. Specify the Sharepoint Tenant ID (xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx) in the **Account**.

Securiti will provide the list of all the relevant instances of the selected data systems configured using the provided Account ID in the **Data System Connector** menu.
  4. In the **Source of Credentials and Connectivity for Access Intelligence Scans** area, you must select the **Data System Connector** tile.

> [!NOTE]
> Note
> 
> You can create multiple ASDs for the same data system type (e.g., multiple SharePoint ASDs). However, you cannot create two ASDs for the same account/configuration, the same combination of Tenant ID and Client ID. Attempting to do so returns an "ASD already exists" error.

![DAG_Connector_as_MDS_ASD.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3c56dba-3bfe-1031-2e93-6ca917a8fb4a(1).png)
  5. In the **Data System Connector** menu, select the data system instance for which you must perform Access Scan.
  6. In the **Data Systems** menu, the instance you selected earlier in **Data System Connector** is selected by default. You can also select other instances related to provided Account ID if required.
  7. In the **Associated Connectors** area, select the associated systems in the **Data Systems** for which access metadata is being scanned.
  8. In the **Privilege Analysis Configuration** area, choose what access metadata you want to collect for SharePoint. These options let you align scan execution with business goals and can help reduce scan duration for large SharePoint environments.

The available options are:

**Default behavior**

If you do not select any option in the Privilege Analysis Configuration area, Securiti will only gather the **SharePoint Site Level Permissions for Users and Groups**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(10).png)

> [!NOTE]
> **Note**
> 
> These scoping options control what privilege metadata is collected during the access scan. Selecting more options provides deeper visibility but may increase scan time, especially for large SharePoint deployments.
    - **Individual File Level Permissions** Collect permission assignment information for every file and folder in the Document Libraries of each Site in the SharePoint account. This provides detailed file-level access visibility across the account.
    - **Sharing Link Permissions** Collect file and folder sharing link information, including links shared anonymously or with external users.
  9. (Optional) In the Scan Configuration area, mark the **Auto Scan** checkbox if you want to automatically scan or re-scan the access information weekly.
  10. Mark the **Activity Analysis** checkbox if you want to see the user activity related data for selected data system. Note that the **Activity Analysis** is supported for SharePoint and Starburst, the option will be displayed only if you select SharePoint or Starburst in the **Data System** menu.
  11. (Optional) Enable **Specify time periods to exclude for running scans** to select the hours on specific weekdays at which you do not want to run the scans.
  12. Click **Add Definition**.
5. On the Access Scan Definition page, activate the Access Scan Definition that you created by enabling the toggle.
6. Click the three dots option, and select the **Scan Now** option.

### **Interactive Demo**

To see these steps in action, watch the video below:

[Embedded content](https://app.storylane.io/demo/pchfdlapmjvc?embed=popup)

### **Configuring Vault Credentials for using Connectors as a Metadata Source**

This section describes how to configure Credential Vaults and execute SharePoint Access Intelligence scans when your SharePoint connector retrieves credentials from an external vault using a key ring. When the key ring is enabled on the SharePoint connector, Securiti fetches credentials from the configured vault at scan runtime. This lets you store and rotate credentials in the vault without updating the connector.

**Supported vault provider**

- **HashiCorp Vault**

Ensure the following prerequisites are met:

- You must have configured and activated a SharePoint connector.
- Your HashiCorp Vault instance is unsealed and reachable from the appliance.
- The appliance can connect to the Vault endpoint (network access/allowlisting is in place).
- You have permissions to create **Credential Vaults**, **Key Rings**, and **Access Scan Definitions**.

> [!NOTE]
> **Note** If you update the credential values in the vault, you do not need to re-activate the connector. The next scan fetches the latest values. If you change the vault path or the vault instance settings (for example, host, port, auth method), you must update the key ring or vault configuration.

**Step 1 – Configure a Credential Vault (HashiCorp)**

This step lets you configure the connection between Securiti and your [HashiCorp Vault instance](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault).

1. In Securiti, go to **System Settings > Integrations > Credential Vaults**.
2. In the **HashiCorp** tile, click **View Instances** and then create a new instance. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112620393.png)
3. On the **Basic Information** tab:
  - Enter the instance name.
  - Set instance location and owner (if required by your tenant configuration).
4. Click **Create Instance & Continue**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112620395.png)
5. On the **Instance Setup** tab, provide your Vault connection details, such as:
  - **Host**
  - **Port**
  - **Authentication Method** (for example, **AppRole**)
  - **AppRole ID**
  - **Secret** (as required)
  - **Namespace** (optional)
6. **Enable Mutual TLS (mTLS)** (optional) ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112620396.png)
7. Click **Test Connection** and verify connectivity.
8. Click **Save**.
9. Open the **Status** tab and confirm the vault instance shows **Authentication completed**.

> [!WARNING]
> **Important** You must complete vault authentication successfully before you can use this vault instance for key rings.

**Step 2 – Create a Key Ring for SharePoint credentials**

A key ring specifies where the SharePoint credentials are stored in the vault and which keys should be fetched.

1. Go to **System Settings > Integrations > Keyrings**.
2. Click **Create Keyring**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112620397.png)
3. In **Keyring details**, provide:
  - **Keyring Name**
  - (Optional) **Keyring Description**
  - **Keyring Type**: HashiCorp Vault
  - **Connector Type**: Microsoft 365 SharePoint Online
  - **Vault Instance**: Select the HashiCorp Vault instance created in Step 1
  - **Secrets Engine**: Select the secrets engine (for example, **KV Version 2**)
  - **Secrets Engine Path**: The mount path where the secrets engine is accessible (for example, secrets/)
4. **Credential Path**: The path inside the vault where credential secrets are stored (for example, secrets/sharepoint/<path>) ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112650863.png)

**OAuth 2.0 Secrets Engine Plugin (With plugin vs without plugin)**

The **OAuth 2.0 Secrets Engine Plugin** toggle determines how authentication works.

- **Without OAuth plugin (toggle OFF)**: Securiti generates OAuth tokens during scan execution using long-lived credentials fetched from the vault.
- **With OAuth plugin (toggle ON)**: Securiti does not generate OAuth tokens. It consumes ready-to-use tokens stored in the vault.

**Configure credential key names (only required when OAuth plugin is disabled)**

In the **Credentials Key Name** section, provide the key names exactly as stored in the vault.

**Option A: Without OAuth plugin (toggle OFF) – Client Secret authentication**

Provide:

- **Client ID Key**: client_id
- **Client Secret Key**: client_secret

**Option B: Without OAuth plugin (toggle OFF) – Certificate-based authentication**

Provide:

- **Client ID Key**: client_id
- **Certificate ThumbPrint Key**: certificate_thumbprint
- **Private Key**: private_key

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112651135.png)

**Option C: With OAuth plugin (toggle ON)**

When **OAuth 2.0 Secrets Engine Plugin** is enabled, you only need to configure the vault location details (Secrets Engine Path and Credential Path). You do not need to provide credential key names in the key ring.

Securiti automatically fetches OAuth token values from the vault during scan execution.

> [!NOTE]
> Note
> 
> Ensure the vault secret at the configured Credential Path contains valid OAuth token values (for example, access token and refresh token). If the token values are missing or expired, the scan fails.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112651332.png)

**Step 3 – Configure the SharePoint connector to use the Key Ring**

This step configures the Microsoft 365 SharePoint Online connector to authenticate using credentials retrieved from HashiCorp Vault through the key ring created in Step 2.

Configure the SharePoint Online connector

1. In Securiti, go to **System Settings > Integrations > Data Systems > Monitored**.
2. Locate **Microsoft 365 SharePoint Online (Self-hosted)** and click **Create Instance** (or open an existing instance). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112651487.png)

On the **Basic Information** tab:

- Enter the **Instance Name**.
- Set the **Hosting Location** (for example, SaaS).
- Select the **Country** and **State/Region**.
- Assign the **Primary Owner**.
- Click **Save** or **Create Instance & Continue**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112655355.png)

On the **Connector** tab, configure the following settings.

Connector connectivity

- **Connect with Pod** Select the appliance (pod) that will connect to Microsoft 365.
- **Cloud** Select **Microsoft Graph global service**.
- **Tenant Name** Enter the Microsoft 365 tenant name.
- **Tenant ID** Enter the Azure Active Directory (Azure AD) tenant ID.

Enable vault-based authentication

- **Use Keyring** Enable this toggle.
- **Keyring Selection** Select the key ring created in **Step 2**.

> [!NOTE]
> Note
> 
> When **Use Keyring** is enabled, Securiti retrieves authentication credentials from HashiCorp Vault at runtime. Credential fields such as **Client ID**, **Client Secret**, **Certificate Thumbprint**, and **Private Key** are not manually populated in the connector.

Optional connector settings

- **Use Mock Server** Leave disabled unless required for testing.
- **Enforce Selective Site(s) Access** Enable only if you want to restrict scans to specific SharePoint sites.
- **Root domain for different regions** Configure only if your tenant uses different regional SharePoint domains.

**Save and authenticate the connector**

- Click **Save**.
- Securiti authenticates the connector using credentials fetched from HashiCorp Vault via the key ring. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112655540.png)

Once authentication completes, the **Connector Status** section is automatically populated and displays verified information, including:

- Connector state (Active/Inactive)
- Authentication status
- Connector scopes synchronization status
- Pod connection details
- Tenant name and tenant ID
- Key ring usage and vault integration status
- OAuth 2.0 Secrets Engine Plugin status

These values are **system-derived and read-only** and do not require manual configuration.

**Inventory and entitlement configuration (optional)**

After the connector is successfully configured, you can optionally configure:

- **Inventory Sync Options** (Private Preview)
  - Run Data Inventory Sync
  - Run Gencore AI Entitlement Scan ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112655559.png)
- Data Inventory and Entitlement Sync Scope
  - Sites
  - Site collections
  - Libraries
  - Folders

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1782112655820.png)

These settings control scan scope, execution of the Access Scan Definition and only the selected Sites will be addressed in ASD.

At the end of this step:

- The SharePoint Online connector is configured to use **HashiCorp Vault–stored credentials** through the key ring.
- No credentials are stored directly in the Securiti platform.
- The connector is ready to be used when creating **Access Scan Definitions (ASDs)** for Access Intelligence.

To configure **Access Scans for Access Intelligence using vault credentials**, you have to follow the same steps as stated in Step 4B - Configuring your Sharepoint Access Scans for Access Intelligence

> [!NOTE]
> Note
> 
> If the selected connector has a key ring enabled, Securiti fetches credentials from the configured vault during scan execution. Credentials stored directly in the platform database are not used for this scan.

## Configuring Cross Border Data Transfer Policies for Microsoft 365 Sharepoint Online

To manage a Cross Border Transfer Policy for your Microsoft 365 Sharepoint Online instance, there are some prerequisites:

### Prerequisites

- [Set up a Securiti pod or elastic pod.](/v1/docs/securiti-pods-and-elastic-pods)
- [Configure and activate the connector](/v1/docs/microsoft-365-sharepoint-online-connectors).
- Perform a discovery scan on your SharePoint instance.
- [Configure an IAM Metadata Source](/v1/docs/creating-a-data-labeling-policy-for-microsoft-365-sharepoint-online).
- [Configure an Access Scan Definition for your SharePoint instance](/v1/docs/creating-a-data-labeling-policy-for-microsoft-365-sharepoint-online).

> [!NOTE]
> **Note**
> 
> Cross Border Data Transfer Policies for SharePoint utilize the metadata gathered from SharePoint Activity Analysis. Therefore, it is mandatory to configure Activity Analysis for SharePoint to receive alerts for your cross border data transfers using policies.
- Define **Data Subject Types**, e.g. employees, job applicants, prospects, partners, etc. for the SharePoint asset in the data mapping automation module. See [creating and editing data subjects](/v1/docs/using-data-mapping-automation).
- Define an Institute in the data mapping automation module. Specify the **Primary Covered Entities**e.g., Educational Institutions, Medical Industry, and **Secondary Covered Entities** e.g., Public Universities, Healthcare Providers, etc. See [creating and editing institutions](/v1/docs/using-data-mapping-automation)

### Demo of Cross border transfer policies

**Interactive Demo**

To see these steps in action, watch the video below:

[Embedded content](https://app.storylane.io/demo/tkijbzpd8jbk?embed=popup)

### Viewing cross-border transfer findings

Cross-border transfer policies let you mitigate the risk associated with illegal data access across borders and assist with the remediation through governance workflows.

To view the cross-border transfer findings, click on the **Cross-Border Transfer** from the left panel. The widgets at the top show you the metrics for **Open Findings**, and count for **Fixed and Suppressed Findings**. The trendlines for the **Open Findings and Closed Findings by Status** show you the weekly, monthly, quarterly, and yearly trends.

Below the widgets, there is a search bar to sort the findings based on the rule name, description, or issue.

Below the search bar, the tiles show you the counts for the **Total Rules with Findings** and **Open Findings**. You can view and group these findings based on:

- Rule
- Owner
- Policy
- Data Source

To group the findings, click on the Group by drop-down menu on the right side, and select the parameter based on which you must sort the findings.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8(8).png)You can also sort the alerts and findings based on the:

- Status
- Severity
- Finding ID
- Subscription
- Owner

Click on the Column selector to select the columns you want to see and rearrange them by dragging and dropping.

You can suppress the findings and change the assignee for a particular finding. To suppress a finding or change its assignee, select the finding, and click on the **Suppress Finding** button. The status of the finding will be changed to **Suppressed**. To Change the Assignee, select the finding, click on the **Change Assignee** button, and select the user in the popup to which you must assign the finding.

## Configuring Data Access Control Policies for Microsoft 365 SharePoint Online

This access control policy type lets you grant or revoke access to your SharePoint Sites.

### Prerequisites

To configure an Access Control Policy for Microsoft 365 SharePoint Online, Steps 1 to 3 from pre-requisites are same and next you have to follow the steps below:

1. Configure Tenant Wide Permissions:
  1. Browse to the following URL, where <tenant> is your Microsoft 365 SharePoint Online tenant name:

https://<tenant>-admin.sharepoint.com/_layouts/15/appinv.aspx

For example, if your Microsoft 365 default domain is sometenant.onmicrosoft.com, your tenant name is sometenant and you would browse to:

https://sometenant-admin.sharepoint.com/_layouts/15/appinv.aspx

You must be a SharePoint Online Administrator (or Global Administrator) to access and use this page.
  2. In the Classic SharePoint admin center apply the following settings, then click **Lookup**.
  3. Enter the Application Id in the **App Id**.
  4. Enter your company’s tenant domain in **App Domain**. The admin center populates the title and the redirect URL for the application.
  5. In the Permission Request XML box, copy and paste the following text:

```plaintext
<AppPermissionRequests AllowAppOnlyPolicy="true">
                                                <AppPermissionRequest
                                                Scope="http://sharepoint/content/tenant" Right="FullControl" />
                                                </AppPermissionRequests>
```
  6. Click **Create**. The admin center redirects you to authenticate the app.
  7. Click **Trust It**.
2. [Set up a pod or elastic pod](/v1/docs/securiti-pods-and-elastic-pods).
3. [Configure and Activate the Connector](/v1/docs/activate-the-onedrive-cloud-connector-in-securiti). Microsoft 365 SharePoint Connector's Scope Sync will fetch SharePoint Sites.
4. Mark the checkbox for **Enable Data Access Control** in the data system’s **Permissions** tab, so that this data system is available for selection when you create the policy.
5. Perform a discovery scan for the SharePoint instance.
6. Configure an IAM Metadata Source and ASD for SharePoint as mentioned in step 4A.

### Creating data access control policies

1. In Securiti, click **Jewel icon** and from the left navigation drawer then choose **Policies>Data Access Control Policies**.
2. Near the upper right corner of the page, click **Create Policy**.
3. On the Create a New Policy popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **Microsoft 365 SharePoint Online**.
  3. Click **Get Started**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(11).png)
4. Enter a name for the policy.
5. (Optional) Add a description for the policy. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7(9).png)

In the Scope area, you can choose to:

- Grant or Revoke access of Users and Groups to SharePoint Sites by adding or removing them in Owners, Members, Visitors, and Admin groups in SharePoint.

OR
- Add or remove users from Owners and Members of Microsoft 365 Groups.

### Grant or Revoke Users and Groups' access to SharePoint Sites

To grant or revoke Users and Groups access to SharePoint Sites:

1. In the Scope area, select the **SharePoint Sites** card. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(11).png)
2. In the Site scope selection area, click **Edit Query** to add the Site to which you must Grant or Revoke Users' and Groups Access. Note that if you do not specify the Sites, the policy would be applied to all the Sites identified during Metadata sync or discovery scans.
  - Select the Site from the data grid on which you must apply the policy.
  - Apply the **increment (+ icon)** operator to add the entity and attribute as an include rule to the page filter. The added filter appears in the top row of the dashboard with the rest of the filters.
  - Near the upper right corner, click **Use Query** to add the selected Site as a scope. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(23).png)
3. In the **Access Condition** area, select **Grant** or **Revoke** to add or remove principals (users and groups) from the selected SharePoint site. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(19).png)
4. In the **Access Level** menu, specify the membership type that you must assign to the principals (users and groups) for the selected site. You must select one of the following membership types:
  - Admin
  - Owners
  - Visitors
  - Members
5. In the **Principals** area, select the Users and Groups that you must provide access to the selected Site.

Note that you will not be able to add/remove a group from another group.
  - To add a user, select the users from the menu. You can also add the users using the menu or use Graph Query button. You must select O365 Users to grant or revoke access for Site.
  - To add a group, click **+ Add a Principal**. Select **Groups**. You can select the Groups from the list. You can also add the Groups using the menu or use Graph Query button. You must select O365 User Group Principal. You can set the Group Type property to O365 to sort O365 User Groups. Sharepoint groups cannot be added in the principals for a policy on a site; only O365 Parent Groups can be used.

![Graph Explorer interface showing User Group Principal and Office365 provider type filter.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (12).png)

### Add or remove users from Owners and Members of Microsoft 365 Groups

To add or remove from Owners and Members of Microsoft 365 Groups:

1. In the Scope area, select the **Microsoft 365 User Groups** card.

![SPO_Policy_Usergroups_card.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-75c1a775-c8b8-096a-9fb5-309660565a99.png)
2. In the User Group Principal scope selection area, click **Edit Query** to add the User Group Principal to which you must add or remove Users.
  - Select the User Group Principal from the data grid on which you must apply the policy. You can specify the **Properties** of the User Group Principal to sort the list of User Group Principals.
  - Apply the **increment (+ icon)** operator to add the entity and attribute as an include rule to the page filter. The added filter appears in the top row of the dashboard with the rest of the filters.
  - Near the upper right corner, click Use Query to add the selected User Group Principal as a scope.
3. In the **Access Condition** area, select **Grant** or **Revoke** to add or remove Users from the selected User Group.
4. In the **Access Level** menu, specify the membership type that you must assign to the principals (users) for the selected User Group. You must select one of the following membership types:
  - Owners
  - Members
5. In the **Principals** area, select the Users that you must add or remove from the selected User Group.
  - To add a user, select the users from the menu. You can also add the users using the menu or use Graph Query button.

## Viewing Access Intelligence for Microsoft 365 SharePoint Online

### Configuring the Resource Access Control List Access Intelligence model for SharePoint Online

To use the **Resource Access Control List** Access Intelligence model for SharePoint Online, follow the steps listed below.

Check that the SharePoint Online connector or **IAM Metadata Source** is authenticated using **Client ID and Certificate**. Note that the **Resource Access Control List** model does not support **Client ID and Secret** authentication method. If that is the configured authentication method, then you must do the following.

1. Reset the **Access Scan** from the **Access Scan Definition**.
2. Deactivate the **Access Scan Definition** and remove the **IAM Metadata Source** or the **Data System Connector** from the **Access Scan Definition**.
3. Delete the **IAM Metadata Source** and create a new one with **Client ID and Certificate**.
  1. Or if using the **Data System Connector** as the source of authentication, reconfigure that Connector to use the **Client ID and Certificate** method, and authenticate the connector.
  2. Reconfigure the **Access Scan Definition** to use the new **IAM Metadata Source** or the **Data System Connector**.
4. Ask your **Customer Success Manager** or **Account Representative** to enable the **Resource Access Control List** Access Intelligence model on your tenant.
5. Initiate the **Access Scan** from the **Access Scan Definition**.

If the SharePoint Online connector is already authenticated using **Client ID and Certificate**, then you must:

1. Reset the **Access Scan Definition**.
2. Ask your **Customer Success Manager** or **Account Representative** to enable the **Resource Access Control List** Access Intelligence model on your tenant.
3. Initiate the **Access Scan** from the **Access Scan Definition**.

### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality.

For more details, see [reporting dashboard documentation](https://helpcenter.securiti.ai/docs/reporting-dashboard).

### Monitoring SharePoint access using reporting dashboard widgets

Microsoft 365 Data and AI Security dashboard includes predefined widgets that let you monitor SharePoint access and sensitive data exposure at a glance.

**All Files Containing Sensitive Data** displays all files that contain sensitive data within your Microsoft 365 environment.

**Files Accessible by All Users** displays the number of files that are accessible by the EEEU (Everyone Except External Users) group in Microsoft 365, helping you monitor content that is potentially shared with users without proper security controls.

![Overview of file counts and sensitive data types in SharePoint system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-23 at 7.41.18 PM.png)

**User Groups with Access to Sensitive Data** displays the list of user groups that have access to sensitive data within Microsoft 365.

**Sites that Allow External Sharing** or **Externally shareable SharePoint sites with Sensitive Data** displays the list of SharePoint sites where external sharing is enabled and a site-level sensitivity label is present, along with the site's sharing capabilities. This widget is populated during the Scoping Inventory Sync and doesn't require a Data Inventory Sync or Discovery scan.

![Overview of user groups with access to sensitive data and external sharing sites.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-23 at 7.41.47 PM.png)

**SharePoint Sites Containing Sensitive Data** displays SharePoint sites containing sensitive data, helping you identify locations where sensitive information is stored. This widget is populated using sensitivity labels collected during the Scoping Inventory Sync. It doesn't require a Data Inventory Sync or Discovery scan.

**Sites Accessible by All Users** displays the count of sites that are accessible by the EEEU (Everyone Except External Users) group, helping you track potentially exposed sites across the organization.

![Overview of SharePoint sites containing sensitive data and user access details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-23 at 7.42.02 PM.png)

> [!NOTE]
> **Note**
> 
> - A site's sensitivity label reflects the site-level sensitivity setting configured in Microsoft 365. It's independent of file-level classification labels and doesn't require a Data Inventory Sync or Discovery scan to populate.
> - Sensitivity label ingestion requires pod version 1.142.0+ and certificate/thumbprint authentication. For more information, see [**Supported items for inventory and classification scans**](/latest/docs/microsoft-365-sharepoint-online-connectors) and [**Reviewing SharePoint scan results in Securiti**](/latest/docs/reviewing-sharepoint-scan-results-in-securiti).

### SharePoint pre-flight checks for access scans

Securiti runs a pre-flight check before it collects any data for a SharePoint access scan. The pre-flight check is a preemptive probe that rules out configuration and permission issues before they can cause the scan to fail. It confirms that the connector's app registration, or the IAM metadata source if the Access Scan Definition is configured to use one instead of the connector, has valid credentials and the required permissions.

Securiti separates collection of metadata during a scan into different streams based on the different types of metadata to be collected, for example, SharePoint and O365 users and groups, Sites, Documents, etc. The pre-flight tests execute for each of these streams and send specific probes relevant to each type.

> [!NOTE]
> Note:
> 
> If a metadata type's required permission isn't granted, the pre-flight check fails for that metadata type only, and Securiti skips collection for it. The entire collection still fails, even if all the other metadata types passed their checks. See [Permissions for SharePoint Access Intelligence Privilege and Activity Analysis](https://helpcenter.securiti.ai/docs/microsoft-365-sharepoint-online#permissions-for-sharepoint-access-intelligence-privilege-and-activity-analysis1) for the required permissions.

#### How the pre-flight check works

For each metadata type, Securiti runs the following checks before starting collection:

1. Loads and validates the credentials configured for the IAM Metadata Source or the Connector.
2. Sends one or more probes (for example, testing relevant API endpoints) to validate the credentials' authorization status vis-a-vis the metadata type in question.

If the probe succeeds, Securiti collects that metadata type. If it fails, Securiti stops collection for that metadata type and logs the reason.

![Session log showing successful pre-flight checks and API initializations for SharePoint.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/1-how-it-works-session-log.png)

#### Troubleshooting pre-flight failures

| Error | Cause | Solution |
| --- | --- | --- |
| `Authorization_RequestDenied: Insufficient privileges to complete the operation` | The app registration, or IAM metadata source if used, is missing a required permission for the particular metadata type. | Grant the missing permission to the app registration, and then retry the scan |
| `App:&lt;app-id&gt; dont have any permissions` | The app registration is missing the required permission for the particular metadata type. | Grant the missing permission to the app registration, and then retry the scan |
| Pre-flight check failed for all metadata types | The client certificate is invalid or has expired. | Requires reconfiguration and reauthorization of the connector or IAM metadata source with the updated certificate |

![Audit log showing system updates and access scan collection details for June 2026.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/2-troubleshooting-audit-log-jun25.png)

![System updates showing multiple access scan definition failures and pre-flight check errors.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/3-troubleshooting-audit-log-jul28-failures.png)

> [!NOTE]
> **Note:**
> 
> Every pre-flight failure creates an audit log entry with the failure reason, along with the correlation ID, batch ID, and account ID for that scan run. Use these IDs to trace the specific run in the audit log.

![Audit log displaying system updates and access scan collection statuses for various users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/4-troubleshooting-audit-log-sep1-statuses.png)

### Using Access Intelligence (Privilege Analysis) Microsoft 365 Sharepoint Online

Below are example use cases to familiarise you with how to leverage Securiti's Data Command Graph to identify access and risk in your Sharepoint tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

**Viewing Access details using Resource Access node**

A **principal** can appear to have access to a resource even when **Is Direct Access** is 🅇 and no direct assignment was made. Access can be inherited through group membership, site membership, or through a permission set at the folder or the site level. The four columns below explain where the access originates.

**Resource Scope**

**Resource Scope** shows the URL at which the permission is defined. This is the most important column for understanding the source of access. There are three tiers:

| Resource Scope URL | What it means |
| --- | --- |
| ```plaintext Site URL (https://.../sites/site_name) ``` | No permission was set at folder or file level. Access is indirectly obtained from site-level group membership or assignment. |
| ```plaintext Drive URL (https://.../sites/site_name/Shared%20Documents) ``` | A permission was set on a drive or at the site-level. All resources within it show this URL as their scope. |
| ```plaintext File URL (https://.../sites/site_name/Shared%20Documents/file.txt) ``` | A permission was set on that specific file only. |

**Is Direct Access**

**Is Direct Access** indicates whether the **principal** in that row was explicitly assigned to the resource:

- ✓ The **principal** was explicitly assigned to the resource.
- 🅇 The **principal**'s access flows through group membership.

**Configured User Groups**

**Configured User Groups** lists only the direct group **principals** through which permission was given. A user or group can have access to a resource through nested permissions; this column helps identify from where permission originated.

If a **principal's** row shows **Is Direct Access** = 🅇, the group through which they have access appears in this column. For example, if Group B is nested inside Group A and Group A was assigned to the resource, Group B's row shows Group A in this column, because that is the assignment giving Group B access.

**Configured Users**

**Configured Users** identifies the **User Principals** who have direct access to the resource. If a **principal** was directly assigned, their name appears in this column on their own row. If their access is indirect, via a **User Group**, this column will be empty. Refer to the **Configured User Groups** section for more information on this scenario. When the principal does have direct access to the resource, the **Is Direct Access** column will display a checkmark **(✓)** as well.

> **Note:**
> 
> **Configured Users** and **Configured User Groups** are independent columns that both describe what is configured on the resource. A resource can have both individual users and groups assigned at the same time, so both columns can be populated on the same row. **Is Direct Access** tells you specifically whether the **principal** in that row was directly assigned **(✓)** or is accessing through a group **(🅇)**.

**Privilege Bundle**

**Privilege Bundle** shows the permission level assigned to the principal:

| Privilege Bundle | Grants |
| --- | --- |
| **Full Control** | Add, edit, delete, approve, and manage content |
| **Edit** | Add, edit, and delete content |
| **Contribute** | Add and edit content |
| **Read** | View content only |
| **Restricted View** | View content only, in browser, with no download |
| **Limited Access** | No usable access |

Organizations can also define custom permission levels beyond the ones listed above. The custom name appears as-is in **Privilege Bundle**, but **Privileges** and **Privilege Categories** still reflect the actual actions configured for that level, not the name itself.

For example, if an organization creates a custom permission level called `Content Reviewer` that only allows opening and editing content, with no delete, approve, or manage rights, **Privilege Bundle** for that row shows `Content Reviewer`, **Privileges** shows `OpenItems` and `EditListItems`, and **Privilege Categories** shows **Read** and **Write**, the same categories any bundle granting those two actions would show, whether the bundle name is standard or custom.

**Privileges** lists the granular actions the bundle grants. **Privilege Categories** normalizes those actions into three fixed types: **Control**, **Read**, and **Write**, so any bundle, standard or custom, maps to the same categories based on what it grants, not its name.

**Access Type**

**Access Type** shows how the access was delivered either as a `RoleAssignment` (a direct or group permission) or a `SharingLink` (a generated share link).

![Access Graph Explorer displaying resource access and privilege assignments for various entities.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3(13).png)

> [!NOTE]
> **Note:**
> 
> To learn more about identifying users with sharing link-based access to files in SharePoint Online, and the additional details captured for this access type, see **Identify users with sharing link-based access to files in SharePoint Online**.

**Examples**

**Example 1: Access through site group membership**

`IAM Test User3` has access to `STRESS_100_3.txt` even though **Is Direct Access** = 🅇 and **Configured Users** is empty. The reason is in **Configured User Groups**: the **principal** belongs to `auto_site_290 Members`, a group assigned at the site level. Since the access is indirectly obtained from that group membership and not a direct file assignment, the **principal** retains access to all resources in the site, including this file.

To remove this **principal's** access to the file, change the group membership or the group's site-level permission, not the file-level assignment.

![Access Graph Explorer displaying user access details and resource information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image2(12).png)

**Example 2: Access through a folder-level site-level permission**

`IAM Test User3` has access to multiple resources (*Folder_1, FichaAdmissao, CreditCard_Tes, Nested_File.txt*) all through`Connector_Sanity Members`. Every one of these resources shows **Resource Scope** = `https://iamautomation.sharepoint.com/sites/Connector_Sanity/Shared%20Documents`, the Shared Documents URL. This means the permission was set at the folder site-level and all resources under it inherit that scope.

![Access Graph Explorer displaying resource access details for various user principals.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image1(9).png)

![Access Graph Explorer displaying resource access and configured user groups for data governance.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image4(10).png)

`Auto User3` appears twice for Folder_1: one row with **Is Direct Access** = ✓ (**Configured Users** shows Auto User1 and Auto User3, both directly assigned) and one row with **Is Direct Access** = 🅇. A **principal** can have both direct and group-based access to the same resource at the same time. Each access path appears as a separate row.

![Access Graph Explorer displaying resource access and user principal information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3(9).png)

> [!NOTE]
> **Note:**
> 
> A plain site URL in **Resource Scope** also indicates site-level access. No permission was explicitly set at the folder or file level. This means the access is indirectly obtained from site-level group membership, as shown in Example 1.

#### Identifying Users with Access to a specific Site(s) using the Data Access Governance Command Graph

To identify users that have access to specific sites:

1. In Securiti, open **Data Access Governance** and choose **Data Governance Command Graph** to access the Command Graph.
2. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set the **Entity** to **Site**. Set the **Attribute** to the **Site Name.** Set the operator to the **Equals**.
3. Select the Site for which you want to identify the users that have access to the Site.
4. Click **Apply**.
5. Click on the **User Principal** node to see the users in the data grid.
6. You can also see the Username and User ID for all the users that have access to the particular Site.
7. Click on the user for which you want to explore the details. This will open instance explorer. You can see the relationship of that particular user principal with usergroups and other entities such as Policy Elements, Policy Objects, etc.

![Data Command Graph displaying asset types and scanned document statistics for governance.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (9).png)

#### Identifying Users with access to a specific file(s) using Data Command Graph

To identify the users that have access to specific files:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph. Click the + sign in the upper left corner.
2. On the filter menu, click **Files** Entity. From the middle panel, select **File Name** property. You can use other user properties that are available in the graph to sort users out. Set the operator to **Is equal to**. Select the relevant File, you can also enter the File Name.

![DAG_SPO_FileName.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5aa3d3f5-dec3-b56e-6c2b-11564a459a00.png)
3. Click **Apply**.
4. Click the **User Principal** node to see the list of users.

#### Identifying all of the Sites and Files Accessible by a particular User Group using the Data Command Graph

1. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set the **Entity** to **User Group Principal**. Set the **Property** to the **Group name**. You can use other user properties that are available in the graph to sort user groups. Set the operator to the **Is Equal to**.

![DAG_SPO_Groupmembers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6eb267b-b0a0-523a-aab6-6229d6e5a8d4.png)
2. Select the User Group for which you want to check that users in that usergroup have access to the specific files and sites.
3. Click **Apply**.
4. Click on the **File** and **Site** node on the left side under the graph to see the results in the data grid.

#### Identifying Files that are accessible by all Internal Users in your Sharepoint tenant using the Data Command Graph.

To identify the files that are only accessible by all the internal users in you SharePoint tenant:

1. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set the **Entity** to **User Group Principal**. Set the **Attribute** to the **Group name**. Set the operator to the **Equals**.
2. Select **Everyone except external users**. Everyone except external users is a non-manageable Microsoft user group that is returned for open access files and sites.

![DAG_SPO_GroupsEveryOne_Except.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-46533856-6fad-9681-a944-bd74944b6f28.png)
3. Click **Apply**.
4. Click on the File node on the left side under the graph to see the results in the data grid.

#### Identifying Sites that Allow External File Sharing using the Data Command Graph

To identify the Files that allow external file sharing:

1. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, set the **Entity** to **Site**. Set the **Attribute** to the **Sharing Enabled**. Set the operator to the **Equals**.
2. Select **true** from the drop down menu.
3. Click **Apply**.
4. Click on the File node on the left side under the graph to see the results in the data grid.

#### ![Data Command Graph displaying asset names and types in a governance interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image (7).png) Identifying access to Files shared via link anonymously that can be accessed externally

To identify access to Files shared via link anonymously:

1. In Securiti, open **Data Access Governance** and choose **Data Command Graph** to access the Command Graph.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter menu. On the filter menu, select the **User Group Principal** Entity. Click three dots with the **User Group Principal** Entity, and select **+ Add Property**. Choose **Display Name**. Enter **Anonymous users group**. Click three dots with the **User Group Principal** Entity, and select **+ Add Property**. Choose Provider Type. Select **SharePointOnline** and **SharePointOnlineOnPrem**.
4. Click three dots with the **User Group Principal** Entity, and select **Add Relationship**. Select **Sharing Link**.
5. Click three dots with the **Sharing Link** Entity, and select **Add Relationship**. Select **Resource Scope**.
6. Click three dots with the **Resource Scope** Entity, and select **Add Relationship**. Select **Files**. entity in the Data category.

> [!NOTE]
> Note
> 
> If this query, or **Users** with **Read Access to Files Shared Via Link** / **User Groups** with **Read Access to Files Shared Via Link**, returns no results even though sharing links exist in the source tenant, confirm the **Sites.FullControl.All Microsoft Graph** application permission is granted with admin consent. Without it, **Microsoft Graph** withholds the sharing link's **webUrl** and **shareId**, and the link is silently excluded from the scan.

**Reporting**

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

#### Identify SharePoint Sites Accessible by Everyone Except External Users

This query identifies SharePoint Online User Principals, traces their membership to the Everyone except external users (EEEU) group, and surfaces the Sites accessible through the policies applied to that group and any groups EEEU is a member of.

To run this query:

1. In Securiti, open Data Access Governance.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the User Principal entity.
5. Click the three dots next to the **User Principal** entity, select **Add Property**, choose **Provider Type**, and select **Office 365 SharePoint Online**.
6. Click the three dots next to the **User Principal** entity, select **Add Relationship**, and choose **User Group Principal**.
7. Click the three dots next to the **User Group Principal** entity, select **Add Property**, choose **Name**, select **is one of**, and enter *Everyone except external users*.
8. Click the three dots next to the **User Group Principal** entity, select **Add Relationship**, and choose **Policy Element**.
9. Click the three dots next to the **Policy Element** entity, select **Add Relationship**, and choose **Resource Scope**.
10. Click the three dots next to the **Resource Scope** entity, select **Add Relationship**, and choose **Site**.
11. Click Apply, and then click Run Query.
12. Click on the **User Group Principal** node in the Entities panel to view the results in the data grid.

![Access Graph Explorer displaying user principals and their associated provider types and IDs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled-20260514-090002.png)

**Default columns displayed in the data grid**

By default, the data grid displays the following for each User Group Principal:

- Display Name
- Group Type
- Provider Type
- Provider Account ID
- System Unique ID

**Additional columns available in the data grid**

You can customize the data grid to include the following additional attributes:

- Name
- Email
- Is External
- Org Unit
- Tenant ID

> [!NOTE]
> **Note**
> 
> The User Group Principal results include Everyone except external users (EEEU) as well as any SharePoint site member groups that EEEU is a direct member of in SPO. This is because the recursive traversal fans out from the EEEU entry point to all connected groups. To verify that a returned group is legitimate, check that EEEU is listed as a direct member of that group in your SharePoint admin center.

**Identify All SharePoint User Group Principals and Their Accessible Sites**

This query returns all User Group Principals associated with SharePoint Online User Principals, along with the Sites accessible through their associated policies. No Display Name filter is applied, so all user groups reachable through recursive traversal are returned.

To run this query:

1. In Securiti, open Data Access Governance.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click + to open the filter menu.
4. On the filter menu, select the User Principal entity.

1. Click the three dots next to the **User Principal** entity, select **Add Property**, choose **Provider Type**, and select **Office 365 SharePoint Online**.
2. Click the three dots next to the **User Principal** entity, select **Add Relationship**, and choose **User Group Principal**. Do not add any property filter to this entity.
3. Click the three dots next to the **User Group Principal** entity, select **Add Relationship**, and choose **Policy Element**.
4. Click the three dots next to the **Policy Element** entity, select **Add Relationship**, and choose **Resource Scope**.
5. Click the three dots next to the **Resource Scope** entity, select **Add Relationship**, and choose **Site**.

1. Click Apply, and then click Run Query.

1. Click on the **User Group Principal** node in the Entities panel to view all user groups in the data grid.

![Access Graph Explorer displaying user principals and their associated provider types and IDs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2-20260514-090841.png)

**Default columns displayed in the data grid**

By default, the data grid displays the following for each User Group Principal:

- Display Name
- Group Type
- Provider Type
- Provider Account ID
- System Unique ID

**Additional columns available in the data grid**

You can customize the data grid to include the following additional attributes:

- Name
- Email
- Is External
- Org Unit
- Tenant ID

> [!NOTE]
> **Note**
> 
> Because no Display Name filter is applied, this query returns all User Group Principals reachable from the matched User Principals through recursive traversal. This includes site member groups, security groups, and any other groups connected through group membership edges. The entity counts returned will be significantly higher than in the filtered query.

**View file and folder access using Resource Access node**

Files and folders use Securiti’s **advanced Resource Access** to deliver faster and more accurate permission analysis.

To view access relationships:

1. In **Securiti**, open **Data Access Governance** and choose **Data Command Graph**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Create a query that includes the **Resource Access** entity.
4. Add a property filter for **Provider Type** and select the required provider. Example: SharepointOnlineOnprem.
5. Click **Run Query**.
6. Click on the **Resource Access** node to view resolved access entries for files and folders.

![Access Graph Explorer displaying resource access details and user privileges for SharePoint.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2 (2)(1).png)

**Default columns displayed in the data grid**

By default, the data grid displays core identity, privilege, and resource attributes for each access entry:

- Principal Unique ID
- Principal Display Name
- Principal Type
- Provider Type
- Provider Account ID
- Privilege Bundle Type
- Privilege Bundle
- Access Type
- Privilege Categories
- Resource ID
- Resource Name
- Resource Scope

These columns provide a normalized view of who has access, how access is granted, and the scope of the resource.

**Identify users with Full Control access to SharePoint sites**

This helps you identify user principals who have Full Control access to sites in Office 365 SharePoint Online. Users granted Full Control can read, edit, delete, and manage permissions on SharePoint sites. Monitoring this level of access helps you enforce least-privilege principles and detect overprivileged users across your SharePoint environment.

To identify users with Full Control access to SharePoint sites:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **User Principal** entity.
5. Click the three dots next to the User Principal entity, select **Add Property**, choose **Provider Type**, and select **Office 365 SharePoint Online**.
6. Click the three dots next to the User Principal entity, select **Add Relationship**, and choose **Is Member Of**, then select **User Group Principal** as the target entity.
7. Click the three dots next to the User Group Principal entity, select **Add Relationship**, and choose **Is Subject Of**, then select **Policy Element** as the target entity.
8. Click the three dots next to the Policy Element entity, select **Add Property**, choose **Privilege Bundle Name**, and select **Full Control**.
9. Click the three dots next to the Policy Element entity, select **Add Relationship**, and choose **Applies To (Data)**, then select **Resource Scope** as the target entity.
10. Click the three dots next to the Resource Scope entity, select **Add Relationship**, and choose **Contains**, then select **Site** as the target entity.
11. Click **Run Query**.
12. Click on the **User Principal** node to view the list of users with Full Control access.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7(7).png)

**Identify users with access to SharePoint files containing sensitive business data**

This helps you identify user principals who have access to files containing non-personal sensitive data in Office 365 SharePoint Online. Files may contain sensitive business information such as financial data elements. Monitoring user access to these files helps you detect overexposure of sensitive business data and enforce appropriate access controls across your SharePoint environment.

To identify users with access to SharePoint files containing sensitive business data:

1. In Securiti, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Data Element** entity.
5. Click the three dots next to the Data Element entity, select **Add Property**, choose **Non-Personal Sensitive Data**, and set it to **True**.
6. Click the three dots next to the Data Element entity, select **Add Relationship**, and choose **Belongs To**, then select **Files** as the target entity.
7. Click the three dots next to the Files entity, select **Add Property**, choose **Data System Type**, and select **Office 365 SharePoint Online**.
8. Click the three dots next to the Files entity, select **Add Relationship**, and choose **Is Object Of**, then select **Resource Access** as the target entity.
9. Click the three dots next to the Resource Access entity, select **Add Relationship**, and choose **Has Subject**, then select **User Principal** as the target entity.
10. Click **Run Query**.
11. Click on the **Data Element** node to view the sensitive data elements detected across the filtered files.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 5(8).png)

### Using Activity Analysis with Microsoft 365 SharePoint Online

> [!NOTE]
> **Important**
> 
> A single **SharePoint action can appear as multiple identical entries** in **Activity Explorer**. This is expected behavior from the **Microsoft Office 365 Management Activity API**, which Securiti uses to ingest SharePoint activity logs. When the **Microsoft audit service encounters an error while processing an audit event**, it retries the operation, which can generate duplicate audit records. **These duplicates are returned by the API** and shown in Activity Explorer. The duplicate entries have identical field values but different event IDs and end times.
> 
> Note that the Microsoft Purview portal removes duplicates when you export audit search results through its UI, so the same event may appear once in Purview and multiple times in Activity Explorer. For more information, see [Troubleshooting the Office 365 Management Activity API](http://learn.microsoft.com/en-us/office/office-365-management-api/troubleshooting-the-office-365-management-activity-api).

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify activity of your users.

#### Identify and report on users that have accessed Files within the specified Time

To filter the users that have accessed Files:

1. In Securiti, open **Data Access Governance**.
2. From the left menu bar, hover over the Dashboards category, click **Activity Explorer**. This will open the Activity Explorer page.
3. The activity explorer page presents you the data related to the activities that your users performed on the data system resources. From the filter panel available on the top of the page, click **Activity Action**. Select the **is one of** operators. Select the **File Accessed** action.
4. Click on the **Apply** button. All the queries in which your users have accessed Files will be displayed in the data grid.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(45).png)
5. Click on the **Time** filter, and specify the **Before** or **After** filter, and select Date and Time, For example, you want to identify the users that have accessed Files **before** 3rd March, 2025, 4:00 am.
6. Click on the View **Metadata** on the right side of the query entry for which you want to see the details. You can view details such as **Type**, **Action**, **User**, **PD Elements**, **Client Country**, etc.

> [!NOTE]
> Note
> 
> Securiti purges the Activity Analysis data in Activity Explorer after 1 year.

#### Identify and report on users that have Created Folder

To filter the users that have Created Folders:

1. In Securiti, open **Data Access Governance**.
2. From the left menu bar, hover over the Dashboards category, click **Activity Explorer**. This will open the Activity Explorer page.
3. The activity explorer page presents you the data related to the activities that your users performed on the data system resources. From the filter panel available on the top of the page, click **Activity Action**. Select the **is one of** operators. Select the **Folder Created** action. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7(8).png)
4. Click on the **Apply** button. All the users that have Created Folders will be displayed in the grid. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8(7).png)
5. Click on the View **Metadata** on the right side of the query entry for which you want to see the details. You can view details such as **Type**, **Action**, **User**, **PD Elements**, **Client Country**, etc.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 10(4).png)

#### Identify and report on users that have revoked sharing

To filter the users that have revoked sharing:

1. In Securiti, open **Data Access Governance**.
2. From the left menu bar, hover over the Dashboards category, click **Activity Explorer**. This will open the Activity Explorer page.
3. The activity explorer page presents you the data related to the activities that your users performed on the data system resources. From the filter panel available on the top of the page, click **Activity Action**. Select the **is one of** operators. Select the **Sharing Revoked** action.
4. Click on the **Apply** button. All the actions related to Sharing Revoked will be displayed.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(10).png)

#### Viewing file and folder access using Resource Access

Access extension nodes are created in the **Access Graph Explorer** only when the **Resource Access** is enabled and executed. This enables full access traversal and detailed permission analysis for files and folders.

To view access file and folder access using Resource Access:

1. In **Securiti**, open **Data Access Governance** and choose **Data Command Graph**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Create a query that includes the **Resource Access** entity.
4. Add a property filter for **Provider Type** and select the required provider. Example : SharepointOnlineOnprem.
5. Click **Run Query**.
6. Click on the **Resource Access** node to view resolved access entries for files and folders.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1781534099448.png)

**Default columns displayed in the data grid**

By default, the data grid displays core identity, privilege, and resource attributes for each access entry:

- Principal Unique ID
- Principal Display Name
- Principal Type
- Provider Type
- Provider Account ID
- Privilege Bundle Type
- Privilege Bundle
- Access Type
- Privilege Categories
- Resource ID
- Resource Name
- Resource Scope

These columns provide a normalized view of who has access, how access is granted, and the scope of the resource.

You can customize the data grid to include the following additional attributes for enhanced analysis.

- Display Name
- Organization
- Privileges

#### **Identify users with sharing link-based access to files in SharePoint Online**

This helps you identify users who have access to files through sharing links in Microsoft SharePoint Online. It provides a clear view of link-based access paths, enabling you to analyze how files are shared and accessed beyond direct permissions.

**To identify users with access to Files via Sharing Link:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Select the **User Principal** entity.
4. Add the relationship to **Resoruce Access** Entity. From **Resource Access**, add relationship to **Files**.
5. From **Files**, add the relationship to **Sharing Link Resource Access**.
6. Click **Run Query** to view the results.

![Access Graph Explorer displaying user principals and resource access details in a table format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(41).png)

By default, the data grid displays the following attributes:

  

Username

Provider Type

Provider Account ID

User Type

Asset Type

---

Hidden Columns

- Username
- Provider Type
- Provider Account ID
- User Type
- Asset Type

You can further analyze sharing link-based access using the following properties available in the **Sharing Link Resource Access** node:

- Download Allowed
- Share Scope
- Shared URL

Download Allowed, Share Scope, and Shared URL are specific to **Link-based access** and aren't available when access is granted through a direct **RoleAssignment**.

- **Download Allowed** shows whether users with the sharing link can download the file, or only view it online.
- **Share Scope** shows who the sharing link is scoped to: Organization, Users, or Anonymous.
- **Shared URL** shows the actual link generated to share the file.

> [!NOTE]
> Note:
> 
> Expiration information for Microsoft SharePoint isn't available, so the **Expiration** field will appear blank in this scenario.

The following screenshot shows an example of the **Sharing Link Resource Access** node with these properties displayed in the data grid:

![Data Access Governance interface displaying user group privileges and sharing link access details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image1(13).png)

Privilege Analysis is a feature set of DAG Access Intelligence which ingests the Identity and Access Management (IAM) and Role Based Access Control (RBAC) metadata within your data systems and presents the data through a normalized knowledge graph allowing you to quickly identify who can access sensitive data, how that access is created, and who can administer that access within a data system.

Self-hosted systems refer to computer systems or software applications that are hosted and operated by organizations or individuals who use them, rather than being hosted and operated by service providers or third parties. It becomes the responsibility of the organization to host, maintain, and manage the system or software.
