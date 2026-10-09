---
title: "Securiti user roles in Cookie Consent Management"
slug: "securiti-user-roles-in-cookie-consent-management"
updated: 2026-08-31T21:12:20Z
published: 2026-08-31T21:12:20Z
canonical: "helpcenter.securiti.ai/securiti-user-roles-in-cookie-consent-management"
stale: true
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Securiti user roles in Cookie Consent Management

Securiti has the following user types:

| Type | Description |
| --- | --- |
| Internal | Users within your organization who have email addresses inside your corporate domain. |
| Partner | Users from managed services partners who have email addresses outside your corporate domain. Such partners might be companies with staff members who use Securiti on your organization's behalf to conduct assessments or process DSR requests. > [!NOTE] > **Note** > > In order for you to add a partner user: > > - The managed services organization must have a Securiti account of type "partner." > - The partner user must have an active user or admin account on the managed services organization's Securiti partner account. |
| Guest | Users without their own Securiti user accounts who have been invited to collaborate on assessments and other Securiti items. Guest users login to Securiti using links they receive via email. They have relatively limited privileges to use Securiti or make changes in it. |

Securiti has the following user roles:

| Role | Description |
| --- | --- |
| Super Admin | An administrator with access to all available Securiti functions and features for all organizations. |
| Org Admin | An administrator with access to all available Securiti functions and features for the organizations they belong to. |
| Operator | A Securiti operator with access to all functions and features except the ability to create and manage Securiti users. (Assessments only) You can't **bulk export assessments** except for which you're an owner. |
| Module Owner | A user who has privileges over a subset of Securiti modules (such as Assessment Automation, Data Subject Rights or both) equivalent to those held by a user with Super Admin role. To establish a user as a module owner, you assign them an access profile that gives them user privileges for the module, then set their role to “Module Owner.” |
| DPO | A Data Protection Officer who uses Securiti to ensure the safety and security of personal data. |
| User | A Securiti user who processes DSR subtasks as required to complete DSR requests from data subjects, or who addresses questions on assessments. |

> [!NOTE]
> **Note**
> 
> Other than **Super Admin** role, all users are restricted to operate on resources within their assigned organizations.

#### Cookie Consent Management user roles and permissions

Use the following table to understand the abilities of the various Securiti user roles and their permissions in the Cookie Consent Management module:

ALL = [Create, Read, Update, Delete, Manage]

| Permissions | Super Admin | Org Admin | Operator | Module Owner | DPO | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Cookie | ALL | ALL | ALL | ALL | Read | Read | No |
| Draft Cookie | ALL | ALL | ALL | ALL | Read | Read | No |
| Cookie Category | ALL | ALL | ALL | ALL | Read | Read | No |
| Draft Cookie Category | ALL | ALL | ALL | ALL | Read | Read | No |
| Domain Actions | ALL | ALL | *ALL (except Delete) | *ALL (except Delete) | Read | Read | No |
| Domain Group | ALL | ALL | ALL | ALL | Read | Read | No |
| Consent | ALL | ALL | ALL | ALL | Read | Read | No |
| Domain Scan | ALL | ALL | ALL | ALL | Read | Read | No |
| Policy Version | ALL | ALL | ALL | ALL | Read | Read | No |
| Current Policy Version | ALL | ALL | ALL | ALL | Read | Read | No |
| IAB EU GDPR Configuration | ALL | ALL | ALL | ALL | Read | Read | No |
| Draft IAB EU GDPR Configuration | ALL | ALL | ALL | ALL | Read | Read | No |
| Consent Management | ALL | ALL | ALL | ALL | Read | Read | No |
| Consent Banner | ALL | ALL | ALL | ALL | Read | Read | No |
| Banner Templates Gallery - Import System Templates | ALL | ALL | ALL | ALL | Read | Read | No |
| Banner Templates Gallery - Create Template | ALL | ALL | ALL | ALL | Read | Read | No |
| Banner Templates Gallery - Apply & Deploy Template | ALL | ALL | ALL | ALL | Read | Read | No |
| Banner Templates Gallery - Delete Template | ALL | ALL | ALL | ALL | Read | Read | No |
| Banner Templates Gallery - Clone Template | ALL | ALL | ALL | ALL | Read | Read | No |
| Banner Templates Gallery - Sync Template | ALL | ALL | ALL | ALL | Read | Read | No |
| Banner Templates Gallery - Preview Template | ALL | ALL | ALL | ALL | Read | Read | No |
| Deploy Domain | ALL | ALL | ALL | ALL | Read | Read | No |
| Bulk Scan Domains | ALL | ALL | ALL | ALL | Read | Read | No |
| Export Domain List | ALL | ALL | ALL | ALL | Read | Read | No |
| Bulk Generate Cookie Report | ALL | ALL | ALL | No | Read | Read | No |
| Bulk Change Domain Group | ALL | ALL | ALL | ALL | Read | ALL | No |
| Bulk Delete Domains | ALL | ALL | Read | Read | Read | Read | No |
| Bulk Deploy Domains | ALL | ALL | Read | Read | Read | Read | No |
| Customize Cookie Banner | ALL | ALL | ALL | Read | Read | Read | No |
| Custom CSS | ALL | ALL | Read | ALL | Read | Read | No |
| Consent Usage Metrics | ALL | No | No | No | No | No | No |
| Cookie Wall | ALL | ALL | ALL | ALL | No | No | No |
| Scan Over Scan Differences | ALL | ALL | ALL | ALL | No | No | No |
| Export Consent Data | ALL | No | No | No | No | No | No |
| Cross-Domain Consent Groups | ALL | ALL | ALL | ALL | Read | Read | No |
| Build with AI | ALL | ALL | No | ALL | No | No | No |
| Compliance Dashboard | ALL | ALL | Read | ALL | Read | Read | No |
