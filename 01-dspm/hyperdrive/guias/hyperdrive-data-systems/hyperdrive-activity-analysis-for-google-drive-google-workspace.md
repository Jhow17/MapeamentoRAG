---
title: "Hyperdrive Activity Analysis for Google Drive (Google Workspace)"
slug: "hyperdrive-activity-analysis-for-google-drive-google-workspace"
updated: 2026-07-23T09:37:06Z
published: 2026-07-23T09:37:06Z
canonical: "helpcenter.securiti.ai/hyperdrive-activity-analysis-for-google-drive-google-workspace"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Activity Analysis for Google Drive (Google Workspace)

## **Overview**

Hyperdrive Activity Analysis for Google Drive provides visibility into how users, applications, and automated services interact with files and folders stored in Google Drive.

It analyzes Drive audit logs to capture a wide range of activity: file views, downloads, edits, renames, folder operations, permission changes, and AI or application reads of file content. Beyond what happened, Activity Analysis identifies who or what performed each action, distinguishing direct user activity from OAuth-authorized applications, service accounts with domain-wide delegation, and Google first-party services, so you can assess risk at the actor level.

## **Prerequisites**

Before configuring Activity Analysis for Google Drive, ensure the following requirements are completed.

### **Connector setup**

Ensure the **Google Drive** connector is configured and synced in Hyperdrive.

For detailed setup instructions of all the required steps, see:

- [Prerequisites for Google Cloud Storage (Google Workspace) (Self-Hosted)](/latest/docs/prerequisites-for-g-suite-google-drive-1)
- [Using custom admin role for non-admin users](/latest/docs/using-custom-role-for-non-admin-users-1)
- [Activate the Google Drive (Google Workspace) (Self-Hosted) connector in Securiti](/latest/docs/activate-the-g-suite-google-drive-self-hosted-connector-in-securiti-1)
- [Connecting Google Drive (Google Workspace) (Self-Hosted) with Securiti](/latest/docs/new-ui-connecting-google-drive-google-workspace-self-hosted-with-securiti-1)
- [Configuring General permissions for Google Drive (Google Workspace) (self-hosted)](/latest/docs/configuring-general-permissions-for-google-drive-google-workspace-self-hosted-1)
- [Configuring Data Inventory Sync for Google Drive (Google Workspace) (Self-hosted)](/latest/docs/configuring-data-inventory-sync-for-g-suite-google-drive-self-hosted-1)
- [Configure discovery scans in Google Drive (Google Workspace) (Self-hosted)](/latest/docs/configure-discovery-scans-in-g-suite-google-drive-self-hosted-1)

### **Google Workspace Activity Analysis requirements**

Ensure the following Google Workspace prerequisites are completed before enabling Activity Analysis.

#### **Enable Google Workspace audit logs**

Activity Analysis requires Google Workspace audit logs to capture user and admin activity events in Google Drive.

Audit logging is enabled by default in Google Workspace. To verify or manage audit log settings:

1. Sign in to the [**Google Admin Console**](https://admin.google.com).
2. Navigate to **Reports → Audit and investigation → Drive log events**.
3. Verify that Drive audit events are being recorded for your organization.

> [!NOTE]
> Note
> 
> It can take up to 24 hours for audit events to start appearing after changes are made to logging settings.

#### **API permissions**

Ensure the Google service account used for the Google Drive connector has the following API scope configured.

| Google API | Scope | What Securiti uses this for |
| --- | --- | --- |
| Admin SDK – Reports API | `https://www.googleapis.com/auth/admin.reports.audit.readonly` | Lets you retrieve audit log data from Google Workspace, including file access, modification, creation, and permission change events in Google Drive. Required to collect activity logs for Activity Analysis. Actor identity, including application name, OAuth client ID, and impersonation status is embedded directly in the Drive audit record and does not require additional Directory API scopes. |
| Admin SDK – Directory API | `https://www.googleapis.com/auth/admin.directory.user.readonly` | Retrieves user directory data to classify actors as internal or external. Required to populate the Is External field in activity log results. |

> [!WARNING]
> Important
> 
> - The service account must impersonate a Google Workspace user with Super Admin privileges when making API calls. Ensure the user account used to configure the GDrive connector has the Super Admin role assigned in Google Workspace.
> - Configure domain-wide delegation on the service account with the `admin.reports.audit.readonly` scope. Domain-wide delegation is required to retrieve tenant-wide audit log data across all user accounts.
> - Verify that the Admin SDK API is enabled in the Google Cloud project linked to your service account.
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

## **Configure and run Activity Analysis**

To configure Activity Analysis for Google Drive:

1. In **Securiti**, navigate to **Integrations** and open your configured **Google Drive** instance in Monitored data systems.
2. From the left navigation panel, click **Activity Analysis**.
3. Select the **Enable Activity Analysis** checkbox.
4. Click **Save** to apply the configuration.
5. Click **Start Sync** to initiate activity data synchronization.

> [!NOTE]
> Note
> 
> - If a connector is configured but **Activity Analysis (AA) has not been executed yet** (either independently or via inventory), the system remains **idle and awaits the user to trigger the first scan**.
> - Once the **initial scan is launched**, the system automatically:
>   - Schedules itself to run **daily**
>   - Captures **incremental (delta) activity logs** between the previous day and the current day

> [!NOTE]
> Note
> 
> - Activity Analysis sync collects Drive activity data including file views, downloads, edits, creates, renames, folder operations, permission changes, and timestamps.
> - If the sync has not been run, activity insights will not be available.

## **Using Activity Analysis in Hyperdrive for Google Drive**

Below are example use cases to help you use **Securiti's Data Command Graph** to analyze user activity and identify risks in your Google Drive environment using Activity Analysis.

When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

### **Identify and report on Google Drive activity by activity type and actor type**

This query helps you identify and analyze Google Drive activity by filtering activity logs based on both activity type and actor type. It lets you monitor how different actors (users, applications, agents, or systems) interact with files and investigate activity patterns.

To identify Google Drive activity by activity type and actor type:

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **G Suite Google Drive**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select one or more of the following:
  - access
  - create
  - delete
  - modify
  - move
  - other
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select one or more of the following:
  - User
  - Application
  - Agent
  - System
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 4(12).png)

