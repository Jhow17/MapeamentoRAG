---
title: "Agent Activity"
slug: "undo-ai-dashboard"
updated: 2026-09-23T11:01:08Z
published: 2026-09-23T11:01:08Z
canonical: "helpcenter.securiti.ai/undo-ai-dashboard"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Agent Activity

**Scenario**

As a Data Security Officer, you must monitor how AI agents interact with sensitive data in Microsoft 365. Reviewing scattered logs across systems makes it difficult to detect risky file changes quickly. After deploying a new AI agent, you notice unusual modifications in SharePoint. Using the Agent Activity application, you first assess exposure in Microsoft 365 Data and AI Security dashboard, then investigate detailed events in Agent Activity Overview. You identify the exact files modified and revert them using restore points. You contain the issue quickly and maintain control over AI-driven automation.

## Overview

> [!WARNING]
> Important
> 
> - If Agent Activity is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
> - The **Microsoft 365 Data and AI Security** dashboard (Hyperdrive) is available only for tenants with **Hyperdrive** mode enabled.

The **Agent Activity** application in Securiti provides end-to-end visibility and control over how AI agents, applications, and users interact with your data. It helps you understand what data AI agents can access, what actions they perform, and how those actions impact your organization’s data security and compliance posture.

Agent Activity includes two integrated dashboards:

- **Agent Activity Overview**, which delivers detailed, event-level monitoring and investigation through audit logs. For more information, see [Agent Activity Overview dashboard](/latest/docs/agent-activity-overview-dashboard).
- **Agent Activity Timeline**, which is a dedicated page for chronological activity analysis across agents and data systems, and for undoing or reverting AI-driven changes. For more information, see [Using Agent Activity Timeline](/latest/docs/using-agent-activity-timeline).
- **Microsoft 365 Data and AI Security** dashboard (Hyperdrive), which is a graph reporting dashboard providing a risk-focused overview of AI agents, applications, and their access to Microsoft 365 data via widgets. For more information, see [Microsoft 365 Data and AI Security dashboard (Hyperdrive)](/latest/docs/agent-commander-dashboard).

## Prerequisites

You must have fulfil the following prerequisites for data to be populated in the dashboard:

- Configure and activate your Hyperdrive data system connector. For more information, see [Hyperdrive data systems](/latest/docs/data-systems).
- To view Veeam’s protection data and use Undo AI capability, configure and activate Veeam Data Cloud (VDC) connector integration. For more information, see [Veeam Data Cloud integration documentation](/latest/docs/veeam-data-cloud-integration).
- Enable the following scans for your data system connector:
  - Data Inventory Sync
  - Entitlement Scan
  - Activity Analysis

For more information, see your Hyperdrive data system’s documentation and [Activity Analysis using Hyperdrive](/latest/docs/activity-analysis).

## Key capabilities

With the Agent Activity, you can:

- Monitor AI agents and applications accessing Microsoft 365 data.
- Understand the volume and sensitivity of data exposed to AI agents.
- Identify broadly shared files and potential data exposure risks.
- Track detailed activities performed by AI agents, users, and applications.
- Visualize activity patterns over time using timeline analysis.
- Detect external access and high-risk actions such as modifications and deletions.
- Undo an AI action or revert to a restore point to reverse AI-driven changes.

##
