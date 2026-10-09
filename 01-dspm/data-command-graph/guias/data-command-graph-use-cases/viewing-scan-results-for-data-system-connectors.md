---
title: "Viewing scan results in Data Command Graph"
slug: "viewing-scan-results-for-data-system-connectors"
updated: 2026-09-02T14:09:25Z
published: 2026-09-02T14:09:25Z
canonical: "helpcenter.securiti.ai/viewing-scan-results-for-data-system-connectors"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Viewing scan results in Data Command Graph

The Data Command Graph lets you view the results for Discovery scans and Data Inventory Syncs run on your data systems, using the Graph Explorer and Inventory. After you run a Data Inventory Sync or a Discovery Scan, the results populate the graph, where you can explore the discovered assets, classifications, metadata, and findings.

You can view the following results in the Data Command Graph:

- **Classification results** for data systems from discovery scans. For more information, see [Discovery scans documentation](/latest/docs/discovery-scans).
- **Metadata for files** discovered during Data Inventory Syncs. For more information, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
- **User entitlements** for data systems from entitlement scans. For more information, see [Data Inventory Sync for self-hosted connectors](/latest/docs/data-inventory-sync-for-self-hosted-connectors).
- **Microsoft Information Protection (MIP) labels** extracted during Data Inventory Syncs. For more information, see [Microsoft Information Protection (MIP) label extraction for data systems](/latest/docs/microsoft-information-protection-mip-label-extraction-for-data-systems).

For example, you can:

- Select the **Data System** entity to see the assets it contains.
- Select the **Database** entity to see all the **Tables** within it.
- Select the **Files** entity and see its properties, such as its path and size.
- Select the **Files** entity and view all the MIP **Scanned Classification Labels** for your SharePoint files.

For a high-level overview of scan results, the **Data System** entity displays key summary counters. The table below describes some key metrics for scanned data and their sources.

| Graph entity | Metric | Data source |
| --- | --- | --- |
| Data System | Total Files | Total files are now calculated primarily from the Data Inventory Sync results. > [!NOTE] > **Important** > > If Data Inventory Sync feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. In case you do not have Data Inventory Sync enabled, the **Total Files** are calculated from the Discovery Scan results. |
| Scanned Documents | Scanned documents count is calculated from the discovery scan results, directly reflecting the number of documents processed during scans. |
| Skipped Files | Skipped files during scans are calculated from discovery scan results. > [!NOTE] > **Note** > > It no longer includes files that were intentionally skipped due to policy configurations. |
| Total File Size | Total file size is now calculated primarily from the Data Inventory Sync results. > [!NOTE] > **Important** > > If Data Inventory Sync feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan. In case you do not have Data Inventory Sync enabled, the **Total File Size** are calculated from the Discovery Scan results. |
| Discovery Scan, Discovery Scan Job | Skipped Files | Skipped Files count during scans now only includes files skipped by Securiti, for example, due to file size, access issues, etc. It no longer includes files that were intentionally skipped due to policy configurations. |

## Filtering columns by content profile

Securiti lets you identify which columns directly contributed to a table's content profile classification. You can filter the **Column** and **Table** entities by content profile using the **Content Profile** property. Consider the following when using content profile property:

- The **Content Profile** property operates at the table level and returns all tables with that content profile enabled, including only the columns that directly contribute to that table's overall content profile, as shown below.

> [!WARNING]
> Important
> 
> This behavior applies only to data scanned in Securiti release 1.149 or later. For the previously scanned data, the **Content Profile** filter continues to show all the columns in the table.

![Data catalog interface displaying various data element types and their attributes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graph_contentprofile.png)

- If you want to view all the columns in a table, apply the **Table** property to filter by a table name, without any reference to content profiles, as shown below.

![Data table displaying various account columns and their data types in a database.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graph_columnwithtable.png)
- If you want to find which columns triggered a content profile on a table, apply the **Content Profile** filter. This displays only the contributing columns, as shown below.

