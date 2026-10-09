---
title: "Configuring general scan settings for Apache Presto"
slug: "configuring-general-scan-settings-for-apache-presto"
updated: 2026-07-03T10:10:03Z
published: 2026-07-03T10:10:03Z
canonical: "helpcenter.securiti.ai/configuring-general-scan-settings-for-apache-presto"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring general scan settings for Apache Presto

This article covers the general scan settings and supported features of Apache Presto after authenticating the connector with Securiti.

## Data Access Control

In the **Configuration** tab for the connector, under the **Data Access Control** section, configure the following settings to include Apache Presto in data access governance policies.

> [!NOTE]
> Note
> 
> If Data Access Governance module is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan

| Parameter | Description |
| --- | --- |
| Enable Data Access Control | Mark this checkbox to include the respective data system in the policy creation in the data access governance module. When enabled, the data system is available for selection when you create the policy in the **Data Access Governance** module. For more information, see [Data Access Control Policy documentation](/latest/docs/data-access-control-policies). You can view the **Sync Masking Policies Status**, repository name, and select the plugin version from the menu. |
