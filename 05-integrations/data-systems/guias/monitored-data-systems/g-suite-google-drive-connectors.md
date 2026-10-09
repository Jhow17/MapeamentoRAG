---
title: "Google Drive (Google Workspace)"
slug: "g-suite-google-drive-connectors"
status: "update"
updated: 2026-08-31T11:36:52Z
published: 2026-08-31T11:36:52Z
canonical: "helpcenter.securiti.ai/g-suite-google-drive-connectors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google Drive (Google Workspace)

Google Drive (Google Workspace) is a cloud-based storage service provided by Google, where you can store files such as documents, photos, and videos. It lets you access your files from any device, share them with others, and collaborate in real-time on documents, spreadsheets, and presentations. With Google Drive (Google Workspace) connectors, you can integrate with Securiti and scan data for your data system. Google Drive (Google Workspace) is a [monitored, unstructured data system](/latest/docs/managing-data-system-connectors#data-systems-classification).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/360-2-Google Drive connector activation-Page-2.drawio.svg)

> [!NOTE]
> **Note**
> 
> Securiti provides API Quota Tracking for Google Drive (Google Workspace) self-hosted connector. This feature monitors API usage and automatically pauses requests when the limit is reached. Once the quota resets, the process continues without causing disruptions.
> 
> For more information, see [API quota tracking for SaaS connectors](/latest/docs/api-quota-tracking-for-saas-connectors).

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Google Drive (Google Workspace) (Self-hosted) | Self-hosted connector supports: - Sensitive Data Intelligence - DSR Automation - Data Breach Management - Security Posture Management - Gencore AI |
| Google Drive (Google Workspace) (Securiti cloud) | Securiti Cloud connector supports: - Sensitive Data Intelligence - DSR Automation - Data Breach Management - Security Posture Management |

### Supported pod types for self-hosted connector

- Standard Securiti Pod.
- Elastic Pod/ EDSS.

### Supported authentication methods

> [!NOTE]
> **Important**
> 
> Service accounts cannot directly activate the Google Drive (Google Workspace) connector because they are separate from your Google Workspace domain and do not have default access to user data. To grant access, you must configure domain-wide delegation. This authorizes the service account to act on behalf of users within your organization. For more information, see [Google Workspace documentation](https://developers.google.com/workspace/guides/auth-overview).

- For Self-hosted connector:
  - Service Account authentication
- For Securiti Cloud connector:
  - Service Account authentication

#### Keyring support for Google Drive (Google Workspace) (self-hosted) connector

You can use a keyring support to store authentication credentials in a vault product during the connector configuration process to securely access your credentials from a vault.

For more information, see:

- [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault)
- [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault)
- [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault)
- [CyberArk](/latest/docs/cyberark-credential-vault)

To learn more about keyrings, refer to [Managing Keyrings](/latest/docs/managing-credentials-using-keyrings).

### Supported items for Inventory and Classification scans

Securiti scans the following entities for Google Drive (Google Workspace) during discovery scans and Data Inventory Syncs.

> [!WARNING]
> Important
> 
> Google Workspace components, such as Google Docs and Google Slides are integral components of the Google Drive ecosystem. Since these files are automatically stored and managed within Google Drive, Securiti includes them in the scanning process when you scan your Google Drive data.

- All the groups present in the domain
- Personal drives of the users who are members of the group
- Shared Drives present in the domain
- All files present in each directory
- All personal files of user in My Drives
- Files in Google Drive Groups
- All items present in Trash

> [!NOTE]
> Note
> 
> To exclude scanning items in trash, you must delete them permanently.
- Sensitivity labels in Google Drive files

> [!NOTE]
> Note
> 
> The sensitivity labels applied across Google Drive files are fetched and ingested during Data Inventory Sync.

**Additional resources**

- For more information, see [Configure discovery scans in Google Drive (Google Workspace) (Self-hosted)](/latest/docs/configure-discovery-scans-in-g-suite-google-drive-self-hosted).
- For more information, see [Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted).
- For more information on inventory and entitlement scans, see [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors).
- For more information about classification in discovery scans, see [Understanding Discovery Scans](/latest/docs/discovery-scans).

### Prerequisites for configuring Google Drive (Google Workspace) connector

#### 1. Pod deployment

> [!NOTE]
> **Important**
> 
> Pod deployment is required for self-hosted connectors only.

You must deploy a Securiti pod in your environment to connect your Google Drive (Google Workspace) with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti endpoints. For more information, see the allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/latest/docs/elastic-pods-deployment).

For more information on configuring pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).

