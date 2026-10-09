---
title: "Configuring general scan settings for Facebook Workplace"
slug: "configuring-general-scan-settings-for-facebook-workplace"
updated: 2026-08-11T09:53:37Z
published: 2026-08-11T09:53:37Z
canonical: "helpcenter.securiti.ai/configuring-general-scan-settings-for-facebook-workplace"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring general scan settings for Facebook Workplace

This article covers the post-authentication scan settings for the Facebook Workplace (Securiti Cloud) connector.

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
| Data Scan Policy Filters | Unmark the **Scan All Objects** checkbox to apply filters. |
| If you want to scan specific data, then unmark the checkbox: - Select the **Scan Group** radio button if you want to select all groups, or specify any group to include or exclude from data scanning. - Select the **Scan Folder** radio button if you want to select all folders, or specify any folder to include or exclude from data scanning. |

Securiti scans your data systems to learn its tables and schemas. Securiti uses this data to respond quickly to DSR requests submitted by data subjects.

Once the connector comes out of the data scanning state, the connector waits for your input to either:

- Scan all discovered contents using the default scan policy.
- Lets you change the scan policy followed by rescans at regular intervals.

## Breach Analysis

In the **Configuration** tab, under the **Breach** section, mark the **Breach Analysis** checkbox to initiate enhanced analysis for any reported incident for your data system and get an automated report for remediation.
