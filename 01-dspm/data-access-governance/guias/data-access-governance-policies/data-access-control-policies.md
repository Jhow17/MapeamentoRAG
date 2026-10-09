---
title: "Data Access Control Policies"
slug: "data-access-control-policies"
status: "update"
updated: 2026-09-25T04:22:58Z
published: 2026-09-25T05:06:07Z
canonical: "helpcenter.securiti.ai/data-access-control-policies"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Data Access Control Policies

## Overview

**Scenario**

As a Data Security Officer, you're responsible for limiting access to sensitive data across multiple systems. Manually updating user permissions in each system is inefficient and increases the risk of exposure. With Access Control Policies, you centrally enforce fine-grained restrictions based on data classification across all connected data systems. This ensures only the right users access sensitive data, saving time and reducing security risks.

Every large enterprise grants more access than it can track. Permissions accumulate across data warehouses, lakehouses, and collaboration systems, and each Data system enforces them in its own way, with its own console, syntax, and administrators.

Data Access Control Policies replace that fragmentation with a single control plane for your structured and unstructured Data Systems. You define access once, in business terms, and Securiti translates the policy into the native controls of each Data System in scope. You can preview the exact changes before anything is enforced, and Securiti backs up every enforced state so you can roll back.

Each policy scopes the data it governs using insights from data discovery, such as sensitivity, classification, data location, and applicable regulations. Because the scope follows what the data is rather than where it sits, your access controls stay accurate as your data changes.

Using Data Access Control Policies, you can:

- Grant or revoke access to files, folders, databases, tables, and columns for specific users and groups.
- Mask sensitive columns so that users see only the values relevant to their work.
- Apply row filters so that users see only the records they are authorized to access.
- Enforce privilege conditions that maintain a least-privileged access model.

> [!NOTE]
> Note
> 
> If Data Access Control Policies are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### How Data Access Control Policies work

A policy moves through the following stages:

- **Scope**: You select the Data System and use Graph Explorer to define the entities the policy governs, such as databases, schemas, tables, columns, files, and folders.
- **Rules**: You define the privileges, masking functions, and row filters that apply to the selected users and groups.
- **Preview**: For Data Systems that support Policy Preview, Securiti shows you the exact entities, privileges, row filters, and masking functions the policy applies. Execution starts only after you accept the preview.
- **Enforcement and rollback**: Securiti creates a backup each time you create, update, or delete a policy, so you can restore any previous state.
- **Re-evaluation**: Securiti re-evaluates policies automatically when a discovery scan completes or access relationships change, so policy states stay current without manual intervention.

The Data Access Control Policies page gives you a single view of every defined policy, along with its current state and owner, so you can create, filter, and manage policies centrally.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.

Data access control is the access to a resource (file, folder, database, table, column, etc.) for a particular set of users and groups. You can create access control policies to enforce authorized access to your organization's resources.
