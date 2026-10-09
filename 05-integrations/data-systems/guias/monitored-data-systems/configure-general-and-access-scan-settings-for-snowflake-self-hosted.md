---
title: "Configure General and Access scan settings for Snowflake (self-hosted)"
slug: "configure-general-and-access-scan-settings-for-snowflake-self-hosted"
updated: 2026-08-10T11:36:08Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/configure-general-and-access-scan-settings-for-snowflake-self-hosted"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure General and Access scan settings for Snowflake (self-hosted)

This article covers the general and access permissions for supported features of Snowflake (Self-Hosted).

## Data Access Control

1. On the **Permissions** tab, under the **Data Access Control** section, apply the following settings.

To configure data access scan for Snowflake, see [Snowflake access intelligence](https://helpcenter.securiti.ai/docs/data-access-governance-snowflake).

> [!NOTE]
> Note
> 
> If Data Access Governance module is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan

| Setting | Description |
| --- | --- |
| Enable Data Access Control | Mark this checkbox to include the respective Data system in the policy creation in the data access governance module. When enabled, the Data system is available for selection when you create the policy in the **Data Access Governance** module. For more information, see [Using Data Access Control Policies](/latest/docs/access-control-policies). |
| Create AD Users Mapping Table | Mark the checkbox and save it to create mapping tables in the Snowflake Data system. You can use them to apply row-level policies, create custom row filters, and apply conditional masking. |
| Enable Database Row Filter Policy | Mark the checkbox and save to enable the Sync Row Filter Policy option, which lets you sync row filter policies from Snowflake to Securiti. |
| Enable Database Column Masking Policy | Mark the checkbox and save to enable the Sync Masking Policies option, which lets you sync masking policies from Snowflake to Securiti. For more information, see [masking policy documentation](https://helpcenter.securiti.ai/docs/data-access-governance-snowflake#prerequisites2). > [!NOTE] > **Note** > > Make sure to sync masking policies after activating the connector. |
| Enable Sync Role | Mark the checkbox and save to enable the Sync Roles Status option, which lets you sync roles from Snowflake. This option fetches the identity and access management roles defined in the Data system. You can use these roles in defining Data Access Control policies in Securiti. > [!NOTE] > **Note** > > Make sure to sync roles after activating the connector. |

## Security posture scan settings

> [!WARNING]
> Important
> 
> - Initiating the Posture scan lets you retrieve the security posture-related configuration for this specific asset.
> - Securiti supports Posture scan for your Snowflake data systems using only key pair and OAuth authentication methods.
> - You must provide `Sysadmin` role to the Snowflake user to run Security Posture Scan successfully.

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
