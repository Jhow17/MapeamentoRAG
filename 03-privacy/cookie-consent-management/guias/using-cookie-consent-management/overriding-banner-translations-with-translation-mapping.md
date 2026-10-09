---
title: "Overriding banner translations with translation mapping"
slug: "overriding-banner-translations-with-translation-mapping"
updated: 2025-10-30T19:44:45Z
published: 2025-11-03T06:12:47Z
canonical: "helpcenter.securiti.ai/overriding-banner-translations-with-translation-mapping"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Overriding banner translations with translation mapping

Normally, when you enable Language in the Banner Intelligence panel for a cookie consent banner, Securiti uses commercially-available machine translation to automatically translate the banner into the default language configured on the website visitor's browser. However, in some cases you might find that this translation does not provide satisfactory results. In those cases, you can override the machine translation of some or all of the banner's elements with your own translations.

> [!NOTE]
> **Note**
> 
> - The **Translation Mapping** feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.
> - The **Location** and **Language** features are available by subscription only for **freemium** and **lite** Securiti tenants. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable them for your freemium or lite Securiti tenant.

In some cases, certain words may not be covered by automatic and custom translations and they remain untranslated, often because they are dynamic values, platform-generated terms, or fall outside the defined translatable fields.

> [!NOTE]
> **Important**
> 
> Securiti offers translation support to help localize your cookie consent experience across global audiences. However, certain terms such as **legal references**, **privacy frameworks**, and **organization** or **product names** will remain untranslated to preserve legal accuracy and brand integrity. These include, but are not limited to:
> 
> `Auti`, `AZURE`, `CCPA`, `Cookie`, `Cookies`, `CPRA`, `DIFC`, `DPL`, `DPIA`, `ePrivacy`, `GDPR`, `KYS`, `LGPD`, `PIA`, `PIPEDA`, `POPIA`, `Privacy Act`, `SCHREMS II`, and `VCDPA`.
> 
> These terms appear in their original form across all supported languages.

1. If you haven't already done so, open Cookie Consent Management, and choose **Cookie Consent > Domains**.
2. On the Cookie Consent Domains page, click the card for the domain you want the banner for.
3. Near the upper right corner of the page, click **Edit**.
4. Click the **Customize Banner** tab.

> [!NOTE]
> **Note**
> 
> If the Customize Banner tab is disabled, it may be because the current cookie policy is in Draft state. Click the Categorize Cookies tab and check to see if the Publish button is enabled. If so, review and publish the policy. See [Categorizing your website cookies](/v1/docs/categorizing-your-website-cookies) and [Managing cookie policies](/v1/docs/managing-cookie-policies) for more information.
5. Near the left edge of the page, at the top of the Banner Intelligence panel, make sure the **Language** toggle is enabled so Securiti displays the banner in the default language configured for the visitor's browser.
6. Scroll down to the Banner and Preference Center Text Options area.
7. Enable the toggle for **Provide Translation Mapping**.

The toggle description changes to **Edit Default Texts**.
8. Create overrides for each language of interest:
  1. From the **Select Language** menu, choose the language.
  2. In the fields below the Select Language menu, enter the text that you want to override the machine translations for the selected language.

Any fields you leave as-is are machine translated into the selected language as usual.

For each language, as soon as you click out of the first field, Securiti creates a chip for the language at the top of the Banner and Preference Center Text Options area.
9. When you have created translation overrides for each language of interest, near the upper right corner of the window, click **Save**.

Securiti saves the banner and translation overrides.

> [!NOTE]
> **Note**
> 
> If you are updating an existing cookie consent banner, it may take up to **24 hours** for the new changes to take effect and be visible to your data subjects and website visitors.

You can also use such overrides to customize banners to address some circumstances where the machine translation might provide the correct language, but not the exact dialect. For instance, machine translation into French might work well for France, but not for the French used in Quebec.

1. If you haven't already done so, open Cookie Consent Management, and choose **Cookie Consent > Domains**.
2. On the Cookie Consent Domains page, click the card for the domain you want the banner for.
3. Near the upper right corner of the page, click **Edit**.
4. Click the **Customize Banner and Preference Center** tab.

> [!NOTE]
> **Note**
> 
> If the Customize Banner and Preference Center tab is disabled, it may be because the current cookie policy is in **Draft** state. Click the **Categorize Cookies** tab and check to see if the Publish button is enabled. If so, review and publish the policy. See [Categorizing your website cookies](/v1/docs/categorizing-your-website-cookies) and [Managing cookie policies](/v1/docs/managing-cookie-policies) for more information.
5. Near the left edge of the page, at the top of the **Banner Intelligence** panel, make sure that:
  - The **Language** toggle is enabled so Securiti displays the banner in the default language configured for the visitor's browser.
  - The **Location** toggle is enabled so that Securiti can display a location-specific banner in the location of interest.
6. Near the top of the Banner Intelligence panel, click **+** to create a new banner for the location.
7. Next to the banner name, click **Edit** (pencil icon) and change the name to suit, then click the checkmark to save the name. We recommend you include the applicable locations in the banner name.
8. In the Location Intelligence area of the central panel, mark the radio button for **Show only in**, and use the menu to build a list of countries and states, provinces, or regions, as shown below.

For our Quebec example, you would find the entry for Canada, expand it, and then mark the checkbox for Quebec.
9. Scroll down to the Banner and Preference Center Text Options area.
10. Enable the toggle for **Provide Translation Mapping**.

The toggle description changes to **Edit Default Texts**.
11. Create overrides for each language of interest:
  1. From the Select Language menu, choose the language.

For our Quebec example, you would choose French.
  2. In the fields below the Select Language menu, enter the text that you want to override the machine translations for the selected language.

For our Quebec example, you would enter translations in the French used in Quebec.
12. When you have created translation overrides for each language of interest, near the upper right corner of the window, click **Save**.

Securiti saves the banner and translation overrides.

> [!NOTE]
> **Note**
> 
> If you are updating an existing cookie consent banner, it may take up to **24 hours** for the new changes to take effect and be visible to your website visitors.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

The California Consumer Privacy Act (CCPA) was the first state-level comprehensive privacy law in the United States. It applies broadly to for-profit businesses that collect personal information from California consumers, creating certain rights for consumers and obligations for businesses in relation to personal data processing. It was amended by the California Privacy Rights Act (CPRA) in 2020.

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

Lei Geral de Proteção de Dados (LGPD) or simply called General Data Protection Law is Brazil’s first comprehensive legislation aimed at protecting the fundamental right of privacy. It applies to every natural person or legal entity, either public or private, that handles personal data of Brazilian citizens. The LGPD can also apply extraterritorially similar to the GDPR. You can choose between Global or LGPD template in Privacy Notice Management module.

The Personal Information Protection and Electronic Documents Act (PIPEDA) is the Canadian federal privacy law for private organizations. It sets out the ground rules for how businesses must handle personal information in the course of their commercial activity and provides the individuals with the right to access and rectify their personal data. Securiti’s Privacy Notice Management module lets you create a PIPEDA compliant privacy notice(s) for your organization.

Virginia Consumer Data Protection Act (VCDPA) is a privacy law applicable to persons doing business in Virginia or producing products or services targeted to Virginia residents, if the persons either process personal data (PD) of 100,000 consumers in a year or derive 50% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.
