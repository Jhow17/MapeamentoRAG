---
title: "Viewing GCS scan results in the Data Command Graph"
slug: "viewing-gcs-scan-results-in-the-data-command-graph"
updated: 2025-10-31T14:01:38Z
published: 2025-11-03T06:14:44Z
canonical: "helpcenter.securiti.ai/viewing-gcs-scan-results-in-the-data-command-graph"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Viewing GCS scan results in the Data Command Graph

The discovered metadata for the GCS Connector can be viewed and analyzed in the Data Command Graph's Graph Explorer module to see which objects and buckets are discovered during the Data Inventory Sync. You can leverage Securiti's Data Command Graph to understand the properties and relationships for GCS objects. The following graph nodes can be used to view GCS metadata.

- **Files**: For GCS objects and data inventory results

The following are some key properties for the discovered GCS files:

| Property | Description |
| --- | --- |
| File Name | Displays the specific name of the document or file, such as "Annual Report.pdf". |
| File Creation Time | Displays the exact date and time when the file was originally created. |
| File Modified Time | Displays the exact date and time when the contents of the file were last changed and saved. |
| File Size | Displays the storage space the file uses, measured in KB, MB, or GB. |
| Version Of | Displays a link to an older, saved version of a file back to the main, current file it belongs to. For example, i`nventory-reports/2025_06_22_00-16-30_blob-inventory-ali_blob-inventory-ali-manifest.json` > [!NOTE] > **Note** > > The **Version Of** property is only for Data Inventory Sync results where file version processing is enabled. |

The screenshot below shows a Graph Explorer query that displays files in GCS and their properties discovered during Discovery scan and Data Inventory Sync.

![gcs_query.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-649197c4-f85c-eaeb-0baa-5d1dfa0b36af.png)

See [Using Graph Explorer](/v1/docs/using-graph-explorer) for more information.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
