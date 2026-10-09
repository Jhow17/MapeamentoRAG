---
title: "Configuring single sign-on"
slug: "system-settings-configuring-single-sign-on"
status: "update"
updated: 2026-09-08T10:51:07Z
published: 2026-09-08T10:51:30Z
canonical: "helpcenter.securiti.ai/system-settings-configuring-single-sign-on"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring single sign-on

## Scenario

As a Data Governance Officer, you oversee users from different departments and regions, each using different identity systems. Managing access manually becomes inefficient and error-prone. With Securiti’s multiple Single Sign-On (SSO) support, you can configure separate identity providers for different business entities. It simplifies identity governance, improves user provisioning, and ensures proper role-based access alignment.

## Overview

You can configure Securiti to use most SAML 2.0-compliant IdPs for single sign-on. Doing so lets Securiti users and administrators sign in to Securiti via SP-initiated SSO. Some IdPs may also support IdP-initiated SSO for Securiti.

SSO lets you define a user role and organization, so that when it onboards a user, it assigns the configured user role and organization.

> [!NOTE]
> Note
> 
> To provide multiple roles to a single user, you can proceed with one of the following in your Identity Provider (IdP).
> 
> - In your IdP, you can separate multiple roles with a comma. For example, `"Vendor Assessment Module Owner Role","Assessment Module Owner Role"`.
> - You can add multiple roles in the group claim, as shown below:
> 
> ```xml
> <Attribute Name="user_role">
> 	<AttributeValue>Vendor Assessment Module Owner Role</AttributeValue>
> 	<AttributeValue>Assessment Module Owner Role</AttributeValue>
> </Attribute>
> ```
> 
> Here the attribute name, “user_role” in the example above”, must be the attribute name you provided for the role during attribute mapping.

## Related

- [Configuring generic SAML single sign-on](/configuring-single-sign-on-configuring-generic-saml-single-sign-on.md)
- [Configuring Entra ID (previously known as Azure AD) single sign-on](/configuring-entra-id-previously-known-as-azure-ad-single-sign-on.md)
- [Configuring Okta single sign-on](/configuring-okta-single-sign-on.md)
- [Configuring OneLogin single sign-on](/configuring-single-sign-on-configuring-onelogin-single-sign-on.md)
- [Configuring Red Hat single-sign on](/configuring-single-sign-on-configuring-red-hat-single-sign-on.md)
- [Configuring ADFS single sign-on](/configuring-single-sign-on-configuring-adfs-single-sign-on.md)
