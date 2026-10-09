---
title: "Risk Management RBAC permissions"
slug: "risk-management-rbac-permissions"
updated: 2026-09-29T07:13:52Z
published: 2026-09-29T07:13:52Z
canonical: "helpcenter.securiti.ai/risk-management-rbac-permissions"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Risk Management RBAC permissions

## Risk permissions with default roles

This table shows which Risk Management permissions are allowed or restricted for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | Super Admin | Org Admin | Operator | DPO | Module Owner | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `Read Risk` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Create Risk` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Risk` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Risk` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Assigned Risk` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Update Assigned Risk` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Delete Assigned Risk` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Update Assigned Risk Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Read Risk Dashboard` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Risk Settings` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Risk Settings` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Apply Risk Filters` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |

> [!NOTE]
> Note
> 
> The Module Owner column above applies whether that role was assigned through Assessment Automation, Vendor Assessment, Self Service Portal, or Data Mapping Automation. Module Owner status in any of these four modules grants full Create, Update, and Delete access to risks.

## Risk permissions with custom roles

Securiti lets you select fine-grained permissions for each custom role you create.

This table lists the Risk Management permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `Read Risk` | Lets you view risk records, export risks, and download the risk import template. | `Apply Risk Filters` |
| `Create Risk` | Lets you create risk records and bulk import risks. | `Read Risk` |
| `Update Risk` | Lets you make full or partial updates to a risk record. | `Read Risk`, `View All Tags`, `Apply Tags To Objects` |
| `Delete Risk` | Lets you delete a risk record. | `Read Risk`, `View All Tags` |
| `Read Assigned Risk` | Lets you view a risk you're assigned to and its attachments. | None |
| `Update Assigned Risk` | Lets you update a risk you're assigned to, including remediation proposals, approvals, send-backs, exception requests, and exception approvals. | `Read Assigned Risk` |
| `Delete Assigned Risk` | Lets you delete a risk you're assigned to. | `Read Assigned Risk` |
| `Update Assigned Risk Metadata` | Lets you update the status, level, deadline, and owner fields on a risk you're assigned to including risk description and tags, without full risk management access. For this to work, you must have a risk reviewer. | `Read Assigned Risk`, `Update Assigned Risk`, `Apply Tags To Object` |
| `Read Risk Dashboard` | Lets you view risk dashboard widgets and heatmap settings. | `Read Assigned Risk` |
| `Read Risk Settings` | Lets you view heatmap settings, calculate change impact, and list migration options. | None |
| `Update Risk Settings` | Lets you save heatmap settings, apply changes, and close pending migrations. | `Read Risk Settings` |
| `Apply Risk Filters` | Lets you choose and apply different filters from the list of available properties. | None |

> [!NOTE]
> Note
> 
> To link an object while creating a risk, you also need that object's read permission. For example, to link an assessment to a new risk, you need Read Assessment in addition to Create Risk.
