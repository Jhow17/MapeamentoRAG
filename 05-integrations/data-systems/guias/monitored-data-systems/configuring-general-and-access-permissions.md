---
title: "Configuring General and Access permissions for Microsoft 365 SharePoint (Self-hosted)"
slug: "configuring-general-and-access-permissions"
updated: 2026-06-23T06:11:02Z
published: 2026-06-23T06:11:02Z
canonical: "helpcenter.securiti.ai/configuring-general-and-access-permissions"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring General and Access permissions for Microsoft 365 SharePoint (Self-hosted)

This article covers the general and access permissions for supported features of Microsoft 365 SharePoint Online (Self-hosted).

## Data Access Intelligence

To Enable Data Access Governance for the data system, on the **Access Permissions** tab, under **Data Access Control** section, apply the following settings.

| Parameter | Description |
| --- | --- |
| Data Access Control | Mark **Enable Data Access Control** checkbox to include the respective Data system in the policy creation in the data access governance module. When enabled, the Data system is available for selection when you create the policy in the Data Access Governance module. See [Data Access Control Policy documentation](/v1/docs/data-access-control-policies), for more information. |

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
