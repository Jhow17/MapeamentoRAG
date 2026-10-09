---
title: "Configuring an IAB Europe TCF v2.4 cookie consent banner"
slug: "configuring-an-iab-eu-tcf-v23-cookie-consent-banner"
updated: 2026-07-21T10:19:45Z
published: 2026-07-21T10:19:45Z
canonical: "helpcenter.securiti.ai/configuring-an-iab-eu-tcf-v23-cookie-consent-banner"
stale: true
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring an IAB EU TCF v2.3 cookie consent banner

**Scenario**

As a Data Compliance Officer, you must implement consent frameworks such as IAB EU TCF, IAB MSPA U.S. National Approach or Google Consent Mode to comply with the regional laws. For instance, when expanding your website to new regions, each jurisdiction may require a different consent framework. Building custom support for each framework can take significant time and legal oversight. With Securiti’s Cookie Consent Management module, you can enable these frameworks with just a few clicks. This helps you meet global compliance requirements without writing additional code.

The IAB EU TCF v2.3 consent framework lets you seamlessly comply with certain requirements of the ePrivacy Directive and the GDPR. It lets you meet the expectations of regulators and the needs of your data subjects by meeting the demands of Data Protection Authorities (DPAs) in terms of data protection.

If you want, you can display the IAB EU TCF v2.3 banner instead of the standard Securiti cookie consent banner. This feature is available by request, contact your Securiti representative to activate it for your Securiti account.

The following table explains the main Policy amendments of EU TCF v2.3. For more information on IAB TCF EU v2.3 changes, see [Learn more about the IAB EU TCF v2.3 update](/v1/docs/securiti-pods-and-elastic-pods).

| EU TCF v2.3 Features | Description |
| --- | --- |
| Simplified legal basis | Under EU TCF v2.3, the Vendor can no longer use legitimate interests as the legal basis for the following purposes: - 3 (create a personalized ads profile) - 4 (select personalized ads) - 5 (create a personalized content profile) - 6 (select personalized content) This means that the Vendors need the consent of your data subjects for these purposes. |
| Improved information | The information is now easier for the data subjects to understand. The names and descriptions of **purposes** have been changed and new **features** have been introduced to explain possible means of Processing. The legal text has been removed and replaced by user-friendly descriptions; supplemented by examples of real use-cases called **illustrations**. |
| More Vendor information | Vendors are now responsible for providing additional information and details about how they handle the data of your data subjects. This includes: - Categories of data they collect and process - How long do they keep the data for each purpose - What their legitimate interests at stake are (if applicable) |
| Clear Vendor count | Consent Management Platforms (CMPs) must disclose how many Vendors are processing personal data on the basis of consent or legitimate interests in the main user interface (UI). |
| Easy consent withdrawal | Publishers and CMPs are responsible for making it simple for the data subjects to revisit the CMP interface and withdraw their given consent if they want to. |

To configure an EU TCF v2.3 cookie consent banner and preference center:

1. If you have not already done so, configure a standard cookie consent banner for your domain as described in [Customizing your cookie banner and preference center](/v1/docs/customizing-your-cookie-banner-and-preference-center).

> [!NOTE]
> **Note**
> 
> - The IAB TCF EU v2.3 cookie consent banner uses the same website code as our standard cookie consent banner.
> - You might want to display the standard cookie consent banner outside of the EU.
> - Securiti **strongly recommends** you to only use the **O****pt-In banner compliance type** when configuring your cookie consent banners with the EU TCF v2.3 consent framework.
2. In Securiti, open **Cookie Consent Management**, then choose **Cookie Consent > Domains**.
3. On the Cookie Consent Domains page, click the card for the domain for which you want to configure an EU TCF v2.3 cookie consent banner.
4. Click the **Consent Frameworks** tab.
5. Click the **Interactive Advertising Bureau (IAB)** tab.
6. Near the upper right corner of the page, click **Edit**.
7. Mark the **EU TCF v2.3** checkbox, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step7.png)
8. (Optional) From the IAB EU Banner section, add custom text for your EU TCF v2.3 cookie consent banner. If you are satisfied with the default cookie banner text, leave it as is, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step8.png)
9. (Optional) From the upper right corner of the Banner Text section, click **Add Links for Purpose/Vendor** to add links for Purpose and Vendors, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step9.png)
10. (Optional) Add custom text for the following cookie banner buttons to suit, as shown below:

