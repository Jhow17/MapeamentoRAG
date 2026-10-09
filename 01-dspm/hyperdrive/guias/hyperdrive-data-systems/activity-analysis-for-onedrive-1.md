---
title: "Hyperdrive Activity Analysis for Microsoft 365 OneDrive"
slug: "activity-analysis-for-onedrive-1"
updated: 2026-08-07T13:01:54Z
published: 2026-08-07T13:01:54Z
canonical: "helpcenter.securiti.ai/activity-analysis-for-onedrive-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Activity Analysis for Microsoft 365 OneDrive

## **Overview**

Hyperdrive Activity Analysis for Microsoft OneDrive provides visibility into how users interact with files stored in OneDrive for Business.

It analyzes activity logs such as file access, sharing actions, and modifications to help identify over-provisioned access, monitor file usage patterns, and detect risks associated with sensitive data.

## **Prerequisites**

Before configuring Activity Analysis for Microsoft OneDrive, ensure the following requirements are completed.

### **Connector Setup**

Ensure the **Microsoft OneDrive** connector is configured and synced in Hyperdrive.

For detailed setup instructions of all the required steps, see:

- [Securiti Outpost - AWS](/latest/docs/securiti-outpost)
- [Creating an Entra ID app and obtaining credentials for Microsoft 365 (Hyperdrive)](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365)
- [Connecting Microsoft 365 using Hyperdrive](/latest/docs/connect-microsoft-365-using-hyperdrive)
- [Configuring Discovery scans in OneDrive (Hyperdrive)](/latest/docs/configuring-discovery-scans)
- [Configuring Data Inventory Sync for OneDrive (Hyperdrive)](/latest/docs/configuring-data-inventory-sync)

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

**Note:** It can take up to 24 hours for audit events to start appearing after enabling logging.

#### **API Permissions**

Ensure the Microsoft Entra ID application used for Microsoft 365 connectors has the following permissions configured.

**Microsoft Graph API (Application)**

- **AuditLogsQuery.Read.All** Lets you retrieve audit log data across Microsoft 365 services, including user and admin activity events. This permission is required to collect activity logs for Activity Analysis.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783486025769.png)

**Office 365 Management APIs (Application)**

- **ActivityFeed.Read** Lets you retrieve activity data from the Office 365 Management Activity API, including service-level events and operational logs. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783486025777.png)

> [!WARNING]
> Important
> 
> - After adding permissions, click **Grant admin consent for your organization**.
> - Ensure client secrets are valid and not expired.
> - Verify permissions are added under the correct APIs:
>   - **AuditLogsQuery.Read.All** → Microsoft Graph
>   - **ActivityFeed.Read** → Office 365 Management APIs

## **Configure and Run Activity Analysis**

To configure Activity Analysis for Microsoft OneDrive:

1. In **Securiti**, navigate to **Data Systems** and open your configured **OneDrive** instance.
2. From the left navigation panel, click **Activity Analysis**.
3. Select the **Enable Activity Analysis** checkbox.
4. Click **Save** to apply the configuration.
5. Click **Start Sync** to initiate activity data synchronization.

> [!NOTE]
> Note
> 
> For Activity Analysis across all connectors, data is retained and displayed for a rolling window of the past 180 days only. Activities older than 180 days are purged from the data side as part of standard cleanup, regardless of whether the connector's source system supports retrieving older events. For OneDrive, Securiti retrieves user search activities (Search events) for the last 7 days only, regardless of scan type. During the initial Activity Analysis scan (180-day historical backfill), Search activities older than 7 days at the time of the scan don't appear in the activity graph. Incremental scans aren't affected, since they always run within the 7-day window. All other activity types i.e, create, modify, delete, move, share, unshare, and access, have full 180-day historical coverage.

> [!NOTE]
> Note
> 
> - If a connector is configured but **Activity Analysis (AA) has not been executed yet** (either independently or via inventory), the system remains **idle and awaits the user to trigger the first scan**.
> - Once the **initial scan is launched**, the system automatically:
>   - Schedules itself to run **daily**
>   - Captures **incremental (delta) activity logs** between the previous day and the current day

