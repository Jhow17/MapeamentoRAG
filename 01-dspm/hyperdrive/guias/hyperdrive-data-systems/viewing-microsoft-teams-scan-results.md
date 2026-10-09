---
title: "Viewing Hyperdrive scan results for M365 Teams"
slug: "viewing-microsoft-teams-scan-results"
updated: 2026-07-20T20:27:29Z
published: 2026-07-20T20:27:29Z
canonical: "helpcenter.securiti.ai/viewing-microsoft-teams-scan-results"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Viewing Hyperdrive scan results for M365 Teams

After you run scans on your Microsoft Teams Hyperdrive connector, Securiti populates inventory, identity, access, and activity data across multiple pages. Depending on the scan you run, you can review discovered files, investigate access relationships, analyze user and AI agent activity, and monitor scan metrics.

This article explains where Microsoft Teams data appears, what each scan populates, and how to use each page to investigate your Teams environment.

## Prerequisite

Before you can view scan results, the required scans must complete successfully. For information about scan order and dependencies, see the following resources:

- [Configuring Data Inventory Sync for Microsoft Teams](/latest/docs/configuring-data-inventory-sync-for-teams-hyperdrive)
- [Hyperdrive Entitlement scan for Microsoft Teams](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-teams)
- [Configuring Activity Analysis for Microsoft Teams](/latest/docs/configure-activity-analysis-for-microsoft-teams-hyperdrive)
- [Hyperdrive data scans](/latest/docs/viewing-hyperdrive-data-in-securiti#hyperdrive-data-scans)

## Viewing Data Inventory Sync results

**Data Inventory Sync** discovers Microsoft Teams files and their metadata. After the scan completes, the **Files** entity is populated in the Graph Explorer and Inventory pages in Securiti.

Use the table below to understand where to view the inventory data:

| Page | What you can do |
| --- | --- |
| Inventory > **Files** entity | Browse and filter all discovered Teams files and their metadata. |
| Graph Explorer > **Files** entity | Query files and build relationships with users, activities, and Teams workspaces. |
| Microsoft 365 Data and AI Security dashboard (Hyperdrive) | Review aggregated Microsoft 365 inventory metrics. |
| Connector **Statistics** page | Review scan performance and inventory metrics, such as Files Cataloged. |

The sections below describe in detail how you can view data in each page.

### Viewing inventory metrics in Statistics page

From the left menu for your Microsoft 365 Teams data system connector, click **Statistics** to view the metrics populated for Data Inventory Sync results and progress. You can use this page when you want to monitor the progress of your Hyperdrive inventory scans in near real time, such as checking metrics for scan duration, files/hour cataloged or large file counts without waiting for the scan to complete.

![Statistics overview for Microsoft Teams Onprem, including file cataloging and scanning details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/teams_statistics.png)

For more information, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive#viewing-data-inventory-sync-statistics).

### Viewing Files in Inventory

In Inventory, from the left entities panel, select **Files** to view all discovered files in your tenant. To view only Microsoft Teams files, filter the **Files** entity by setting the **Data System Type** property to **Microsoft 365 Teams**, as shown below.

![Inventory interface displaying Microsoft Teams data system type and file details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/teamsfiles_inventory.png)

You can use this page to find a specific Teams document and review its metadata and ownership.

### Viewing inventory results in Graph Explorer

In Graph Explorer, from the top-level filter, select **Files** to view all discovered files in your tenant. To view only Microsoft Teams files, add **Files** as your entity and set the **Data System Type** property filter to **Microsoft Teams**, as shown below.

![Graph Explorer interface displaying Microsoft Teams data files and their properties.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/teamsfiles_graph.png)

You can use Graph Explorer to run targeted queries on Teams files. For example, to find files of a specific format, review file metadata, or explore which users have access to a specific file using the **Relationship** view.

### Analyzing inventory data in Microsoft 365 Data and AI Security dashboard

In the **Microsoft 365 Data and AI Security** dashboard (Hyperdrive), the **Files** widget displays aggregate counts of files and user identities discovered across all connected Microsoft 365 data systems, including Microsoft Teams.

To access the dashboard, from the left navigation menu, click the **Jewel icon** and select **Agent Activity > Dashboard**. You can also access it from **Dashboard > System > Microsoft 365 Data and AI Security**.

You can use this dashboard to get a high-level view of how many files are available in your Microsoft 365 environment and how many users and groups have been identified, without needing to run a query. For a full description of all available widgets, see [Using Microsoft 365 Data and AI Security dashboard (Hyperdrive)](/latest/docs/agent-commander-dashboard).

### Use cases for Data Inventory Sync

Use the following table to understand the potential use cases for Data Inventory Syncs for Hyperdrive data systems:

| Use case | Description |
| --- | --- |
| Finding a specific Teams file | - Use Inventory to search the **Files** entity and filter **Data System Type = Microsoft Teams**. - If you need additional context, open Graph Explorer, select the **Files** entity, apply the same filter, and query properties such as **File Name**, **Resource Path**, or **File Format** to locate the file. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Files** widget shows the aggregate file count and total file size across all connected M365 data systems, including Teams. |
| Analyze file types in your Teams environment | - Use Inventory to review file metadata or Graph Explorer to query the **Files** entity and group or filter by the **File Format** property. This helps identify the types of content stored across Teams channels. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive) to understand the overall distribution of Teams content. |
| Identifying large or stale Teams files | - Open the **Statistics** page for your Microsoft Teams connector to review metrics such as **Total Number of Large Files** and **Oldest Modified File Date**. Use these metrics together with the inventory results to identify files that may require archival, cleanup, or further review. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Files** widget shows the aggregate file count and total file size across all connected M365 data systems, including Teams. |

