---
title: "Configuring General permissions for MySQL (Securiti Hosted)"
slug: "configuring-general-permissions-for-mysql-securiti-hosted"
updated: 2026-04-07T04:00:44Z
published: 2026-04-07T04:00:44Z
canonical: "helpcenter.securiti.ai/configuring-general-permissions-for-mysql-securiti-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General permissions for MySQL (Securiti Hosted)

This article covers the general permissions for supported features of MySQL (Securiti Hosted).

## Data Scan Policies

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
| Mark the **Disable Scanning** checkbox to specify the **From** and **To** values for the interval in which you want to skip scanning. |
