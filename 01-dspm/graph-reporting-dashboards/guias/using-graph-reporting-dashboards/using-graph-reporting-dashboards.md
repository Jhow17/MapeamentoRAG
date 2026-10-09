---
title: "Using Graph Reporting Dashboards"
slug: "using-graph-reporting-dashboards"
status: "update"
updated: 2026-09-17T16:24:28Z
published: 2026-09-17T16:24:28Z
canonical: "helpcenter.securiti.ai/using-graph-reporting-dashboards"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Using Graph Reporting Dashboards

> [!WARNING]
> **Important**
> 
> - If the Graph Reporting Dashboard feature isn't available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - Securiti's **Reporting** module uses conditional visibility to display relevant system dashboards and widgets for your data. You must have at least one instance configured for your IaaS cloud connector to view the cloud data and security findings in the dashboards.

The **Dashboards** module provides out-of-the-box and custom reporting capabilities powered by the rich metadata in Securiti's Data Command Graph. Securiti provides a collection of out-of-the-box dashboards that highlight data inventory, security, and AI security insights under the **System** dashboards tab. The **Custom** dashboards tab contains dashboards you create using **Graph Explorer** or **Dashboard Agents**.

> [!WARNING]
> Important
> 
> This module is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

To access the Graph Reporting Dashboards, from the left navigation menu, click the **Jewel** icon and select **Dashboard** from the menu, as shown below.

![Dashboard displaying security posture findings and risk severity metrics for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dashboard_nav.png)

## Using dashboards with multiple organizations

If your Securiti tenant uses multiple organizations, dashboards and widgets respect your active organization context. Data shown in a dashboard reflects the organization or combination of organizations you have currently selected, not your entire tenant.

> [!WARNING]
> Important
> 
> If the multi-org feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Trend widgets and organization scoping

Trend widgets collect data points on a recurring schedule. Each data point is scoped to the organization that is active in your tenant at the time of collection. When you select multiple organizations, Securiti combines data from all selected organizations into a single trend line. The trend line represents the selected organization combination rather than individual organizations.

This has the following effects on trend data:

- Trend history for a specific organization includes only the data points collected while that organization was active.
- Selecting a combination of organizations displays trend data scoped only to the selected organizations.
- Trend data for a new combination of organizations begins collecting from the first time you select that combination. Historical trend data is not available for combinations that were not previously selected.
- The **All Organizations** view displays trend data for all organizations.

> [!CAUTION]
> Warning
> 
> - If trend widget data appears incomplete or inconsistent after switching organizations, this is expected behavior. Trend data for non-default organizations builds accurate history starting from the point when organization-level scoping became active in your tenant.
> - Securiti does not correct historical trend data collected before your tenant's organization filtering was applied. To remove this stale data from your tenant, contact your Customer Success Manager.

#### Interactive demo

See the interactive demo below to understand how trend widgets update with organization scoping:

[Embedded content](https://app.storylane.io/demo/hp6jprkrgf0l?embed=inline)

## Related

- [Creating widgets in Graph Explorer](/creating-widgets-in-graph-explorer.md)
