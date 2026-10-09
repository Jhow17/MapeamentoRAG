---
title: "Assign the permisions and enable APIs for Gmail Activity Analysis"
slug: "assign-permissions-for-gmail-google-workspace-activity-analysis"
status: "new"
updated: 2026-09-26T20:07:00Z
published: 2026-09-26T20:05:14Z
canonical: "helpcenter.securiti.ai/assign-permissions-for-gmail-google-workspace-activity-analysis"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Assign the permisions and enable APIs for Gmail Activity Analysis

Complete the following prerequisites for Gmail (Google Workspace) Activity Analysis:

### **1. Enable Google Workspace audit logs**

Activity Analysis requires Google Workspace audit logs to capture user and admin activity events in Gmail.

Audit logging is enabled by default in Google Workspace. To verify or manage audit log settings:

1. Sign in to the [**Google Admin Console**](https://admin.google.com).
2. Navigate to **Reports → Audit and investigation → Gmail log events**.
3. Verify that Gmail audit events are being recorded for your organization.

> [!NOTE]
> Note
> 
> It can take up to 24 hours for audit events to start appearing after changes are made to logging settings.

#### **2. API permissions**

Ensure the Google service account used for the Gmail connector has the following API scopes configured.

| Google API | Scope | What Securiti uses this for |
| --- | --- | --- |
| Admin SDK – Reports API | `https://www.googleapis.com/auth/admin.reports.audit.readonly` | Lets you retrieve audit log data from Google Workspace, including user and admin activity events in Gmail. Required to collect activity logs for Activity Analysis, including Gmail audit log events and admin domain-wide delegation grant events. |

> [!WARNING]
> Important
> 
> - The service account must impersonate a Google Workspace user with Super Admin privileges when making API calls. Ensure the user account used to configure the Gmail connector has the Super Admin role assigned in Google Workspace.
> - Configure domain-wide delegation on the service account with all of the scopes listed above.
> - Ensure service account credentials (JSON key) are valid and not expired.

Ensure the following GCP APIs are enabled in the Google Cloud project associated with the Hyperdrive service account.

| GCP API | Scope | What Securiti uses this for |
| --- | --- | --- |
| Cloud Resource Manager API | cloudresourcemanager.googleapis.com | Enumerates all GCP projects in the organization. |
| Discovery Engine API (Vertex AI Search) | discoveryengine.googleapis.com | Lists data stores and finds those backed by Gmail Workspace. Lists engines (apps) linked to those data stores. *(For the GDrive article: replace Gmail Workspace with Google Drive Workspace)* |
| Agent Registry API | agentregistry.googleapis.com | Lists all registered AI agents in a project. |

All three APIs must be enabled in the GCP project where your service account lives, and in each target project you want to scan.

1. Sign in to [console.cloud.google.com](http://console.cloud.google.com) and select your project.
2. Navigate to **APIs & Services → Library**.
3. Search for and enable each of the following APIs:

> [!NOTE]
> Note
> 
> If scanning multiple projects, these APIs must be enabled in each target project as well.
  - Cloud Resource Manager API ([cloudresourcemanager.googleapis.com](http://cloudresourcemanager.googleapis.com))
  - Discovery Engine API ([discoveryengine.googleapis.com](http://discoveryengine.googleapis.com))
  - Agent Registry API ([agentregistry.googleapis.com](http://agentregistry.googleapis.com))
