---
title: "Hyperdrive Activity Analysis for Microsoft 365 SharePoint Online"
slug: "activity-analysis-for-microsoft-sharepoint"
updated: 2026-08-07T13:01:12Z
published: 2026-08-07T13:01:12Z
canonical: "helpcenter.securiti.ai/activity-analysis-for-microsoft-sharepoint"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Activity Analysis for Microsoft 365 SharePoint Online

## **Overview**

Hyperdrive Activity Analysis for Microsoft SharePoint Online provides visibility into how users interact with sites, documents, and files within SharePoint.

It analyzes activity logs such as file access, sharing actions, permission changes, and collaboration events to help identify over-provisioned access, monitor usage patterns, and detect risks associated with sensitive data.

## **Prerequisites**

Before configuring Activity Analysis for Microsoft SharePoint Online, ensure the following requirements are completed.

### **Connector Setup**

Ensure the **Microsoft SharePoint Online** connector is configured and synced in Hyperdrive.

For detailed setup instructions of all the required steps, see:

- [Securiti Outpost - AWS](/latest/docs/securiti-outpost)
- [Creating an Entra ID app and obtaining credentials for Microsoft 365 (Hyperdrive)](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365)
- [Connecting Microsoft 365 using Hyperdrive](/latest/docs/connect-microsoft-365-using-hyperdrive)
- [Configuring Data Inventory Sync for SharePoint (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-sharepoint-hyperdrive)
- [Configuring Discovery scans in SharePoint (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-sharepoint-hyperdrive)

### **Microsoft 365 Activity Analysis Requirements**

Ensure Microsoft 365 Activity Analysis prerequisites are completed, including:

#### **Enable Unified Audit Logging**

Activity Analysis requires Microsoft Unified Audit Logging to capture user and admin activity events.

**Option A: Microsoft Purview Portal**

1. Sign in to [**https://purview.microsoft.com**](https://purview.microsoft.com).
2. Navigate to **Solutions → Audit**.
3. Click **Start recording user and admin activity** (if not already enabled).

**Option B: PowerShell**

Run the following commands:

```plaintext
Install-Module -Name ExchangeOnlineManagement
Connect-ExchangeOnline
Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
```

> [!NOTE]
> **Note:** It can take up to 24 hours for audit events to start appearing after enabling logging.

#### **API Permissions**

Ensure the Microsoft Entra ID application used for Microsoft 365 connectors has the following permissions configured.

**Microsoft Graph API (Application)**

- **AuditLogsQuery.Read.All** Lets you retrieve audit log data across Microsoft 365 services, including user and admin activity events. This permission is required to collect activity logs for Activity Analysis.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783486107937.png)

**Office 365 Management APIs (Application)**

- **ActivityFeed.Read** Lets you retrieve activity data from the Office 365 Management Activity API, including service-level events and operational logs. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783486107940.png)

> [!WARNING]
> Important
> 
> - After adding permissions, click **Grant admin consent for your organization**.
> - Ensure client secrets are valid and not expired.
> - Verify permissions are added under the correct APIs:
>   - **AuditLogsQuery.Read.All** → Microsoft Graph
>   - **ActivityFeed.Read** → Office 365 Management APIs

## **Configure and Run Activity Analysis**

To configure Activity Analysis for Microsoft SharePoint Online:

1. In **Securiti**, navigate to **Integrations** and open your configured **SharePoint Online** instance.
2. From the left navigation panel, click **Activity Analysis**.
3. Select the **Enable Activity Analysis** checkbox.
4. Click **Save** to apply the configuration.
5. Click **Start Sync** to initiate activity data synchronization.

> [!NOTE]
> **Note**
> 
> For Activity Analysis across all connectors, data is retained and displayed for a rolling window of the past 180 days only. Activities older than 180 days are purged from the data side as part of standard cleanup, regardless of whether the connector's source system supports retrieving older events. For SharePoint Online, Securiti retrieves user search activities (Search events) for the last 7 days only, regardless of scan type. During the initial Activity Analysis scan (180-day historical backfill), Search activities older than 7 days at the time of the scan don't appear in the activity graph. Incremental scans aren't affected, since they always run within the 7-day window. All other activity types i.e, create, modify, delete, move, share, unshare, and access, have full 180-day historical coverage.

> [!NOTE]
> Note
> 
> Before starting sync, you must make sure that relevant permissions stated earlier in pre-requisites are complete, else you can encounter errors

![Settings page for SharePoint Online with options for Activity Analysis and syncing data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(26).png)

> [!NOTE]
> **Note**
> 
> - Activity Analysis sync collects activity data such as file access, sharing actions, permission changes, user interactions, and timestamps.
> - If the sync has not been run, activity insights will not be available.
> - If a connector is configured but **Activity Analysis (AA) has not been executed yet** (either independently or via inventory), the system remains **idle and awaits the user to trigger the first scan**.
> - Once the **initial scan is launched**, the system automatically:
>   - Schedules itself to run **daily**
>   - Captures **incremental (delta) activity logs** between the previous day and the current day

## **Using Activity Analysis in Hyperdrive for Microsoft SharePoint**

Below are example use cases to help you use **Securiti’s Data Command Graph** to analyze user activity and identify risks in your Microsoft SharePoint Online environment using Activity Analysis.

When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

#### **Identify and report on SharePoint activity by activity type and actor type**

This helps you identify and analyze Microsoft SharePoint Online activity by filtering activity logs based on both activity type and actor type. It enables you to monitor how different actors (users, applications, agents, or systems) interact with SharePoint sites, documents, and files, and investigate activity patterns.

**To identify SharePoint activity by activity type and actor type:**

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 SharePoint Online**.

![Access Graph Explorer interface displaying activity logs and resource paths for Office 365.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(32).png)
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select one or more of the following:

![Access Graph Explorer displaying activity logs for Office 365 SharePoint resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(22).png)
  - access
  - chat
  - create
  - delete
  - modify
  - move
  - other
  - search
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select one or more of the following:

![Access Graph Explorer displaying activity logs for Office 365 SharePoint Online.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(33).png)
  - User
  - Application
  - Agent
  - System
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Activity log displaying access events for Office 365 SharePoint Online agents.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(34).png)

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

