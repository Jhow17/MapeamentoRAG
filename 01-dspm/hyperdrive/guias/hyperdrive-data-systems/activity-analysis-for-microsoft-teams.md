---
title: "Hyperdrive Activity Analysis for Microsoft Teams"
slug: "activity-analysis-for-microsoft-teams"
updated: 2026-07-17T07:29:42Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/activity-analysis-for-microsoft-teams"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Activity Analysis for Microsoft Teams

## **Overview**

Hyperdrive Activity Analysis for Microsoft Teams provides visibility into user interactions across collaboration and communication workflows within Teams.

It analyzes activity logs such as chat interactions, meetings, and file operations to help identify over-provisioned access, monitor collaboration patterns, and detect risks associated with shared data.

Microsoft Teams activity is derived from both communication events and file activities, combining insights from Teams interactions and underlying SharePoint and OneDrive storage.

## **Prerequisites**

Before configuring Activity Analysis for Microsoft Teams, ensure the following requirements are completed.

### **Connector Setup**

Ensure the **Microsoft Teams** connector is configured and synced in Hyperdrive.

For detailed setup instructions of all the required steps, see:

- [Securiti Outpost - AWS](/latest/docs/securiti-outpost)
- [Creating an Entra ID app and obtaining credentials for Microsoft 365 (Hyperdrive)](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365)
- [Connecting Microsoft 365 using Hyperdrive](/latest/docs/connect-microsoft-365-using-hyperdrive)
- [Configuring Discovery scans in Teams (Hyperdrive)](/latest/docs/configuring-discovery-scans-in-sharepoint-hyperdrive-1-1)
- [Configuring Data Inventory Sync for Teams (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-sharepoint-hyperdrive-1-1)

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

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783486170192.png)

**Office 365 Management APIs (Application)**

- **ActivityFeed.Read** Lets you retrieve activity data from the Office 365 Management Activity API, including service-level events and operational logs. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783486170195.png)

> [!WARNING]
> Important
> 
> - After adding permissions, click **Grant admin consent for your organization**.
> - Ensure client secrets are valid and not expired.
> - Verify permissions are added under the correct APIs:
>   - **AuditLogsQuery.Read.All** → Microsoft Graph
>   - **ActivityFeed.Read** → Office 365 Management APIs

## **Configure and Run Activity Analysis**

To configure Activity Analysis for Microsoft Teams:

1. In **Securiti**, navigate to **Integrations** and open your configured **Microsoft Teams** instance.
2. From the left navigation panel, click **Activity Analysis**.
3. Select the **Enable Activity Analysis** checkbox.
4. Click **Save** to apply the configuration.
5. Click **Start Sync** to initiate activity data synchronization.

> [!NOTE]
> Note
> 
> For Activity Analysis across all connectors, data is retained and displayed for a rolling window of the past 180 days only. Activities older than 180 days are purged from the data side as part of standard cleanup, regardless of whether the connector's source system supports retrieving older events.

> [!NOTE]
> Note
> 
> - If a connector is configured but **Activity Analysis (AA) has not been executed yet** (either independently or via inventory), the system remains **idle and awaits the user to trigger the first scan**.
> - Once the **initial scan is launched**, the system automatically:
>   - Schedules itself to run **daily**
>   - Captures **incremental (delta) activity logs** between the previous day and the current day

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(27).png)

> [!NOTE]
> **Note**
> 
> - Activity Analysis sync collects activity data such as Teams interactions (chat, meetings, and collaboration events) and file operations (access, sharing, and modifications).
> - Activity data is derived from multiple audit streams, including communication and file-based events.
> - If the sync has not been run, activity insights will not be available.

## **Using Activity Analysis in Hyperdrive for Microsoft Teams**

Below are example use cases to help you use **Securiti’s Data Command Graph** to analyze user activity and identify risks in your Microsoft Teams environment using Activity Analysis.

When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

### **Identify and report on Microsoft Teams activity by activity type and actor type**

By filtering activity logs based on activity type and actor type, you can gain visibility into how different actors (users, applications, agents, or systems) interact across Teams communication and file collaboration workflows.

**To identify Microsoft Teams activity by activity type and actor type:**

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Microsoft Teams**.

![Access Graph Explorer displaying activity logs for Office 365 services and resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(23).png)
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select one or more of the following:

![Data Access Governance interface displaying activity logs and filter options for Microsoft Teams.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(18).png)
  - access
  - chat
  - create
  - delete
  - modify
  - move
  - other
  - search
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select one or more of the following:

![Data Access Governance interface displaying activity logs and filter options for Microsoft Teams.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(35).png)
  - User
  - Application
  - Agent
  - System
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access Graph Explorer displaying activity logs for Microsoft Teams applications and user actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(24).png)

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

#### **Identify and report on Microsoft Teams access activities performed by applications**

This helps you identify access activities performed by applications in Microsoft Teams. It provides visibility into how applications interact with Teams data and collaboration workflows, enabling you to monitor automated access patterns and investigate potential risks from non-user-driven interactions.

**To identify Microsoft Teams access activities performed by applications:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Microsoft Teams**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **access**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Application**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access Graph Explorer displaying Microsoft Teams activity log with various timestamps and resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 16.png)

#### **Identify and report on Microsoft Teams create activities performed by users**

This helps you identify create activities performed by users in Microsoft Teams. It provides visibility into how users initiate collaboration events such as creating content, interactions, or related resources, helping you monitor user-driven activity and detect unusual behavior patterns.

**To identify Microsoft Teams create activities performed by users:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Microsoft Teams**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **create**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **User**.
8. Click **Apply**, and then click **Run Query**.

![Access Graph Explorer displaying activity logs for Microsoft Teams and other resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 17.png)