#### 2. Admin access

- You must be a super admin for your Google account to create custom role and assign privileges

> [!NOTE]
> **Note**
> 
> - For self-hosted connectors, you can either use a super admin email or a non-admin email with a custom role to activate the connector. For more information, see [Prerequisites for Google Drive (Google Workspace) (Self-Hosted)](/latest/docs/prerequisites-for-g-suite-google-drive)
> - For cloud connectors, you must use admin email while creating Google Workspace Service account. For more information, see [Prerequisites for Google Drive (Google Workspace) (Securiti Cloud) connector](/latest/docs/prerequisites-for-g-suite-google-drive-securiti-cloud-connector).
- You must have the Admin role in your Securiti accounts.

#### 3. Allowlisting APIs for Data Inventory Sync and Discovery Scans

You must allowlist the following APIs to successfully run the Data Inventory Sync and Discovery Scans for Google Drive (Google Workspace) (Self-hosted) connector.

For more information, see [Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted).

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | `https://www.googleapis.com/drive/v3/files` | Get drive items |
| 2 | GET | `https://www.googleapis.com/drive/v3/files/{{folder_id}}` | Get folder name |
| 3 | GET | `https://www.googleapis.com/admin/directory/v1/groups/{{group_id}}/members` | Get group members |
| 4 | GET | `https://www.googleapis.com/admin/directory/v1/groups/{{group_id}}` | Get group aliases |
| 5 | GET | `https://www.googleapis.com/admin/directory/v1/customer/my_customer/orgunits` | Get organization |
| 6 | GET | `https://www.googleapis.com/admin/directory/v1/groups/` | Get Google Workspace domain groups |
| 7 | GET | `https://www.googleapis.com/drive/v3/files/{{drive_id}}/permissions` | Get shared drive permission |
| 8 | GET | `https://www.googleapis.com/admin/directory/v1/users` | Get users within org |
| 9 | GET | `https://www.googleapis.com/admin/directory/v1/users` | Fetch Google Workspace domain user |
| 10 | GET | `https://www.googleapis.com/admin/directory/v1/users` | Get users |
| 11 | GET | `https://www.googleapis.com/admin/directory/v1/groups/` | Get groups |
| 12 | GET | `https://www.googleapis.com/admin/directory/v1/groups/{{group_id}}/members` | Get group members |
| 13 | GET | `https://www.googleapis.comdrive/v3/files/{{id}}/permissions` | Get permissions |

#### 4. Use cases and permissions for Google Drive (Google Workspace)

This section covers use cases and permissions required for Google Drive (Google Workspace) self-hosted and Securiti cloud connectors.

The use cases and permissions vary depending on whether the service account impersonates a super admin user or a non-admin user with a custom admin role. For more information, see the below tables:​

- Permissions when using Super Admin role to be impersonated
- Permissions when using non-admin role with custom admin role

> [!NOTE]
> **Note**
> 
> If you are using a non-admin email to activate the self-hosted connector, you must follow the procedure to create and assign the privileges to the custom role mentioned in [Prerequisites for Google Drive (Google Workspace) (Self-Hosted)](/latest/docs/prerequisites-for-g-suite-google-drive), in addition to enabling the domain-wide delegation scopes described in the table below.

#### Permissions for Super Admin role