> [!NOTE]
> Note
> 
> In Google Drive, activity types and actor types map to the following:
> 
> **Activity types**
> 
> - **access** — File views, downloads, desktop sync operations, AI or app reads of file content, and app URL resolution.
> - **create** — New file or folder creation. A single create event can generate multiple audit records in the same log entry, including permission assignment and folder placement.
> - **delete** — File deletion.
> - **modify** — File content edits and file renames.
> - **move** — File and folder moves, including placement into a folder.
> - **other** — Permission changes (sharing updates, editor list modifications) and Drive search events.
> 
> **Actor types**
> 
> - **User.** A Google Workspace user acting directly, with no application involved. Includes direct file interactions (view, edit, create, rename) and Drive desktop sync operations.
> - **Application.** An OAuth 2.0 application authorized by the user. Includes AI-capable apps such as Gemini and Make, and standard integrations such as Canva, Jotform, Evernote, and Docusign. Access scope depends on what the user granted when authorizing the app.
> - **Agent.** A service account with domain-wide delegation, authorized by a Google Workspace admin. Agents can access files across the organization without per-user consent. Identified in audit logs by a plain numeric OAuth client ID and `impersonation: true`.
> - **System.** A Google first-party service embedded in Workspace, such as Gemini for Workspace. Operates without an OAuth client ID and does not go through a standard authorization flow.

**Default columns displayed in the data grid**

By default, the data grid displays the following activity metadata:

- Resource Name
- Activity Type
- Actor Type
- Connector Type ID
- Activity Timestamp
- Is External
- Source Resource Path
- Target Resource Path
- Resource ID
- Activity ID
- Data Asset ID
- Resource Path
- Container ID
- Actor ID
- Resource URL

**Additional columns available in the data grid**

You can customize the data grid to include additional attributes for deeper activity analysis:

- Display Name
- Organization
- Securiti Tags

### **Identify and report on Google Drive delete activities performed by the system**

This helps you identify file deletion activities performed by the system in Google Drive. System actors such as automated platform processes can delete files as part of internal operations. Monitoring system deletions lets you distinguish expected platform behavior from unexpected or unauthorized removal of files.

To identify Google Drive delete activities performed by the system:

1. In Securiti, open Data Access Governance.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the Activity Log entity, select **Add Property**, choose **Connector Type ID**, and select **G Suite Google Drive**.
6. Click the three dots next to the Activity Log entity, select **Add Property**, choose **Actor Type**, and select **System**.
7. Click the three dots next to the Activity Log entity, select **Add Property**, choose **Activity Type**, and select **delete**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(20).png)

### **Identify and report on Google Drive access activities performed by applications**

This helps you identify file access activities performed by OAuth applications in Google Drive. Access events cover a range of interactions, from AI-capable apps reading file content for analysis or automation, to standard integrations downloading files or resolving Drive URLs. Monitoring application access lets you track which apps are reading sensitive files and identify patterns of non-user-driven data access.

**To identify Google Drive access activities performed by applications:**

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **G Suite Google Drive**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **access**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Application**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(28).png)

### **Identify and report on Google Drive access activities performed by agents**

This helps you identify file access activities performed by agents in Google Drive. Agents such as workflow automation tools can access and read files as part of automated multi-step processes. Monitoring agent access lets you distinguish expected automation behavior from unexpected or unauthorized access to file content.

To identify Google Drive access activities performed by agents:

1. In Securiti, open Data Access Governance.
2. From the left navigation menu, click Data Command Graph, and choose Access Graph Explorer.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the Activity Log entity, select **Add Property**, choose **Connector Type ID**, and select **G Suite Google Drive**.
6. Click the three dots next to the Activity Log entity, select **Add Property**, choose **Activity Type**, and select **access**.
7. Click the three dots next to the Activity Log entity, select **Add Property**, choose **Actor Type**, and select **Agent**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the Activity Log node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(43).png)

A type of data system that you can connect via Securiti to perform discovery scans on data for enhanced breach analysis.
