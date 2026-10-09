---
title: "Configuring IP address restrictions and masking"
slug: "configure-securiti-settings-configuring-ip-address-restrictions-and-masking"
updated: 2025-10-30T19:23:36Z
published: 2025-11-03T06:11:41Z
canonical: "helpcenter.securiti.ai/configure-securiti-settings-configuring-ip-address-restrictions-and-masking"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring IP address restrictions and masking

If you have a Premium account, you can restrict access to Securiti and its modules to devices within specified ranges of IP addresses. For example, to restrict access to users within your company, add the IP addresses of your company. You can also allow users of your self-service portal to bypass this restriction.

This feature enforces IP address restrictions for:

- Sign in for all Securiti modules
- Access to functionality within all Securiti modules
- API calls to Securiti
- Pod registration and functionality
- Partner access

However, Securiti does not enforce IP address restrictions for:

- Privacy Central users submitting DSR requests
- External or Guest users and collaborators (Assessments, DSR and Data Mapping module)
- Vendor collaborators
- Preference Center users
- Inbound webhook calls
- Privacy notices
- Securiti Support users
- Cookie and Universal Consent Recording API
- Cookie Consent Geolocation service

> [!NOTE]
> **Important**
> 
> Enabling IP-based access restrictions can break 3rd party integrations and partner access. Make sure you allow all external IPs that must access your account through the Securiti API. If you experience any access issues after enabling this feature, please reach out to Securiti Support at [support@securiti.ai](mailto:support@securiti.ai).

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. Choose **Security > IP Restrictions and Masking**.
4. Activate the toggle for **Enable IP Restrictions**.
5. Use the tools in the Allowed IP Ranges area to add one or more IP addresses or address ranges in CIDR notation as shown below.

![RN_IP_address_restriction.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b47a7b41-d225-b336-3707-2248e3b1841e(3).png)
6. (Optional) If you want IP address restrictions to apply also to the Securiti self-service portal, clear the checkbox for **Allow external users to access Self-Service Portal**.
7. When you are done, near the upper right corner of the page click **Save Settings**.

The new settings take effect within about five minutes.

### IP masking for audit logs

You can mask your IP addresses in the audit logs. IP masking feature lets you mask the last three digits of the IP addresses and last four digits for IPv6 in the UI while keeping them unmasked in the database. By default, this setting is turned off. When this setting is enabled, the audit logs display masked IP addresses according to your configuration.

To enable IP masking for audit logs:

1. In Securiti dashboard, go to the **Settings** section by clicking on the jewel icon on the bottom.
2. Choose **Security > IP Restriction and Masking** .
3. Activate the toggle for **Enable IP Masking in Audit Logs**.

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

A preference center helps organizations immediately and adequately honor consent preferences and consent revocations of their data subjects across multiple systems.