## Viewing Hyperdrive Access Intelligence results

After **Entitlement scan** and **Activity Analysis** complete, Securiti populates identity and access data for your Microsoft Teams environment. The scan discovers users, groups, AI agents, applications, and Microsoft Teams workspaces, along with their access relationships to Teams files.

You can use this data to understand some of the following use cases:

- Who has access to Microsoft Teams content
- Identify excessive permissions
- Review AI agent and application access
- Investigate relationships between identities and files

| Page | Data populated | What you can do |
| --- | --- | --- |
| Inventory | Following graph entities are populated as a result of Entitlement scan and Activity Analysis: - User Principal - User Group Principal - AI Agent - Microsoft 365 Application - Microsoft Team - Activity Log - Actor Type (Agent, Application, System, User) | Browse users, groups, AI agents, applications, and Teams workspaces. |
| Graph Explorer | Investigate relationships between identities, Teams workspaces, files, and applications. |
| Access Graph Explorer in DAG |
| Microsoft 365 Data and AI Security dashboard (Hyperdrive) | Access and posture related widgets for AI Agents and applications. | Review AI access, applications, and exposure across Microsoft 365. |
| Connector **Statistics** page | Widgets for the total Users, groups, and AI Agents Cataloged during entitlement scans. | Review scan performance and entitlement metrics, such as Users Cataloged. |

The sections below describe in detail how you can view data in each page.

### Viewing Statistics page for entitlements

From the left menu for your Microsoft 365 Teams data system connector, click **Statistics** to view the metrics populated for Entitlement scan results and progress. You can use this page when you want to monitor the progress of your Hyperdrive entitlement scans in near real time, such as checking metrics for scan duration, users and groups cataloged without waiting for the scan to complete.

![Statistics overview for Microsoft Teams Onprem, including file cataloging and scanning details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/teams_statistics.png)

For more information, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive#viewing-entitlement-sync-statistics).

### Viewing entitlements and activities in Inventory

In Inventory, from the left entities panel you can select the following entities to view Hyperdrive Access Intelligence data:

- Select an entity such as **User Principal**, **User Group Principal**, **AI Agent**, **Microsoft 365 Application**, or **M365 Team** to view the objects discovered during the entitlement scan.
- Select the **Activity Log** entity to view recorded activities.

You can use this page to review identities, AI agents, applications, and Teams workspaces before investigating their relationships in Graph Explorer. Moreover, you can search and filter activity records by resource, timestamp, actor, and activity details.

### Viewing access intelligence data in Graph Explorer

In Graph Explorer, from the top-level filter, you can select the following entities to view Hyperdrive Access Intelligence data:

- Select an entity such as **User Principal**, **AI Agent**, or **M365 Team** from the left entities pane to explore its relationships with files and other entities. You can build queries to answer questions like, “Which Teams files are writable by users?”
- Select Activity Log and filter by properties, such as **Connector Type**, **Activity Type**, and **Actor Type** to investigate specific activities. You can use this entity to trace activities back to the affected resources and identify whether the action was performed by a **User**, **Application**, **AI Agent**, or **System**.

You can also use Data Access Governance’s **Access Graph Explorer** to explore these entities. For more information, see [Hyperdrive Activity Analysis for Microsoft Teams](/latest/docs/activity-analysis-for-microsoft-teams) and [Hyperdrive Entitlement scan for Microsoft Teams](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-teams).

![Graph Explorer interface displaying files and user principal data for Microsoft Teams.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(22).png)

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

![Summary of accessible data distribution for Microsoft Teams and other Office 365 services.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/teamsdata_dashboard.png)

### Viewing activity logs in Agent Activity Overview dashboard

In the **Agent Activity > Overview** dashboard, select the **Activity Log** entity and apply **Connector Type = Microsoft Teams** to scope results.

You can use the **Timeline** view to understand the sequence of events and the **Audit Log** view to filter, export, and investigate recorded activities, as shown below.

![Overview of agent activity log with Microsoft Teams connector type highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/teams_activitylog.png)

For more information, see [Using Agent Activity Overview dashboard](/latest/docs/agent-activity-overview-dashboard).

### Use cases for Hyperdrive Access Intelligence

Use the following table to understand the potential use cases for Hyperdrive Access Intelligence for your data systems:

| Use case | Description |
| --- | --- |
| Review AI agent access to Teams files | - In Graph Explorer, select the **AI Agent** entity and add a **Has access → Files** relationship to identify the Teams files accessible to each AI agent. - Use Inventory to review the AI agent's properties. - Analyze **AI Agents and Applications** and **Agents Accessible Data Volume** widgets in the Microsoft 365 Data and AI Security dashboard (Hyperdrive) to assess AI exposure. |
| Find externally shared Teams workspaces | - In Graph Explorer, select the **M365 Team** entity and filter **Is External = True**. Add a relationship to **Files** to review content accessible through externally shared workspaces. - Use Inventory to review workspace properties and identify the associated Teams instances. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Agents Accessible Data Volume** widget shows the proportion of data accessible to agents across M365 services, including Teams. |
| Investigate file modifications | - In Graph Explorer or Inventory, select the **Activity Log** entity and filter **Activity Type = Modify** and **Connector Type = Microsoft Teams** to identify modified Teams resources. - Use the **Agent Activity Overview** dashboard to identify similar modification events over time. |