These buttons appear on your cookie banner, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step10.png)
  - Accept All Button Text
  - Reject All Button Text
  - Advance Settings Text

![Screenshot_2023-11-22_at_2_36_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d157fd5d-d4e4-19e1-2bbe-30f5ef88c2bb.png)
11. (Optional) From the IAB Purposes Tab section, add custom heading and description text for the **IAB Purposes** tab that appears on your EU TCF v2.3 cookie preference center, as shown below.

![Screenshot_2023-11-22_at_2_37_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-562e4005-a418-48f9-3700-d2da1f5b0e1f.png)

![Classic-Preference-Center-Purposes-Tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-def01d50-9698-4aa9-e388-c6d0287e9db3.png)

*EU TCF v2.3 cookie preference center with the* ***classic*** *style.*

![Multi-Level-Preference-Center-Purposes-Tab_png.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39a00afc-2d0c-6a83-f92f-668bb156db5e.png)

*EU TCF v2.3 cookie preference center with the* ***multi-level*** *style.*

From the upper right corner of the Description section, click **Add Links for Purpose/Vendor** to add links for Purpose and Vendors.
12. From the **IAB Purposes** **Tab** section, enable the **Display TC String s****torage** **and access information** toggle. This displays essential details on the cookie preference center about which cookies or trackers store the TC String on their devices, along with their storage durations.

Editable From the **Description** text field located right below this toggle, edit the description to suit. There is a non-editable table outlining information about each tracker, including **Tracker Name**, **Tracker Type**, and **Tracker Duration**, as shown below.

![IAB-EU-TCF-Toggle-All-Revised.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2990babe-7ada-27db-754f-71f8b03cf03c.png)

![IAB-TCF-Pref-Center-Revised.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d43d29e9-dace-d50f-0d1f-739fe0f7a41f.png)
13. (Optional) From the Vendor List Tab section, add custom heading and description text for the **Vendor List** tab that appears on your EU TCF v2.3 cookie preference center, as shown below.

![Screenshot_2023-11-22_at_2_37_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b3a3680-0665-9f73-a47a-caebee41cc8f.png)

![Classic-Preference-Center-Vendors-Tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a3174eff-6150-b1ad-20ad-65fac71d1a87.png)

*EU TCF v2.3 cookie preference center with the* ***classic*** *style*

![Multi-Level-Preference-Center-Vendors-Tab_png.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0d153e19-c313-9511-514c-867190b6bfe4.png)

*EU TCF v2.3 cookie preference center with the* ***multi-level*** *style*

From the upper right corner of the Description section, click **Add Links for Purpose/Vendor** to add links for Purpose and Vendors.
14. Use the **Location Intelligence** section to select a specific region in which you want to display your EU TCF v2.3 configured cookie consent banner and preference center, as shown below.
  1. Mark the **All** radio button to display your cookie banner and preference center globally.
  2. Mark the **Show only in** radio button, and type the name of the country in which you want to display this cookie banner and preference center. You can select one specific country, multiple countries, and also select specific states, provinces or regions in the selected country or countries, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step14.png)
15. From the Integrate with GCM section, activate the **Enable integration with GCM** toggle, as shown below. This lets you integrate the IAB EU TCF v2.3 consent framework with the Google Consent Mode (GCM).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step15.png)

> [!WARNING]
> **Important**
> 
> Securiti does not let you enable the GCM integration toggle in the IAB EU TCF v2.3 consent framework if GCM is either not configured or is configured but turned off in the management portal.
16. From the **IAB TCF** **Vendors** tab, mark the checkboxes for the Vendors that you want to show on your EU TCF v2.3 cookie preference center, as shown below.

> [!CAUTION]
> **Caution**
> 
> - There may be vendors that do not use the consent of your data subjects and rather rely on legitimate interest as the basis of data processing for specific purposes. For all such vendors, even if your data subjects or website visitors do not give explicit consent on the IAB EU TCF v2.3 configured cookie banner and preference center, the **legitimate interest** against that vendor is captured which is then passed down to the IAB TCF string. Any positive or negative signal for legitimate interest given by the data subject is passed down to the IAB TCF string.
> - Vendors that have not declared any purpose and are using special purposes (as defined under the IAB Policies) to which the data subject or website visitor has no right to object are automatically removed from the IAB TCF String by the IAB. Consequently, such vendors are not included in the automatic vendor count. However, they may still appear in the management portal and be shown to your data subjects on the cookie preference center for transparency purposes.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step16.png)

