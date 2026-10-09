---
title: "Hyperdrive Activity Analysis for M365"
slug: "activity-analysis-for-microsoft365"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/activity-analysis-for-microsoft365"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive Activity Analysis for M365

Hyperdrive Activity Analysis for M365 provides visibility into how users interact with data across M365 services, including Outlook, OneDrive, SharePoint, and Microsoft Teams.

You can configure Activity Analysis centrally for all supported Microsoft 365 connectors using the **M365 integration** in Hyperdrive, which enables unified configuration for Outlook, OneDrive, SharePoint, and Microsoft Teams. Alternatively, you can configure Activity Analysis individually for each connector based on your requirements.

By leveraging Microsoft Unified Activity Logs, it enables organizations to monitor real user activity, and analyze usage patterns across email, files, and collaboration platforms.

This helps security and governance teams detect risky behavior, remove unused access, and ensure that access permissions are aligned with actual data usage. If you prefer to configure Activity Analysis separately for each Microsoft 365 connector, refer to the following articles:

- [Activity Analysis for Microsoft Outlook](/latest/docs/activity-analysis-for-outlook)
- [Activity Analysis for Microsoft OneDrive](/latest/docs/activity-analysis-for-onedrive-1)
- [Activity Analysis for Microsoft SharePoint Online](/latest/docs/activity-analysis-for-microsoft-sharepoint)
- [Activity Analysis for Microsoft Teams](/latest/docs/activity-analysis-for-microsoft-teams)

## **Supported Connectors**

Activity Analysis is supported for the following Microsoft 365 connectors:

| **Connector** | **Audit Content Type** | **Purpose** |
| --- | --- | --- |
| **Outlook** | Audit.Exchange | Captures email-related activities, including mailbox access, message operations, and administrative actions |
| **OneDrive for Business** | Audit.SharePoint | Captures file-level activities, including file access, sharing, and modifications |
| **SharePoint Online** | Audit.SharePoint | Captures site and document activities, including file access, sharing, permission changes, and collaboration events |
| **Microsoft Teams** | Audit.General, Audit.SharePoint | Captures collaboration and communication activities (Teams interactions) and file operations |

## **Prerequisites**

Before configuring Activity Analysis for any Microsoft 365 connector, ensure the following requirements are completed :

### **Connector Setup**

Ensure the **Microsoft365** connector is configured and synced in Hyperdrive.

For detailed setup instructions of all the required steps, see:

- [Securiti Outpost - AWS](/latest/docs/securiti-outpost)
- [Creating an Entra ID app and obtain credentials for Microsoft 365](/latest/docs/create-an-entra-id-app-and-obtain-credentials-for-microsoft-365)
- [Connecting Microsoft 365 using Hyperdrive](/latest/docs/connect-microsoft-365-using-hyperdrive)
- [Configure data inventory sync for Microsoft 365 applications (Hyperdrive)](/latest/docs/configure-data-inventory-sync-for-microsoft-365-applications-hyperdrive)

### **Microsoft 365 Activity Analysis Requirements**

Ensure Microsoft 365 Activity Analysis prerequisites are also completed, including:

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
```

The above stated command installs the Exchange Online PowerShell module required to manage Microsoft 365 audit settings.

```plaintext
Connect-ExchangeOnline
```

Authenticates and connects your session to Exchange Online using admin credentials.

```plaintext
Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
```

Enables Unified Audit Logging, allowing Microsoft 365 to start recording user and admin activity events.

> [!NOTE]
> **Note:** It can take up to 24 hours for audit events to start appearing after enabling logging.

#### **API Permissions**

Ensure the Microsoft Entra ID application used for Microsoft 365 connectors has the following permissions configured.

**Microsoft Graph API (Application)**

- **AuditLogsQuery.Read.All** Lets you retrieve audit log data across Microsoft 365 services, including user and admin activity events. This permission is required to collect activity logs for Activity Analysis.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783485744202.png)

**Office 365 Management APIs (Application)**

- **ActivityFeed.Read** Lets you retrieve activity data from the Office 365 Management Activity API, including service-level events and operational logs. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1783485744207.png)

> [!WARNING]
> Important
> 
> - After adding permissions, click **Grant admin consent for your organization**.
> - Ensure client secrets are valid and not expired.
> - Verify permissions are added under the correct APIs:
>   - **AuditLogsQuery.Read.All** → Microsoft Graph
>   - **ActivityFeed.Read** → Office 365 Management APIs

## **Configure and Run Activity Analysis**

To configure Activity Analysis for Microsoft 365:

1. In **Securiti**, navigate to **Integrations** and open your configured **Microsoft 365** instance.
2. From the left navigation panel, click **Activity Analysis**.
3. Select the **Enable Activity Analysis** checkbox.
4. Click **Save** to apply the configuration.
5. Click **Start Sync** to initiate activity data synchronization.

> [!NOTE]
> Note
> 
> For Activity Analysis, data is retained and displayed for a rolling window of the past 180 days only. Activities older than 180 days are purged from the data side as part of standard cleanup, regardless of whether the connector's source system supports retrieving older events.

> [!NOTE]
> Note
> 
> - If a connector is configured but **Activity Analysis (AA) has not been executed yet** (either independently or via inventory), the system remains **idle and awaits the user to trigger the first scan**.
> - Once the **initial scan is launched**, the system automatically:
>   - Schedules itself to run **daily**
>   - Captures **incremental (delta) activity logs** between the previous day and the current day

![Activity Analysis section showing sync duration and enable option for data collection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(26).png)

## **Activity Analysis for Supported M365 Connectors**

If you prefer to configure and use Activity Analysis individually for a specific Microsoft 365 connector instead of centrally for all Microsoft 365 applications, refer to the following articles:

- [Activity Analysis for Microsoft Outlook](/latest/docs/activity-analysis-for-outlook)
- [Activity Analysis for Microsoft OneDrive](/latest/docs/activity-analysis-for-onedrive-1)
- [Activity Analysis for Microsoft SharePoint Online](/latest/docs/activity-analysis-for-microsoft-sharepoint)
- [Activity Analysis for Microsoft Teams](/latest/docs/activity-analysis-for-microsoft-teams)

## **Using Activity Analysis in Hyperdrive for Microsoft 365**

Below are example use cases to help you use **Securiti’s Data Command Graph** to analyze user activity and identify risks across your Microsoft 365 environment using Activity Analysis.

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
