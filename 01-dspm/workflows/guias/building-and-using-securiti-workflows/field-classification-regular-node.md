---
title: "Field Classification"
slug: "field-classification-regular-node"
updated: 2026-02-12T14:30:48Z
published: 2026-02-12T14:30:48Z
canonical: "helpcenter.securiti.ai/field-classification-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Field Classification

Operate on classifications found in structured data system

| Parameter | Description |
| --- | --- |
| Data Source Name | Data system instance name in Securiti |
| Operation | List | List field classifications of selected data system |
| Match PD Types | When enabled, accepts a list of PD types to match incoming classifications. "Contains PD" flag is raised only if incoming classifications contain matching PD |
| PD Type | Build a list of PD types to match to incoming classifications |

> [!NOTE]
> **Note**
> 
> - To use the field classification node, use the **Cron Trigger** in active mode.
> - Every time the field classification node is executed, it returns one page as a result with 25 tables. The pipeline is executed on these 25 items and the next execution brings the next 25 tables and so on. When all the pages are processed, the node doesn’t emit any item which means that succeeding nodes in the pipeline won’t run.
