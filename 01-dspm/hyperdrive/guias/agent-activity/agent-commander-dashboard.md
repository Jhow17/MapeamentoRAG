---
title: "Using Microsoft 365 Data and AI Security dashboard (Hyperdrive)"
slug: "agent-commander-dashboard"
updated: 2026-08-01T11:35:52Z
published: 2026-08-01T11:35:52Z
canonical: "helpcenter.securiti.ai/agent-commander-dashboard"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Microsoft 365 Data and AI Security dashboard (Hyperdrive)

**Scenario**

As a Data Security Officer, you must understand how AI agents and applications access sensitive data across Microsoft 365. Manually reviewing permissions and data exposure across OneDrive, SharePoint, and Teams is time-consuming and prone to oversight. Using the **Microsoft 365 Data and AI Security** (Hyperdrive) dashboard, you quickly view which AI agents have access to sensitive data and identify broadly shared files that increase risk. You focus on a high-risk agent with extensive access to financial documents and take corrective action. You reduce data exposure, strengthen governance, and gain clear visibility into AI-related risks.

## Overview

> [!WARNING]
> Important
> 
> - If this dashboard is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - The Microsoft 365 Data and AI Security dashboard (Hyperdrive) is available only for tenants with **Hyperdrive** mode enabled.

The Microsoft 365 Data and AI Security dashboard (Hyperdrive) provides centralized visibility into AI agents, applications, and their access to Microsoft 365 data. It helps you understand what data agents can access, how much data is exposed, and where sensitive information resides.

This dashboard supports risk assessment, governance, and oversight of AI-driven interactions across OneDrive, SharePoint, Outlook, and Teams.

You can use this dashboard to:

- View the total number of AI agents and applications connected to M365.
- Analyze agent-accessible data volume across data systems.
- Identify sensitive data elements exposed to agents.
- Detect broadly shared files and potential exposure risks.
- Monitor OWASP LLM risk indicators related to sensitive data access.
- Review distribution summaries across SaaS systems.

To access the Agent Commander for M365 dashboard, in Securiti, in the left navigation menu, click the **Jewel** icon and select **Agent Activity > Dashboard**, as shown below.

![Overview of agent activity with highlighted dashboard and activity log sections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/agent365dash_access1.png)

Securiti also lets you access the dashboard from **Dashboard > System > Microsoft 365 Data and AI Security** (Hyperdrive), as shown below.

![Dashboard displaying Microsoft 365 data security metrics and agent accessible data volume.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/iro_m365dashboard.png)

## Widgets in Microsoft 365 Data and AI Security dashboard (Hyperdrive)

The table below provides an overview of the predefined widgets in the **Microsoft 365 Data and AI Security** dashboard (Hyperdrive) dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| Files | Metric | Displays the total number of files discovered across connected Microsoft 365 data systems, along with the total file size. |
| Users & Groups | Metric | Displays the the total number of users and groups identified in the environment. |
| AI Agents & Applications | Metric | Displays the total count of registered applications and AI agents interacting with Microsoft 365 data. |
| Agents Accessible Data Volume | Chart | This donut chart shows the distribution of data volume accessible to AI agents across Microsoft 365 services such as SharePoint Online, OneDrive, Outlook, and Microsoft Teams. |
| Broadly Shared Files | Chart | Displays the number of files that have been broadly shared over a selected time period, typically the last 30 days. The trend chart helps you monitor sharing patterns and detect unusual increases. |
| Agents Accessible Data Elements by Category | Treemap | Displays the distribution of sensitive and classified data elements accessible to AI agents, grouped by categories such as Contact Info, Location, Name, Social, Physical Attributes, Government Identifiers, and Financial data. |
| Agents Accessible Data Distribution Summary | Grid | This table summarizes agent-accessible data across Microsoft 365 services, including OneDrive, SharePoint Online, Outlook, and Teams. It displays the number of data systems, files, total data volume, and sensitive data elements. |
| Agents Accessible Files by File Format | Treemap | Displays the files accessible to AI agents based on file formats. It helps you understand which document types, such as spreadsheets, documents, or presentations are most commonly accessible. |
| Agents Modifying Data | Metric | Displays the total number of AI agents that have performed data modification activities. It highlights agents with write-level interactions that may introduce operational or security risks. |
| Active AI Agents | Time-series | This time-series widget displays the number of active AI agents over a selected period, such as the last 30 days. It helps you track adoption trends and identify sudden increases in agent activity. |
| Agent Accessible ROT Data | Grid | Displays the volume of redundant, obsolete, and trivial (ROT) data accessible to AI agents. |
| OWASP LLM Risk 2 - Sensitive Information Disclosure | Metric | Displays the number of AI agents that have access to sensitive data, aligned with OWASP LLM Risk 2 (Sensitive Information Disclosure). It provides a quick risk indicator for AI-related data exposure. |
| OWASP LLM Risk 2 - Agents with Access to Sensitive Data | Grid | This grid widget lists the specific agents and applications that have access to sensitive data. It includes attributes such as account, asset name, service account name, external status, and provider type. |
