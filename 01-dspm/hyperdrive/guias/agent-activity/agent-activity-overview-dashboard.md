---
title: "Using Agent Activity Overview dashboard"
slug: "agent-activity-overview-dashboard"
updated: 2026-09-23T07:10:49Z
published: 2026-09-23T07:10:49Z
canonical: "helpcenter.securiti.ai/agent-activity-overview-dashboard"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Agent Activity Overview dashboard

**Scenario**

As a Data Security Officer, you must monitor how AI agents and users interact with sensitive financial data in Microsoft 365. Previously, reviewing scattered audit logs made it difficult to detect risky file deletions quickly. One morning, you spot multiple modifications and a deletion on a high-risk SharePoint site. Using the Agent Activity Overview dashboard, you filter by activity type and timeline, identify the responsible agent, and confirm a restore point exists. You trigger Undo and restore the file within minutes, reducing incident response time and minimizing data loss.

## Overview

> [!WARNING]
> Important
> 
> If Agent Activity is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

The Agent Activity Overview dashboard provides a unified view of activity collected through Hyperdrive Activity Analysis. It visualizes how users, AI agents, service accounts, and applications interact with data across connected data systems.

You can use this dashboard to:

- Monitor access and modification activity
- Investigate suspicious or unexpected behavior
- Correlate actions across agents and data systems
- Identify high-risk operations
- Trigger recovery actions where supported

To access the **Agent Activity Overview** dashboard, in Securiti, from the left navigation menu, click the **Jewel** icon and select **Agent Activity** from the menu, as shown below.

![Overview of agent activity with various data systems and restore points displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/agentactivity_nav.png)

## Using the Agent Activity Overview dashboard

The dashboard includes the following components to view how actors like AI agents, applications, and users interact with data across connected systems:

- **Top-level filter**: The dashboard includes a top-level filter that let you narrow activity by applying filters on different entities such as AI Agent, Data System, Activity Type, etc.
- **Entity panel**: The left panel aggregates counts across different entities that represent activity analysis. Selecting an entity automatically narrows the dashboard to that subset. The entities are grouped into the following categories:

