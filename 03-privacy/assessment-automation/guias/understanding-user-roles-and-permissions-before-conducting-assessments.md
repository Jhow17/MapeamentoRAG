---
title: "Assessment roles and default user permissions"
slug: "understanding-user-roles-and-permissions-before-conducting-assessments"
updated: 2026-09-23T10:09:56Z
published: 2026-09-23T10:09:56Z
canonical: "helpcenter.securiti.ai/understanding-user-roles-and-permissions-before-conducting-assessments"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Assessment roles and default user permissions

The tables below describe the Securiti user types and roles, and their various abilities.

| Type | Description |
| --- | --- |
| Internal | Users within your organization who have email addresses inside your corporate domain. |
| Partner | Users from managed services partners who have email addresses outside your corporate domain. Such partners might be companies with staff members who use Securiti on your organization's behalf to conduct assessments. > [!NOTE] > **Note** > > In order for you to add a partner user: > > - The managed services organization must have a Securiti account of type "partner." > - The partner user must have an active user or admin account on the managed services organization's Securiti partner account. |
| Guest | Users without their own Securiti user accounts who have been invited to collaborate on assessments and other Securiti items. Guest users log in to Securiti using links they receive via email. They have relatively limited privileges to use Securiti or make changes in it. |

| Role | Description |
| --- | --- |
| Super Admin | An administrator with access to all available Securiti functions and features for all orgs. > [!NOTE] > **Note** > > You must also be the assessment owner or added as a reviewer to update the assessment title. |
| Org Admin | An administrator with access to all available Securiti functions and features for the orgs they belong to. |
| Operator | A Securiti operator with access to all functions and features except the ability to create and manage Securiti users. > [!NOTE] > **Note** > > You can't bulk export assessments. You can only export individual assessments via their details page. |
| Module Owner | A user with privileges over a subset of Security modules (such as Assessment Automation) is equivalent to those held by a user with a Super Admin role. To establish a user as a module owner, you assign them an access profile that gives them user privileges for the module, then set their role to “Module Owner.” |
| DPO | A Data Protection Officer who uses Securiti to ensure the safety and security of personal data. |
| User | A Securiti user who addresses questions on assessments. |

## Assessment permissions with default roles

This table shows which Assessment Automation permissions are allowed or restricted for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents restricted access.

| Permission | Super Admin | Org Admin | Operator | DPO | Module Owner | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `Read Assigned Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Update Assigned Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Delete Assigned Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Create Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Assignment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `View Assessment Dashboard` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Review Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Read Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Create Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Assessment Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Assessment Workflow Stage` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Workflow Stage` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Assessment Notification Templates` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Create Assessment Notification Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Assessment Notification Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Assessment Notification Template` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Apply Assessment Filters` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Unmask Emails` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |

> [!NOTE]
> Note
> 
> If Guest User Unmasking is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. When enabled, guest users cannot access the assessment messaging channel. Guest users can still communicate with reviewers through the comments panel.

For more information, see [RBAC permissions with custom roles](/latest/docs/rbac-permissions-with-custom-roles).
