---
title: "Viewing Hyperdrive scan results for M365 OneDrive"
slug: "viewing-hyperdrive-scan-results-for-onedrive"
updated: 2026-07-20T20:24:34Z
published: 2026-07-20T20:24:34Z
canonical: "helpcenter.securiti.ai/viewing-hyperdrive-scan-results-for-onedrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Viewing Hyperdrive scan results for M365 OneDrive

After you run scans on your OneDrive Hyperdrive connector, Securiti populates inventory, identity, access, and activity data across multiple pages. Depending on the scan you run, you can:

- Review discovered files
- Investigate access relationships
- Analyze user and AI agent activity
- Monitor scan metrics

This article explains where Microsoft 365 OneDrive data appears, what each scan populates, and how to use each page to investigate your OneDrive environment.

## Prerequisite

Before you can view scan results, the required scans must complete successfully. For information about scan order and dependencies, see the following resources:

- [Configuring Data Inventory Sync for Microsoft 365 OneDrive](/latest/docs/configuring-data-inventory-sync)
- [Configuring Activity Analysis for Microsoft 365 OneDrive](/latest/docs/activity-analysis-for-onedrive-1)
- [Hyperdrive data scans](/latest/docs/viewing-hyperdrive-data-in-securiti#hyperdrive-data-scans)

## Viewing Data Inventory Sync results

**Data Inventory Sync** discovers OneDrive files and their metadata. After the scan completes, the **Files** entity is populated in the Graph Explorer and Inventory pages in Securiti.

Use the table below to understand where to view the inventory data:

| Page | What you can do |
| --- | --- |
| Inventory > **Files** entity | Browse and filter all discovered OneDrive files and their metadata. |
| Graph Explorer > **Files** entity | Query files and build relationships with users, activities, and OneDrive resources. |
| Microsoft 365 Data and AI Security dashboard (Hyperdrive) | Review aggregated Microsoft 365 inventory metrics. |
| Connector **Statistics** page | Review scan performance and inventory metrics, such as Files Cataloged. |

The sections below describe in detail how you can view data in each page.

### Viewing inventory metrics in Statistics page

From the left menu for your Microsoft 365 OneDrive data system connector, click **Statistics** to view the metrics populated for Data Inventory Sync results and progress. You can use this page when you want to monitor the progress of your Hyperdrive inventory scans in near real time, such as checking metrics for scan duration, files/hour cataloged or large file counts without waiting for the scan to complete.

![Statistics overview for OneDrive OnPrem inventory, including files cataloged and data size.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrive_statistics.png)

For more information, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive#viewing-data-inventory-sync-statistics).

### Viewing Files in Inventory

In Inventory, from the left entities panel, select **Files** to view all discovered files in your tenant. To view only OneDrive files, filter the **Files** entity by setting the **Data System Type** property to **Office 365 OneDrive**, as shown below.

![Inventory interface displaying files stored in Office 365 OneDrive with file details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrivefiles_inventory.png)

You can use this page to find a specific OneDrive file and review its metadata and ownership.

### Viewing inventory results in Graph Explorer

In Graph Explorer, from the top-level filter, select **Files** to view all discovered files in your tenant. To view only OneDrive files, add **Files** as your entity and set the **Data System Type** property filter to **Office 365 OneDrive**, as shown below.

![Graph Explorer interface displaying files with properties related to Office 365 OneDrive.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrivefiles_graph.png)

You can use Graph Explorer to run targeted queries on OneDrive files. For example, to find files of a specific format, review file metadata, or explore which users have access to a specific file using the **Relationship** view.

### Analyzing inventory data in Microsoft 365 Data and AI Security dashboard

In the **Microsoft 365 Data and AI Security** dashboard (Hyperdrive), the **Files** widget displays aggregate counts of files and user identities discovered across all connected Microsoft 365 data systems, including Microsoft OneDrive.

To access the dashboard, from the left navigation menu, click the **Jewel icon** and select **Agent Activity > Dashboard**. You can also access it from **Dashboard > System > Microsoft 365 Data and AI Security**.

You can use this dashboard to get a high-level view of how many files are available in your Microsoft 365 environment and how many users and groups have been identified, without needing to run a query. For a full description of all available widgets, see [Using Microsoft 365 Data and AI Security dashboard (Hyperdrive)](/latest/docs/agent-commander-dashboard).

### Use cases for Data Inventory Sync

Use the following table to understand the potential use cases for Data Inventory Syncs for Hyperdrive data systems:

| Use case | Description |
| --- | --- |
| Finding a specific OneDrive file | - Use Inventory to search the **Files** entity and filter **Data System Type = Office 365 OneDrive**. - If you need additional context, open Graph Explorer, select the **Files** entity, apply the same filter, and query properties such as **File Name**, **Resource Path**, or **File Format** to locate the file. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Files** widget shows the aggregate file count and total file size across all connected M365 data systems, including OneDrive. |
| Analyze file types in your OneDrive environment | - Use Inventory to review file metadata or Graph Explorer to query the **Files** entity and group or filter by the **File Format** property. This helps identify the types of content stored across OneDrive resources. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive) to understand the overall distribution of OneDrive content. |
| Identifying large or stale OneDrive files | - Open the **Statistics** page for your Microsoft 365 OneDrive connector to review metrics such as **Total Number of Large Files** and **Oldest Modified File Date**. Use these metrics together with the inventory results to identify files that may require archival, cleanup, or further review. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Files** widget shows the aggregate file count and total file size across all connected M365 data systems, including OneDrive. |

