---
title: "Hyperdrive Activity Analysis for Gmail (Google Workspace)"
slug: "hyperdrive-activity-analysis-for-gmail-google-workspace"
updated: 2026-09-25T16:33:01Z
published: 2026-09-25T16:33:01Z
canonical: "helpcenter.securiti.ai/hyperdrive-activity-analysis-for-gmail-google-workspace"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Activity Analysis for Gmail (Google Workspace)

## **Overview**

Hyperdrive Activity Analysis for Gmail provides visibility into how users interact with emails and data stored in Gmail.

It analyzes activity logs such as message access, send actions, deletions, and label changes to help identify over-provisioned access, monitor email usage patterns, and detect risks associated with sensitive data. It also identifies who or what performed each action, including users, OAuth-authorized applications, and service accounts with domain-wide delegation, so you can assess risk at the actor level.

## **Prerequisites**

Before configuring Activity Analysis for Gmail, ensure the following requirements are completed.

### **Connector setup**

Ensure the **Gmail** connector is configured and synced in Hyperdrive.

For detailed setup instructions of all the required steps, see:

- [Prerequisites and obtaining authentication credentials for Gmail (Self-hosted) (Hyperdrive)](/latest/docs/prerequisites-and-obtaining-authentication-credentials-in-google-apps-1)
- [Connecting the Gmail (Google Workspace) (self-hosted) with Securiti (Hyperdrive)](/latest/docs/new-ui-connecting-google-workspace-gmail-message-body-attachments-securiti)
- [Configure Data Inventory Sync for Gmail (Google Workspace) (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-gmail-google-workspace-hyperdrive)
- [Configure discovery scans in Gmail (Google Workspace) (self-hosted) (Hyperdrive)](/latest/docs/configure-discovery-scans-in-g-suite-gmail-message-body-attachments-1)

### **Google Workspace Activity Analysis requirements**

Ensure the following Google Workspace prerequisites are completed before enabling Activity Analysis.

#### **Enable Google Workspace audit logs**

Activity Analysis requires Google Workspace audit logs to capture user and admin activity events in Gmail.

Audit logging is enabled by default in Google Workspace. To verify or manage audit log settings:

1. Sign in to the [**Google Admin Console**](https://admin.google.com).
2. Navigate to **Reports → Audit and investigation → Gmail log events**.
3. Verify that Gmail audit events are being recorded for your organization.

> [!NOTE]
> Note
> 
> It can take up to 24 hours for audit events to start appearing after changes are made to logging settings.

#### **API permissions**

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

## **Configure and run Activity Analysis**

To configure Activity Analysis for Gmail:

1. In **Securiti**, navigate to **Integrations** and in Monitored data systems open your configured **Gmail** instance.
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
> - Activity Analysis sync collects activity data such as message access, send actions, deletions, and timestamps.
> - If the sync has not been run, activity insights will not be available.

## **Using Activity Analysis in Hyperdrive for Gmail**

Below are example use cases to help you use **Securiti's Data Command Graph** to analyze user activity and identify risks in your Gmail environment using Activity Analysis.

When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

### **Identify and report on Gmail activity by activity type and actor type**

This query helps you identify and analyze Gmail activity by filtering activity logs based on both activity type and actor type. It lets you monitor how different actors (users, applications, agents, or systems) interact with emails and investigate activity patterns.

To identify Gmail activity by activity type and actor type:

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Gmail**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select one or more of the following:
  - access
  - create
  - delete
  - modify
  - other
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select one or more of the following:
  - User
  - Application
  - Agent
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 10(3).png)

> [!NOTE]
> Note
> 
> In Gmail, actor types map to the following principal types:
> 
> - **User.** A Google Workspace user account. Users can also appear as delegators or delegates if mailbox delegation is configured.
> - **Application.** A third-party OAuth application individually authorized by a user, such as Evernote or Docusign eSignature. The access level depends on the OAuth scopes the user granted when authorizing the app.
> - **Agent.** A service account with domain-wide delegation, or an AI agent, such as GPT Workspace or Smallpdf. Agents can access mailboxes across the organization without per-user consent.
> - **System.** An internal system or automated process.

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

### **Identify and report on Gmail delete activities performed by user**

This helps you identify email deletion activities performed by users in Gmail. It provides visibility into user initiated deletion events, letting you monitor activity and investigate potential data removal patterns.

**To identify Gmail delete activities performed by users:**

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Gmail**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **delete**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **User**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 8(5).png)

### **Identify and report on Gmail access activities performed by user**

This helps you identify message access activities performed by users in Gmail. It provides visibility into how users interact with emails, letting you monitor access patterns and investigate potential user-driven data access.

**To identify Gmail access activities performed by users:**

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Gmail**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **access**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **User**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 9(7).png)

### **Identify and report on Gmail create activities performed by agents**

This helps you identify email creation activities performed by agents in Gmail. It provides visibility into how service accounts with domain-wide delegation create emails across the organization, letting you monitor automated or system-driven email creation and detect potential unauthorized or unexpected activity.

**To identify Gmail create activities performed by agents:**

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Gmail**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **create**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Agent**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 11(1).png)

A type of data system that you can connect via Securiti to perform discovery scans on data for enhanced breach analysis.
