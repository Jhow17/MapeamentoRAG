---
title: "Prerequisites for Google Drive (Google Workspace) (Self-Hosted)"
slug: "prerequisites-for-g-suite-google-drive"
updated: 2026-09-03T18:15:35Z
published: 2026-09-03T18:15:35Z
canonical: "helpcenter.securiti.ai/prerequisites-for-g-suite-google-drive"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Google Drive (Google Workspace) (Self-Hosted)

This topic contains information about the following prerequisites for Google Drive (Google Workspace) connector:

> [!NOTE]
> **Important**
> 
> You must have administrative access and role in your Google Workspace account.

1. Google Cloud Project Creation
2. Enabling APIs in GCP
3. Creating Google Workspace Service Account
4. Enabling Domain-Wide Delegation for Service Account
5. Generating Service Account Key File for activation
6. Recording email for connector activation:
  - Recording administrator email
  - Creating custom role to record non-administrator role

## 1. Creating a project in Google Workspace

Google Cloud projects form the basis for creating, enabling, and using all Google Cloud services, including (but not limited to) managing APIs and Permissions for Google Cloud resources. For more information, see [Google's documentation on creating a project](https://cloud.google.com/resource-manager/docs/creating-managing-projects#creating_a_project).

To create a project:

1. Log in to [Google Cloud Console](https://console.developers.google.com/apis/dashboard) with your Google Workspace admin account.
2. Select your project or create one if not already, by following the procedure described in [Google's official documentation](https://cloud.google.com/resource-manager/docs/creating-managing-projects#creating_a_project). Specify the necessary project details, like the project name. For more information, see [Creating and managing projects](https://cloud.google.com/resource-manager/docs/creating-managing-projects).

> [!NOTE]
> Note
> 
> Each step from step 2 to step 5 resides in the project you just created in the Google Cloud Console.

## 2. Enabling APIs in GCP

> [!CAUTION]
> Warning
> 
> You must enable the APIs for your service account that resides in your selected project. If your service account lives in Project A but you enabled the APIs in Project B, scans fail with 403 "API not enabled" at runtime.

1. From the project picker in the top navigation bar, select the project that contains your service account.
2. On the **APIs & Services** > **Library** page, search for an API using its service name. For instance, [admin.googleapis.com](http://admin.googleapis.com).
3. On the **API details** page, click the API card, then click **Enable**.
4. Repeat steps 2-3 for each remaining API in the table below:

| API | Service Name | Use Case |
| --- | --- | --- |
| **Admin SDK API** For more information, see [Enabling Admin SDK API](https://console.cloud.google.com/apis/library/admin.googleapis.com). | `admin.googleapis.com` | Required for Data scanning and DSR Automation |
| **Google Drive API** For more information, see [Enabling Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com). | `drive.googleapis.com` | Required for Data scanning and DSR Automation |
| **Google Sheets API** For more information, see [Enabling Google Sheets API](https://console.cloud.google.com/apis/library/sheets.googleapis.com). | `sheets.googleapis.com` | Required for Data scanning and DSR Automation |
| **Drive Labels API** For more information, see [Enabling Drive Labels API](https://console.cloud.google.com/apis/library/drivelabels.googleapis.com). | `drivelabels.googleapis.com` | Required for Data Labeling Policy and ingestion of Google Drive labels during Data Inventory Sync. |

## 3. Creating Google Workspace Service Account

> [!NOTE]
> **Important**
> 
> Service accounts cannot directly activate the Google Drive (Google Workspace) connector because they are separate from your Google Workspace domain and do not have default access to user data. To grant access, you must configure domain-wide delegation. This authorizes the service account to act on behalf of users within your organization. For more information, see [Google Workspace documentation](https://developers.google.com/workspace/guides/auth-overview).

Once you have enabled the APIs, create a service account as described in [Google's official documentation](https://cloud.google.com/iam/docs/service-accounts-create).

1. Select a Google Cloud Project where you want to create the service account.

![gdrive_createservaccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce77e091-cf95-86e0-7446-b26efc128f95.png)
2. Click **Create service account**, enter a name and description for it and click **Create** and then **Done**.

> [!NOTE]
> **Important**
> 
> You can't use service account email for connector activation. You can only use admin email or non-admin email linked to custom role created in [Using custom role for non-admin users](/latest/docs/prerequisites-for-g-suite-google-drive#6-recording-email-for-connector-activation).

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

> [!NOTE]
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

| Use case | Scopes |
| --- | --- |
| Minimum permissions for Connector Activation and data scanning | ```plaintext https://www.googleapis.com/auth/admin.directory.customer.readonly, https://www.googleapis.com/auth/admin.directory.user.readonly, https://www.googleapis.com/auth/admin.directory.domain.readonly, https://www.googleapis.com/auth/admin.directory.group.readonly, https://www.googleapis.com/auth/drive.readonly, https://www.googleapis.com/auth/drive.metadata.readonly, https://www.googleapis.com/auth/drive.photos.readonly, ``` |
| Workflow | To run the Workflow node, also add the following scope: ```plaintext https://www.googleapis.com/auth/drive, ``` |
| Data Inventory Sync and Entitlements scanning | To run the Data Inventory Sync and Gencore AI Entitlement Scan, add the following scope: ```plaintext https://www.googleapis.com/auth/admin.directory.orgunit.readonly ``` |
| Google Drive label ingestion during Data Inventory Sync | To enable Google Drive label ingestion during the Data Inventory Sync and publish them to **Data Command Graph**, add the following scope: ```plaintext https://www.googleapis.com/auth/drive.labels.readonly https://www.googleapis.com/auth/drive.admin.labels.readonly ``` |
| Data Labeling Policy | To view labels, add the following scopes: ```plaintext https://www.googleapis.com/auth/drive.labels.readonly https://www.googleapis.com/auth/drive.admin.labels.readonly ``` To create or manage labels, add the following scopes: ```plaintext https://www.googleapis.com/auth/drive.labels https://www.googleapis.com/auth/drive.admin.labels ``` To apply labels, add the following scope: ```plaintext https://www.googleapis.com/auth/drive.metadata ``` |
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

> [!WARNING]
> **Caution**
> 
> The JSON file is sensitive information. Store it securely and do not expose it publicly.

## 6. Recording email for connector activation

After generating Service Account Key file, you have two options to record email for Google Drive connector activation:

- Record the administrator email that you used when logging into the Google admin console.
- Create a custom role to record the non-admin email.

**Record admin email**

- Record the administrator email that you used when logging into the Google admin console.

Proceed to [connecting Google Drive (Google Workspace) (Self-hosted) with Securiti](/latest/docs/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti).

**Create custom role**

If you don’t want to use the super admin email to be impersonated by the service account for connector activation, you can create a custom admin role with the required privileges. Assign this custom admin role to a non-admin user, and activate the connector using that user’s email.

> [!NOTE]
> **Note**
> 
> This procedure requires super admin privileges. For more information, see [Google documentation](https://support.google.com/a/answer/9807615?sjid=10419280129718041577-EU).

Perform the following steps to create a custom role and assign permissions:

1. Log in to [Google Admin Console](https://admin.google.com/u/3/ac/home?hl=en) using your administrator credentials.
2. On the left sidebar under **Account**, choose **Admin roles**.

![2-admin-role.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a194796c-736d-a465-5fef-396cf5dcc5ec.png)
3. On the **Roles** page, click **Create new role**.

![Admin roles management interface displaying various user roles and their descriptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-new-role.png)
4. On the **Role info** page:
  1. Enter a suitable name and description for a new role.
  2. Click **CONTINUE**. ![Creating a custom role for Google Drive connector authentication in Securiti platform.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/role-info.png)
5. On the **Select Privileges** page, under **Admin Privileges**, assign the following privileges to the new role:

> [!NOTE]
> Note
> 
> You must also configure the OAuth scopes as described in [Assigning scopes and permissions](/v1/docs/prerequisites-for-g-suite-google-drive).

| **Use case** | **Constraints** | **Admin Privileges** |
| --- | --- | --- |
| Sensitive Data Intelligence (Discovery Scan) | SDI via Discovery Scans is only available on the self-hosted connector. | - In **Services** > **Drive and Docs**, mark the checkbox for **Settings** which automatically mark the following privileges: - `Docs Templates` - `Manage classic Google sites` - `Move any file or folder into shared drives` - `View details of new Google Sites` - In Organizational Units: - `Read` - In **Users**: - `Read` - In **Groups**: - `Read` |
| Data Inventory Sync and Gencore AI Entitlement scanning | - Available for self-hosted connector only. - Requires allowlisting APIs between your deployed Securiti pod and the Google Workspace APIs. | - In **Services > Drive and Docs**, mark the checkbox for **Settings** which automatically mark the following privileges: - `Docs Templates` - `Manage classic Google sites` - `Move any file or folder into shared drives` - `View details of new Google Sites` - In Organizational Units: - `Read` - In **Users**: - `Read` - In **Groups**: - `Read` |
| Security Posture Management (Posture scan) | This capability lets Securiti apply Google APIs for Google Drive Security Posture Findings. | - In **Services** > **Drive and Docs**, mark the checkbox for **Settings** which automatically mark the following privileges: - `Docs Templates` - `Manage classic Google sites` - `Move any file or folder into shared drives` - `View details of new Google Sites` - In **Manage customer** > **Read customer:** - `Read customer branding settings` - `Read customer contact info` - `Read customer onboard settings` - `Read customer profile settings` - `Read customer support settings` - `Read customer timezone settings` - `Reports` - In **Groups**: - `Read` |
| Data Labeling Policy | - You must enable the Turn Labels On option from the Google admin console. - A label can have up to 10 fields. | - In **Services > Data Classification:** - `Manage Labels` |

![Selecting admin privileges with a search bar and continue button in a role creation interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/search-privileges(1).png)
6. On the bottom right of the **Select Privileges** page, click **CONTINUE**.

It redirects you to the **Review Privileges** page, where you see the list of privileges assigned to the new role.
7. Click **CREATE ROLE**.

![Reviewing selected privileges for a custom role in Google Drive authentication settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Review Privileges.png)
8. On the **CUSTOM ROLE** page, click **Assign members**.

![Admin roles interface showing options to assign members and manage roles.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Assign Members.png)
9. On the **Add members** page, in the **Find and select a user or security group search** field, search and select the user you want to assign to this role.
  1. Click **ASSIGN ROLE** to assign the custom role to the selected users in the list. Record the email address, as it is required during the connector activation step.

![Interface for assigning admin roles to users or security groups in a system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add Member.png)

> [!NOTE]
> **Note**
> 
> Service accounts can’t be used to assign custom roles and access user data; you must impersonate a user included in the Google Workspace domain. For more information, see [Google documentation](https://developers.google.com/workspace/cloud-search/docs/guides/delegation).
10. Record the email address of the user you assigned the custom role to. You need this address to activate the connector if you intend to use non-admin email.
11. Proceed to [connecting Google Drive (Google Workspace) (Self-Hosted) with Securiti](/latest/docs/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti).
