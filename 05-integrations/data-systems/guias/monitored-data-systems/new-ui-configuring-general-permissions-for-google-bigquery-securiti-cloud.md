---
title: "Configuring General permissions for Google BigQuery (Securiti cloud)"
slug: "new-ui-configuring-general-permissions-for-google-bigquery-securiti-cloud"
updated: 2026-04-28T04:06:16Z
published: 2026-04-28T04:06:16Z
canonical: "helpcenter.securiti.ai/new-ui-configuring-general-permissions-for-google-bigquery-securiti-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General permissions for Google BigQuery (Securiti cloud)

This article covers the general permissions for supported features of Google BigQuery (Securiti cloud).

## Data Scan Policies

If you constantly add, edit, and delete files from their respective drives, the Securiti Connector must regularly rescan your data systems to discover new and updated files.

To discover new and updated files, on the **General** tab, under the **Data Scan Policies** section, configure the following settings :

> [!NOTE]
> Note
> 
> You can change scan policy settings (if any) during a scan instead of waiting for the scan to complete. New changes take effect when the current scan finishes.

| Setting | Description |
| --- | --- |
| Data Scan Policies | Mark the **Auto Scan** checkbox to enable automatic re-scans of your data systems Instance. |
| Use the **Scan Interval** tools to configure how often Securiti does the re-scan. |
| Mark the **Disable Scanning** checkbox to specify the **From** and **To** values for the interval in which you want to skip scanning. |
| Mark the **Scan All Objects** checkbox to scan all objects. |

Securiti scans your data systems to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