## Viewing Hyperdrive Access Intelligence results

After **Entitlement scan** and **Activity Analysis** complete, Securiti populates identity and access data for your Microsoft OneDrive environment. The scan discovers users, groups, AI agents and applications, along with their access relationships to OneDrive files.

You can use this data to understand some of the following use cases:

- Who has access to OneDrive content
- Identify excessive permissions
- Review AI agent and application access
- Investigate relationships between identities and files

| Page | Data populated | What you can do |
| --- | --- | --- |
| Inventory | Following graph entities are populated as a result of Entitlement scan and Activity Analysis: - User Principal - User Group Principal - AI Agent - Microsoft 365 Application - Files - Activity Log - Actor Type (Agent, Application, System, User) | Browse users, groups, AI agents, applications, and OneDrive resources. |
| Graph Explorer | Investigate relationships between identities and OneDrive resources. |
| Access Graph Explorer in DAG |
| Microsoft 365 Data and AI Security dashboard (Hyperdrive) | Access and posture related widgets for AI Agents and applications. | Review AI access, applications, and exposure across Microsoft 365. |
| Connector **Statistics** page | Widgets for the total Users, groups, and AI Agents Cataloged during entitlement scans. | Review scan performance and entitlement metrics, such as Users Cataloged. |

The sections below describe in detail how you can view data in each page.

### Viewing Statistics page for entitlements

From the left menu for your Microsoft 365 OneDrive data system connector, click **Statistics** to view the metrics populated for Entitlement scan results and progress. You can use this page when you want to monitor the progress of your Hyperdrive entitlement scans in near real time, such as checking metrics for scan duration, users and groups cataloged without waiting for the scan to complete.

![Statistics overview for OneDrive OnPrem inventory, including files cataloged and data size.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrive_statistics.png)

For more information, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive#viewing-entitlement-sync-statistics).

### Viewing entitlements and activities in Inventory

In Inventory, from the left entities panel you can select the following entities to view Hyperdrive Access Intelligence data:

- Select an entity such as **User Principal**, **User Group Principal**, **AI Agent**, or **M365 Application** to view the objects and permissions discovered during the entitlement scan.
- Select the **Activity Log** entity to view recorded activities.

