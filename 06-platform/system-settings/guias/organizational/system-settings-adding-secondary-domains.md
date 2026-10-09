---
title: "Adding secondary domains"
slug: "system-settings-adding-secondary-domains"
updated: 2025-10-30T19:13:25Z
published: 2025-11-03T06:11:41Z
canonical: "helpcenter.securiti.ai/system-settings-adding-secondary-domains"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Adding secondary domains

You can add secondary domains to your Securiti account. When you do so, Securiti allows users with email addresses within those domains to have Securiti user and admin accounts and to use Securiti apps and tools.

![RN_secondary_domain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5843dd08-c165-287a-8ce4-dff8f7c5195d(3).png)

> [!NOTE]
> **Note**
> 
> To add a secondary domain, you must have access to the domain's DNS TXT record.
> 
> Once we verify a secondary domain as described below, you cannot delete it on your own. Contact [support@securiti.ai](mailto:support@securiti.ai) to remove a secondary domain.

To add one or more secondary domains:

1. In Securiti open **System Settings** and choose **Organizational > General**.
2. Near the upper right corner of the page, click **Edit** (pencil icon).
3. In the Secondary Domains area, click **+ Add Secondary Domain**.
4. On the Add Secondary Domain popup, use the tools to enter one or more secondary domains, then click **Update Domain List**.
5. In the Secondary Domains area, do the following for each new domain:
  1. Next to the domain name, click **Copy Text** to copy a verification string to the clipboard.
  2. In a DNS TXT record for the domain, add the verification string and save the TXT record.
  3. In Securiti, next to the domain name, click **Verify DNS Record**.

Securiti confirms your ownership of the domain by checking the domain's TXT record to make sure that the correct verification string is present. Afterwards, it marks the secondary domain as "Verified."
  4. If Securiti marks the domain as "Failed," double-check that you correctly added the verification string to the domain TXT record and try again.

## Related

- [Adding admin and security contact emails and phone numbers](/configuring-securiti-general-settingsadding-admin-and-security-contact-emails-and-phone-numbers.md)
- [Configuring concurrent login session limits](/configuring-securiti-general-settings-configuring-concurraent-login-session-limits.md)
- [Configuring Securiti general settings](/system-settings-configuring-securiti-general-settings.md)
