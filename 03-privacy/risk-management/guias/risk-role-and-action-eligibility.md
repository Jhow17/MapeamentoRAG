---
title: "Risk role and action eligibility"
slug: "risk-role-and-action-eligibility"
updated: 2026-09-01T12:05:18Z
published: 2026-09-01T12:05:18Z
canonical: "helpcenter.securiti.ai/risk-role-and-action-eligibility"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Risk role and action eligibility

This article explains who can perform each risk action, including cases where eligibility depends on being assigned to that specific risk or reviewing the assessment it's linked to, rather than holding a module-wide permission.

## Read Risk

| Role | All risks in system | Assigned risk only |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, Module Owner, Vendor Assessment Module Owner | Yes | N/A |
| A custom role with Read Assessment | Yes | N/A |
| User, Assessment User, Vendor Assessment User | N/A | Yes |
| A custom role with Read Assigned Risk | N/A | Yes |

## Export Risk

| Role | All risks in system |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, Module Owner, Vendor Assessment Module Owner | Yes |
| A custom role with Read Assessment | Yes |

## Update Risk

| Role | Any risk | Assigned risk only | Condition |
| --- | --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, Module Owner, Vendor Assessment Module Owner | Yes | N/A | N/A |
| A reviewer on the assessment | Yes | N/A | Only for risks linked to that particular assessment |
| User, Assessment User, Vendor Assessment User | N/A | Yes | Must be a reviewer on the assessment |
| A custom role with Update Assigned Risk Metadata | N/A | Yes | Must be a risk reviewer |

## Create Risk

| Role | Can create | Notes |
| --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, Module Owner, Vendor Assessment Module Owner | Yes | N/A |
| A reviewer on the assessment | Yes | Can create and update the risk linked to an assessment question |
| A custom role with Create Risk | Yes | N/A |

To link an object while creating a risk, you also need that object's read permission. See the Create Risk permission in the Risk Management RBAC permissions article for details.

## Import Risk

| Role | Can import |
| --- | --- |
| Super Admin, Org Admin, Operator, DPO, Module Owner | Yes |
| A custom role with Create Risk | Yes |

## Delete Risk

| Role | Any risk | Assigned risk only | Condition |
| --- | --- | --- | --- |
| Super Admin, Org Admin, Operator, DPO | Yes | N/A | N/A |
| A custom role with Delete Risk | Yes | N/A | N/A |
| Assessment Module Owner, Module Owner, Vendor Assessment Module Owner | Yes | N/A | N/A |
| User, Assessment User, Vendor Assessment User | N/A | Yes | Must be a reviewer on that assigned risk |
| A custom role with Delete Assigned Risk | N/A | Yes | Must be a reviewer on the risk |

## Risk Owner and Risk Reviewer Eligibility

| Role | Can be risk owner | Can be risk reviewer |
| --- | --- | --- |
| Super Admin | Yes | Yes |
| Org Admin | Yes | Yes |
| Operator | Yes | Yes |
| DPO | Yes | Yes |
| Assessment Module Owner | Yes | Yes |
| Module Owner | Yes | Yes |
| Vendor Assessment Module Owner | Yes | Yes |
| User | Yes | Yes |
| Assessment User | Yes | Yes |
| Vendor Assessment User | Yes | Yes |
| Guest User | Yes, through an email invite | No |
| A custom role with Update Assigned Risk | Yes | Yes |

## Risk Settings

| Action | Who |
| --- | --- |
| Read Risk Settings | Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, Module Owner, or a custom role with Read Risk Settings |
| Update Risk Settings | Super Admin, Org Admin, Operator, DPO, Assessment Module Owner, Module Owner, or a custom role with Update Risk Settings |

For more information, see [Risk Management RBAC permissions](/latest/docs/risk-management-rbac-permissions).
