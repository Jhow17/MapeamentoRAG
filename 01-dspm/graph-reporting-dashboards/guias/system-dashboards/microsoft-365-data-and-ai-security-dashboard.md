---
title: "Microsoft 365 Data and AI Security dashboard"
slug: "microsoft-365-data-and-ai-security-dashboard"
updated: 2026-08-18T14:18:23Z
published: 2026-08-18T14:18:23Z
canonical: "helpcenter.securiti.ai/microsoft-365-data-and-ai-security-dashboard"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 Data and AI Security dashboard

The Microsoft 365 Data and AI Security dashboard focuses on data security insights specific to Microsoft 365 environments, including OneDrive and SharePoint. It consolidates file, site, and group-level visibility to help identify sensitive data exposure, excessive sharing, and access anomalies. This dashboard is tailored for administrators managing Microsoft 365 security to ensure data remains protected, sharing is compliant, and access is continuously monitored and governed.

The dashboard lets you:

- Monitor access levels across user groups, shared drives, and files
- Detect overexposed data and potential compliance risks
- Track posture trends and data movement within your Microsoft 365 ecosystem

> [!WARNING]
> Important
> 
> The **Microsoft 365 Data and AI Security** dashboard displays different widgets depending on your tenant's configuration. The widget set that appears is determined automatically based on whether Hyperdrive mode is enabled in your tenant.
> 
> | Tenant configuration | Widget set displayed |
> | --- | --- |
> | Hyperdrive mode enabled | AI agent visibility widgets; covering agent-accessible data volume, OWASP LLM risk indicators, broadly shared files, active AI agents, and ROT data. For more information, see [Microsoft 365 Data and AI Security dashboard (Hyperdrive)](/latest/docs/agent-commander-dashboard). |
> | Hyperdrive mode not enabled | Microsoft 365 security posture widgets; covering risk findings, SharePoint sites with external sharing, files accessible by all users, and sensitive data exposure. For more information, see the widget table in this article below. |
> 
> 
> 
> If the Graph Reporting Dashboard feature or Hyperdrive mode isn't available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

![Dashboard displaying Microsoft 365 risk findings and shareable SharePoint site data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ms365dataandaisecurity_dashboard(1).png)

The table below provides an overview of the predefined widgets in the **Microsoft 365 Data and AI Security** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| Microsoft 365 Risk Findings | - Metric - Grid | Displays the number of open findings against your connected Sharepoint and Onedrive data systems. |
| Sharepoint Sites that Allow External Sharing | - Metric - Grid | Displays the list of SharePoint sites where external sharing is enabled. Also provides information about the site's sharing capabilities using the Microsoft sharing terms. This widget helps track sites that might expose sensitive data externally. |
| Files Accessible By All Users | - Metric - Grid | Displays the number of files that are accessible by all users in Microsoft 365. It helps monitor content that is potentially shared with users without proper security controls. > [!NOTE] > **Important** > > Securiti determines organization-wide access based on the default "All Company" user group. If this group is not used in your environment, you must create custom queries and dashboard widgets to retrieve the relevant data. |
| Sensitive Files Accessible By All Users | Metric | Displays the number of sensitive files that are accessible by all users. It helps in identifying and remediating sensitive data that is overly accessible within the organization. > [!NOTE] > **Important** > > Securiti determines organization-wide access based on the default "All Company" user group. If this group is not used in your environment, you must create custom queries and dashboard widgets to retrieve the relevant data. |
| All Files Containing Sensitive Data | Metric | Displays all files that contain sensitive data within your Microsoft 365 environment. |
| Sharepoint Sites Containing Sensitive Data | Grid | Displays SharePoint sites containing sensitive data, assisting in identifying locations where sensitive information is stored, potentially guiding access control and data security policies. |
| User Groups with Access to Sensitive Data | Grid | Displays the list of user groups that have access to sensitive data within Microsoft 365. It helps monitor which user groups have permissions to access sensitive information. |
| Sites Accessible By All Users | - Metric - Grid | Displays the count of sites that are accessible by all users, giving visibility into the number of sites within Microsoft 365 that have open access to all users. This widget helps track potentially exposed sites across the organization. > [!NOTE] > **Important** > > Securiti determines organization-wide access based on the default "All Company" user group. If this group is not used in your environment, you must create custom queries and dashboard widgets to retrieve the relevant data. |
| Sharepoint Files Containing Sensitive Data | Grid | Displays SharePoint files that contain sensitive data, helping you identify, track, and protect sensitive content shared across SharePoint sites. |