![Graph Explorer interface displaying data columns and content profiles for database management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/graph_columntocp.png)
- You can also view content profiles for columns discovered for your data systems in the **Inventory** page, as shown below.

![Overview of data columns and types in a database inventory management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_contentprofile.png)

## Viewing Data Inventory Sync results

Securiti lets you view statistics for your Data Inventory Syncs in the Graph Explorer and Inventory pages using the following entities.

| Entity | Description | Related entities |
| --- | --- | --- |
| Inventory Scan Job | Displays the Inventory Scan job details configured for Data Inventory Syncs. > [!NOTE] > Important > > - The ​**Inventory Scan Job​** entity is only visible for unstructured data systems supporting the ​**Data Inventory Sync**​​ functionality. > - Securiti Graph Explorer displays the details and statistics for the latest Inventory scan job only. | - Data System - Files |
| Files | Displays all the discovered files and their metadata during Data Inventory Syncs. | - Resource Access - Resource Scope - File Findings - Access Control - Data Labeling - File Insights - Policy - Collection - Database - Data System - Inventory Scan Job - Data Element - Site - Scanned Classification Label |
| Folders | Displays the discovered folders, sub-folders, and shares for SMB data systems. Each folder includes key properties, such as name, path, last modified date, folder type (share or folder), and top-level directory (SMB Share name). | - Data System - Files |

### Using the Inventory Scan Job entity

The **Inventory Scan Job** entity lets you view the following statistics in the Graph Explorer and Inventory:

| Property | Description | Supported operators and properties |
| --- | --- | --- |
| Execution ID | Displays the unique identifier for each inventory scan execution. For example, `1234abcd-acme-1234-abcd-wxyz12345` | You can filter the execution ID by the following operators: - Contains - Not contains - Begins with - Not begins with - Ends with - Not ends with - Equals - Not equals - Is empty - Is not empty - Is one of - Is not one of - Most recent scan - Not most recent scan |
| Ingestion Status | Displays the status of the data ingested after a inventory scan job is executed. For example, `completed`. | You can filter the Ingestion Status by the following operators: - Contains - Not contains - Begins with - Not begins with - Ends with - Not ends with - Equals - Not equals - Is empty - Is not empty - Is one of - Is not one of |
| Status | Displays the status of an inventory scan job. | You can filter the execution ID by the following operators: - Contains - Not contains - Begins with - Not begins with - Ends with - Not ends with - Equals - Not equals - Is empty - Is not empty - Is one of - Is not one of - Most recent scan - Not most recent scan |
| Start Time | Displays the timestamp when the inventory scan began. For example, `Jun 10 2024, 12:13 pm` | You can filter the Start and End Time by the following operators: - Before - After - In the past - In the upcoming - Older than - Between - Is empty - Is not empty |
| End Time | Displays the timestamp when the inventory scan completed. For example, `Jun 11 2024, 07:20 pm` |
| Data System ID | Displays the data system instance ID associated with the scan job. For example, `2680` | You can filter the Data System ID by the following operators: - Equals - Not equals - Greater than - Greater or Equals to - Less than - Less or Equals to - Is one of - Is not one of |
| Organization | Displays the Organization name of the particular organization where inventory scan job is executed. For example, `Default Organization`. | You can filter the Data System ID by the following operators: - Equals - Not equals - Greater than - Greater or Equals to - Less than - Less or Equals to - Is one of - Is not one of |

You can filter the **Inventory Scan Job** entity by the following properties:

- Data System ID
- End Time
- Execution ID
- Ingestion Status
- Organization
- Start Time

## Related

- [Discovery scans](/discovery-scans.md)
- [Data Inventory Sync and Entitlement Scan for data systems](/data-inventory-sync-for-self-hosted-connectors.md)
- [Microsoft Information Protection (MIP) label extraction for data systems](/microsoft-information-protection-mip-label-extraction-for-data-systems.md)
- [Managing queries in the Graph Explorer](/managing-queries-in-the-graph-explorer.md)
