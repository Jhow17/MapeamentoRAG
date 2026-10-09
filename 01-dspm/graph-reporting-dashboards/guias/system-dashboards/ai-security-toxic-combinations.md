---
title: "AI Security: Toxic Combinations"
slug: "ai-security-toxic-combinations"
updated: 2026-08-18T14:21:16Z
published: 2026-08-18T14:21:16Z
canonical: "helpcenter.securiti.ai/ai-security-toxic-combinations"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# AI Security: Toxic Combinations

The **AI Security: Toxic Combinations** dashboard provides a centralized view of critical security posture findings related to AI agents, platforms, and their underlying configurations. It focuses on detecting high‑risk combinations of permissions, access, encryption gaps, and sensitive data exposure.

The dashboard aligns with OWASP LLM risk, helping you identify AI agents that have broader access than necessary, interact with sensitive or publicly accessible data, or operate on misconfigured infrastructure.

![Dashboard displaying AI security findings and toxic combinations across the enterprise.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/aisecurityandtoxiccombinations_dashboard.png)

> [!WARNING]
> Important
> 
> Dashboard widgets depend on preconfigured cloud assets and the presence of sensitive data in your cloud sources before scans are initiated. Ensure that Asset Discovery, Posture Scans, and Discovery Scans have completed successfully for data to appear in the widgets.
> 
> For more information, see Configuring [Discovery Scans](/latest/docs/discovery-scans), [Security Posture Scans](/latest/docs/getting-started-with-iaas-connectors), and [Asset Discovery](/latest/docs/viewing-asset-discovery-results-in-graph-explorer).

The table below provides an overview of the predefined widgets in the **AI Security: Toxic Combinations** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| Security Posture Findings on Agents | Metric | Displays the total number of AI security posture findings detected across all connected AI agents. |
| Highly Critical Posture Findings | Metric | Displays the count of findings classified as highly critical based on severity scoring. These findings represent the highest‑risk toxic combinations. |
| Agents With Security Posture Findings | Metric | Indicates the number of unique AI agents that have at least one associated security posture finding. |
| Agents With Very High Posture Findings | Metric | Displays the number of AI agents that are associated with very high severity findings. |
| Highly Critical Security Posture Findings on Agents - by Rule Category | Treemap | Displays highly critical findings grouped by rule category, such as Encrypt Data at Rest, Access Control, and Privileged Access. The size of each block represents the number of findings in that category. |
| File Distribution by Severity | Bar chart | Displays the distribution of AI security posture findings across severity levels, including Very Low, Medium, High, and Very High. |
| Count of Posture Findings Related to AI Agents by Status | Bar chart | Displays the findings by remediation status, such as Open, Fixed, and Passed, letting you track remediation progress. |
| Security Posture Findings for AI Agents (Trend) | Trend Chart | Displays the trend of total AI security posture findings over the selected time range. |
| High Severity Posture Findings for AI Agents (Trend) | Trend Chart | Displays the trend of high‑severity findings over time. |
| AI Agents with Access Control Findings | Grid | Lists AI agents that violate access control rules, such as overly broad permissions or missing least‑privilege enforcement. Each row includes the rule name, region, applicable regulations, service, and asset details. |
| AI Agents with Encryption Findings | Grid | Displays AI agents with encryption‑related findings, such as missing customer‑managed keys or unencrypted data at rest. |
| AI Agents with Privileged Access Findings | Grid | Displays AI agents that operate with elevated or unnecessary privileged access. |
| Agents Ranked by Most Critical Security Posture Findings (Top 05) | Bar chart | Ranks the top five AI agents with the highest number of critical findings |
| Posture Findings for AI Agents by Region | Bar chart | Displays how AI security posture findings are distributed across regions, enabling geographic risk assessment. |
| Highly Critical Open Security Posture Findings on Agents | Grid | Lists highly critical findings that remain open. Each entry includes rule details, severity, hosting environment, and affected AI agent. |
| Top 10 AI Platform Security Posture Findings | Grid | Displays the top AI platforms with the highest number of security posture findings, including asset type and hosting cloud. |
| AI Platform Security Posture Findings by Cloud | Bar chart | Displays findings grouped by cloud provider, such as AWS and Azure. |
| Unencrypted Buckets with Sensitive Data Accessible by AI | Bar chart | Displays AWS and GCP Vertex storage buckets that contain sensitive data, are not encrypted, and are accessible by AI agents. |
| Sensitive Data Publically Accessible & Connected with AI Agents | Grid | Displays AI agents that have access to publicly exposed sensitive data, including asset details, hosting, and first‑seen timestamps. |
| Overview of AI agents with sensitive data and misconfigurations | Bar chart | Provides a consolidated view of AI agents that combine sensitive data access with misconfigurations, representing high‑risk toxic combinations. |
