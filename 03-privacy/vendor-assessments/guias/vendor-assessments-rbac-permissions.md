---
title: "Vendor Assessments RBAC permissions"
slug: "vendor-assessments-rbac-permissions"
updated: 2026-09-29T07:11:14Z
published: 2026-09-29T07:11:14Z
canonical: "helpcenter.securiti.ai/vendor-assessments-rbac-permissions"
area: privacy
modulo: vendor-assessments
tipo: guia
data_captura: 2026-10-08
---

# Vendor Assessments RBAC permissions

## Vendor Assessment permissions with default roles

This table shows which Vendor Management permissions are allowed or restricted for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | Super Admin | Org Admin | Operator | DPO | Module Owner | User | Guest |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `Read Vendor Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Create Vendor Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Vendor Assessment` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Read Vendor` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Create Vendor` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Update Vendor` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| `Invite Vendor` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Delete Vendor` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `Manage Vendor Bulk Import` | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ |
| `View Vendor Explorer` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |

## Vendor Assessment permissions with custom roles

Securiti lets you select fine-grained permissions for each custom role you create.

This table lists the Vendor Assessment permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| `Read Vendor Assessment` | Lets you list vendor assessments and view risk data linked to them. | `Read Vendor` |
| `Delete Vendor Assessment` | Lets you delete a vendor assessment instance. | `Read Vendor Assessment`, `Read Vendor` |
| `Read Vendor` | Lets you view vendor profiles, vendor files, vendor photos, and vendor listings. Also grants access to the shared assessments list and the basic connector list for vendor-module users. | None |
| `Create Vendor` | Lets you create new vendor entities. | `Read Vendor` |
| `Update Vendor` | Lets you update vendor profiles, upload, archive, and delete files, and manage vendor photos. | `Read Vendor` |
| `Invite Vendor` | Lets you send bulk invitations to vendors through a CSV import. | None |
| `Delete Vendor` | Lets you delete vendor entities and vendor files. | `Read Vendor` |
| `Manage Vendor Bulk Import` | Lets you manage vendor import in bulk. | None |
| `View Vendor Explorer` | Lets you view available vendors in Securiti. | None |

> [!WARNING]
> Important
> 
> - Create Vendor Assessment doesn't add a visible button in the UI. To let a user launch a reassessment, assign the Invite Vendor permission instead.
> - View Vendors, Create Vendor, and Delete Vendor don't open any screen on their own. Pair one of these with Read Vendor Assessment to give a user working access to the Vendor Assessment module.
> - Invite Vendor also relies on a small number of internal permissions that Securiti manages automatically. These don't appear as separate options in the Roles UI, so you don't need to select them yourself.

### Common permissions between vendor and internal assessments

If you select one of these permissions in vendor assessment, Securiti enables them by default in the assessment module:

| Resource | Common | Exception (only apply to vendor assessment) |
| --- | --- | --- |
| `Delete Assigned Assessment`, `Read Assigned Assessment`, `Update Assigned Assessment` | Yes | `Read Vendor` |
| `Review Assessment` | Yes |  |
| `Update Assessment Assignment` | Yes |  |
| `Update Assessment Metadata` | Yes |  |
| `Apply Assessment Filters` | Yes |  |
