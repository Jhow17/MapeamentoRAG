---
title: "Deployment RBAC permissions and roles"
slug: "deployment-rbac-permissions-and-roles-en"
description: "Manage user permissions with Securiti's RBAC framework, offering fine-grained access control for deployment functionalities and custom role creation."
updated: 2026-09-29T08:40:43Z
published: 2026-09-29T08:40:43Z
canonical: "helpcenter.securiti.ai/deployment-rbac-permissions-and-roles-en"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Deployment RBAC permissions and roles

Securiti provides an RBAC framework to manage user permissions. In the Deployment module, these permissions control access to deployment-related functionalities. The fine-grained permissions provide access control from viewing the details of pods to creation of pods.

RBAC includes both default roles and custom roles. You can assign a default role to a user or create a custom role with specific permissions. Each default role contains a predefined set of permissions from the Deployment module.

## Accessing Deployment permissions

To navigate to Deployment RBAC permissions in Securiti Platform, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Settings** from the left navigation bar.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deployment-rbac-permissions-and-roles-en-image-2euwd1iq.png)

1. Under the **Organizational**, choose **Access Management > Roles**.
2. On the **Roles** page, select **+ Create Role**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deployment-rbac-permissions-and-roles-en-image-lin49x8e.png)

1. Under the **Permissions** section, click the **Deployment** tab to access the Deployment permissions, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deployment-rbac-permissions-and-roles-en-image-t8j59sb6.png)

## Deployment permissions with default roles

This table shows which Deployment permissions are allowed or disallowed for each system-generated role. A check mark(✅) indicates allowed access, while a cross (❌) represents no access.

| **Permission** | **Super Admin** | **Operator** | **DPO** | **Organization Admin** | **MODULE OWNER** | **Gencore Admin** | **Firewall Admin** | **Gencore Pipe Builder** | **Gencore Reader** | **USER** | **Data Classification Manager** | **SDI Evidence Analyst** | SDI Analyst | **SDI Classification Reviewer** | **Discovery Scan Manager** | **MODULE OWNER Self Service Portal User Profile ROLE** | **GUEST Self Service Portal User Profile ROLE** | **MODULE OWNER Data map User Profile ROLE** | **USER DSR User Profile ROLE** | **MODULE OWNER Data Breach User Profile ROLE** | **DATA USER** | **GUEST Data map User Profile ROLE** | **USER Data map User Profile ROLE** | **USER Self Service Portal User Profile ROLE** | **MODULE OWNER DSR User Profile ROLE** | **GUEST DSR User Profile ROLE** | **Provider Manager** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `Configure My Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Generate Diagnostic Report of Deployments` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View My Deployments` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Deployment` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete All Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update All Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete My Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Revoke My Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Configure All Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View All Deployments` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update My Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Revoke All Deployments` | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

## Deployment permissions with custom roles

Securiti lets you select fine-grained permissions for each custom role you create in the Deployments.

**Definitions**

- **Permission**: It is a parent permission that grants specific rights to perform certain actions within the system. For example, `View Data System`, `Update Keying`, and `Delete Data System Driver`.
- **Explanation:** Describes why the permission is needed and the context in which it is used. For example, the Create and Activate Data System permission is required to create a data system and activate its connector.
- **Dependent permissions:** These are a set of permissions that are automatically applied in the same or different modules when a parent permission is selected.

This table lists the Deployment permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `Configure My Deployments` | This permission lets the user to configure backup and restore settings for pods and Epods they own. | **Deployments****:** - `ViewMy Deployments` - `Generate Diagnostic Report of Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `Delete All Deployments` | This permission allows the user to delete any pod in the system. | **Deployments:** - `View My Deployments` - `View All Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `Update All Deployments` | This comprehensive permission provides administrative rights to edit, revoke access, and configure backup/restore settings for all pods and epods. | **Deployments:** - `View My Deployments` - `Generate Diagnostic Report of Deployments` - `Create Deployments` - `Configure All Deployments` - `View All Deployments` - `Revoke All Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `Delete My Deployments` | This permission allows visibility into the list and details of pods and epods the user owns. | **Deployments:** - `View My Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `Revoke My Deployments` | This permission grants the ability to revoke pods and epods that the user owns. | **Deployments:** - `View My Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `Configure All Deployments` | This permission grants the ability to configure backup and restore settings for all pods and epods in the system. | **Deployments:** - `View My Deployments` - `View All Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `View All Deployments` | This permission allows visibility into the list and details of all pods and epods throughout the system. | **Deployments:** - `View My Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `Update My Deployments` | This comprehensive permission provides administrative rights to edit, revoke access, and configure backup/restore settings for all pods and epods user owns. | **Deployments:** - `View My Deployments` - `Generate Diagnostic Report of Deployments` - `Create Deployments` - `Configure All Deployments` - `Revoke My Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |
| `Revoke All Deployments` | This permission grants the ability to revoke all pods and epods throughout the system. | **Deployments:** - `View My Deployments` - `View All Deployments` **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) |

## Related

- [Pods (cluster version v1.28 and later)](/pods-cluster-version-v128-and-later.md)
- [Elastic Pods V2](/elastic-pods-v2.md)
- [Securiti Hosted Scanning](/securiti-hosted-scanning.md)
