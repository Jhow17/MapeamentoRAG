---
title: "Understanding just-in-time user provisioning"
slug: "configuring-single-sign-on-understanding-just-in-time-user-provisioning"
updated: 2026-08-30T10:52:26Z
published: 2026-08-30T10:52:26Z
canonical: "helpcenter.securiti.ai/configuring-single-sign-on-understanding-just-in-time-user-provisioning"
stale: true
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Understanding just-in-time user provisioning

When you configure a single sign-on integration as described in one of the following topics, you have the option of enabling just-in-time (JIT) user provisioning. When enabled, the first time each of your users logs in through single sign-on, Securiti automatically creates a user account for them, if there is not already an account corresponding to their email address.

If you disable just-in-time provisioning, if there is not already a Securiti account corresponding to their email address, Securiti does not let them log in.

Under just-in-time provisioning, Securiti assigns the new user either the default RBAC role and organization(s) you configure in Securiti, or the role and organization(s) you configure the SSO provider to pass in a SAML assertion. A role determines the user's permissions, including any custom RBAC role you define. See [Managing Securiti users](/latest/docs/configuring-access-management-managing-securiti-users) for more information about roles and organizations.

> [!NOTE]
> **Note**
> 
> Securiti applies the role setting passed in the SAML assertion only if it is present and valid.

When a Securiti account already matches the email address used for an SSO login, Securiti updates the role and organization for the user based on the IdP configuration each time they log in. If the role or organization is missing from the IdP, Securiti uses the default SSO configurations from the portal settings.

## Related

- [Configuring ADFS single sign-on](/configuring-single-sign-on-configuring-adfs-single-sign-on.md)
- [Configuring Okta single sign-on](/configuring-okta-single-sign-on.md)
- [Configuring OneLogin single sign-on](/configuring-single-sign-on-configuring-onelogin-single-sign-on.md)
- [Configuring Red Hat single-sign on](/configuring-single-sign-on-configuring-red-hat-single-sign-on.md)