Use the table below for permissions and use cases if you are not using a custom role.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing - DSR Automation through Smart Search | SDI via Discovery Scans and DSR Automation Indexing is only available on the self-hosted connector. | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/admin.directory.customer.readonly, https://www.googleapis.com/auth/admin.directory.user.readonly, https://www.googleapis.com/auth/admin.directory.domain.readonly, https://www.googleapis.com/auth/admin.directory.group.readonly, https://www.googleapis.com/auth/drive.readonly, https://www.googleapis.com/auth/drive.metadata.readonly, https://www.googleapis.com/auth/drive.photos.readonly, ``` | These permissions let Securiti read the files and metadata in Google Drive (Google Workspace) for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation and enables PII data search. |
| Data Inventory Sync and Gencore AI Entitlement scanning | - Available for self-hosted connector only. - Requires allowlisting APIs between your deployed Securiti pod and the Google Workspace APIs. See [section above](/v1/docs/g-suite-google-drive-connectors). | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/admin.directory.orgunit.readonly ``` | This permission lets Securiti read the files and file metadata in Google Drive (Google Workspace) for inventory. The permission also lets Securiti discover entitlements. |
| Security Posture Management Rule Evaluation | This capability lets Securiti apply Google APIs for Google Drive Security Posture Findings. | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/admin.directory.customer.readonly https://www.googleapis.com/auth/admin.reports.audit.readonly ``` | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |
| Workflows | Only required to run the workflow node for Google Drive (Google Workspace) connector | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/drive ``` | This permission lets you use and run the workflow node of the connector in Securiti **Workflows**. |
| Data Labeling Policy | - You must enable the **Turn Labels On** option from the Google admin console. - A label can have up to 10 fields. | **OAuth scopes for reading labels:** ```plaintext https://www.googleapis.com/auth/drive.labels.readonly https://www.googleapis.com/auth/drive.admin.labels.readonly ``` **OAuth scopes for creating labels:** ```plaintext https://www.googleapis.com/auth/drive.labels https://www.googleapis.com/auth/drive.admin.labels ``` **OAuth scopes for applying labels:** ```plaintext https://www.googleapis.com/auth/drive.metadata ``` | These permissions let Securiti view, manage, and apply labels to Google Drive (Google Workspace) files. With these permissions, you can apply Data Labelling Policy to your files. |

#### Permissions for custom admin role

Use the table below for permissions and use cases if you are using a custom role.

