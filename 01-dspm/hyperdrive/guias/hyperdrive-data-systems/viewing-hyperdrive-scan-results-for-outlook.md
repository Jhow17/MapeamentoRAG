---
title: "Viewing Hyperdrive scan results for Outlook"
slug: "viewing-hyperdrive-scan-results-for-outlook"
updated: 2026-07-20T20:22:04Z
published: 2026-07-20T20:22:04Z
canonical: "helpcenter.securiti.ai/viewing-hyperdrive-scan-results-for-outlook"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Viewing Hyperdrive scan results for Outlook

After you run scans on your Microsoft Outlook Hyperdrive connector, Securiti populates inventory, identity, access, and activity data across multiple pages. Depending on the scan you run, you can:

- Review discovered messages and attachments
- Investigate access relationships
- Analyze user and AI agent activity
- Monitor scan metrics

This article explains where Outlook data appears, what each scan populates, and how to use each page to investigate your Outlook environment.

## Prerequisite

Before you can view scan results, the required scans must complete successfully. For information about scan order and dependencies, see the following resources:

- [Configuring Data Inventory Sync for Microsoft Outlook](/latest/docs/configuring-data-inventory-sync-for-outlook-hyperdrive)
- [Configuring Activity Analysis for Microsoft Outlook](/latest/docs/configure-activity-analysis-for-microsoft-365-outlook-hyperdrive)
- [Hyperdrive Entitlement scan for Microsoft Outlook](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-365-outlook)
- [Hyperdrive data scans](/latest/docs/viewing-hyperdrive-data-in-securiti#hyperdrive-data-scans)

## Viewing Data Inventory Sync results

**Data Inventory Sync** discovers Microsoft Outlook files and their metadata. After the scan completes, the **Files** entity is populated in the Graph Explorer and Inventory pages in Securiti.

Use the table below to understand where to view the inventory data:

| Page | What you can do |
| --- | --- |
| Inventory > **Files** entity | Browse and filter all discovered Outlook files and their metadata. |
| Graph Explorer > **Files** entity | Query files and build relationships with users and activities. |
| Microsoft 365 Data and AI Security dashboard (Hyperdrive) | Review aggregated Microsoft 365 inventory metrics. |
| Connector **Statistics** page | Review scan performance and inventory metrics, such as Files Cataloged. |

The sections below describe in detail how you can view data in each page.

### Viewing inventory metrics in Statistics page

From the left menu for your Microsoft Outlook data system connector, click **Statistics** to view the metrics populated for Data Inventory Sync results and progress. You can use this page when you want to monitor the progress of your Hyperdrive inventory scans in near real time, such as checking metrics for scan duration, files/hour cataloged or large file counts without waiting for the scan to complete.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlook_statistics.png)

For more information, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive#viewing-data-inventory-sync-statistics).

### Viewing Files in Inventory

In Inventory, from the left entities panel, select **Files** to view all discovered files in your tenant. To view only Microsoft Outlook files, filter the **Files** entity by setting the **Data System Type** property to **Office 365 Outlook**, as shown below.

![Overview of inventory files with highlighted data system type and file details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlookfiles_inventory.png)

You can use this page to find a specific Outlook document and review its metadata and ownership.

### Viewing inventory results in Graph Explorer

In Graph Explorer, from the top-level filter, select **Files** to view all discovered files in your tenant. To view only Microsoft Outlook files, add **Files** as your entity and set the **Data System Type** property filter to **Office 365 Outlook**, as shown below.

![Overview of files in Office 365 Outlook with highlighted resource path and file names.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlookfiles_graph.png)

You can use Graph Explorer to run targeted queries on Outlook files. For example, to find files of a specific format, review file metadata, or explore which users have access to a specific file using the **Relationship** view.

### Analyzing inventory data in Microsoft 365 Data and AI Security dashboard

In the **Microsoft 365 Data and AI Security** dashboard (Hyperdrive), the **Files** widget displays aggregate counts of files and user identities discovered across all connected Microsoft 365 data systems, including Microsoft Outlook.

To access the dashboard, from the left navigation menu, click the **Jewel icon** and select **Agent Activity > Dashboard**. You can also access it from **Dashboard > System > Microsoft 365 Data and AI Security**.

You can use this dashboard to get a high-level view of how many files are available in your Microsoft 365 environment and how many users and groups have been identified, without needing to run a query. For a full description of all available widgets, see [Using Microsoft 365 Data and AI Security dashboard (Hyperdrive)](/latest/docs/agent-commander-dashboard).

### Use cases for Data Inventory Sync

Use the following table to understand the potential use cases for Data Inventory Syncs for Hyperdrive data systems:

| Use case | Description |
| --- | --- |
| Finding a specific Outlook file | - Use Inventory to search the **Files** entity and filter **Data System Type = Office 365 Outlook**. - If you need additional context, open Graph Explorer, select the **Files** entity, apply the same filter, and query properties such as **File Name**, **Resource Path**, or **File Format** to locate the file. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Files** widget shows the aggregate file count and total file size across all connected M365 data systems, including Outlook. |
| Analyze file types in your Outlook environment | - Use Inventory to review file metadata or Graph Explorer to query the **Files** entity and group or filter by the **File Format** property. This helps identify the types of content stored across Outlook channels. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive) to understand the overall distribution of Outlook content. |
| Identifying large or stale Outlook files | - Open the **Statistics** page for your Microsoft Outlook connector to review metrics such as **Total Number of Large Files** and **Oldest Modified File Date**. Use these metrics together with the inventory results to identify files that may require archival, cleanup, or further review. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Files** widget shows the aggregate file count and total file size across all connected M365 data systems, including Outlook. |

