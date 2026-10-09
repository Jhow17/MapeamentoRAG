---
title: "Configuring the GPC consent framework and flyout"
slug: "configuring-the-gpc-consent-framework-and-flyout"
updated: 2026-07-21T10:22:10Z
published: 2026-07-21T10:22:10Z
canonical: "helpcenter.securiti.ai/configuring-the-gpc-consent-framework-and-flyout"
stale: true
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring the GPC consent framework and flyout

**Scenario**

As a Data Compliance Officer, you must implement consent frameworks such as IAB EU TCF, IAB MSPA U.S. National Approach or Google Consent Mode to comply with the regional laws. For instance, when expanding your website to new regions, each jurisdiction may require a different consent framework. Building custom support for each framework can take significant time and legal oversight. With Securiti’s Cookie Consent Management module, you can enable these frameworks with just a few clicks. This helps you meet global compliance requirements without writing additional code.

You can enable the GPC consent framework and ensure detection of GPC signals on data subjects’ web browsers and devices to honor their opt-out cookie preferences.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

To configure the GPC consent framework and flyout banner:

1. Configure a standard cookie consent banner for your domain as described in [Customizing your cookie banner and preference center](/v1/docs/customizing-your-cookie-banner-and-preference-center) if you have not done so before.
2. The GPC framework uses the same website code as our standard cookie consent banner.
3. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
4. On the Cookie Consent Domains page, click the domain you want to enable the GPC framework for.
5. Click the **Consent Frameworks** tab.
6. Click the **Global Privacy Control** tab.
7. Near the upper right corner of the page, click **Edit**.
8. Enable the **Enable GPC** toggle, as shown below.

![Enable_GPC.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2190bfd9-cd37-ac40-4f3f-94267354a7ea.png)
9. Configure the GPC banner settings as explained in the following table:

