---
title: "Viewing ADLS (self-hosted) metadata in Securiti"
slug: "viewing-adls-self-hosted-metadata-in-securiti-en"
updated: 2026-02-04T13:45:17Z
published: 2026-02-04T13:45:17Z
canonical: "helpcenter.securiti.ai/viewing-adls-self-hosted-metadata-in-securiti-en"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Viewing ADLS (self-hosted) metadata in Securiti

After Securiti completes an inventory or discovery scan on Azure Data Lake Storage (ADLS) data system, you can view the scanned metadata in the [Data Command Graph](/modules/data-command-graph/en/index-en.html?contextId=dcgTop).

The metadata for ADLS files and containers can be viewed under the following graph entities:

- **Files**
- **Folders**

The properties provide key metadata about a file's name, last accessed or modified time, and ownership, giving you a complete picture of your data.

## Data Inventory Sync results for ADLS documents

In the **Data Command Graph**, you can view the following properties for your ADLS documents after Data Inventory Sync completion. The table below lists some key properties for ADLS documents.

| Graph entity | Property | Description |
| --- | --- | --- |
| - Files - Folders | Data Source | Displays the data system instance ID for the ADLS connector, such as `abcd1234-1234-4f33-abcd-abcd12345f7c` |
| File Owner | Displays the user name for the document's owner in Azure Data Lake, such as `$superuser` |
| File Modified Time | Displays the date and time of the file's last change in the data system, such as `May 16 2023, 11:25 am` |
| File Size | Displays the size of the file in Bytes, KB, or MB, such as `10.6KiB`. |
| File Name | Displays the document name, such as `Contact_email.docx` |
| Top Level Directory | Displays the container name, such as `azure-new` |
| Resource Path | Displays the path for file excluding the file name, such as `current/delta_log` |
| Files | Last Access Time | Displays the most last access time for a file , such as `May 16 2023, 11:25 am`. |
