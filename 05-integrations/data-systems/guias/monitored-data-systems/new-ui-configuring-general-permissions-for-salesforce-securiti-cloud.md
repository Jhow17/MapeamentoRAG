---
title: "Configuring General permissions for Salesforce (Securiti Cloud)"
slug: "new-ui-configuring-general-permissions-for-salesforce-securiti-cloud"
updated: 2026-03-10T05:53:38Z
published: 2026-03-10T05:53:38Z
canonical: "helpcenter.securiti.ai/new-ui-configuring-general-permissions-for-salesforce-securiti-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (New UI) Configuring General permissions for Salesforce (Securiti Cloud)

This article covers the general permissions for supported features of Salesforce Securiti Cloud.

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
