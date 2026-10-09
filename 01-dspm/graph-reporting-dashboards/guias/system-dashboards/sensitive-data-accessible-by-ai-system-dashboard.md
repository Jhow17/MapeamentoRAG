---
title: "Sensitive Data Accessible by AI system dashboard"
slug: "sensitive-data-accessible-by-ai-system-dashboard"
updated: 2026-08-18T14:21:30Z
published: 2026-08-18T14:21:30Z
canonical: "helpcenter.securiti.ai/sensitive-data-accessible-by-ai-system-dashboard"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Sensitive Data Accessible by AI system dashboard

The **Sensitive Data Accessible by AI** dashboard provides visibility into sensitive data that AI agents, models, and knowledge bases can access across your enterprise. It helps you understand where sensitive data is exposed to AI systems, how that data is distributed across platforms and regions, and which AI assets pose the highest risk. The dashboard aligns with **OWASP LLM Risk 2: Sensitive Information Disclosure** and supports risk assessment, governance, and remediation planning.

![Dashboard displaying sensitive data metrics accessible by AI agents and security notes.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sensitivedataaccessiblebyai_dashboard(1).png)

> [!WARNING]
> Important
> 
> Dashboard widgets depend on preconfigured cloud assets and the presence of sensitive data in your cloud sources before scans are initiated. Ensure that Asset Discovery, Posture Scans, and Discovery Scans have completed successfully for data to appear in the widgets.
> 
> For more information, see Configuring [Discovery Scans](/latest/docs/discovery-scans), [Security Posture Scans](/latest/docs/getting-started-with-iaas-connectors), and [Asset Discovery](/latest/docs/visualising-results-of-aws-asset-discovery-in-graph-explorer).

The table below provides an overview of the predefined widgets in the **Sensitive Data Accessible by AI** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| Sensitive Files Accessible by Agents | Metric | Displays the total number of sensitive files that AI agents can access across connected data systems. |
| AI Models Trained On Sensitive Data | Metric | Displays the count of AI models that are trained using datasets containing sensitive data. |
| AI Knowledge Bases With Sensitive Data | Metric | Displays the total number of AI knowledge bases that contain sensitive data elements. |
| Sensitive Buckets Connected With Agents | Metric | Displays the number of object storage buckets with sensitive data that are connected to AI agents. |
| **OWASP LLM Risk 2 - Sensitive Information Disclosure** |
| VectorDBs Accessible By AI Agents | Map | Displays the geographic distribution of vector databases that AI agents can access, grouped by cloud provider. |
| Sensitive Data in Object Storages Accessible By Agents | Map | Displays the locations of object storage systems containing sensitive data that are accessible by AI agents. |
| Sensitive Data in Data Systems Accessible By Agents | Map | Displays the global distribution of data systems with sensitive data that AI agents can access. |
| **Top 5 AI Knowledge Bases Containing Sensitive Data** |
| Ranking View: Sensitive Data Elements Per Knowledge Base | Bar chart | Ranks the top knowledge bases by the number of sensitive data elements they contain. |
| Detailed View of Top 10 Knowledge Bases with Sensitive Data | Grid | Provides detailed information for each knowledge base, including service, asset type, hosting cloud, region, sensitive data count, and related security posture findings. |
| **Knowledge Bases with Sensitive Data - Ranked by Most Sensitive Posture Findings - Top 10** |
| Sensitive Data Exposure Map | Treemap | Highlights knowledge bases with the highest number of sensitive-data-related posture findings. |
| Detailed View: Sensitive Knowledge Bases With Most Findings | Grid | Lists knowledge bases with the highest number of sensitive-data-related posture findings. |
| **Unencrypted AI Knowledge Bases with Sensitive Data - Top 10** |
| AI Knowledge Bases with Data Element Exposure Map | Treemap | Displays knowledge bases containing sensitive data that are not encrypted, helping prioritize remediation. |
| Detailed View: Unencrypted AI Knowledge Bases Ranked by Most Sensitive Data | Grid | Lists unencrypted knowledge bases with sensitive data, including data element counts, encryption status, hosting platform, and region. |
| **OWASP LLM Risk 2 - Distribution of Sensitive Data Accessible by AI Agents** |
| By Data System | Treemap | Displays how sensitive data accessible by AI agents is distributed across different data systems. |
| By Data Category | Treemap | Breaks down sensitive data by category, such as financial, medical, personal, or government identifiers. |
| By Document Type | Treemap | Displays the distribution of sensitive data across document types, such as contracts, research papers, or medical records. |
| By File Format | Treemap | Displays sensitive data exposure by file format, for example documents, spreadsheets, databases, or text files. |
| Sensitive File Count Accessible By AI Agents (Trend) | Trend Chart | Displays changes over time in the number of sensitive files accessible by AI agents, helping you monitor exposure growth or reduction. |