| Setting | Purpose |
| --- | --- |
| Location Intelligence | - Mark the **All** radio button to enable GPC detection in all regions of the globe. - Mark the **Show only in** radio button and select specific regions from the menu for which you want to enable the GPC detection. |
| Category Mapping | Select one or more cookie categories to map to the GPC signal. When the GPC signal is detected on the web browser or devices, these cookie categories mapped are automatically opted out. |
| Conflict Messaging | Enable the **Enable Conflict Messaging** toggle to configure three distinct conflict messages, as shown below. ![GPC-Conflict-Messaging-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-458ed179-54c9-10cb-6a5f-d4a2e0da2134.png) Once enabled, this feature lets you handle conflict between the GPC and a data subject’s privacy preferences. In case of a conflict, you can notify the data subject of the conflict and give them the choice to confirm their privacy preferences. Add custom conflict messages that you wish to show your data subjects for the following scenarios: \| Interaction Nature \| Description \| \| --- \| --- \| \| Opt-in via cookie banner after GPC signal detection \| When the GPC signal is enabled in the web browser and the data subject selects **Accept All** on an opt-in cookie banner, we accept those cookies. A conflict message informs the data subject of this action. \| \| Opt-in via cookie preference center after GPC signal detection \| When the GPC signal is enabled in the web browser and the data subject opts in to cookies from the cookie preference center, we accept those cookies. A conflict message within the cookie preference center notifies the data subject of this action. \| \| GPC Signal activation after opt-in \| If a data subject previously opted in to cookies, but later enables the GPC signal in their web browser, we now decline the cookies according to the GPC signal. A conflict message on the banner flyout informs the data subject of this change. \| |
| Interaction Nature | Description |
| Opt-in via cookie banner after GPC signal detection | When the GPC signal is enabled in the web browser and the data subject selects **Accept All** on an opt-in cookie banner, we accept those cookies. A conflict message informs the data subject of this action. |
| Opt-in via cookie preference center after GPC signal detection | When the GPC signal is enabled in the web browser and the data subject opts in to cookies from the cookie preference center, we accept those cookies. A conflict message within the cookie preference center notifies the data subject of this action. |
| GPC Signal activation after opt-in | If a data subject previously opted in to cookies, but later enables the GPC signal in their web browser, we now decline the cookies according to the GPC signal. A conflict message on the banner flyout informs the data subject of this change. |
| Global Privacy Control Flyout | Enable GPC Flyout Banner (toggle) | Enable this toggle to configure the details of the GPC flyout before and to deploy it on your organizational website when GPC gets detected so that data subjects are timely informed that the GPC signal is detected. > [!WARNING] > **Important** > > Disabling this toggle automatically disables the other three toggles in this section, as shown below. If you enable it, you can toggle the remaining options to suit. If you disable the GPC flyout banner, you can choose to display or hide the floating icon, which opens the banner for five seconds. > > ![GPC-Toggles-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1be1397d-c20f-2750-7177-46ca3766e0f1.png) |
| Enable Floating Icon (toggle) | Enable this toggle to show a floating icon on your domain. When a website visitor lands on your domain, the GPC Flyout Banner appears for **five seconds**. After it disappears, the visitor can click the floating icon to reopen the GPC flyout banner. > [!WARNING] > **Important** > > If you hide the floating icon, you must provide an alternative method for data subjects to manage their consent preferences. For instance, configure a **Revoke Consent** button on your domain that lets visitors access the cookie preference center again. This is necessary because the GPC flyout banner is displayed for only five seconds. |
| Hide Cookie Banner When GPC Signal is Detected (toggle) | Enable this toggle to not show the cookie banner when the GPC signal gets detected on the web browser or device of your data subjects and website visitors. > [!WARNING] > Important > > - Enable this toggle to comply with the CPRA regulation for the **California** region. The regulation prohibits re-asking consent for a period of **12 months** from the data subjects who have already opted-out of the sale and sharing of their personal information. > - When you enable this toggle, it takes precedence over the **Hide Cookie Consent Banner** setting located in the **Customize Banner and Preference Center > Configuration & Mapping** sub-tab of the management portal because we prioritize GPC configurations. For instance, if you have configured a GPC cookie banner for the U.S. and enabled the **Hide Cookie Banner When GPC Signal is Detected** toggle, we don't show the cookie banner to the website visitors in the U.S. if Securiti detects a GPC signal on their device. This occurs regardless of any settings in the **Customize Banner and Preference Center** tab. |
| Hide GPC Flyout After End-User Gives Consent (toggle) | Enable this toggle to comply with the CPRA regulation for the California region. When a Global Privacy Control (GPC) signal is detected, Securiti displays the GPC flyout instead of the cookie banner. Enabling this toggle ensures that once data subjects give consent, the flyout is hidden for the remainder of their session. Per CPRA guidelines, consent should not be requested again for **12 months** from individuals who have already opted out of the sale and sharing of their personal information. |
| Global Privacy Control Setting > [!NOTE] > **Note** > > These settings control the flyout that your data subjects view while visiting your website from a web browser or device with an opt-out preference signal. | Flyout Heading Text | Add a heading text for the expanded mode of the GPC flyout banner. |
| Flyout Text | Add the body text for the expanded mode of the GPC flyout banner to let your data subjects know that the GPC signal is detected and their device and web browsers are opted-out of third party cookies. |
| Add Do Not Sell or Share URL (toggle) | Enable this toggle to add a **Do Not Sell or Share (DNSS)** URL to facilitate the data subject’s opt-out request to comply with the **CPRA Regulation 7025(c)**. |
| Label Text | Use this text field to add the title of the label in which you want to embed your DNSS URL. |
| Label URL | Use this text field to add the DNSS URL to embed in the label title. |
| Add Privacy URL (toggle) | Enable this toggle to add the label in the GPC flyout banner body to reroute your data subjects to the privacy policy of your organization. |
| Label Text | Use this text field to add the title for the privacy policy label. |
| Label URL | Use this text field to add the URL of your privacy policy to embed in the label title. |
| Flyout Hide Button (toggle) | Enable this toggle to display a button for your data subjects to hide the GPC flyout banner. |
| Label Text | Use this field to add the title for the hide button on the GPC flyout. |

> [!NOTE]
> **Note**
> 
> Securiti automatically saves your changes.

For more information on GPC, see [Understanding GPC consent framework and flyout](/v1/docs/understanding-gpc-consent-framework-and-flyout).

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

## Related

- [Configuring an IAB MSPA U.S. National cookie consent banner](/configuring-an-iab-mspa-us-national-cookie-consent-banner.md)
- [Configuring an IAB EU TCF v2.3 cookie consent banner](/configuring-an-iab-eu-tcf-v23-cookie-consent-banner.md)
- [Configuring Google Consent Mode](/configuring-google-consent-mode.md)