| Use case | Constraints | Permissions | Explanation of use case |
| --- | --- | --- | --- |
| - Sensitive Data Intelligence (SDI) - Data Subject Request (DSR) Automation Indexing - DSR Automation through Smart Search | SDI Discovery Scans and DSR Automation Indexing is only available on the self-hosted connector. | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/admin.directory.customer.readonly, https://www.googleapis.com/auth/admin.directory.user.readonly, https://www.googleapis.com/auth/admin.directory.domain.readonly, https://www.googleapis.com/auth/admin.directory.group.readonly, https://www.googleapis.com/auth/drive.readonly, https://www.googleapis.com/auth/drive.metadata.readonly, https://www.googleapis.com/auth/drive.photos.readonly, ``` **Admin Console Privileges:** - In **Services > Drive and Docs > Settings**, mark all checkboxes. - In **Organizational Units**, select **Read** **Admin API privileges:** - Users: **Read** - Organization: **Read** - Groups: **Read** | These permissions let Securiti read the files and metadata in Google Drive (Google Workspace) for inventory and classification purposes. These permissions also build the Personal Data Index for DSR Automation and enables PII data search. |
| Data Inventory Sync and Gencore AI Entitlement scanning | - Available for self-hosted connector only. - Requires allowlisting APIs between your deployed Securiti pod and the Google Workspace APIs. See [section above](/v1/docs/g-suite-google-drive-connectors). | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/admin.directory.orgunit.readonly ``` **Admin Console Privileges:** - In **Services > Drive and Docs > Settings**, mark all checkboxes. - In **Organizational Units**, select **Read** **Admin API privileges:** - Users: **Read** - Organization: **Read** - Groups: **Read** | This permission lets Securiti read the files and file metadata in Google Drive (Google Workspace) for inventory. The permission also lets Securiti discover entitlements. |
| Security Posture Management Rule Evaluation | This capability lets Securiti apply Google APIs for Google Drive Security Posture Findings. | **Admin Console Privileges:** - In **Services > Drive and Docs > Settings**, mark all checkboxes. **Admin API privileges:** - In **Manage customer**, select **Read customer** - Select **Reports** - Groups: **Read** **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/admin.directory.customer.readonly https://www.googleapis.com/auth/admin.reports.audit.readonly ``` | These permissions let Securiti retrieve the configuration details required to evaluate the Security Posture rules. |
| Data Labeling Policy | - You must enable the **Turn Labels On** option from the Google admin console. - A label can have up to 10 fields. | **Admin Console privileges:** - In **Services > Data Classification**, select **Manage Labels** **OAuth scopes for reading labels:** ```plaintext https://www.googleapis.com/auth/drive.labels.readonly https://www.googleapis.com/auth/drive.admin.labels.readonly ``` **OAuth scopes for creating labels:** ```plaintext https://www.googleapis.com/auth/drive.labels https://www.googleapis.com/auth/drive.admin.labels ``` **OAuth scopes for applying labels:** ```plaintext https://www.googleapis.com/auth/drive.metadata ``` | These permissions let Securiti view, manage, and apply labels to Google Drive (Google Workspace) files. With these permissions, you can apply Data Labelling Policy to your files. |

### Connect Google Drive (Google Workspace) connectors with Securiti

This section covers the methods to integrate your Google Drive (Google Workspace) with Securiti using self-hosted or Securiti cloud connectors, depending on your setup.

#### Steps to connect the Google Drive (Google Workspace) (Self-Hosted) connector with Securiti

To configure the Google Drive (Google Workspace) (Self-hosted) connector, perform the procedures in the following topics:

1. Deploy and configure Pod using [Securiti Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. [Prerequisites for Google Drive (Google Workspace) (Self-Hosted)](/latest/docs/prerequisites-for-g-suite-google-drive)
3. [Connecting Google Drive (Google Workspace) (self-hosted) with Securiti](/latest/docs/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti).
4. [Configuring General permissions for Google Drive (Google Workspace) (self-hosted)](/latest/docs/configuring-general-permissions-for-google-drive-google-workspace-self-hosted).
5. [Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted).
6. [Configure discovery scans in Google Drive (Google Workspace) (Self-hosted)](/latest/docs/configure-discovery-scans-in-g-suite-google-drive-self-hosted).

#### Steps to connect the Google Drive (Google Workspace) (Securiti Cloud) connector with Securiti

To configure the Google Drive (Google Workspace) (Securiti Cloud) connector, perform the following steps:

1. [Prerequisites for Google Drive (Google Workspace) (Securiti Cloud) connector](/latest/docs/prerequisites-for-g-suite-google-drive-securiti-cloud-connector).
2. [Connecting Google Drive (Google Workspace) (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-google-drive-google-workspace-securiti-cloud-with-securiti).
3. [Configure General permissions for Google Drive (Google Workspace) (Securiti cloud)](/latest/docs/configure-general-permissions-for-google-drive-google-workspace-securiti-cloud).

**Additional resources**

- For more information about how Securiti uses the data to respond to DSR requests, see [Fulfilling DSR requests for Google Drive (Google Workspace)](/latest/docs/fulfilling-dsr-requests-for-g-suite-google-drive) .
- For more information about Google Drive (Google Workspace) FAQs, see [Google Drive (Google Workspace) FAQs](/latest/docs/g-suite-google-drive-faqs-en).
- For more information on the authentication and scanning issues, see [Troubleshooting for Google Drive (Google Workspace)](/latest/docs/troubleshooting-for-g-suite-google-drive)
