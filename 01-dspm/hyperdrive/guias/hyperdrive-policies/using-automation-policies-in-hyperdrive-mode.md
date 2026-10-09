---
title: "Using Automation policies in Hyperdrive mode"
slug: "using-automation-policies-in-hyperdrive-mode"
status: "new"
updated: 2026-09-22T03:50:15Z
published: 2026-09-22T03:50:15Z
canonical: "helpcenter.securiti.ai/using-automation-policies-in-hyperdrive-mode"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Automation policies in Hyperdrive mode

Automation policies let you automate remediation workflows for findings and file entities that Securiti generates at runtime. You can define the policy scope and conditions, group related entities into work items, and configure actions for entities that match the policy criteria.

For supported entity types, grouping attributes determine how Securiti organizes related entities into work items. Grouping can reduce the number of individual work items when a policy includes a large number of findings or files.

Use the following table to understand the supported grouping attributes for each entity type:

| Grouping Attributes | Entity Type | Mandatory/Optional |
| --- | --- | --- |
| Asset Name | - File Insights - File Quarantine - File ROT | Optional |
| File Owner | Optional |
| Securiti Tag Category | Optional |
| Cloud Asset | - Security Posture Finding - Test Finding | Optional |
| Rule | Security Posture Finding | Optional |
| Data Asset | Structured Data Finding | Mandatory |
| Table | Optional |

> [!NOTE]
> Note
> 
> You can group an entity type by only one grouping attribute at a time.

For more information, see [Using Automation Policies](/latest/docs/using-automation-policies).

## Creating an Automation policy

You can create an Automation policy to define the scope and configure actions for matching findings or file entities. Depending on the configured action, Securiti can create ServiceNow tasks or Jira Cloud tickets, generate Security Command Center findings, or send email notifications. For more information, see [Creating an Automation policy](/latest/docs/creating-an-automation-policy-for-query-type).

## Using Automation templates

Automation templates let you reuse ServiceNow or Jira ticket configurations across multiple Automation policies instead of configuring the same ticket fields for each policy. You can clone system templates to create editable copies and manage your custom templates from the **Automation Templates** page. For more information, see [Using Automation Templates](/latest/docs/creating-an-automation-policy-for-query-type-1).
