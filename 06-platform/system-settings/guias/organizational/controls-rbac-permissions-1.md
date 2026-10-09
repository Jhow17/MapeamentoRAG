---
title: "Controls RBAC permissions"
slug: "controls-rbac-permissions-1"
updated: 2026-09-29T07:14:45Z
published: 2026-09-29T07:14:45Z
canonical: "helpcenter.securiti.ai/controls-rbac-permissions-1"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Controls RBAC permissions

## Control permissions with default roles

This table shows which Controls Register permissions in Risk Management are allowed or restricted for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | Super Admin | Org Admin | Operator | DPO | Module Owner | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Create Control | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Read Control | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Update Control | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Delete Control | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| Create Assigned Control | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Read Assigned Control | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Update Assigned Control | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Delete Assigned Control | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |

> [!NOTE]
> **Note**
> 
> Guest access varies by how the guest was invited. A guest invited to a control directly gets Read and Update only, as shown above. A guest invited through an assessment can also get Create. Neither type of guest can be added as a reviewer.

## Control permissions with custom roles

Securiti lets you select fine-grained permissions for each custom role you create.

This table lists the Controls Register permissions in Risk Management, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| Create Control | Lets you create a new control from the Controls Register. | None |
| Read Control | Lets you view any control, regardless of whether you're assigned to it. | None |
| Update Control | Lets you update any control's fields, state, and effectiveness rating, manage its owners and reviewers, and upload attachments, add links, and post comments, regardless of whether you're assigned to it. | None |
| Delete Control | Lets you delete any control, regardless of whether you're assigned to it. | None |
| Create Assigned Control | Lets you create a control from a risk's details page. You can't create a control this way from the Controls Register. | None |
| Read Assigned Control | Lets you view a control you're assigned to. | None |
| Update Assigned Control | Lets you update a control you're assigned to, including its fields, state, and effectiveness rating. | None |
| Delete Assigned Control | Lets you delete a control you're assigned to, if you're a reviewer on it. | None |

> [!NOTE]
> **Note**
> 
> Linking a control to a compliance control or framework needs Read Compliance Control or Read Compliance Framework as well. Linking a control to a risk needs Read Risk or Read Assigned Risk. Tagging a control needs View All Tags and Apply Tags To Objects. For the full set of conditions on who can perform each control action, see [Control role and action eligibility](/latest/docs/control-role-and-action-eligibility).
