---
title: "Microsoft 365 FAQs"
slug: "faqs"
updated: 2026-03-10T08:20:05Z
published: 2026-03-10T08:20:05Z
canonical: "helpcenter.securiti.ai/faqs"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 FAQs

---

### 

#### Does granting `Sites.FullControl.All` give Securiti full write or modification access to SharePoint?

Despite the name, Securiti uses this permission read-only for advanced permission analysis. The name "FullControl" comes from Microsoft's SharePoint API naming, not Securiti’s usage.

#### What does `Sites.FullControl.All` do?

`Sites.FullControl.All` is specifically for SharePoint site-level permissions and configuration. It provides access to SharePoint REST APIs that are not available through the Microsoft Graph API.

#### What functionalities are unavailable if `Sites.FullControl.All` permission is not granted?

- No Entitlements data for SharePoint:
  - Cannot determine who has access to SharePoint sites, lists, and documents through role assignments and custom permission levels.
- No site sharing settings:
  - Cannot read site-level sharing policies, external sharing configurations, and sharing capabilities.
- No Hub sites data:
  - Cannot identify hub sites and their associated spoke sites in the SharePoint architecture.

> [!NOTE]
> Note
> 
> OneDrive file permissions are primarily accessed through Microsoft Graph API (`Files.Read.All)`. However, OneDrive for Business sites that use SharePoint-style site collections might also require `Sites.FullControl.All` for complete entitlement analysis.

#### Which features fail if `Sites.FullControl.All` is revoked?

Use the following table to understand the features that cannot be completed if `Sites.FullControl.All` permission is revoked.

| Feature | Impact | Severity |
| --- | --- | --- |
| Advanced Permission Analysis | Fails – Cannot read role assignments or custom permission levels | CRITICAL |
| File-Level Access Control | PARTIAL – Can read files but not detailed SharePoint permissions | HIGH |
| Custom Permission Levels | FAILS – Cannot enumerate custom roles beyond Read/Edit/Full Control | HIGH |
| Inheritance Analysis | FAILS – Cannot determine where permissions are broken or inherited | HIGH |
| Site Admin Detection | FAILS – Cannot identify site collection administrators | HIGH |
| Document Library Scanning | WORKS – Microsoft Graph API can still read files | MEDIUM |
| Basic File Metadata | WORKS – File names, sizes, dates still accessible | Low |

> [!NOTE]
> Note
> 
> Following REST APi also fail if `Sites.FullControl.All` is revoked:
> 
> - /_api/web/roleassignments
> - /_api/web/roledefinitions
> - /_api/lists/{id}/roleassignments
> - /_api/web/siteusers
> - /_api/web/sitegroups
> 
> Microsoft Graph API does NOT provide equivalent functionality for reading SharePoint role assignments
> 
> and custom permission levels. The SharePoint REST API with Sites.FullControl.All is the only
> 
> programmatic method to access this data.
