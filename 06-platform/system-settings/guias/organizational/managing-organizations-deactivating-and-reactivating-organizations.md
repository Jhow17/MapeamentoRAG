---
title: "Deactivating and reactivating organizations"
slug: "managing-organizations-deactivating-and-reactivating-organizations"
updated: 2025-10-30T19:14:13Z
published: 2025-11-03T06:11:41Z
canonical: "helpcenter.securiti.ai/managing-organizations-deactivating-and-reactivating-organizations"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Deactivating and reactivating organizations

You cannot delete organizations once you create them; you can only deactivate them. Once you deactivate the organization, all of its elements or properties become read-only. You may be able to move or copy them to a different organization, but you can no longer change them. If you later reactivate the organization, you can again edit its elements and properties.

### Deactivating an organization

> [!NOTE]
> **Important**
> 
> In order to deactivate an organization, you must delete all of the DSR forms belonging to it.
> 
> In the case of assessments, delete all of the assessments (internal and vendor) in that organization or move them to a different organization. For Vendor Assessments, you must also delete the vendor from the system in order to deactivate the organizaton.
> 
> For Data Maps, you must delete all of the data mapping entities (assets, vendors, processes, institutions).

1. Log in to Securiti with your super admin credentials (only super admins can deactivate organizations).
2. If you are subscribed to the Data Subject Rights module, change to the organization and delete all of its DSR request forms:

If your module is Assessments, switch to the desired organization and delete the assessments therein:

Similarly, follow the steps to delete each entity in Data Maps before proceeding with org deactivation.
  1. Click your avatar, choose **Organizations**, then choose the organization you want to deactivate.
  2. In Securiti, open **Data Subject Rights** and choose **Settings > Form Builder**.
  3. On the DSR Form Dashboard, for every DSR request form choose **Options > Delete**.
  1. Click your avatar, choose **Organizations**, then choose the organization you want to deactivate.
  2. On the Securiti Dashboard view, select **Assessment Automation** or **Vendor Assessments**.
  3. On the following page (list view), click **Options** (three vertical dots) next to each assessment and click **Delete Assessment**.
3. Open **System Settings** and choose **Organizational > Organizations**.
4. On the Organizations page, find the organization you want to deactivate and choose **Options > Deactivate**, then click **Yes** to confirm.

Securiti deactivates the organization, prefixes the organization name with "[Deactivated]," and marks its status as "Inactive" on the list of organizations.

### Reactivating an organization

1. Log in to Securiti with your super admin credentials (only super admins can reactivate organizations).
2. Open **System Settings** and choose **Organizational > Organizations**.
3. On the Organizations page, find the organization you want to reactivate and choose **Options > Activate**.

Securiti reactivates the organization, removes the "[Deactivated]" prefix, and marks its status as "Active" on the list of organizations.

## Related

- [Adding users to an organization](/managing-organizations-adding-users-to-an-organization.md)
- [Managing Securiti users](/configuring-access-management-managing-securiti-users.md)
- [Creating and editing organizations](/managing-organizations-creating-and-editing-organizations.md)
