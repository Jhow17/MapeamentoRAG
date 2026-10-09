---
title: "Agents with Access to Sensitive Data"
slug: "agents-with-access-to-sensitive-data"
updated: 2026-08-18T14:21:24Z
published: 2026-08-18T14:21:24Z
canonical: "helpcenter.securiti.ai/agents-with-access-to-sensitive-data"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Agents with Access to Sensitive Data

The **Agents with Access to Sensitive Data** dashboard helps you identify AI agents that can access sensitive data across your cloud environments. It highlights where sensitive data is exposed to agents, how broadly it is accessed, and which agents present the highest security and compliance risk.

![Dashboard displaying agents with access to sensitive data and their total counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/agentswithaccesstosensitivedata_dashboard(1).png)

> [!WARNING]
> Important
> 
> Dashboard widgets depend on preconfigured cloud assets and the presence of sensitive data in your cloud sources before scans are initiated. Ensure that Asset Discovery, Posture Scans, and Discovery Scans have completed successfully for data to appear in the widgets.
> 
> For more information, see Configuring [Discovery Scans](/latest/docs/discovery-scans), [Security Posture Scans](/latest/docs/getting-started-with-iaas-connectors), and [Asset Discovery](/latest/docs/viewing-asset-discovery-results-in-graph-explorer).

The table below provides an overview of the predefined widgets in the **Agents with Access to Sensitive Data** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| AI Agents | Metric | Displays the total number of AI agents discovered across your connected environments. |
| Agents with Access to Sensitive Files | Metric | Displays the number of AI agents that can access files or data elements classified as sensitive. |
| Agents With Security Posture Findings | Metric | Displays the number of AI agents associated with one or more open security posture findings. |
| Sensitive Files Accessible by Agents | Metric | Displays the total number of sensitive files that are accessible to AI agents through connected data systems. |
| **OWASP LLM Risk 2 - Sensitive Information Disclosure** |
| Location of Agents with Access to Sensitive Data (in Knowledge Base Data Systems) | Map | Displays the geographic distribution of AI agents that can access sensitive data through AI knowledge bases. |
| VectorDBs Accessible By Agents | Map | Displays the geographic locations of vector databases that are accessible by AI agents and contain sensitive data. |
| **Top Agents with Highest Access to Sensitive Data** |
| Top 5 Rankings: Sensitive File Access per Agent | Bar chart | Ranks the top five AI agents by the number of sensitive files they can access. |
| Detailed View: Top 10 Agents with Highest Sensitive Data Access | Grid | Provides a detailed breakdown of the top AI agents, including: - Agent name and service - Asset type and hosting cloud - Region - Number of accessible sensitive files - Associated security posture findings - CMK encryption status |
| **OWASP LLM Risk 6: Excessive Agency** **Agents with Sensitive Data Access Ranked by Most Security Findings** |
| Top 05 Rankings | Bar Chart | Ranks AI agents based on the number of security posture findings associated with their access to sensitive data. |
| Detailed View - Top 10 | Grid | Lists AI agents that violate access control rules, such as overly broad permissions or missing least‑privilege enforcement. Each row includes the rule name, region, applicable regulations, service, and asset details. |
| **OWASP LLM Risk 3: AI Supply Chain Vulnerabilities** |
| Vertex Agents Connected to Unencrypted GCP Buckets with Sensitive Data - Top 10 | - Grid - Bar Chart | Displays Vertex AI agents connected to unencrypted GCP buckets that contain sensitive data, grouped by agent. |
| AWS Agents Connected to Unencrypted S3 Buckets with Sensitive Data - Top 10 | - Grid - Bar Chart | Displays AWS Bedrock agents connected to unencrypted S3 buckets that contain sensitive data, grouped by agent. |