![Activity Analysis section showing options to enable sync and start sync process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(4).png)

**Note**

- Activity Analysis sync collects activity data such as file access, sharing actions, modifications, and timestamps.
- If the sync has not been run, activity insights will not be available.

## **Using Activity Analysis in Hyperdrive for Microsoft OneDrive**

Below are example use cases to help you use **Securiti’s Data Command Graph** to analyze user activity and identify risks in your Microsoft OneDrive environment using Activity Analysis.

When you apply filters in the **Access Graph Explorer**, all associated results update dynamically based on your selected criteria.

### **Identify and report on OneDrive activity by activity type and actor type**

This query helps you identify and analyze Microsoft OneDrive activity by filtering activity logs based on both activity type and actor type. It enables you to monitor how different actors (users, applications, agents, or systems) interact with files and investigate activity patterns.

To identify OneDrive activity by activity type and actor type:

1. In **Securiti**, open **Data Access Governance**.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 OneDrive**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select one or more of the following:

![Activity log displaying user actions in Office 365, including file sharing and access.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(30).png)
  - access
  - chat
  - create
  - delete
  - modify
  - move
  - other
  - search
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select one or more of the following:

![Access Graph Explorer displaying activity logs for Office 365 OneDrive resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(21).png)
  - User
  - Application
  - Agent
  - System
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access log details for Office 365 OneDrive activities and user interactions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(31).png)

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

#### **Identify and report on OneDrive create activities performed by agents**

This helps you identify file creation activities performed by agents in Microsoft OneDrive. It provides visibility into automated or system-driven file creation events, enabling you to monitor non-human activity and investigate potential automated data generation or ingestion patterns.

**To identify OneDrive create activities performed by agents:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 OneDrive**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **create**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Agent**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access Graph Explorer displaying activity log for Office 365 OneDrive resource creation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 9(4).png)

#### **Identify and report on OneDrive access activities performed by applications**

This helps you identify file access activities performed by applications in Microsoft OneDrive. It provides visibility into how applications interact with files, enabling you to monitor automated access patterns and investigate potential non-user-driven data access.

**To identify OneDrive access activities performed by applications:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 OneDrive**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **access**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **Application**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access log displaying various documents accessed through Office 365 OneDrive applications.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 10(1).png)

#### **Identify and report on OneDrive create activities performed by users**

This helps you identify file creation activities performed by users in Microsoft OneDrive. It enables you to monitor how users are generating new files, track content creation patterns, and investigate potential risks related to sensitive data creation or unauthorized uploads.

**To identify OneDrive create activities performed by users:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 OneDrive**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **create**.
7. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Actor Type**, and select **User**.
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records.

![Access Graph Explorer displaying user activity logs for Office 365 OneDrive resources.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 12(1).png)

#### **Identify and report on OneDrive access activities performed by applications**

This helps you identify access activities performed by applications in Microsoft OneDrive. It provides visibility into how applications interact with files and resources, enabling you to monitor automated access patterns and detect potential risks associated with non-human access.

**To identify OneDrive access activities performed by applications:**

1. In **Securiti**, open **Data Access Governance** after clicking the top left jewel icon.
2. From the left navigation menu, click **Data Command Graph**, and choose **Access Graph Explorer**.
3. Near the upper left corner of the page, click **+** to open the filter menu.
4. On the filter menu, select the **Activity Log** entity.
5. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Connector Type ID**, and select **Office 365 OneDrive**.
6. Click the three dots next to the **Activity Log** entity, select **Add Property**, choose **Activity Type**, and select **access**.
7. Click the three dots next to the **Activity Log** entity, select **Add Relationship**, and choose **M365 Application** (represents applications performing the activity).
8. Click **Apply**, and then click **Run Query**.
9. Click on the **Activity Log** node to view the filtered activity records along with associated applications.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(7).png)
