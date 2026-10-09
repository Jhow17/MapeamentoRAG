---
title: "Configuring Google Consent Mode"
slug: "configuring-google-consent-mode"
status: "update"
updated: 2026-08-27T08:00:25Z
published: 2026-08-27T08:00:44Z
canonical: "helpcenter.securiti.ai/configuring-google-consent-mode"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring Google Consent Mode

**Scenario**

As a Data Compliance Officer, you must implement consent frameworks such as IAB EU TCF, IAB MSPA U.S. National Approach or Google Consent Mode to comply with the regional laws. For instance, when expanding your website to new regions, each jurisdiction may require a different consent framework. Building custom support for each framework can take significant time and legal oversight. With Securiti’s Cookie Consent Management module, you can enable these frameworks with just a few clicks. This helps you meet global compliance requirements without writing additional code.

Securiti lets you integrate Google Consent Mode (GCM)v2 with its Cookie Consent Management module, enhancing your ability to manage the consent of your data subjects and website visitors across Google products efficiently. This integration supports a smoother experience for you and your website visitors by respecting consent preferences across their journey.

Google Consent Mode lets Google's measurement system track consent state throughout the journey of a website visitor. This helps Google tags to automatically adjust their behavior based on the consent given by website visitors. For instance, if a website visitor denies consent for **ad storage**, the system that usually places tracking cookies will instead send a simple signal (cookieless pings) without using cookies. This way, the website visitor's choice is respected, and no tracking cookies are placed. Using the consent mode instead of manually blocking tags also lets you collect generalized measurement information while still respecting the consent choices of your website visitors.

Use the following to understand the key offerings of Google Consent Mode:

| Feature | Description |
| --- | --- |
| Seamless integration with Google products | Easily connect Securiti’s Cookie Consent Management (CMP) module with Google Consent Mode (GCM) v2, streamlining consent management for all Google tags on your website. |
| Adaptive tag behavior | Tags automatically adjust based on the website visitor's consent. For instance, if a user declines consent for ad storage, the system generates cookieless pings instead, ensuring compliance without sacrificing data insight. |
| Enhanced measurement capabilities | Even with consent restrictions, collect generalized measurement information to understand visitor behavior better, all while adhering to user preferences. |

