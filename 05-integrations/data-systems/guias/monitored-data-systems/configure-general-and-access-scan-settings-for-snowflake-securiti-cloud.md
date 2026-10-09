---
title: "Configure General and Access scan settings for Snowflake (Securiti Cloud)"
slug: "configure-general-and-access-scan-settings-for-snowflake-securiti-cloud"
updated: 2026-08-05T11:29:48Z
published: 2026-08-05T11:29:48Z
canonical: "helpcenter.securiti.ai/configure-general-and-access-scan-settings-for-snowflake-securiti-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure General and Access scan settings for Snowflake (Securiti Cloud)

This article covers the general and access permissions for supported features of Snowflake Securiti Cloud.

## Data Access Intelligence

> [!NOTE]
> Note
> 
> If Data Access Governance module is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan

In the Access tab, enable the toggle to run access scans on your Snowflake Data system Instance. Access scans monitors your Data system to help you enforce least privilege access on your Sensitive data. The scan runs in **Monitor** mode, requiring read-only privilege to your Data system.

For more information, see [Data Access Governance for Snowflake](/v1/docs/data-access-governance-snowflake).

## Data Scan Policy

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
| Data Scan Policy Filters | Unmark the **Scan All Objects** checkbox to apply filters. |
| If you want to scan specific data, then unmark the checkbox: - Select the **Scan Group** radio button if you want to select all groups, or specify any group to include or exclude from data scanning. - Select the **Scan Folder** radio button if you want to select all folders, or specify any folder to include or exclude from data scanning. |

Securiti scans your data systems to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.
