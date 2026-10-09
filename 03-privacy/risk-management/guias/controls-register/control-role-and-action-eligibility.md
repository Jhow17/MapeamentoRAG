---
title: "Control role and action eligibility"
slug: "control-role-and-action-eligibility"
updated: 2026-09-08T09:45:43Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/control-role-and-action-eligibility"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Control role and action eligibility

This article explains who can perform each control action, including cases where eligibility depends on being a control's owner, reviewer, or general control user, rather than holding a module-wide permission.

## Create Control

| Role | From the Controls Register | From a risk's details page |
| --- | --- | --- |
| A custom role with Create Control | Yes | Yes |
| A custom role with Create Assigned Control | No | Yes |

## Update Control Fields

Covers a control's name, description, deadline, and expiry date.

| Role | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| A custom role with Update Control | Yes | N/A | N/A |
| A custom role with Update Assigned Control | N/A | Yes | Must be a control user |

## Delete Control

| Role | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| A custom role with Delete Control | Yes | N/A | N/A |
| A custom role with Delete Assigned Control | N/A | Yes | Must be a reviewer |

## Change Control State

| Role | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| A custom role with Update Control | Yes | N/A | N/A |
| A custom role with Update Assigned Control | N/A | Yes | Must be a control user |

> [!NOTE]
> Note
> 
> Securiti also sets a control's status to Expired automatically once its expiry date passes. This happens independently of the permissions above and isn't performed by any user.

## Effectiveness Rating

| Role | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| A custom role with Update Control | Yes | N/A | N/A |
| A custom role with Update Assigned Control | N/A | Yes | Must be a control user |

## Owners and Reviewers

> Only users who already have Read Control or Read Assigned Control can be added as an owner or reviewer.

| Action | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| Add owner | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |
| Add reviewer | Yes, with Update Control | Yes, with Update Assigned Control | Must be a reviewer |
| Remove owner | Yes, with Update Control | Yes, with Update Assigned Control | Must be a reviewer |
| Remove reviewer | Yes, with Update Control | Yes, with Update Assigned Control | Must be a reviewer |

## Attachments

| Action | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| Upload | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |
| Remove | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |
| Download | Yes, with Read Control | Yes, with Read Assigned Control | Must be a control user |

## Links

| Action | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| Add link | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |
| Remove link | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |

## Comments

| Action | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| Post a public comment | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |
| Post a private comment | Yes, with Update Control | Yes, with Update Assigned Control | Must be a reviewer |
| View public comments | Yes, with Read Control | Yes, with Read Assigned Control | Must be a control user |
| View private comments | Yes, with Read Control | Yes, with Read Assigned Control | Must be a reviewer |

## Compliance Control and Compliance Frameworks

Setting or clearing a compliance control needs Read Compliance Control as well. Linking or unlinking a compliance framework needs Read Compliance Framework as well.

| Action | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| Set or clear compliance control | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |
| Link or unlink compliance framework | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |

## Linked Risks

Linking or unlinking a risk needs Read Risk or Read Assigned Risk as well.

| Action | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| Link risk | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |
| Unlink risk | Yes, with Update Control | Yes, with Update Assigned Control | Must be a control user |

## Tags

Adding or removing a tag needs View All Tags and Apply Tags To Objects as well.

| Role | Any control | Assigned control only | Condition |
| --- | --- | --- | --- |
| A custom role with Update Control | Yes | N/A | N/A |
| A custom role with Update Assigned Control | N/A | Yes | Must be a control user |

## Import and Export

| Action | Any control | Assigned control only |
| --- | --- | --- |
| Import controls | Yes, with Create Control | Not available |
| Download import template | Yes, with Read Control | Not available |
| Export controls | Yes, with Read Control | Yes, with Read Assigned Control (must be a control user) |
| Export evidence | Yes, with Read Control | Yes, with Read Assigned Control (must be a control user) |

## Guest Users

A guest user invited to a control directly is provisioned with a role that grants:

- Read Assigned Control, to view controls they're assigned to
- Update Assigned Control, to interact with controls they own

Guest users can't be added as reviewers on a control, since reviewer status requires Update Assigned Control on a non-guest account.