## Viewing Hyperdrive Access Intelligence results

After **Entitlement scan** and **Activity Analysis** complete, Securiti populates identity and access data for your Microsoft Outlook environment. The scan discovers users, groups, AI agents, applications, along with their access relationships to Outlook messages and attachments.

You can use this data to understand some of the following use cases:

- Who has access to Microsoft Outlook content
- Identify excessive permissions
- Review AI agent and application access
- Investigate relationships between identities and files

| Page | Data populated | What you can do |
| --- | --- | --- |
| Inventory | Following graph entities are populated as a result of Entitlement scan and Activity Analysis: - User Principal - User Group Principal - AI Agent - Microsoft 365 Application - Files - Activity Log - Actor Type (Agent, Application, System, User) | Browse users, groups, AI agents, applications, and Outlook messages. |
| Graph Explorer | Investigate relationships between identities, Outlook messages and attachments. |
| Access Graph Explorer in DAG |
| Microsoft 365 Data and AI Security dashboard (Hyperdrive) | Access and posture related widgets for AI Agents and applications. | Review AI access, applications, and exposure across Microsoft 365. |
| Connector **Statistics** page | Widgets for the total Users, groups, and AI Agents Cataloged during entitlement scans. | Review scan performance and entitlement metrics, such as Users Cataloged. |

The sections below describe in detail how you can view data in each page.

### Viewing Statistics page for entitlements

From the left menu for your Microsoft 365 Outlook data system connector, click **Statistics** to view the metrics populated for Entitlement scan results and progress. You can use this page when you want to monitor the progress of your Hyperdrive entitlement scans in near real time, such as checking metrics for scan duration, users and groups cataloged without waiting for the scan to complete.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlook_statistics.png)

For more information, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive#viewing-entitlement-sync-statistics).

### Viewing entitlements and activities in Inventory

In Inventory, from the left entities panel you can select the following entities to view Hyperdrive Access Intelligence data:

- Select an entity such as **User Principal**, **User Group Principal**, **AI Agent**, or **Microsoft 365 Application** to view the objects and access permissions discovered during the entitlement scan.
- Select the **Activity Log** entity to view recorded activities.

You can use this page to review identities, AI agents, applications, and Outlook messages before investigating their relationships in Graph Explorer. Moreover, you can search and filter activity records by resource, timestamp, actor, and activity details.

### Viewing access intelligence data in Graph Explorer

In Graph Explorer, from the top-level filter, you can select the following entities to view Hyperdrive Access Intelligence data:

- Select an entity such as **User Principal**, **AI Agent**, or **M365 Application** from the left entities pane to explore its relationships with files and other entities. You can build queries to answer questions like, “Which Outlook files are controllable by M365 Application?”
- Select Activity Log and filter by properties, such as **Connector Type**, **Activity Type**, and **Actor Type** to investigate specific activities. You can use this entity to trace activities back to the affected Outlook resources and identify whether the action was performed by a **User**, **Application**, **AI Agent**, or **System**.

You can also use Data Access Governance’s **Access Graph Explorer** to explore these entities. For more information, see [Hyperdrive Activity Analysis for Outlook](/latest/docs/activity-analysis-for-outlook) and [Hyperdrive Entitlement scan for Outlook](/latest/docs/hyperdrive-entitlement-scan-for-microsoft-365-outlook).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 12(3).png)

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

![Summary of accessible data distribution for Microsoft 365 applications including Outlook.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlookdata_dashboard.png)

### Viewing activity logs in Agent Activity Overview dashboard

In the **Agent Activity > Overview** dashboard, select the **Activity Log** entity and apply **Connector Type = Office 365 Outlook** to scope results.

You can use the **Timeline** view to understand the sequence of events and the **Audit Log** view to filter, export, and investigate recorded activities, as shown below.

![Overview of agent activity log with highlighted connector type for Office 365 Outlook.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/outlook_activitylog.png)

For more information, see [Using Agent Activity Overview dashboard](/latest/docs/agent-activity-overview-dashboard).

### Use cases for Hyperdrive Access Intelligence

Use the following table to understand the potential use cases for Hyperdrive Access Intelligence for your data systems:

| Use case | Description |
| --- | --- |
| Review AI agent access to Outlook resources | - In Graph Explorer, select the **AI Agent** entity and add a **Has access → Files** relationship to identify the Outlook files accessible to each AI agent. - Use Inventory to review the AI agent's properties. - Analyze **AI Agents and Applications** and **Agents Accessible Data Volume** widgets in the Microsoft 365 Data and AI Security dashboard (Hyperdrive) to assess AI exposure. |
| Find externally shared Outlook resources | - In Graph Explorer, select the **M365 Application** entity and filter **Is External = True**. Add a relationship to **Files** to review content accessible through externally shared workspaces. - Use Inventory to review workspace properties and identify the associated Outlook instances. - In the Microsoft 365 Data and AI Security dashboard (Hyperdrive), the **Agents Accessible Data Volume** widget shows the proportion of data accessible to agents across M365 services, including Outlook. |
| Investigate file modifications | - In Graph Explorer or Inventory, select the **Activity Log** entity and filter **Activity Type = Modify** and **Connector Type = Office 365 Outlook** to identify modified Outlook resources. - Use the **Agent Activity Overview** dashboard to identify similar modification events over time. |
