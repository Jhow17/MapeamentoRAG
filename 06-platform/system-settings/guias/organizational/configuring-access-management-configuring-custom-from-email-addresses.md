---
title: "Configuring custom From email addresses"
slug: "configuring-access-management-configuring-custom-from-email-addresses"
updated: 2025-12-08T08:47:35Z
published: 2025-12-08T08:47:35Z
canonical: "helpcenter.securiti.ai/configuring-access-management-configuring-custom-from-email-addresses"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Configuring custom From email addresses

You can use custom From email addresses and Mail From domain information for all emails (including Privacy Central portal emails) sent out by your Securiti tenant.

> [!NOTE]
> **Important**
> 
> We strongly recommend that, if you configure custom from email addresses for your Securiti tenant, you also enable and configure **Use a custom MAIL FROM domain** as described below. Mailbox providers such as Gmail and Yahoo are taking steps to protect their customers from spammers, resulting in rejected messages from unverified senders.

The available options are described in the table below.

| Type | Description |
| --- | --- |
| [Email verification](/v1/docs/configuring-access-management-configuring-custom-from-email-addresses#email-verification) | Uses Email-based verification. You must have access to the email address inbox. |
| [Domain verification](/v1/docs/configuring-access-management-configuring-custom-from-email-addresses#domain-verification) | Avoids the "via" label; emails are signed by your domain. You must have access to the DNS service to add TXT and CNAME records as part of the domain verification process. |
| [Domain verification with optional Custom mail From domain](/v1/docs/configuring-access-management-configuring-custom-from-email-addresses#custom-mail-from-domain) | Sets the mail From domain field in the email header to achieve the highest confidence at the receiving end and handles complaints and bounce emails. Requires MX and SPF records within the DNS server. We recommend that you configure it under a subdomain. |

## Email verification

> [!NOTE]
> Note
> 
> Securiti has deprecated the **Email Verification** method in **Customized Emails**, requiring you to migrate to **Domain Verification**. As outbound email volumes grow more than 5000, major providers such as Gmail, Yahoo, and Outlook treat high-volume senders as bulk and strictly enforce Sender Policy Framework (SPF), DomainKeys Identified Mail (DKIM), and Domain-based Message Authentication, Reporting & Conformance (DMARC).
> 
> The Email Verification method can fail these checks, leading to spam folder placement and delivery failure. Migrating to the Domain Verification feature strengthens authentication, reduces spam filtering risk, and improves deliverability and trust at scale.
> 
> If you have enquiries about migrating to Domain Verification, contact [support@securiti.ai](mailto:support@securiti.ai).

With email verification, all emails sent from your Securiti tenant use your custom From email address. However, email verification shows the “via amazonses.com” label in the From address, and emails are signed by amazonses.com as shown below.

![Email_with_Via.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b7a3ff0-b3e1-5f0f-54b6-3557eca8ae61(3).png)

1. Confirm that you can receive email at the intended address by sending a test message to it.
2. In Securiti, click the jewel at the bottom of the **Dashboard**.
3. From the list of options, select **Settings**.
4. **Choose Organizational > Customized Emails**.
5. From the Instance Type menu, choose **Email**.
6. In the Email Address box, type or paste the email address you want to use as the From address on emails that Securiti sends out.
7. Click **Save Configuration**.

Securiti sends a verification email to the address you entered.
8. Check the inbox for the email address you entered for the verification email.
9. When you receive the email, click the verification link to complete the email verification.

![email_with_verification_link.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9faef294-e541-4556-b1e0-f755801d370f(3).png)
10. Check the Settings > Organizational > Customized Emails page to make sure that the instance status is "Complete" as shown below. ![custom_email2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-986d5cdd-fa62-7a4a-3034-07b49645f173(3).png)

## Domain verification

Domain verification avoids the "via" label; emails are signed by your domain. You must have access to the DNS service to add TXT and CNAME records as part of the domain verification process.

1. Confirm that you can receive email at the intended address by sending a test message to it.
2. In Securiti, click the jewel at the bottom of the **Dashboard**.
3. From the list of options, select **Settings**.
4. **Choose Organizational > Customized Emails**.
5. Apply the following settings and click **Save Configuration**:

| Setting | Description |
| --- | --- |
| Instance Type | Choose **Domain** |
| Domain | Enter your DNS domain |
| From email address | Enter your preferred From email address in that domain |

Securiti verifies the settings you entered.
6. Wait for the Instance Status to change to Verification Complete.
7. Click **View Mail from Config** to view the entries that you must make in your DNS server for that domain, as shown below.

![domain_verification_instance_status.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-11038c12-ac85-4c26-069d-d98b029458c1(3).png)
8. Configure the appropriate custom resource records within your DNS service, as shown below.

![config_DNS_service.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bdb5f2e4-d0a4-ecb1-0557-dae8d068d877(3).png)

Once the verification is completed (which could take up to 30 minutes if there are no errors), the From email address for all emails sent from your Securiti tenant are the custom email address.

## Custom mail From domain

Optionally, for either email or domain-based verification method, you can configure a custom mail From domain as shown below. When combined with domain verification, it results in the highest confidence at the receiving end and handles complaints and bounce emails.

Before mail-from domain configuration:

![before1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83f02228-7f05-816e-4945-760c9ad7fc80(3).png)

After mail-from domain configuration:

![after1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34e8b237-7101-6122-6e33-ada0cd2e6a1b(3).png)

To do this, you must add additional resource records (MX and SPF records) within your DNS service for that domain.

> [!NOTE]
> **Note**
> 
> We recommend that you create the MX record for a subdomain, and not against your main domain.

1. Configure either email verification or domain verification as described in the previous sections. But before clicking Save Configuration, enable the slider for **Use a custom MAIL FROM domain**.
2. After the Instance Status changes to Verification Complete, click **View Mail from Config** and record the DNS resource record configuration as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M7BH8U5Y.png)
3. Copy the DNS resource record configuration to your DNS service as shown below. ![resource_records.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-348b9a8a-ee5d-3e06-a146-d16a8515786e(3).png)

## Related

- [Configuring the Securiti self-service portal](/configuring-the-securiti-self-service-portal.md)
- [Managing organizations](/system-settings-managing-organizations.md)
- [Deactivating and reactivating organizations](/managing-organizations-deactivating-and-reactivating-organizations.md)