> [!WARNING]
> **I****mportant**
> 
> You must select at least one IAB TCF Vendor to configure IAB EU TCF v2.3.
17. (Optional) From the **Google ATPs** tab, mark the **Use Google ATPs** checkbox to enable Google Advertising Technology Providers.

> [!CAUTION]
> Caution
> 
> Google’s Additional Consent (AC) version 2 is not the same as Google Consent Mode v2. While both are privacy specifications from Google and may sound similar, they serve different purposes. This feature is intended to be used alongside IAB EU TCF v2 (including v2.2, v2.3, and later versions).
  1. Mark the checkboxes for the vendors that you want to include in your EU TCF v2.3 cookie preference center, as shown below.

> [!WARNING]
> Important
> 
> When you enable Google ATPs, make sure you display the following two purposes used by Google Advertising Technology Providers (ATPs) to process personal data in the preference center.
> 
> These purposes include:
> 
> 1. Use of cookies or other local storage where legally required; and
> 2. Collection, sharing, and use of personal data for ad personalization by an ATP.
> 
> Displaying these purposes helps you align with Google policies and improves transparency for data subjects. If granular purposes are available, configure and display them accordingly.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step17.png)
18. From the **Purposes** tabs, mark the checkboxes for the Purposes that you want to show on your EU TCF v2.3 cookie preference center, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step18.png)

> [!WARNING]
> Important
> 
> You must select at least one IAB Purpose to configure IAB EU TCF v2.3.
19. By remaining on the **Purposes** tab, scroll down, and mark the checkboxes for the **Features**, **Special Purposes**, **Special Features**, and **Stacks** that you want to show on your cookie preference center, from their respective sections, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step19a.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step19b.png)

Securiti displays them as tabs, under the **IAB Purposes** tab on your cookie preference center, as shown below.

![Screenshot_2023-11-22_at_5_28_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d118b88-d3d9-94a6-2db6-1f18ce3bc87b.png)

*EU TCF v2.3 cookie preference center with the* ***classic*** *style*

![Multi-level_Pref_Center_IAB_Purposes_Tab_Layout.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5a33fce7-cfcb-8cb2-e82b-44c7610f904d.png)

*EU TCF v2.3 cookie preference center with the* ***multi-level*** *style*
20. From the **Data Categories** tab, review the available data categories and their descriptions to understand what types of personal data vendors may collect or process, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step20(1).png)
21. Near the upper right corner of the page, click **Save** to save your configured changes, as shown below.

![Screenshot_2023-11-22_at_2_44_09_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ec5079c-cc97-65b1-82a4-ef2490f1abe7.png)

Securiti saves your cookie configuration changes in the draft mode, and shows you a yellow banner at the top of the Cookie Configuration page to indicate that you have **unpublished** changes.
22. To preview your latest saved changes in the draft, click **Preview**. Securiti shows you the latest changes you made for your cookie banner and preference center, as shown below.

![Screenshot_2023-11-22_at_5_26_48_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-551b5fe4-bed2-4b1d-c8c3-39e4f9e008fe.png)
23. Click **Deploy** to publish your cookie banner, as shown below.

![Screenshot_2023-11-22_at_2_59_21_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ef7878f-6400-4cf3-b225-27c421ee562c.png)
24. Follow the deployment procedure on the Publish Code popup. For instance, in the **Change Note** text section, add the summary of your latest changes that you have made for your cookie banner and preference center, as shown below.

![Screenshot_2023-11-22_at_3_00_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b689c866-aeb2-b903-1798-4eb08151d342.png)
25. On the Publish Code popup, mark the **Show Banner Again** checkbox if you want to show your cookie banner and preference center on your domain(s) **again** to your data subjects, as shown below. After you publish your latest changes, this feature ensures to show your cookie banner and preference center again to your data subjects when they visit your domain.

![Screenshot_2023-11-22_at_3_00_14_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b288f8c9-537a-9479-fbe2-fe5d6b15a140.png)
26. Near the bottom of the Publish Code popup, click **Publish** to publish your EU TCF v2.3 cookie banner and preference center, as shown below.