You can use this page to review identities, AI agents, applications, and OneDrive resources before investigating their relationships in Graph Explorer. Moreover, you can search and filter activity records by resource, timestamp, actor, and activity details.

### Viewing access intelligence data in Graph Explorer

In Graph Explorer, from the top-level filter, you can select the following entities to view Hyperdrive Access Intelligence data:

- Select an entity such as **User Principal**, **AI Agent**, or **M365 Application** from the left entities panel to explore its relationships with files and other entities. You can build queries to answer questions like, “Which OneDrive files are readable by users?”
- Select **Activity Log** and filter by properties, such as **Connector Type**, **Activity Type**, and **Actor Type** to investigate specific activities. You can use this entity to trace activities back to the affected resources and identify whether the action was performed by a **User**, **Application**, **AI Agent**, or **System**.

You can also use Data Access Governance’s **Access Graph Explorer** to explore these entities. For more information, see [Hyperdrive Activity Analysis for Microsoft 365 OneDrive](/latest/docs/activity-analysis-for-onedrive-1) and [Hyperdrive Entitlement scan for Microsoft 365 OneDrive.](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-onedrive)

![Overview of files in Office 365 OneDrive with various document types listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 6(9).png)

### Analyzing access intelligence data in Microsoft 365 Data and AI Security dashboard

In the **Microsoft 365 Data and AI Security** dashboard (Hyperdrive), the following widgets display data for Hyperdrive Access Intelligence:

- AI Agents and Applications
- Users and Groups
- Agents Accessible Data Volume
- Active AI Agents
- Agents Modifying Data
- Broadly Shared Files
- Agent Accessible Data Elements by Category
- Agent Accessible ROT Data

You can use this dashboard to get a high-level view of how many users, user groups, and AI Agents are available in your Microsoft 365 environment and their access to resources. For a full description of all available widgets, see [Using Microsoft 365 Data and AI Security dashboard (Hyperdrive)](/latest/docs/agent-commander-dashboard).

![Dashboard displaying Microsoft 365 data security metrics and agent accessible data volume.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrivedata_dashboard.png)

### Viewing activity logs in Agent Activity Overview dashboard

In the **Agent Activity > Overview** dashboard, select the **Activity Log** entity and apply **Connector Type ID = Office 365 OneDrive** to scope results.

You can use the **Timeline** view to understand the sequence of events and the **Audit Log** view to filter, export, and investigate recorded activities, as shown below.

![Overview of Agent Activity with highlighted Activity Log and Office 365 OneDrive details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/onedrive_activitylog.png)

For more information, see [Using Agent Activity Overview dashboard](/latest/docs/agent-activity-overview-dashboard).

### Use cases for Hyperdrive Access Intelligence

Use the following table to understand the potential use cases for Hyperdrive Access Intelligence for your data systems:

| Use case | Description |
| --- | --- |
| Review AI agent access to OneDrive files | - In Graph Explorer, select the **AI Agent** entity and add a **Has access → Files** relationship to identify the OneDrive files accessible to each AI agent. - Use Inventory to review the AI agent's properties. - Analyze **AI Agents and Applications** and **Agents Accessible Data Volume** widgets in the Microsoft 365 Data and AI Security dashboard (Hyperdrive) to assess AI exposure. |
| Find externally shared OneDrive workspaces | - In Graph Explorer, select the **M365 Application** entity and filter **Is External = True**. Add a relationship to **Files** to review content accessible through externally shared workspaces. - Use Inventory to review workspace properties and identify the associated OneDrive instances. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Agents Accessible Data Volume** widget shows the proportion of data accessible to agents across M365 services, including OneDrive. |
| Investigate file modifications | - In Graph Explorer or Inventory, select the **Activity Log** entity and filter **Activity Type = Modify** and **Connector Type ID = Office 365 OneDrive** to identify modified OneDrive resources. - Use the **Agent Activity Overview** dashboard to identify similar modification events over time. |