## **Identify and report on SharePoint delete activities performed by agents**

This helps you identify deletion activities in Microsoft SharePoint Online performed specifically by **agents** (automated or system-driven processes). It enables you to monitor automated deletions, investigate system-driven actions, and detect potential risks related to unintended or unauthorized data removal.

**To identify SharePoint delete activities performed by agents:**

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 SharePoint Online**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Agent**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **delete**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access Graph Explorer displaying activity logs for SharePoint Online agents and their actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(36).png)

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

You can customize the data grid to include additional attributes for deeper analysis:

- Display Name
- Organization
- Securiti Tags

#### **Identify and report on SharePoint create activities performed by users**

This helps you identify content creation activities performed by users in Microsoft SharePoint Online. It enables you to monitor how users create sites, documents, and files, and helps detect unusual content creation patterns or potential risks involving sensitive data.

**To identify SharePoint create activities performed by users:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 SharePoint Online**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **create**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **User**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access Graph Explorer displaying activity log for Office 365 SharePoint Online resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 13.png)

#### **Identify and report on SharePoint create activities performed by agents**

This helps you identify content creation activities performed by agents in Microsoft SharePoint Online. It provides visibility into automated or system-driven creation of files, documents, or site content, enabling you to monitor non-user activity and investigate potential automation-related risks.

**To identify SharePoint create activities performed by agents:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 SharePoint Online**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **create**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Agent**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Activity log displaying various agents and their creation timestamps in SharePoint Online.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 14.png)

#### **Identify and report on SharePoint search activities performed by applications**

This helps you identify search activities performed by applications in Microsoft SharePoint Online. It provides visibility into how applications query and discover content, enabling you to monitor automated search behavior and investigate potential data exposure risks.

**To identify SharePoint search activities performed by applications:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 SharePoint Online**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **search**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Application**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access Graph Explorer displaying activity logs for Office 365 SharePoint Online applications.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 15.png)

#### **Identify and report on SharePoint Online search activities performed by applications**

This helps you identify search activities performed by applications in Microsoft SharePoint Online. It provides visibility into how applications query and retrieve data, enabling you to monitor automated search behavior and detect potential risks related to excessive or unauthorized data discovery.

**To identify SharePoint Online search activities performed by applications:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 SharePoint Online**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **search**.
7. Click the three dots next to the **Activity Log** entity, select **Add Relationship**, and choose **M365 Application** (represents applications performing the activity).
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records along with **M365 Application** node to get associated applications with these logs.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 7(5).png)

#### **Identify and report on external activities in SharePoint Online**

This helps you identify activities performed by external actors in Microsoft SharePoint Online. It provides visibility into interactions involving external users or systems, enabling you to monitor third-party access and detect potential risks associated with external data exposure.

This use case is especially important for identifying how data is accessed or interacted with outside your organization.

**To identify external activities in SharePoint Online:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Is External**, and set it to **True**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 SharePoint Online**.
7. (Optional) Click the three dots next to the **Activity Log** entity to add additional filters such as **Activity Type** or relationships like **User Principal** or **M365 Application** for deeper analysis.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 13(2).png)

**Default columns displayed in the data grid**

By default, the data grid displays the following activity metadata:

- Display Name
- Activity ID
- Connector Type ID
- Data Asset ID
- Container ID
- Is External

> [!NOTE]
> Note
> 
> The **Is External = True** filter ensures that only activities involving external actors are displayed. You can further correlate these activities with users or applications to identify who initiated the action