![Screenshot_2023-11-22_at_3_00_28_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-51978a96-0c39-fed0-3c90-193e4897e99b.png)

Securiti displays a success message when your cookie configuration changes are successfully published, as shown below.

![Screenshot_2023-11-22_at_3_01_59_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0908f617-e58c-3d7e-319b-4b6c59d074da.png)

> [!WARNING]
> **Important**
> 
> - If you have configured your cookie banners and preference centers with the EU TCF **v2.0** consent framework, and you are using **automatic SDK deployment** option, your cookie banners and preference centers are automatically transitioned to EU TCF v2.3 following the Securiti **release 1.105**. After this transition to the latest EU TCF v2.3, Securiti does not let you retain your older configurations for the EU TCF v2.0 consent framework.
> - If your domain uses the **automatic SDK deployment** option, this functionality is available for you to configure following the Securiti release 1.105 (29 and 30 November 2023).
>   - If you are already using the EU TCF **v2.0** consent framework with the automatic SDK deployment option, you must also **republish** your cookie configuration changes from the management portal. This ensures the seamless working of your custom and default translations on your cookie banner and preference center.
> - If your domain uses the **manual SDK deployment** option (pinned to an older Securiti version) for cookie banners and preference centers, you must **republish** your cookie configuration changes from the management portal to leverage this functionality.
>   - If you have already switched from the **legacy SDK deployment** option to either **manual** or **automatic SDK deployment** option, you **don’t** need to add the **Deployment Code** in the `&lt;head&gt;` tag of your domain(s) again.
> - When using the **O****pt-In** or **Opt-Out** banner compliance type for your cookie consent banner, your cookie consent banner shows the following buttons irrespective of which banner compliance type you are using:
>   - **Consent to all** button (it acts as **Allow cookies** button that **grants** consent against all cookie categories)
>   - **Withdraw consent to all** button (it acts as **Deny** button that **declines** consent for all cookie categories)
> - Securiti **strongly recommends** you to only use the **Opt-In banner compliance type** when configuring your cookie consent banners with the EU TCF v2.3 consent framework.

For more information, see [Understanding IAB Global Privacy Protocol (GPP)](/v1/docs/understanding-iab-global-privacy-platform-gpp)

## Comparing IAB EU TCF v2.0 and v2.3 cookie consent banner buttons

The following table explains how the buttons on your cookie consent banners differ for different compliance types in the IAB EU TCF v2.0 and v2.3 consent frameworks:

| Cookie Banner Compliance Type | Cookie Consent Banner Buttons in EU TCF v2.0 | Cookie Consent Banner Buttons in EU TCF v2.3 |
| --- | --- | --- |
| Opt-out | **Dismiss** link **Decline** button | **Consent to all** button acts as **Allow cookies** button. **Withdraw consent to all** button acts as **Deny/Decline** button. > [!WARNING] > **Important** > > The **Dismiss** button/link is not applicable for the **Opt-Out compliance type** cookie consent banners in the EU TCF v2.3 consent framework. |
| Opt-in | **Allow cookies** button **Dismiss** link | **Consent to all** button acts as **Allow cookies** button. **Withdraw consent to all** button acts as **Deny/Decline** button. |

## Integrating IAB EU TCF v2.3 with Google Consent Mode (GCM)

### Prerequisites

To successfully integrate IAB EU TCF v2.3 with Google Consent Mode (GCM):

- You must configure both IAB EU TCF v2.3 and GCM for your domain from the management portal to achieve this integration. If GCM is not configured, Securiti does not let you enable the GCM integration toggle within the IAB EU TCF v2.3 consent framework. For instance, if you previously configured the GCM for your domain and also enabled the GCM integration toggle, but later disable the GCM configuration, Securiti automatically turns off the GCM integration toggle. To alert you, Securiti also displays an alert message in the upper right corner of the page, as shown below.

![GCM-Automatically-Disabled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c266683-4ac0-e151-4ee6-8d60c0a666d6.png)

- Both functionalities work independently and you can enable or disable them as needed. However, if GCM is not configured for your domain in the management portal or is configured but turned off, Securiti disables the GCM integration toggle, as shown below.