For more information about how Google processes personal information, see [Google's Privacy Policy](https://policies.google.com/privacy) and [Google's Use of Information](https://policies.google.com/technologies/partner-sites).

Use the **Consent Frameworks** tab to configure Google Consent Mode v2 either via **GTM Template**, `gtag.js` or **Custom** implementation approach.

> [!CAUTION]
> Warning
> 
> If you deploy Securiti's Cookie Consent SDK using Google Tag Manager (GTM), you must first complete the setup described in [Integrating Securiti with Google Tag Manager](/latest/docs/integrating-securiti-with-google-tag-manager). After you deploy the SDK and verify that it works correctly in GTM, then configure Google Consent Mode v2 (GCM).

To configure the Google Consent Mode on your domain:

> [!NOTE]
> **Note**
> 
> First you must **configure**, **save**, and **deploy** the Google Consent Mode changes from the management portal, then follow the respective integration guides corresponding to the **Implementation Option** that you selected. For instance, if you select:
> 
> - **GTM Template** implementation option, follow [Integrating Securiti with Google Consent Mode using GTM Template](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtm-template).
> - `gtag.js` implementation option, follow [Integrating Securiti with Google Consent Mode using gtag.js](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtagjs).
> - Custom implementation option, follow [Integrating Securiti with Google Consent Mode using Custom implementation](/v1/docs/integrating-securiti-with-google-consent-mode-using-custom-implementation).

1. In Securiti, open Cookie Consent Management, and choose **Cookie Consent > Domains**.
2. On the Cookie Consent Domains page, click the card for the domain you want to enable Google Consent Mode for.
3. Click the **Consent Frameworks** tab.
4. Click the **Google Consent Mode** tab.
5. Near the upper right corner of the page, click **Edit**.
6. Near the center of the page, enable the **Google Consent Mode** toggle, as shown below.

![Enable_GCM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0f29f00-f576-db99-195c-f9a9c54c5dba.png)
7. From the **Implementation Option** section, select the card either one of the following options that you want to use:
  - GTM Template
  - `gtag.js`
  - Custom

![Updated-Implementation_Option.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ee3f15d-ad50-c5e7-0071-da2094ac2be1.png)
8. From the **Consent Type and Category Mapping** section, map cookie categories (default or custom) to the Google Consent Types, and also set the **Default Google Consent States** against each cookie category for the consent types, as shown below.

![Updated-Category-Mapping.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f7276ba-1248-fcd1-3d05-fcf15d10aa9b.png)

The default consent states let Google know that the website visitor or data subject has yet not given consent, and is simply browsing or visiting your website.

> [!NOTE]
> **Note**
> 
> These **Default Google Consent States** always take precedence over the cookie banner compliance types such as basic, opt-in, or opt-out.
9. Enable the **Show Google Consent Mode Description** toggle to display the descriptions of Google Consent Types on your cookie preference center, as shown below.

> [!NOTE]
> **Note**
> 
> Securiti recommends using this template when enabling Google Consent Mode without IAB EU TCF v2.3. We provide default description text that you can also customize to suit your business needs.

![Show-Google-Description.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0fac42a6-76ee-361b-29de-bc578dfe2fbf.png)

![Google-Description-Pref-Center.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3316134-cd65-4c65-597a-3cee2c8d80fb.png)
10. From the **Region Override** section, enable the **Enable Region Override** toggle to override the seven google consent types based on the region, as shown below.

> [!CAUTION]
> **Caution**
> 
> Only perform this action if you want to set a distinct default state for consent types based on specific countries and/or their regions.
> 
> For instance, if you select **France** with **Paris** region, in this case, Securiti prioritizes the cookie category you've mapped, and the default consent state with Google consent type. However, it applies only when a website visitor or data subject from this region visits your domain, and gives consent via the cookie banner and preference center.

![Enable-Region-Override-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22da8d06-453b-8abf-686f-2907a5d0f8ae.png)
  1. Click **Add countries or regions for override**, and mark the checkbox against the specific country name to select it, as shown below.

![Enable-Region-Override-v2_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-94a65ef0-7a15-c9fb-5f53-c15af7f83f44.png)
  2. Click **country** to select specific regions of this country. From the right side, mark the checkboxes against as many regions as you wish, as shown below.

![Select-Country-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9d974c81-3741-7f68-73d8-0962da685055.png)

![Select-Region-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8307d1cb-8962-8a16-064e-5fb2e71aa744.png)
  3. Once done, near the bottom of the selected country and region(s), click **Add Mapping**, as shown below. ![Add-Mapping-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab765146-e5ad-35d1-91a3-769a103ddf23.png)
  4. Select up to seven Google's consent types, as shown below.

![Select-Google-Consent-Types-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-88b19acb-4356-d69b-b0c9-9d9f1238c049.png)
  5. Select **cookie category** and **default consent state** for the selected consent types, as shown below.

![Map-Category-and-Default-State-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7970c235-ba2c-5e67-07aa-eb14047692e1.png)
11. From the **Additional Consent Events** section, enable the toggles to trigger data layer consent events. You can customize these event names by replacing the default ones.

You can trigger events when the data subject explicitly gives consent or on each page load after consent is given, as explained in [this section](/v1/docs/configuring-google-consent-mode).
12. Near the upper right corner of the page, click **Save** to save your configured changes.
13. After saving, near the upper right corner of the page, click **Deploy** to deploy these changes on your domain.
14. Follow the deployment procedure on the **Publish Code** popup. For instance, in the **Change Note** text section, add the summary of your latest changes that you have made for your cookie banner and preference center.
15. On the **Publish Code** popup, mark the **Show Banner Again** checkbox if you want to show your cookie banner and preference center on your domain(s) again to your data subjects, as shown below. After you publish your latest changes, this feature ensures to show your cookie banner and preference center again to your data subjects when they visit your domain.
16. Near the bottom of the Publish Code popup, click **Publish** to publish your Google Consent Mode changes.

Securiti displays a success message when your cookie configuration changes are successfully deployed to your domain.
17. After successfully configuring Google Consent Mode in the management portal, follow the integration guides corresponding to the implementation option you selected in **step 7** of this procedure.
  - If you selected the **GTM Template** implementation option, follow [Integrating Securiti with Google Consent Mode using GTM Template](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtm-template).
  - If you selected the `gtag.js` implementation option, follow [Integrating Securiti with Google Consent Mode using gtag.js](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtagjs).

### Difference between **Basic** and **Advanced** consent mode

You can implement consent mode on your domain using one of the following two ways:

- Basic Consent Mode
- Advanced Consent Mode

Use the tables below to comprehensively understand the distinctions between **Basic** and **Advanced** consent Modes, detailed both generally and technically.

Table 3. General Overview of Basic vs. Advanced Consent Mode

| Aspect | Basic Consent Mode | Advanced Consent Mode |
| --- | --- | --- |
| Purpose | Simplifies the consent process by providing a basic on/off switch for data collection and usage. | Offers more granular control over the types of data that can be collected and used based on user consent. |
| User Control | Data subjects can either consent to all or opt out completely. | Data subjects can choose which types of data they consent to, such as analytics, advertising, or functional data. |
| Flexibility | Less flexible as it does not allow for differentiation between types of data or purposes of data processing. | More flexible, allowing for tailored data processing settings based on specific data subject consents. |

Table 4. Technical Details of Basic vs. Advanced Consent Mode

| Aspect | Basic Consent Mode | Advanced Consent Mode |
| --- | --- | --- |
| Consent Configuration | Configured to treat consent as a binary decision. Either full consent is given, or all tracking is disabled. | Allows for configuration of multiple consent states, enabling or disabling specific types of tracking and data use. |
| Data Handling | All or none of the data is processed based on the data subject's decision to consent or not. | Data processing is nuanced, with different data streams activated depending on the data subject's detailed preferences. |
| Implementation | Easier to implement due to its straightforward nature. | Requires more complex implementation to handle various consent scenarios and data handling rules. |
| Impact on Analytics | May lead to significant data loss if data subjects opt-out completely, affecting data-driven decisions. | Reduces potential data loss by allowing partial data collection based on user preferences, optimizing data utility. |

For detailed comparison, see Google's [Basic versus Advanced consent mode](https://developers.google.com/tag-platform/security/concepts/consent-mode#basic-vs-advanced).

### Triggering additional data layer events for Google Consent Mode

Securiti lets you fire the additional data layer consent events for your GCM configurations, when you enable the following toggles:

- Trigger an event upon end-user consent
- Trigger an event on each page load after end-user consent

![Additional_Consent_Events.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b666d9d-db48-beaf-016c-7fee833e7e79.png)

These events are completely optional and compatible with all implementation options, including GTM Template, `gtag.js`, and Custom. They provide you with more flexibility and control over how you monitor consent actions.

Use the following table to understand the additional consent events:

| Toggle | Data Layer Consent Event | Description |
| --- | --- | --- |
| Trigger an event upon end-user consent | `userConsentUpdate` | Lets you trigger an event when the data subject explicitly gives consent or when implicit consent is enforced by compliance regulations. |
| Trigger an event on each page load after end-user consent | `pageConsentUpdate` | Lets you trigger an event on each page load once the data subject has given consent. |

Google Tag Manager (GTM) is a tag management system that lets organizations set up and manage website or mobile app tags without frequently changing the application code. It uses containers, tags, triggers, and variables to control when tracking, analytics, marketing, or consent-related scripts run across digital properties.

## Related

- [Integrating Securiti with Google Consent Mode using GTM Template](/integrating-securiti-with-google-consent-mode-using-gtm-template.md)
- [Using the advanced event-driven methods](/using-the-advanced-event-driven-methods.md)
- [Configuring an IAB MSPA U.S. National cookie consent banner](/configuring-an-iab-mspa-us-national-cookie-consent-banner.md)
- [Configuring an IAB EU TCF v2.3 cookie consent banner](/configuring-an-iab-eu-tcf-v23-cookie-consent-banner.md)
