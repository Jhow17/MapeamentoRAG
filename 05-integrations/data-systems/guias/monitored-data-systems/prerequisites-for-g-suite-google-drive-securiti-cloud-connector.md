---
title: "Prerequisites for Google Drive (Google Workspace) (Securiti Cloud) connector"
slug: "prerequisites-for-g-suite-google-drive-securiti-cloud-connector"
updated: 2026-07-14T03:38:40Z
published: 2026-07-14T03:38:40Z
canonical: "helpcenter.securiti.ai/prerequisites-for-g-suite-google-drive-securiti-cloud-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Google Drive (Google Workspace) (Securiti Cloud) connector

This topic contains information about the following prerequisites for Google Drive (Google Workspace) connector:

> [!NOTE]
> **Important**
> 
> - You must have administrative access and role in your Google Workspace account.

1. Google Cloud Project Creation
2. Enabling APIs in GCP
3. Creating Google Workspace Service Account
4. Enabling Google Workspace Domain-Wide Delegation
5. Generating Service Account Key File for activation
6. Recording admin email for connector activation

### 1. Creating a project in Google Workspace

Google Cloud projects form the basis for creating, enabling, and using all Google Cloud services, including (but not limited to) managing APIs and Permissions for Google Cloud resources. For more information, see [Google's documentation on creating a project](https://cloud.google.com/resource-manager/docs/creating-managing-projects#creating_a_project).

To create a project:

1. Log in to [Google Cloud Console](https://console.developers.google.com/apis/dashboard) with your Google Workspace admin account.
2. Select your project or create one if not already, by following the procedure described in [Google's official documentation](https://cloud.google.com/resource-manager/docs/creating-managing-projects#creating_a_project). Specify the necessary project details, like the project name. For more information, see [Creating and managing projects](https://cloud.google.com/resource-manager/docs/creating-managing-projects).

### 2. Enabling APIs in GCP

In your project, enable the necessary APIs to retrieve data. Each API must be enabled individually within the scope of your selected project. Ensure that you have the appropriate project selected in the Google Cloud Console prior to enabling any APIs.

To enable APIs, see their relevant documentation as listed below:

- [Admin SDK API](https://console.cloud.google.com/apis/library/admin.googleapis.com)
- [Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com)
- [Google Sheets API](https://console.cloud.google.com/apis/library/sheets.googleapis.com)
- [Drive Labels API](https://console.cloud.google.com/apis/library/drivelabels.googleapis.com) Required for **Data Labeling Policy** and ingestion of Google Drive labels during the Data Inventory Sync.

Click an API card and on its API description page, click **Enable**, as shown below.

![gdrive_enableAPIs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ccabab6-21a6-d719-c6c5-becb83c382c5(1).png)

Alternatively, you can enable the required APIs by filtering them from the [Google Workspace APIs page](https://developers.google.com/workspace/guides/enable-apis). Use the **Service Name** listed in the Table below to search for and activate each API in your project.

| API | Service Name | Use Case |
| --- | --- | --- |
| **Admin SDK API** For more information, see [Enabling Admin SDK API](https://console.cloud.google.com/apis/library/admin.googleapis.com). | `admin.googleapis.com` | Required for Data scanning and DSR Automation |
| **Google Drive API** For more information, see [Enabling Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com). | `drive.googleapis.com` | Required for Data scanning and DSR Automation |
| **Google Sheets API** For more information, see [Enabling Google Sheets API](https://console.cloud.google.com/apis/library/sheets.googleapis.com). | `sheets.googleapis.com` | Required for Data scanning and DSR Automation |
| **Drive Labels API** For more information, see [Enabling Drive Labels API](https://console.cloud.google.com/apis/library/drivelabels.googleapis.com). | `drivelabels.googleapis.com` | Required for Data Labeling Policy and ingestion of Google Drive labels during Data Inventory Sync. |

### 3. Creating Google Workspace Service Account

> [!NOTE]
> **Important**
> 
> Service accounts cannot directly activate the Google Drive (Google Workspace) connector because they are separate from your Google Workspace domain and do not have default access to user data. To grant access, you must configure domain-wide delegation. This authorizes the service account to act on behalf of users within your organization. For more information, see [Google Workspace documentation](https://developers.google.com/workspace/guides/auth-overview).

Once you have enabled the APIs, create a service account as described in [Google's official documentation](https://cloud.google.com/iam/docs/service-accounts-create).

1. Select a Google Cloud Project where you want to create the service account.

![gdrive_createservaccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce77e091-cf95-86e0-7446-b26efc128f95(1).png)
2. Click **Create service account**, enter a name and description for it and click **Create** and then **Done**.

> [!NOTE]
> **Important**
> 
> You can't use service account email for connector activation. You can only use admin email or non-admin email linked to custom role created in [Using custom role for non-admin users](/v1/docs/using-custom-role-for-non-admin-users).

![gdrive_Servacc.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac0b2356-47c2-7aca-794f-4bf1e8b1cca3(1).png)

### 4. Enabling Domain-Wide Delegation for Service Account

A super administrator must configure domain-wide delegation to grant a service account the necessary Permissions to access user data. This is required because, unlike user accounts, service accounts are not part of your domain and are blocked from accessing user data via Workspace APIs by default. Enabling delegation lets the service account to impersonate users to perform its functions.

For more information, see the following Google Drive documentation:

- [Understanding Service Accounts](https://cloud.google.com/iam/docs/service-account-overview)
- [Delegating domain-wide authority to service account](https://developers.google.com/identity/protocols/oauth2/service-account#delegatingauthority)

To set up domain-wide delegation of authority for a service account:

1. On the [Admin console](/v1/docs/securiti-pods-and-elastic-pods) of your Google Workspace domain, click the navigation or main menu (three horizontal bars) in the top left and select **IAM & Admin > Service Accounts**, or click [here](https://console.cloud.google.com/iam-admin/serviceaccounts) to directly access Service Accounts.
2. Select your project and open the service account you created earlier.
3. On the service account page, click the **Advanced Settings** section.
4. Under the **Domain-wide delegation**, record the **Client ID** for your account.

![gdrive_copyclientID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-708dc3d9-9425-645b-d424-02dfd77cfc0b(1).png)
5. In Google Admin Console, on the top left, click the main menu (three horizontal bars) and select **Security > Access and data control > API controls**.

> [!NOTE]
> **Important**
> 
> You must have super administrator access to the [Google Workspace account](https://accounts.google.com/v3/signin/challenge/pk?TL=ALgCv6wHTabmBRRP9iRMLfLAmCV2iktxmkXmiCimCOMLGyMQtiyvtSkmjsgePhD4&amp;authuser=0&amp;cid=1&amp;continue=https%3A%2F%2Fadmin.google.com%2F&amp;flowName=GlifWebSignIn&amp;ifkv=AdBytiOfLoZyBPy3O3ftBIsLnP-i8nIzPne-FGi1JINZpK6vXxULIR4i5Ki0aXyFQC7Z4eM3EqSMfQ&amp;osid=1&amp;rart=ANgoxcfFNlllT5NBLHI5ppRCnJTmTIU8h5YPtZiI_zLHm6hS4e0ec1f8TY0nbMDOEAGkIr9K9_JG8uJibnGBqHkRvSzNkto1csaSc4mqvaNs4-Yu2sBJJ6U&amp;rpbg=1&amp;sarp=1) to complete this step.
6. Click **Manage Domain Wide Delegation**.

![gdrive_domainwide_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-adefcecf-df80-cd66-45d1-bef6de6d1762(1).png)
7. Click **Add New**.

![gdrive_adddomainwide.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07c307fa-7aed-0dd1-aeaa-4ad4d71c0839(1).png)
8. In the **Client ID** field, paste the value you copied earlier.

![gdrive_addclientID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7512a4dd-b329-2d5e-2a96-bfe794e28f7a(1).png)

#### Assigning scopes and permissions

Provide the following scopes and Permissions to let Securiti access your Google Drive data.

1. In the **OAuth Scopes** field, enter a comma-delimited list of the scopes required by your application. The below Table describes the scopes required for Google Drive.

| Use case | Scopes |
| --- | --- |
| Minimum Permissions for Connector Activation and data scanning | ```plaintext https://www.googleapis.com/auth/admin.directory.customer.readonly, https://www.googleapis.com/auth/admin.directory.user.readonly, https://www.googleapis.com/auth/admin.directory.domain.readonly, https://www.googleapis.com/auth/admin.directory.group.readonly, https://www.googleapis.com/auth/drive.readonly, https://www.googleapis.com/auth/drive.metadata.readonly, https://www.googleapis.com/auth/drive.photos.readonly, ``` |
| Workflow | To run the Workflow node, also add the following scope: ```plaintext https://www.googleapis.com/auth/drive, ``` |
| Google Drive label ingestion during Data Inventory Sync Private Preview | To enable Google Drive label ingestion during the Data Inventory Sync and publish them to **Data Command Graph**, add the following scope: ```plaintext https://www.googleapis.com/auth/drive.labels.readonly https://www.googleapis.com/auth/drive.admin.labels.readonly ``` |
| Data Labeling Policy Private Preview | To view labels, add the following scopes: ```plaintext https://www.googleapis.com/auth/drive.labels.readonly https://www.googleapis.com/auth/drive.admin.labels.readonly ``` To create or manage labels, add the following scopes: ```plaintext https://www.googleapis.com/auth/drive.labels https://www.googleapis.com/auth/drive.admin.labels ``` To apply labels, add the following scope: ```plaintext https://www.googleapis.com/auth/drive.metadata ``` |
2. Click **Authorize**.
3. (Optional) In the **Drive and Docs** section of your application, enable the **Turn Labels On** to apply labels to your Google Drive files.

![gdrive_turnonlabels_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c8c0179-1408-de90-e5fc-e00aa76c3452(1).png)

### 5. Generating Service Account Key File

Service Account Key File is required as an Authentication credential to connect with Securiti. To generate Service Account Key File:

1. On the **Service Accounts** page in the Google Cloud Console, select your project.
2. Click the email address of the respective service account to open details and select **Keys** tab.
3. From the **Add Key** menu, select **Create new key**.

![gdrive_createnewkey.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7296761b-71dc-c834-6b62-0da798b34878(1).png)
4. In the popup, in the **Key type**, select **JSON** and click **Create**.

![gdrive_jsontype.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-000ccdd7-ca27-0272-3565-617345a8a4df(1).png)

A file is downloaded on your system that you must store safely for the next step.

> [!WARNING]
> **Caution**
> 
> The JSON file is sensitive information. Store it securely and do not expose it publicly.

### 6. Record admin email for connector activation

Record the administrator email that you used when logging into the Google admin console.

Proceed to [Connecting Google Drive (Google Workspace) (Securiti-Cloud) with Securiti](/latest/docs/new-ui-connecting-google-drive-google-workspace-securiti-cloud-with-securiti).
