---
title: "Inventory: AI Models & Agents system dashboard"
slug: "inventory-ai-models-agents"
updated: 2026-08-18T14:21:35Z
published: 2026-08-18T14:21:35Z
canonical: "helpcenter.securiti.ai/inventory-ai-models-agents"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Inventory: AI Models & Agents system dashboard

The **Inventory: AI Models and Agents** dashboard provides a centralized view of all AI models, AI agents, and AI knowledge bases discovered across your organization. It helps you understand where AI assets are deployed, which cloud providers and services host them, how they are distributed geographically, and how they evolve. This dashboard supports OWASP LLM Risk 3 (AI Supply Chain)

![Dashboard displaying AI models, agents, and knowledge base counts for enterprise security.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_aimodelsandagents_dashboard.png)

> [!WARNING]
> Important
> 
> Dashboard widgets depend on preconfigured cloud assets and the presence of sensitive data in your cloud sources before scans are initiated. Ensure that Asset Discovery, Posture Scans, and Discovery Scans have completed successfully for data to appear in the widgets.
> 
> For more information, see Configuring [Discovery Scans](/latest/docs/discovery-scans), [Security Posture Scans](/latest/docs/getting-started-with-iaas-connectors), and [Asset Discovery](/latest/docs/viewing-asset-discovery-results-in-graph-explorer).

The table below provides an overview of the predefined widgets in the **Inventory: AI Models and Agents** dashboard.

| Widget title | Widget type | Description |
| --- | --- | --- |
| AI Models | Metric | Displays the total number of AI models discovered across your organization, including base, customized, and fine-tuned models. |
| AI Agents | Metric | Displays the total number of AI agents discovered across all connected cloud platforms. |
| AI Knowledge Base | Metric | Displays the total number of AI knowledge bases identified across supported AI services. |
| **OWASP LLM Risk 3: AI Supply Chain** |
| AI Models Across Regions | Map | Displays the geographic distribution of AI models by cloud provider and region. |
| AI Agents Across Regions | Map | Displays the geographic distribution of AI agents by cloud provider and region. |
| AI Models Count Over Time | Trend Chart | Shows how the total number of AI models changes over time. Use this trend to monitor growth, cleanup, or consolidation of models. |
| AI Models Count Over Time | Trend Chart | Shows how the total number of AI agents changes over time, helping you track adoption. |
| **Distribution by Cloud Hosting:** Model Hosting | Treemap | Breaks down AI models by hosting cloud provider, such as AWS, Azure, and GCP. |
| **Distribution by Cloud Hosting:** Agent Hosting | Treemap | Breaks down AI agents by hosting cloud provider, showing where runtime workloads operate. |
| **Distribution by Deployment Service:** Model Deployment | Bar chart | Displays how AI models are deployed across AI services such as Amazon Bedrock, Azure OpenAI, Vertex AI, and OpenAI. |
| **Distribution by Deployment Service:** Agent Deployment | Bar chart | Displays the distribution of AI agents by deployment service and agent type. |
| **Distribution by Model Provider:** Model Providers | Treemap | Displays the AI models grouped by model provider, helping you understand third-party dependencies and supply chain exposure. |
| **Distribution by Model Provider:** Model Providers Connected with AI Agents | Treemap | Displays which model providers are actively used by AI agents, highlighting runtime dependencies. |
| AI Models Inventory | Grid | Provides a detailed list of discovered AI models, including asset type, hosting cloud, region, and access links. |
| AI Agents Inventory | Grid | Provides a detailed list of discovered AI agents, including asset type, hosting cloud, region, and access links. |
| Base vs Customized Models Distribution | Bar chart | Compares the number of base models with customized or fine-tuned models to help assess customization risk. |
| Fine Tuned Models | Grid | Lists fine-tuned and customized models, including service, resource type, and hosting details. |
