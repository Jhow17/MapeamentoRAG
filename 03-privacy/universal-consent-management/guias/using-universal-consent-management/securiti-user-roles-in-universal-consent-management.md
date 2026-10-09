---
title: "Securiti user roles in Universal Consent Management"
slug: "securiti-user-roles-in-universal-consent-management"
updated: 2026-04-21T08:22:56Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/securiti-user-roles-in-universal-consent-management"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Securiti user roles in Universal Consent Management

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
| Operator | A Securiti operator with access to all functions and features except the ability to create and manage Securiti users. (Assessments only) You can't **bulk export assessments** except for which you are an owner. |
| Module Owner | A user who has privileges over a subset of Securiti modules (such as Assessment Automation, Data Subject Rights or both) equivalent to those held by a user with Super Admin role. To establish a user as a module owner, you assign them an access profile that gives them user privileges for the module, then set their role to “Module Owner.” |
| DPO | A Data Protection Officer who uses Securiti to ensure the safety and security of personal data. |
| User | A Securiti user who processes DSR subtasks as required to complete DSR requests from data subjects, or who addresses questions on assessments. |

> [!NOTE]
> **Note**
> 
> Other than **Super Admin** role, all users are restricted to operate on resources within their assigned organizations.

The following table describes the abilities of the various Securiti user roles and their permissions in the Universal Consent Management module:

### Universal Consent Management user roles and permissions

ALL = [Create, Read, Update, Delete, Manage]

| Permissions | Super Admin | Org Admin | Operator | Module Owner | DPO | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Form Endpoint | ALL | ALL | ALL | ALL | Read | Read | No |
| Consent Purpose | ALL | ALL | ALL | ALL | Read | Read | No |
| Form Preference | ALL | ALL | ALL | ALL | Read | Read | No |
| Purpose Consent | ALL | ALL | ALL | ALL | Read | Read | No |
| Custom Parameter | ALL | ALL | ALL | ALL | Read | Read | No |
| Form Information | ALL | ALL | ALL | ALL | Read | Read | No |
| Draft Form Information | ALL | ALL | ALL | ALL | Read | Read | No |
| Consent Management | ALL | ALL | ALL | ALL | Read | Read | No |
| Processing Purpose | ALL | ALL | ALL | ALL | Read | Read | No |
| Form Endpoint Owner | ALL | ALL | ALL | ALL | Read | Read | No |
| Purpose User Validation Token | ALL | ALL | ALL | ALL | Read | Read | No |
| Delete Consent Records | ALL | ALL | Read | ALL | Read | Read | No |
| Bulk Upload Consent Records | ALL | ALL | ALL | ALL | Read | Read | No |
| Export Consent Data | ALL | No | No | No | No | No | No |
| Webhook Update | ALL | ALL | ALL | ALL | Read | Read | No |
| Unique Subject Identifier | *ALL (except Delete) | *ALL (except Delete) | Read | *ALL (except Delete) | Read | Read | No |
| Rules Matrix | ALL | ALL | Read | ALL | Read | Read | No |
| Privacy Platform Integrations | ALL | ALL | Read | *ALL (except Delete) | Read | No | No |
| Consent Usage Metrics | ALL | No | No | No | No | No | No |
| Preference Center Email Templates | ALL | ALL | Read | Read | Read | Read | No |

## Related

- [Organization-level access in Universal Consent](/organization-level-access-in-universal-consent.md)