For more information on the complete list of supported entities, see the [Supported entities in Agent Activity](/latest/docs/agent-activity-overview-dashboard#supported-entities-in-agent-activity-dashboard) section below.
  - Access Intelligence
  - Data
  - AI
  - Data Classification
  - Protected Data
- **Grid view**: The main grid displays structured results for all instance of a selected entity. Each row represents a single instances and includes properties as columns, such as resource name, connector type, etc. You can search within the grid to locate specific files, agents, or systems. The grid updates dynamically when filters are applied.
- **Search capability**: The dashboard supports keyword search within the grid. You can search by resource name, agent name, or other visible identifiers. Search works in combination with applied filters, letting you narrow large result sets efficiently.
- **Metrics and summary indicators**: The dashboard includes metrics at the top of grid, such as counts of entities and activity logs within the selected scope. These summary indicators help you understand scale before reviewing detailed records.

![Overview of agent activity with filters, data systems, and activity logs displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/agentactivity_landingpage.png)

## Understanding Activity Logs in dashboard

The **Activity Log** entity captures and displays every recorded action performed by users, AI agents, and applications on data assets across connected systems. To view the activity logs for your AI Agent and data system:

1. From the left **Entities** panel, select **Activity Log.**

![Overview of agent activity with filter options and timeline for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/activitylog_entity.png)
2. The activity log data opens in timeline view by default for all AI Agents and data systems.
3. From the top-level filter, click **+** to add filters according to your scope, such as **Activity Type = Access** to display only access logs.

The **Activity Log** results include two primary views:

- **Timeline**, which presents activity logs in a chronological, visual format. Activity logs open in Timeline view by default. A dedicated Timeline page is also available for cross-agent analysis. For more information, see [Using Agent Activity Timeline](/latest/docs/using-agent-activity-timeline).
- **Audit Log**, which provides a structured, tabular representation of activity log entries. Each row corresponds to a single event and includes detailed attributes that support precise investigation and reporting.

### Using Audit Logs view for activity analysis

The **Audit Log** view in the Agent Activity Overview dashboard provides a structured, tabular record of all captured activities. Each row in the Audit Log represents a single activity event captured from the connected data system. These events may include:

- Access
- Modify
- Share
- Delete

![Overview of agent activity with highlighted activity log count and timestamp filter options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/activitylog_auditlogs.png)

The Audit Log view includes the following key components:

- A search bar to search results by display name
- A summary metric at the top of the grid that displays the total **Activity Log Count**
- A structured table view to represent all activity logs with each column representing a key property.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.

Some key columns in the Audit Logs table are listed in the table below:

| Column | Description |
| --- | --- |
| Resource Name | Displays the unique identifier or display name of the resource involved in the activity, such as a file, object, or asset. For example, `1234acme-1234-abcd-0000-1234acme000` You can use this value to identify which specific resource was accessed, modified, shared, searched, or deleted. |
| Activity Type | Displays the type of action performed on the resource. Common activity types include Access, Modify, Share, Delete, and Search. |
| Actor Type | Displays the category of the entity that performed the action, such as User, AI Agent, or Application. You can use this to distinguish between human activity and automated or AI-driven actions. |
| Connector Type ID | Displays the data system where the activity occurred, such as Office 365 OneDrive, SharePoint Online, Outlook, or Microsoft Teams. |
| Activity Timestamp | Shows the exact date and time when the activity took place, such as `Nov 21 2025, 11:34 pm` |
| Is External | Indicates whether the activity originated from an external entity outside the organization. A tick confirms external involvement and a cross means activity is not external. |
| Source Resource Path | Displays the original location or path of the resource involved in the activity. You can use this for actions such as sharing, moving, or copying. |
| Target Resource Path | Displays the destination path of the resource for actions that involve movement, copying, or sharing. |
| Resource ID | Displays the unique identifier for the resource associated with the activity. |
| Activity ID | Displays the unique identifier for the specific activity event. |
| Data Asset ID | Displays the corresponding data asset ID in Securiti’s unified data inventory. |
| Resource Path | Displays the hierarchical path of the resource within the data system. |
| Container ID | Displays the unique identifier of the container that holds the resource, such as a OneDrive instance, SharePoint site, or folder structure. |
| Actor ID | Displays the unique identifier of the actor, i.e, user, AI agent, or application, that performed the activity. |
| Resource URL | Displays a direct or system-generated link reference to the resource involved in the activity. |

To view activity logs in the Audit Log view:

1. From the left entities menu, select the **Activity Log** entity.
2. The activity logs open in timeline view by default. From the upper right corner of the view, select **Audit Log.**

![Overview of agent activity log with detailed search results and filters applied.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/auditlogbutton.png)
3. To narrow down the results, you can apply filters directly from the grid by using increment and decrement operators for a row, as shown below.

![Overview of agent activity log with filter options and activity details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfiltersfromgrid_option.png)
4. From the top of the grid, click **Apply Filters**.

![Overview of agent activity with filter options and asset details displayed on the screen.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/applyfilter_fromgrid.png)
5. You can also use the top-level filter to narrow down the scope.

![Overview of agent activity log with filters for Office 365 SharePoint Online.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/filtersapplied.png)
6. Click on an entity from the left entities panel to view the associated entities, such as AI Agent that performed the action.

![Overview of agent activity with filters for asset types and timestamps displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/appliedfiltersfor_agent.png)

## Saving Agent Activity filters

To reuse a specific filter combination:

1. From the top right corner, click **Save View.**
2. From the **Save View** popup, enter the following details, as shown below.

![Overview of agent activity log with filters for SharePoint and activity details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/agentact_saveview.png)
  1. Group
  2. Name
  3. (Optional) Description
3. From the bottom of the popup, click **Save View** to save the filter configuration.
4. To reuse the saved filter combination later, click **Saved Views** and select the view you saved, as shown below.

![Interface showing saved views and activity logs for SharePoint Online management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/agentact_savedviews.png)

## Supported entities in Agent Activity dashboard

Use the table below to understand the entities included in this dashboard for analyzing agent activity results:

****Entities and their properties in Agent Activity Overview****

| Category | Entities | Description | Supported properties |
| --- | --- | --- | --- |
| Access Intelligence | User Principal | Represents an individual user identity that performs actions on data assets. You use this entity to investigate which specific user accessed, modified, shared, or deleted a resource. | - Asset Type - Data Asset IDs - Datasource IDs - Display Name - Email - External - Organization - Provider Account ID - Provider Type - Securiti Tags - User ID - User Type - Username |
| User Group Principal | Represents a group-based identity that has permissions on data assets. This entity helps you understand access inherited through group membership and investigate group-level activity. | - Asset Type - Data Asset IDs - Datasource IDs - Description - Display Name - Email - Group Name - Group Type - Group Unique ID - Is External - Organization - Provider Account ID - Provider Type - Securiti Tags |
| M365 Application | Represents application(s) registered in Microsoft 365 that interacts with data. You use this entity to monitor automation, integrations, or service-based access to resources. | - Application Name - Is External - Organization - Other IDs - Provider Account ID - Provider Type - Securiti Tags - Service Account Name - Unique ID |
| Activity Log | Represents a recorded event performed by an actor on a resource. Each activity log captures the action type, timestamp, actor type, connector source, and related asset. | - Activity ID - Activity Timestamp - Activity Type - Actor ID - Actor Type - Connector Type ID - Container ID - Data Asset ID - Data System Graph Node ID - Display Name - Is External - Organization - Resource ID - Resource Name - Resource Path - Source Resource Path - Target Resource Path - Tenant Merged Inventory Reference Column - Tenant Merged Inventory Reference Value |
| Data | Data System | Represents a connected platform such as SharePoint Online, OneDrive, Teams, or other supported systems. This entity lets you scope activity to a specific system. | - Access Methods - Account - Asset Data Type - Asset Exist - Asset ID - Asset Name - Asset Type - Backup Status - Cloud Resource ID - Connected Via - Country - Data Format - Data Map Ownership - Data Objects - Data Size - Data System Instance Exists - Data System State - Data Volume - Description - DPO Email - DPO Name - Encrypted - Encrypted In Motion - External Contact Email - External Contact Name - First Seen At - Host Type - Hosting - Hosting Provider - IaaS Instance ID - Is Connectable - Is Hyperscale - Last Seen At - Managing Organization - Organization - Owning Department - Purpose - Region - Resource Type - Risk - Securiti Tags - Service - State - Tags - Volume of Data Records - Volume of PD Attributes - Weblink |
| Files | Represents individual files within connected data systems. You use this entity to investigate file-level activity such as access, modification, sharing, or deletion. | - Account Name - Action - Broadly Shared - Checksum - Cluster Name - Container Name - Data Source - Data Source Execution IDs - Data System Type - Data System URN - Discovery Scan IDs - Discovery Scan Job IDs - Document Type - Error Reason - Errored - Evidence File Path - File Created time - File Format - File Modified time - File Name - File Owner - File Record Creation Time - File Record Updated Time - File Size - File Scan Time - Graph Node ID - Groups - Is Quarantined - Is Reverted - Last Access Time - Last Scan Time - Mime Type - O365 ID - Object Type - Pipeline ID - Public - Quarantine Data System ID - Quarantine Destination ID - Quarantine Path - Quarantine Policy Status - Quarantined At - Quarantined/Reverted by Policy ID - Resource Path - Reverted At - Sensitivity Label Name - Skip Reason - Skipped - Super Groups - Top Level Directory - Version Of |
| Site | Represents a SharePoint site within a data system. This entity helps you analyze activity at a site level rather than at an individual file level. | - Account ID - Asset ID - Description - Graph Data System Type - Organization - Securiti Tags - Sensitivity Labels - Sharing Capabilities - Sharing Enabled - Site Name - Site Owner - Site Type - Web ID - Web Link - Web URL |
| AI | AI Agent | Represents an autonomous or configured AI agent that interacts with connected data systems. You use this entity to monitor agent behavior, validate scope of operation, and investigate automated actions. | - Account - Agent Resource Role ID - Analytics Disabled - Asset Name - Asset Type - Cloud Resource ID - CMK Encryption - Company Name - File IDs - First Seen At - Foundation Model - Guardrail Identifier - Hosting - Idle Session Timeout (seconds) - Industry Verticle - Is External - Last Seen At - Organization - Other IDs - Provider Account ID - Provider Type - Region - Resource Creation Time - Resource ID - Resource Type - Resource Updating Time - Search Tier - Securiti Tags - Service - Service Account Name - Solution Type - State - Tags - Tools Enabled - Unique ID - Weblink |
| Data Classification | Data Element | Represents a classified data attribute detected within content, such as personal data or regulated information. This entity helps you correlate activity with sensitive data exposure. | - Category - Data Element Name - Description - Enabled - Non-Personal Sensitive Data - Organization - Personal Data - Securiti Tags - Special Category - System - System Category - System Name |
| Content Profile | Represents a classification profile assigned to content based on detected data elements. You use this entity to assess whether activity involves regulated or high-risk content. | - Category - Content Profile Name - Data Type - Description - Enabled - Organization - Securiti Tags - System - System Name |
| File Format | Represents the file type or extension associated with a resource. This entity helps you analyze activity by document type, such as spreadsheets, documents, or PDFs. | - Description - Enabled - Extensions - File Format Name - Organization - Securiti Tags - System Name |
| Protected Data | Protected M365 Site | Represents a SharePoint site protected through Veeam Data Cloud. You use this entity to correlate activity with backup coverage at the site level. | - Backup Resource ID - Backup Resource Name - Display Name - Organization - Resource MSID - Securiti Tags - Site ID - Site URL |
| Protected OneDrive | Represents a OneDrive account protected through Veeam Data Cloud. This entity helps you assess whether user drive data has backup coverage before or after activity events. | - Backup Resource ID - Backup Resource Name - Display Name - Organization - Resource MSID - Securiti Tags - User ID - Drive URL |
| Protected Outlook Mailbox | Represents a mailbox protected through Veeam Data Cloud. You use this entity to review protection status when investigating mailbox-related activity. | - Backup Resource ID - Backup Resource Name - Display Name - Email - Is Archive - Is Group Mail - Organization - Resource MSID - Securiti Tags - Group ID |
| Protected M365 Teams | Represents a Microsoft Teams environment protected through Veeam Data Cloud. This entity helps you evaluate backup alignment when reviewing team-level activity. | - Alias - Backup Resource ID - Backup Resource Name - Display Name - Group Email - Is Archived - Organization - Privacy - Securiti Tags - Settings |
| Restore Point | Represents a specific backup snapshot available for a protected resource. You use this entity to determine whether a resource can be reverted to a previous state following a destructive action. | - Backup Time - Display Name - Is Copy - Is Deleted - Is Exchange - Is Long Term Copy - Is OneDrive - Is SharePoint - Is Teams - Is Retrieved - Job ID - Organization - Organization ID - Repository ID - Restore Point ID - Retrieval ID - Securiti Tags - Workload Tenant ID |
