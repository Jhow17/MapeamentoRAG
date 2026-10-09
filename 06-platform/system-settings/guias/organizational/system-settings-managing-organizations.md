---
title: "Managing organizations"
slug: "system-settings-managing-organizations"
status: "update"
updated: 2026-07-16T12:33:52Z
published: 2026-07-16T12:33:52Z
canonical: "helpcenter.securiti.ai/system-settings-managing-organizations"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Managing organizations

You use Securiti's organization-level access features to isolate the Securiti resources of various groups or business units from one another. These new features let you restrict access to views and functionality based on group or organization membership. Use these features if your organization contains multiple business units or similar groupings for which you must isolate the data and functionality in Securiti. For simplicity, we refer to each group within your organization as an “organization.”

This feature is available by request; contact [support@securiti.ai](mailto:support@securiti.ai) to have us activate it for your Securiti tenant. If you do not activate it for your Securiti tenant, you continue to use Securiti as before, with no impact on how you use it.

When you enable the organizations feature, it is as if each organization has its own Securiti account, separate from the Securiti accounts of all other organizations within your Securiti tenant, each with its own set of Securiti elements. For example, each organization has its own data systems and connectors, its own assessments, its own DSR forms and DSR requests, its own workflows, and its own data maps and data catalog.

However, some resources remain global, and apply to all organizations within your Securiti tenant, for example:

- SSO configurations
- Pods and Elastic Pods V2
- Securiti support access
- General settings

When you configure these resources, they apply to all organizations within your Securiti tenant, not just the organization you are using Securiti for at the time you configure the resource.

Organizations within your Securiti tenant are arranged in a flat list, without hierarchy. So, for example, you cannot have one organization contained within another.

For each Securiti user, you can specify one or more organizations to which they belong. Users can then switch between the organizations on whose behalf they are using Securiti. However, if you have [configured secondary domains](/v1/docs/system-settings-adding-secondary-domains), you can restrict access to an organization and its resources to just those users whose email addresses fall within one or more of your domains. The exceptions are Super Admins and Securiti support users, who can access all organizations (active and inactive) regardless of domain access restrictions.

For each organization, you can create one or more Organization Admins. A user with the Organization Admin role can perform administrative functions, but only within their assigned organizations. In System Settings, they can only view organizations, users, and new user assignments that fall within those organizations. An organization admin can create a new user or update user but with roles limited to `User` or `Organization Admin` within the same assigned organizations.

Once we enable this feature for your Securiti tenant, it contains a Default Organization for which all your existing resources, views, and functionality apply. All your Securiti users initially belong to this default organization. Once you add new organizations of your own, you can add your existing Securiti users to them. The default organization is where you configure the global resources described above.

## Related

- [Creating and editing organizations](/managing-organizations-creating-and-editing-organizations.md)
- [Importing organizations](/managing-organizations-importing-organizations.md)
- [Adding users to an organization](/managing-organizations-adding-users-to-an-organization.md)
- [Deactivating and reactivating organizations](/managing-organizations-deactivating-and-reactivating-organizations.md)
