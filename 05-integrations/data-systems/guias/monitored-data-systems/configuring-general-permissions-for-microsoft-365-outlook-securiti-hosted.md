---
title: "Configuring General permissions for Microsoft 365 Outlook (Securiti Hosted)"
slug: "configuring-general-permissions-for-microsoft-365-outlook-securiti-hosted"
updated: 2026-06-23T06:38:57Z
published: 2026-06-23T06:38:57Z
canonical: "helpcenter.securiti.ai/configuring-general-permissions-for-microsoft-365-outlook-securiti-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General permissions for Microsoft 365 Outlook (Securiti Hosted)

This article covers the general permissions for supported features of Microsoft 365 Outlook (Securiti-Cloud).

## Data Scan Policies and Filters

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

## Breach

To apply breach permissions to your data system, on the **General** tab, under the **Breach** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Breach | Mark the **Unique Identity Analysis for Breach** checkbox to integrate the data system with the Data Breach Management. When enabled and saved, this will scan and link identities to evaluate the unique identities present. |
