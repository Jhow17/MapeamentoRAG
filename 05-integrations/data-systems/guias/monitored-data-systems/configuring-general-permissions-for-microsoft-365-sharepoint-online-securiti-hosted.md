---
title: "Configuring General permissions for Microsoft 365 SharePoint Online (Securiti-Cloud)"
slug: "configuring-general-permissions-for-microsoft-365-sharepoint-online-securiti-hosted"
updated: 2026-06-23T06:25:53Z
published: 2026-06-23T06:25:53Z
canonical: "helpcenter.securiti.ai/configuring-general-permissions-for-microsoft-365-sharepoint-online-securiti-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General permissions for Microsoft 365 SharePoint Online (Securiti-Cloud)

This article covers the general permissions for supported features of Microsoft 365 SharePoint Online (Securiti-Cloud).

## Security Posture Scan Settings

To monitor misconfigurations across your data systems, on the **General** tab, under **Security Posture Scan Settings** section, configure the following settings:

> [!NOTE]
> Note
> 
> You cannot cancel a running Security Posture scan, it must complete its current scanning because the platform does not support in-flight termination. However, you can disable posture scanning by clearing Enable Security Posture Scan checkbox to prevent any future or scheduled runs from starting.

| Setting | Description |
| --- | --- |
| Security Posture Scan Settings | Marking the **Enabling Security Posture Management** checkbox runs one-time or periodic posture scans as per your schedule settings. After marking the checkbox, set the Period and Exclusion Time in the fields below. Running posture scans on the Data system checks for any policy violations and performs automated Remediation of misconfigurations. > [!NOTE] > **Note** > > By default, the **Auto Scan** option is selected. |
| The **Select mode** lets you monitor the misconfigurations associated with your SaaS Cloud account. For SaaS applications, **Monitor Only** is available for now. > [!NOTE] > **Note** > > This option is enabled by default if the Enable Security Posture Management checkbox is marked. |
| Marking the **Auto Scan** checkbox lets you schedule automatic posture scans to discover your data systems and their security posture. |
| If **Schedule automatic scans to Discover Data Systems and their Security Posture** is selected, you can set the Period for your scan frequency. The scan period can be hourly, weekly, or monthly. |
| After scheduling automatic scans, you can set the time range in **Exclusion Time**, which you need to avoid running posture scans, such as maintenance. |

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
