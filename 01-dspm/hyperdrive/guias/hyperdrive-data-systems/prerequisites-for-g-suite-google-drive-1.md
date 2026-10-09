---
title: "Obtain authentication credentials for Google Drive (Hyperdrive)"
slug: "prerequisites-for-g-suite-google-drive-1"
updated: 2026-08-18T09:28:15Z
published: 2026-08-18T09:28:15Z
canonical: "helpcenter.securiti.ai/prerequisites-for-g-suite-google-drive-1"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials for Google Drive (Hyperdrive)

This topic contains information about the following prerequisites for Google Drive (Google Workspace) self-hosted connector using Hyperdrive mode.

> [!WARNING]
> **Important**
> 
> You must have administrative access and role in your Google Workspace account.

1. Google Cloud Project Creation
2. Enabling APIs in GCP
3. Creating Google Workspace Service Account
4. Enabling Domain-Wide Delegation for Service Account
5. Generating Service Account Key File for activation
6. Recording email for connector activation

## 1. Creating a project in Google Workspace

Google Cloud projects form the basis for creating, enabling, and using all Google Cloud services, including (but not limited to) managing APIs and Permissions for Google Cloud resources. For more information, see [Google's documentation on creating a project](https://cloud.google.com/resource-manager/docs/creating-managing-projects#creating_a_project).

To create a project:

1. Log in to [Google Cloud Console](https://console.developers.google.com/apis/dashboard) with your Google Workspace admin account.
2. Select your project or create one if not already, by following the procedure described in [Google's official documentation](https://cloud.google.com/resource-manager/docs/creating-managing-projects#creating_a_project).
3. Specify the necessary project details, like the project name. For more information, see [Creating and managing projects](https://cloud.google.com/resource-manager/docs/creating-managing-projects).

> [!NOTE]
> Note
> 
> Each step from step 2 to step 5 resides in the project you just created in the Google Cloud Console.

## 2. Enabling APIs in GCP

> [!CAUTION]
> Warning
> 
> You must enable the APIs for your service account that resides in your selected project. If your service account lives in Project A but you enabled the APIs in Project B, scans fail with 403 "API not enabled" at runtime.

In your project, enable the necessary APIs to retrieve data. Each API must be enabled individually within the scope of your selected project. Ensure that you have the appropriate project selected in the Google Cloud Console prior to enabling any APIs.

To enable APIs, see their relevant documentation as listed below:

- [Admin SDK API](https://console.cloud.google.com/apis/library/admin.googleapis.com)
- [Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com)
- [Google Sheets API](https://console.cloud.google.com/apis/library/sheets.googleapis.com)

Click an API card and on its API description page, click **Enable**, as shown below.

![gdrive_enableAPIs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ccabab6-21a6-d719-c6c5-becb83c382c5.png)

Alternatively, you can enable the required APIs by filtering them from the [Google Workspace APIs page](https://developers.google.com/workspace/guides/enable-apis). Use the **Service Name** listed in the Table below to search for and activate each API in your project.

| API | Service Name | Use Case |
| --- | --- | --- |
| **Admin SDK API** For more information, see [Enabling Admin SDK API](https://console.cloud.google.com/apis/library/admin.googleapis.com). | `admin.googleapis.com` | Required for data scanning |
| **Google Drive API** For more information, see [Enabling Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com). | `drive.googleapis.com` | Required for data scanning |
| **Google Sheets API** For more information, see [Enabling Google Sheets API](https://console.cloud.google.com/apis/library/sheets.googleapis.com). | `sheets.googleapis.com` | Required for data scanning |

## 3. Creating Google Workspace Service Account

> [!WARNING]
> **Important**
> 
> Service accounts cannot directly activate the Google Drive (Google Workspace) connector because they are separate from your Google Workspace domain and do not have default access to user data. To grant access, you must configure domain-wide delegation. This authorizes the service account to act on behalf of users within your organization. For more information, see [Google Workspace documentation](https://developers.google.com/workspace/guides/auth-overview).

Once you have enabled the APIs, create a service account as described in [Google's official documentation](https://cloud.google.com/iam/docs/service-accounts-create).

1. Select a Google Cloud Project where you want to create the service account.

![gdrive_createservaccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce77e091-cf95-86e0-7446-b26efc128f95.png)
2. Click **Create service account**, enter a name and description for it and click **Create** and then **Done**.

![gdrive_Servacc.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac0b2356-47c2-7aca-794f-4bf1e8b1cca3.png)

## 4. Enabling Domain-Wide Delegation for Service Account

A super administrator must configure domain-wide delegation to grant a service account the necessary permissions to access user data. This is required because, unlike user accounts, service accounts are not part of your domain and are blocked from accessing user data via Workspace APIs by default. Enabling delegation lets the service account to impersonate users to perform its functions.

For more information, see the following Google Drive documentation:

- [Understanding Service Accounts](https://cloud.google.com/iam/docs/service-account-overview)
- [Delegating domain-wide authority to service account](https://developers.google.com/identity/protocols/oauth2/service-account#delegatingauthority)

To set up domain-wide delegation of authority for a service account:

1. On the [Admin console](/v1/docs/securiti-pods-and-elastic-pods) of your Google Workspace domain, click the navigation or main menu (three horizontal bars) in the top left and select **IAM & Admin > Service Accounts**, or click [here](https://console.cloud.google.com/iam-admin/serviceaccounts) to directly access Service Accounts.
2. Select your project and open the service account you created earlier.
3. On the service account page, click the **Advanced Settings** section.
4. Under the **Domain-wide delegation**, record the **Client ID** for your account.

![gdrive_copyclientID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-708dc3d9-9425-645b-d424-02dfd77cfc0b.png)
5. In Google Admin Console, on the top left, click the main menu (three horizontal bars) and select **Security > Access and data control > API controls**.

> [!WARNING]
> **Important**
> 
> You must have super administrator access to the [Google Workspace account](https://accounts.google.com/v3/signin/challenge/pk?TL=ALgCv6wHTabmBRRP9iRMLfLAmCV2iktxmkXmiCimCOMLGyMQtiyvtSkmjsgePhD4&amp;authuser=0&amp;cid=1&amp;continue=https%3A%2F%2Fadmin.google.com%2F&amp;flowName=GlifWebSignIn&amp;ifkv=AdBytiOfLoZyBPy3O3ftBIsLnP-i8nIzPne-FGi1JINZpK6vXxULIR4i5Ki0aXyFQC7Z4eM3EqSMfQ&amp;osid=1&amp;rart=ANgoxcfFNlllT5NBLHI5ppRCnJTmTIU8h5YPtZiI_zLHm6hS4e0ec1f8TY0nbMDOEAGkIr9K9_JG8uJibnGBqHkRvSzNkto1csaSc4mqvaNs4-Yu2sBJJ6U&amp;rpbg=1&amp;sarp=1) to complete this step. If you do not have this access, you will need to contact an administrator and provide them with your service account's Client ID and OAuth Scopes.
6. Click **Manage Domain Wide Delegation**.

![gdrive_domainwide_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-adefcecf-df80-cd66-45d1-bef6de6d1762.png)
7. Click **Add New**.

![gdrive_adddomainwide.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07c307fa-7aed-0dd1-aeaa-4ad4d71c0839.png)
8. In the **Client ID** field, paste the value you copied earlier. ![gdrive_addclientID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7512a4dd-b329-2d5e-2a96-bfe794e28f7a.png)

### 4.1 Assigning scopes and permissions

Provide the following scopes and permissions to let Securiti access your Google Drive (Google Workspace) data.

1. In the **OAuth Scopes** field, enter a comma-delimited list of the scopes required by your application. The below table describes the scopes required for Google Drive.

| OAuth scopes | Explanation |
| --- | --- |
| `https://www.googleapis.com/auth/admin.directory.customer.readonly` | Lets you view customer information in Google Workspace. Securiti uses this permission to retrieve customer details for inventory and discovery scans. |
| `https://www.googleapis.com/auth/admin.directory.user.readonly` | Lets you view users and user aliases in Google Workspace. Securiti uses this permission to retrieve user details for inventory and discovery scans. This permission also retrieves user directory data to classify actors as internal or external and populate the Is External field in activity log results. |
| `https://www.googleapis.com/auth/admin.directory.domain.readonly` | Lets you view domains in Google Workspace. Securiti uses this permission to retrieve domain details for inventory and discovery scans. |
| `https://www.googleapis.com/auth/admin.directory.group.readonly` | Lets you view groups, group aliases, and group members in Google Workspace. Securiti uses this permission to retrieve group information for inventory and discovery scans. |
| `https://www.googleapis.com/auth/drive.readonly` | Lets you view and download files in Google Drive. Securiti uses this permission to retrieve file content for inventory and discovery scans. |
| `https://www.googleapis.com/auth/drive.metadata.readonly` | Lets you view metadata for files in Google Drive. Securiti uses this permission to retrieve file metadata for inventory and discovery scans. |
| `https://www.googleapis.com/auth/drive.photos.readonly` | Lets you view and download photos stored in Google Drive. Securiti uses this permission to retrieve image content for inventory and discovery scans. |
| `https://www.googleapis.com/auth/admin.directory.orgunit.readonly ` | Lets you view organizational units in Google Workspace. Securiti uses this permission to retrieve organizational unit details for inventory and discovery scans. |
| `https://www.googleapis.com/auth/admin.directory.user.security` | Lets you view user security information, including OAuth tokens, application-specific passwords, and verification code settings. Securiti uses this permission to retrieve user security details required for entitlement syncs. |
| `https://www.googleapis.com/auth/cloud-platform` | Lets you access Google Cloud Platform resources that the application is authorized to use. Securiti uses this permission to access required Google Cloud services during entitlement syncs. |
| `https://www.googleapis.com/auth/admin.reports.audit.readonly` | Lets you retrieve audit logs from Google Workspace, including file access, creation, modification, and permission change events in Google Drive. Securiti uses this permission to collect activity logs for Activity Analysis. The audit logs include actor information, such as the application name, OAuth client ID, and impersonation status, so no additional Directory API scopes are required to retrieve this information |
2. Click **Authorize**.
3. (Optional) In the **Drive and Docs** section of your application, enable the **Turn Labels On** to apply labels to your Google Drive files. ![gdrive_turnonlabels_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c8c0179-1408-de90-e5fc-e00aa76c3452.png)

## 5. Generating Service Account Key File

Service Account Key File is required as an authentication credential to connect with Securiti. To generate Service Account Key File:

1. On the **Service Accounts** page in the Google Cloud Console, select your project.
2. Click the email address of the respective service account to open details and select **Keys** tab.
3. From the **Add Key** menu, select **Create new key**.

![gdrive_createnewkey.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7296761b-71dc-c834-6b62-0da798b34878.png)
4. In the popup, in the **Key type**, select **JSON** and click **Create**.

![gdrive_jsontype.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-000ccdd7-ca27-0272-3565-617345a8a4df.png)

A file is downloaded on your system that you must store safely for the next step.

> [!CAUTION]
> **Caution**
> 
> The JSON file is sensitive information. Store it securely and do not expose it publicly.

## 6. Recording email for connector activation

You have two options of recording email for Connector activation.

- Record the administrator email that you used when logging into the Google admin console.

Proceed to [Connecting Google Drive (Google Workspace) (Self-Hosted) with Securiti (Hyperdrive)](/latest/docs/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti-1).
