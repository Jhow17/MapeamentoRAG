---
title: "Securiti user roles in Mobile App Consent Management"
slug: "securiti-user-roles-in-mobile-app-consent-management"
updated: 2026-09-03T09:18:10Z
published: 2026-09-03T09:18:10Z
canonical: "helpcenter.securiti.ai/securiti-user-roles-in-mobile-app-consent-management"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Securiti user roles in Mobile App Consent Management

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

The following table describes the abilities of the various Securiti user roles and their permissions in the Mobile App Consent Management module:

## Mobile App Consent Management user roles and permissions

ALL = [Create, Read, Update, Delete, Manage, List]

| Permissions | Super Admin | Org Admin | Operator | Module Owner | DPO | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Mobile App Consent Dashboard | ALL | ALL | ALL | ALL | Read | Read | No |
| Mobile Application | ALL | ALL | ALL | ALL | Read | Read | No |
| Upload File and App Scan | ALL | ALL | ALL | ALL | Read | Read | No |
| Purposes | ALL | ALL | ALL | ALL | Read | Read | No |
| SDKs | ALL | ALL | ALL | ALL | Read | Read | No |
| Permissions | ALL | ALL | ALL | ALL | Read | Read | No |
| Export Reports | ALL | ALL | ALL | ALL | Read | Read | No |
| SDK and Permissions Library | ALL | ALL | Read | ALL | Read | Read | No |
| SDK and Permissions Library (Bulk Edit) | Yes | Yes | Read | Yes | Read | Read | No |
| SDK and Permissions Library (Bulk Delete and Remove) | Yes | Yes | Read | Yes | Read | Read | No |
| Export Consent Data | ALL | No | No | No | No | No | No |
