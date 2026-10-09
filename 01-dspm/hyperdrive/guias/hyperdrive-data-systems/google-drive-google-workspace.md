---
title: "Google Drive (Google Workspace) (Hyperdrive)"
slug: "google-drive-google-workspace"
updated: 2026-08-18T09:25:41Z
published: 2026-08-18T09:28:21Z
canonical: "helpcenter.securiti.ai/google-drive-google-workspace"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Google Drive (Google Workspace) (Hyperdrive)

Google Drive (Google Workspace) is a cloud-based storage service provided by Google, where you can store files such as documents, photos, and videos. It lets you access your files from any device, share them with others, and collaborate in real-time on documents, spreadsheets, and presentations. With Google Drive (Google Workspace) connectors, you can integrate with Securiti and scan data for your data system. Google Drive (Google Workspace) is a [monitored, unstructured data system](/latest/docs/managing-data-system-connectors#data-systems-classification).

> [!NOTE]
> Note
> 
> To activate the Google Drive (Google Workspace) connector with Hyperdrive mode, use a super admin account to create a service account and obtain its credentials. Hyperdrive mode does not support activation using custom role credentials.

## Supported connector types and modules

| Connector type | Supported modules features |
| --- | --- |
| Google Drive (Google Workspace) Self-hosted | - Discovery scan - Data Inventory Sync and Entitlement Scan - Activity Analysis |

## Supported outpost deployments

- Hybrid deployment with Outpost
- Full SaaS Hyperdrive deployment

## Supported authentication methods

- Service Account authentication

> [!WARNING]
> **Important**
> 
> Service accounts cannot directly activate the Google Drive (Google Workspace) connector because they are separate from your Google Workspace domain and do not have default access to user data. To grant access, you must configure domain-wide delegation. This authorizes the service account to act on behalf of users within your organization. For more information, see [Google Workspace documentation](https://developers.google.com/workspace/guides/auth-overview).

### Keyring support

- Keyring support is not available for data systems using Hyperdrive mode.

## Supported items for inventory and classification scans

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

For more information, see [Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted) (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted-1). For more information about classification in discovery scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

## Prerequisites

Complete the following prerequisites to authenticate the Google Drive (Google Workspace):

### 1. Outpost deployment

If you use Hyperdrive mode while creating a data system instance, you must deploy Securiti Outpost, which uses AWS services to scale scanning operations. For more information, see [Securiti Outpost deployment](/latest/docs/securiti-outpost-deployment).

### 2. Admin access in Google account

You must be a super admin for your Google account to create obtain service account and assign privileges.

### 3. Enable Google Workspace audit logs for Activity Analysis

You must enable Google Workspace audit logs to capture user and admin activity events in Google Drive. For more information, see [Hyperdrive Activity Analysis for Google Drive (Google Workspace)](/latest/docs/hyperdrive-activity-analysis-for-google-drive-google-workspace)

### 4. Use cases and permissions

This section covers Google Drive OAuth scopes required for Google Drive connectors to leverage Hyperdrive features. Use the following table to understand the OAuth scopes required if you authenticate Google Drive using super admin role:

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

### Connect Google Drive (Google Workspace) using Hyperdrive with Securiti

To configure the Google Drive (Google Workspace) connector using Hyperdrive mode, perform the procedures in the following topics:

1. [Deploy Securiti Outpost](/latest/docs/securiti-outpost-deployment)..
2. [Using super admin role for Google Drive (Google Workspace) (Self-Hosted) (Hyperdrive)](/latest/docs/prerequisites-for-g-suite-google-drive-1)
3. [Connecting Google Drive (Google Workspace) (Self-Hosted) with Securiti (Hyperdrive)](/latest/docs/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti-1)
4. [Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted) (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted-1)
5. [Configure discovery scans in Google Drive (Google Workspace) (Self-hosted) (Hyperdrive)](/latest/docs/configure-discovery-scans-in-g-suite-google-drive-self-hosted-1)

### Additional resources

- [View Activity Analysis results for Google Drive (Google Workspace)](/latest/docs/hyperdrive-activity-analysis-for-google-drive-google-workspace)
- [Troubleshooting for Google Drive (Google Workspace) (Hyperdrive)](/latest/docs/troubleshooting-for-google-drive-google-workspace)
