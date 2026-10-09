---
title: "Vendor Assessment role and action eligibility"
slug: "vendor-assessment-role-and-action-eligibility"
updated: 2026-09-01T11:53:45Z
published: 2026-09-01T11:53:45Z
canonical: "helpcenter.securiti.ai/vendor-assessment-role-and-action-eligibility"
area: privacy
modulo: vendor-assessments
tipo: guia
data_captura: 2026-10-08
---

# Vendor Assessment role and action eligibility

This article explains who can perform each vendor assessment action, including cases where a custom role needs more than one permission together to complete the action.

## Read Vendor Assessment

| Role | All vendor assessments | Assigned only |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner | Yes | N/A |
| A custom role with Read Vendor Assessment and Read Vendor | Yes | N/A |
| Assessment User, Vendor Assessment User | N/A | Yes |
| A custom role with Read Assigned Assessment and Read Vendor | N/A | Yes |

## Create Vendor Assessment (via Invite Vendor)

| Role | Can create |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner | Yes |
| A custom role with Invite Vendor | Yes |

## Delete Vendor Assessment

| Role | All vendor assessments | Assigned only |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner | Yes | N/A |
| A custom role with Delete Vendor Assessment | Yes | N/A |
| Assessment Reviewer | N/A | Yes |
| Assessment Reviewer | N/A | Yes |

## Create Vendor

| Role | Can create |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner | Yes |
| A custom role with Read Vendor, Create Vendor, and either Read Vendor Assessment or Read Assigned Assessment | Yes |

## Import Vendor via CSV

| Role | Can import |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner | Yes |
| A custom role with Read Vendor, Create Vendor, and either Read Vendor Assessment or Read Assigned Assessment | Yes |

## Export Vendor

| Role | Can export |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner, Assessment User, Vendor Assessment User | Yes |
| A custom role with Read Vendor and either Read Vendor Assessment or Read Assigned Assessment | Yes |

## Delete Vendor

| Role | Can delete |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner | Yes |
| A custom role with Read Vendor, Delete Vendor, and either Read Vendor Assessment or Read Assigned Assessment | Yes |

## Vendor Assessment Dashboard

| Role | Can view |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner, Assessment User, Vendor Assessment User | Yes |
| A custom role with View Vendor Assessment Dashboard | Yes |

## Vendor Explorer

| Role | Can view |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner, Assessment User, Vendor Assessment User | Yes |
| A custom role with View Vendor Explorer | Yes |

## Vendor Import Manager

| Role | Can view |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner, Assessment Module Owner, Vendor Assessment Module Owner | Yes |
| A custom role with Manage Vendor Bulk Import | Yes |

For more information, see [Vendor Assessment RBAC permissions](/latest/docs/vendor-assessments-rbac-permissions).