![Integration-Disabled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac6fee1f-1067-7ca6-2c39-0f660bd8e536.png)

### Integration

Consider the prerequisites outlined in the Integrate with Google Consent Mode section, and then activate the **Enable integration with GCM** toggle, as shown below.

![GCM-Integration-Toggle.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a82ab6c3-9080-ddd6-57bd-7a8b4545e42a.png)

Securiti lets you integrate your IAB EU TCF v2.3 configured cookie banners and preference centers with Google Consent Mode (GCM). This integration lets you seamlessly transmit consent signals to Google tags (`gtags`), ensuring compliance with privacy regulations and Google’s advertising policies, and optimization of advertising strategies.

Securiti achieves this integration by implementing Google’s `TCData.enableAdvertiserConsentMode` Flag on the `TCData` object upon its creation. When set to **True**, Google infers consent for `ad_storage`, `ad_user_data`, and `ad_personalization` from the TC String.

Use the following table to understand the key components of a *TCF String*:

| Component | Description |
| --- | --- |
| Version | Indicates the version of the TCF being used such as version 2.3. |
| Purpose Consents | Specifies whether the data subject has consented to data processing for specific purposes such as personalized ads, analytics, etc. |
| Vendor Consents | Lists the individual vendors that have received consent to process data. |
| Special Features | Contains information about special features like legitimate interests, which may not require data subject consent. |
| Timestamp | Records when the consent was given or updated. |
| Policy Version | Indicates the version of the policy that applies. |

Once you successfully configure this feature and the integration is enabled, the IAB EU TCF v2.3 consent framework automatically transmits consent signals to Google tags, supporting compliance and aligning consent data across advertising channels.

### Caveats

You must consider the following caveats to ensure seamless integration of IAB EU TCF v2.3 with GCM:

- The `gtag` must load before the TCF stub. If `gtags` are loaded after the TCF stub, you see the following error in your web browser's console:

![1-TCF_is_disabled__but_TCF_stub_is_loaded.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-943f1b21-4f86-d88d-d73c-4492921c05a0.png)
- The `google_consent_defaults` script must load when GCM is enabled. If GCM is enabled but `google_consent_defaults` script is not loaded, the following error appears in your web browser's console:

![2-If_GCM_is_enabled_but_google_consent_defaults_js_is_not_loaded.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7dfd8e7a-18db-7904-ddff-e84fbb68a84f.png)
- The TCF stub should not load when TCF is disabled in the management portal. If TCF is disabled but the TCF stub loads on the domain, you see the following error in your web browser's console: ![3-GTags_are_loaded_before_TCF_stub.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-591f403b-21e6-4f9b-d730-4cb218aba5f6.png)

An EU regulation that governs the confidentiality of electronic communications and the use of cookies and similar technologies. It requires consent from data subjects before storing or accessing information on their devices, except when strictly necessary for providing a service. It works alongside the GDPR and applies to domains targeting individuals in the EU.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

Vendors are the companies you collaborate with and send assessments to for completion. You can also evaluate prospective vendors and track the performance of existing ones.

Data being processed that's stored by the entity, for example, an asset.

A TC String in the IAB EU TCF v2.2 is a standardized encoded string that contains information about a user’s consent choices regarding data processing. It is part of the framework developed by the Interactive Advertising Bureau (IAB) to help organizations comply with GDPR and ePrivacy regulations. It allows publishers and advertisers to communicate consent information to all relevant parties, ensuring that user preferences are respected across different platforms and services. It helps to facilitate compliance with legal requirements regarding user privacy and data protection.

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

Under an Opt-in cookie banner compliance type, cookies are not set on the data subject's device until they have explicitly given permission. This means that, except for strictly necessary cookies (which are essential for the basic functioning of the website), no cookies are loaded until the data subject actively consents to them. This approach is particularly common in regions like the European Union, where regulations such as the General Data Protection Regulation (GDPR) require explicit consent for the storage or access of information on a user's device.

## Related

- [Understanding IAB Global Privacy Protocol (GPP)](/understanding-iab-global-privacy-platform-gpp.md)
- [Configuring the GPC consent framework and flyout](/configuring-the-gpc-consent-framework-and-flyout.md)
- [Configuring Google Consent Mode](/configuring-google-consent-mode.md)
