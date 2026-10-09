---
title: "Configuring General permissions for Couchbase NoSQL"
slug: "configuring-general-permissions-for-couchbase-nosql"
updated: 2026-07-30T10:26:08Z
published: 2026-07-30T10:26:08Z
canonical: "helpcenter.securiti.ai/configuring-general-permissions-for-couchbase-nosql"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General permissions for Couchbase NoSQL

This article covers the General scans settings supported features of Couchbase NoSQL after authenticating the connector with Securiti.

## Data Scan Policies

> [!NOTE]
> **Note**
> 
> Securiti supports classification scans for Couchbase NoSQL Self-hosted connector through Legacy Data Scan feature. Discovery scan is not supported for Couchbase NoSQL.

If you constantly add, edit, and delete files from their respective drives, the Securiti connector must regularly rescan your data systems to discover new and updated files.

To discover new and updated files, on the **General** tab, under the **Data Scan Policies** section, configure the following settings :

> [!NOTE]
> Note
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.

| Setting | Description |
| --- | --- |
| Data Scan Policies | Mark the **Auto Scan** checkbox to enable automatic re-scans of your data systems Instance. |
| Use the **Scan Interval** tools to configure how often Securiti does the re-scan. |

Securiti scans your data systems to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.

After the connector finishes learning the tables and schemas, it redirects you to the **Table Training** tab.

Do Table training on the Couchbase data system instance as described in [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems).
