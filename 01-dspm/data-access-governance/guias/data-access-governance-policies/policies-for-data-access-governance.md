---
title: "Data Access Governance Policies"
slug: "policies-for-data-access-governance"
updated: 2026-09-22T06:39:41Z
published: 2026-09-22T06:39:41Z
canonical: "helpcenter.securiti.ai/policies-for-data-access-governance"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Data Access Governance Policies

## Overview

Data Access Governance (DAG) policies let you define rules that continuously monitor and control access to sensitive data and how that data moves across your environment. Each policy evaluates your data and access activity against the conditions you set, such as a user's role, location, or the sensitivity of the data involved, and takes action when those conditions are met.

You configure a policy once, and Securiti evaluates it continuously as new activity occurs, so you don't have to review access or transfers manually. This category includes the following policy types.

## Data Access Control Policies

Data Access Control Policies give you a centralized framework to enforce fine-grained access control across your structured and unstructured data systems, restricting access to files, folders, databases, tables, and columns for specific users and groups. You can apply masking, enforce least-privileged access through privilege conditions, and define row filters based on data sensitivity, location, and applicable regulations. Before a policy is enforced, you can preview its impact on your data systems and roll back to a prior state using automatic backups.

- Enforce fine-grained access using masking, privilege conditions, and row filters
- Preview a policy's impact before enforcement, with automatic backup and rollback
- Supported for Databricks, Snowflake, Google BigQuery, Microsoft 365 SharePoint Online, and more

For more information, refer to [Using Data Access Control Policies](/latest/docs/access-control-policies).

## Cross Border Transfer Policies

Cross Border Transfer Policies let you monitor and control the movement of data across geographic or jurisdictional boundaries. They help you track where sensitive data is being sent, both within and outside your organization, and compare that movement against your data residency requirements. Use these policies to flag or block transfers that violate regional data protection regulations before they happen.

- Track cross-border data flows in real time
- Enforce data residency and regulatory requirements (e.g. GDPR, data localization laws)
- Flag or block non-compliant transfers automatically

For more information, refer to [Using Cross Border Transfer Policies](/latest/docs/using-cross-border-transfer-policies).
