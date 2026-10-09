---
title: "Configuring Activity Analysis for Google Drive (Hyperdrive)"
slug: "configuring-activity-analysis-for-google-drive-hyperdrive"
updated: 2026-07-20T20:57:21Z
published: 2026-07-20T20:57:21Z
canonical: "helpcenter.securiti.ai/configuring-activity-analysis-for-google-drive-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Configuring Activity Analysis for Google Drive (Hyperdrive)

This article covers the Activity Analysis configuration for the Google Drive (Google Workspace) (Hyperdrive) connector.

## Prerequisites

To use the Activity Analysis feature, you must complete the following prerequisites:

1. **Enable Google Workspace audit logs**

Activity Analysis requires Google Workspace audit logs to capture user and admin activity events in Google Drive.

Audit logging is enabled by default in Google Workspace. To verify or manage audit log settings:
  1. Sign in to the Google Admin Console.
  2. Navigate to **Reports** → **Audit and investigation** → **Drive log events**.
  3. Verify that Drive audit events are being recorded for your organization.

> [!NOTE]
> Note
> 
> It can take up to 24 hours for audit events to start appearing after changes are made to logging settings.
2. **Assign OAuth Scopes** Ensure the Google service account used for the Google Drive connector has the following OAuth scopes configured.

| Scope | Explanation |
| --- | --- |
| `https://www.googleapis.com/auth/admin.reports.audit.readonly` | Lets you retrieve audit log data from Google Workspace, including file access, modification, creation, and permission change events in Google Drive. Required to collect activity logs for Activity Analysis. Actor identity, including application name, OAuth client ID, and impersonation status is embedded directly in the Drive audit record and does not require additional Directory API scopes. |
| `https://www.googleapis.com/auth/admin.directory.user.readonly` | Retrieves user directory data to classify actors as internal or external. Required to populate the Is External field in activity log results. |

> [!WARNING]
> Important
> 
> - The service account must impersonate a Google Workspace user with Super Admin privileges when making API calls. Ensure the user account used to configure the GDrive connector has the Super Admin role assigned in Google Workspace.
> - Configure domain-wide delegation on the service account with the `admin.reports.audit.readonly` scope. Domain-wide delegation is required to retrieve tenant-wide audit log data across all user accounts.
> - Verify that the Admin SDK API is enabled in the Google Cloud project linked to your service account.
> - Ensure service account credentials (JSON key) are valid and not ex
3. Run data inventory sync and entitlement scan You must run data inventory sync and entitlement scan before initiating Activity analysis.

## Configure Activity Analysis

1. After activating your data system connector, under the **Configuration**, click **Activity Analysis**.
2. On the **Activity Analysis** page, mark the **Enable Activity Analysis** checkbox to include the data system in the activity analysis, and click **Save.**
3. Click **Start Sync** to start the activity analysis sync.

The Securiti will start the activity analysis scan for your data system, providing visibility into how users, AI agents, service accounts, and applications interact with data across connected data systems. For more information, see Activity Analysis for Google Drive (Google Workspace).
