---
title: "Configuring general scan settings for Apache Trino"
slug: "configuring-general-scan-settings-for-apache-trino"
updated: 2026-07-03T10:42:00Z
published: 2026-07-03T10:42:00Z
canonical: "helpcenter.securiti.ai/configuring-general-scan-settings-for-apache-trino"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring general scan settings for Apache Trino

This article covers the general scan settings and supported features of Apache Trino after authenticating the connector with Securiti.

## Data Access Control

In the **Configuration** tab for the connector, under the **Data Access Control** section, configure the following settings to include Apache Trino in data access governance policies.

> [!NOTE]
> Note
> 
> If Data Access Governance module is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan

| Parameter | Description |
| --- | --- |
| Enable Data Access Control | Enable this option to include the respective data system in the policy creation in the data access governance module. When enabled, the data system is available for selection when you create the policy in the **Data Access Governance** module. For more information, see [Data Access Control Policy documentation](/latest/docs/data-access-control-policies). |
