---
title: "Integrating Securiti with Google Consent Mode using gtag.js"
slug: "integrating-securiti-with-google-consent-mode-using-gtagjs"
updated: 2026-02-24T17:01:19Z
published: 2026-02-24T17:01:19Z
canonical: "helpcenter.securiti.ai/integrating-securiti-with-google-consent-mode-using-gtagjs"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Securiti with Google Consent Mode using gtag.js

Follow the appropriate procedure below to integrate Google Consent Mode (GCM) with your domain using the Google tag (`gtag.js`), depending on your specific use case:

> [!WARNING]
> **Important**
> 
> Google advises switching from Google tag (`gtag.js`) to Google Tag Manager (GTM) because `gtag` will be phased out soon. For reasons and how to migrate, visit [Google's guide](https://developers.google.com/tag-platform/tag-manager/web).
> 
> Securiti advises that if you encounter issues with missing Google Consent Mode or TCF signals on Google tags, you must start troubleshooting with Securiti support, not Google. If you encounter such an issue, contact the Customer Success Manager or Account Representative to enable this feature for your Securiti tenant.

### For customers already using Google tag and Securiti’s SDK

To integrate Google Consent Mode with your domain that is already using Google tag (`gtag.js`) and Securiti's SDK:

1. Configure Google Consent Mode from the management portal by following the procedure as explained in [Configuring Google Consent Mode](/latest/docs/configuring-google-consent-mode).
2. After configuring Google Consent Mode from the management portal, you must load the **Consent Defaults** by adding the following code snippets in the `&lt;head&gt;` tag in your website. You must add the code snippet before the `gtag`.

```javascript
<script async src="{{CDN}}/consent/cookie_banner/{{TenantID}}/{{DomainID}}/google_consent_defaults.js"></script>
```

You can find and copy the respective values for these variables from the **Deployment Code** snippet located in the **Consent Code & Custom CSS > Consent Code** tab of your scanned domain in the management portal, as shown below.

![User-Defined_Variable_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d87ec9c-4635-10eb-56bc-32794cac1e77(1).png)

### For customers configuring GCM on new domains for the first time

To integrate Google Consent Mode on your new domain for the first time:

1. Configure Google Consent Mode from the management portal by following the procedure as explained in [Configuring Google Consent Mode](/latest/docs/configuring-google-consent-mode).
2. After configuring Google Consent Mode from the management portal, you must load the **Consent Defaults** by adding the following code snippets in the `&lt;head&gt;` tag in your website. You must add the code snippet before the `gtag`.

You can find and copy the respective values for these variables from the **Deployment Code** snippet present in the **Consent Code & Custom CSS > Consent Code** tab of your scanned domain in the management portal, as shown below.

![User-Defined_Variable_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d87ec9c-4635-10eb-56bc-32794cac1e77(1).png)

```javascript
<script async src="{{CDN}}/consent/cookie_banner/{{TenantID}}/{{DomainID}}/google_consent_defaults.js"></script>
```
3. Once done, load the Google tag (`gtag.js`). To do so:
  1. Access and log in to your Google Tag Manager account.
  2. From the upper left corner, click **Back** (back arrow icon), as shown below.

![Gtag_main_screen.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff9d772f-6f5a-1732-d451-e7310464be49.png)
  3. On the **All accounts** page, click the **Google tags** tab, as shown below. Here you see all of your configured Google tags.

![Google_tag_option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58387df4-e8a0-823b-9aac-607d91c2ef9c.png)
  4. Click the Google tag you used to configure your domain. On the **Tag Manager** page, click **Configuration** tab, and then near the middle right side of the screen, click **Installation instructions**, as shown below.

![Installation_instructions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e123ddee-8221-2d49-63f4-4f973fe69cae.png)
  5. On the **Installation instruction** sidebar, near the upper right corner, click **Install manually**, as shown below.

![Install_Manually.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0cd2c51d-363f-ebd9-61eb-2d108da6bc4e.png)
  6. On the **Install manually** page, from the right corner, click the **clipboard** icon to copy your Google tag (`gtag.js`) code snippet, as shown below.

![Copy_Google_tag_code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73e75d27-aade-4c80-8819-83e371bf4ebf.png)
  7. Paste the copied Google tag (`gtag.js`) into the code of each page on your website, immediately after the `&lt;head&gt;` tag.
4. Now load Securiti’s Consent SDK in your website. To do so, you must add the following code snippet at the beginning of the `&lt;head&gt;` tag in your website's code.

You can find and copy the respective values for these variables from the **Deployment Code** snippet located in the **Consent Code & Custom CSS > Consent Code** tab of your scanned domain in the management portal, as shown below.

![User-Defined_Variable_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d87ec9c-4635-10eb-56bc-32794cac1e77(1).png)

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.
