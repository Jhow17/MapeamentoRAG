---
title: "Universal Consent Configurations"
slug: "universal-consent-configurations"
updated: 2025-12-09T16:40:19Z
published: 2025-12-09T16:40:19Z
canonical: "helpcenter.securiti.ai/universal-consent-configurations"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Universal Consent Configurations

Using this page, you can hide Securiti branding from preference centers and email notification templates at the tenant level, including the:

- Access screen where data subjects enter their details
- Emails containing the verification link to access the preference center
- Preference center screen

### Hiding Securiti branding from within module

To hide the Securiti branding from within the Universal Consent Management module:

1. In Securiti, open Universal Consent Management, and choose **Settings > Universal Consent Configurations**.
2. From the Universal Consent Configurations page, enable the **Hide Securiti Branding** toggle.
3. Near the upper right corner of this page, click **Save**, as shown below. ![hide_securiti_branding.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-678ccfb8-bdb5-8405-43e0-68ce82a032b6.png)

### Enabling Rules Matrix from within module

To enable the Rules Matrix from within the Universal Consent Management module:

1. In Securiti, open Universal Consent Management, and choose **Settings** > **Universal Consent Configurations**.

> [!NOTE]
> **Note**
> 
> - Securiti lets you use Rules Matrix to drive consent statuses via the following APIs:
>   - [Schedule consent for upload via Rules Matrix](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Consent%20upload)
>   - [Bulk import consents via Rules Matrix](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Bulk_import_consents)
>   - [Bulk import consents via CSV via Rules Matrix](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Bulk_import_consents_via_csv)
> 
> - It lets you derive consent statuses using the two-letter country code based on jurisdiction-specific exceptions and the **Default Consent State**. For instance, if you want to derive consent for **Brazil** under a **Business to Business (B2B)** subrule, you must set the value of the location parameter to `BR` in the payload. You can also derive consent statuses based on one or multiple exceptions and populate the results on the Universal Consent Management dashboard.
2. From the Universal Consent Configurations page, enable the **Consent uploads/API** toggle.
3. Near the upper right corner of this page, click **Save**, as shown below.

![consent_api_toggle.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e03cb8e4-edeb-b371-de06-3fd71bdab11d.png)

## Related

- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Using the Rules Matrix](/using-the-rules-matrix.md)
