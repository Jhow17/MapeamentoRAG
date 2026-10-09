---
title: "Viewing Hyperdrive scan results for Amazon S3"
slug: "viewing-hyperdrive-scan-results-for-amazon-s3"
updated: 2026-07-22T08:17:39Z
published: 2026-07-22T08:17:39Z
canonical: "helpcenter.securiti.ai/viewing-hyperdrive-scan-results-for-amazon-s3"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Viewing Hyperdrive scan results for Amazon S3

After you run scans on your Amazon S3 Hyperdrive connector, Securiti populates inventory data across multiple pages. Depending on the scan you run, you can:

- Review discovered objects
- Analyze object metadata and storage details
- Monitor scan metrics

This article explains where Amazon S3 data appears, what the scan populates, and how to use each page to investigate your Amazon S3 environment.

## Prerequisites

Before you can view scan results, the required scan must complete successfully. For information about scan order and dependencies, see the following resources:

- [Configuring Data Inventory Sync for Amazon S3 (Hyperdrive)](/latest/docs/configuring-data-inventory-sync-for-amazon-s3-hyperdrive)
- [Hyperdrive data scans](/latest/docs/viewing-hyperdrive-data-in-securiti#hyperdrive-data-scans)

## Viewing Data Inventory Sync results

Data Inventory Sync discovers Amazon S3 objects and their metadata. After the scan completes, the **Files** entity is populated in the Graph Explorer and Inventory pages in Securiti.

Use the table below to understand where to view the inventory data:

| Page | What you can do |
| --- | --- |
| Inventory > **Files** entity | Browse and filter all discovered S3 objects and their metadata. |
| Graph Explorer > **Files** entity | Query objects and build relationships with other entities. |
| Unstructured Data Overview dashboard | Review aggregated unstructured data metrics across your connected data systems, including Amazon S3. |
| The connector’s **Statistics** page | Review scan performance and inventory metrics, such as Objects Processed and Data Size Inventoried. |

  

The sections below describe in detail how you can view data in each page.

### 

### Viewing inventory metrics in Statistics page

From the left menu for your Amazon S3 data system connector, click **Statistics** to view the metrics populated for Data Inventory Sync results and progress. Use this page to monitor the progress of your Hyperdrive inventory scans in near real time. You can check metrics such as scan duration, Files Cataloged, and ROT Files by extension, without waiting for the scan to complete.

![Inventory statistics showing files cataloged, data size, and scanning details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/s3_statistics.png)

For more information, see [Using Inventory Sync statistics (Hyperdrive)](/latest/docs/using-inventory-sync-statistics-hyperdrive).

### Viewing Files in Inventory

In Inventory, from the left entities panel, select **Files** to view all discovered objects in your tenant. To view only Amazon S3 objects, filter the **Files** entity by setting the **Data System Type** property to **Amazon S3**, as shown below.

![Inventory interface displaying file types and data system type options for organization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/s3files_inventory.png)

You can use this page to find a specific S3 object and review its metadata, such as bucket name, storage class, and version information.

  

### Viewing inventory results in Graph Explorer

In Graph Explorer, from the top-level filter, select **Files** to view all the discovered files during inventory syncs. To view only Amazon S3 objects, add **Files** as your entity and set the **Data System Type** property filter to Amazon S3, as shown below.

![Graph Explorer interface displaying files with properties filtered by Amazon S3 data type.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/s3files_graph.png) You can use Graph Explorer to run targeted queries on S3 objects. For example, you can find objects of a specific format, review object metadata, or explore object properties such as owner and resource tags.

### Analyzing inventory data in Unstructured Data Overview dashboard

In the **Unstructured Data Overview** dashboard, widgets such as **Total Files Discovered** and **Volume of All Files Discovered** display aggregate counts and storage volume for unstructured data discovered across all connected data systems, including Amazon S3.

To access the dashboard, from the left navigation menu, click **Dashboard**, then select **System > Data Security > Unstructured Data Overview.**

![Overview of unstructured data, including file counts and sensitive data metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/unstructuredoverview_dashboard(1).png)

You can use this dashboard to get a high-level view of your unstructured data footprint and identify exposure risks, without needing to run a query. For more information, see [Unstructured Data Overview dashboard](/latest/docs/unstructured-data-overview-dashboard).

  

## Use cases for Data Inventory Sync

Use the following table to understand the potential use cases for Data Inventory Sync for your Hyperdrive Amazon S3 data systems:

| Use case | Description |
| --- | --- |
| Finding a specific S3 object | Use Inventory or Graph Explorer to search the **Files** entity and filter **Data System Type = Amazon S3**. If you need additional context, query by properties such as **File Name** or **Resource Path** to locate the object |
| Analyze object types in your S3 environment | - Use Inventory to review object metadata or Graph Explorer to query the **Files** entity and group or filter by the **File Format** property to identify the types of content stored across your S3 buckets. - Use the Unstructured Data Overview dashboard's **Files By File Format** widget to understand the overall distribution of content. |
| Identifying ROT or stale S3 files | - Open the connector's Statistics page for your Amazon S3 connector to review metrics from the inventory sync. Use these metrics with the inventory results to identify objects that might require archival, cleanup, or further review. - In the Unstructured Data Overview dashboard, use the **Files Not Modified in Greater Than 1 Year Per Data System** widget to identify stale objects. |
