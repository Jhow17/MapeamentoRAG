---
title: "Configuring General permissions for PostgreSQL (Securiti cloud)"
slug: "configuring-general-permissions-for-postgresql-securiti-cloud"
updated: 2026-05-29T05:37:13Z
published: 2026-05-29T05:37:13Z
canonical: "helpcenter.securiti.ai/configuring-general-permissions-for-postgresql-securiti-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General permissions for PostgreSQL (Securiti cloud)

This article covers the general permissions for supported features of PostgreSQL Securiti cloud.

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
| Mark the **Full scan of string data type columns in** checkbox to scan every field of a string data type column for every data element type. |
| If you have marked the Full scan of string data type columns checkbox: - Choose the **Column Types** if you want to select specific column type. for example; TEXT. - Select the **Max detections to store** if you want to restrict detections. By default the per column limit is set to 5000, and per PD type limit is set to 1000. |

Securiti scans your data systems to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
