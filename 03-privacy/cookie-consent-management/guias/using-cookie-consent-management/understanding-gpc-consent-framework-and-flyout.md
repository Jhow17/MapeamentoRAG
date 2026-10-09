---
title: "Understanding GPC consent framework and flyout"
slug: "understanding-gpc-consent-framework-and-flyout"
updated: 2026-04-06T15:44:03Z
published: 2026-04-06T15:44:03Z
canonical: "helpcenter.securiti.ai/understanding-gpc-consent-framework-and-flyout"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Understanding GPC consent framework and flyout

**Scenario**

As a Data Privacy Officer, you need to respect browser-level opt-out signals such as GPC. For instance, when a data subject enables Global Privacy Control in their browser, your website must recognize and honor that preference automatically. Without native support, honoring these signals is difficult to scale. Securiti detects GPC headers automatically and adjusts consent logic accordingly. This helps you comply with emerging privacy standards while reducing friction for privacy-conscious users.

Securiti lets you deploy a **Global Privacy Control (**GPC**) consent framework** that enables you to detect **global opt-out preference signals** on your data subjects’ web browsers or devices and opts them out of third party cookie categories. The GPC consent framework also includes the **GPC flyout banner**. This GPC flyout lets you inform data subjects that visit your website and have the GPC enabled on their web browsers and devices that their GPC signal is detected for their web browsers and devices by deploying a flyout banner. It keeps your data subjects informed about whether their signal is being detected or not as required in California and other U.S. states including Colorado, Connecticut, Delaware, Maryland, Minnesota, Montana, Nebraska, New Hampshire, New Jersey, Oregon, and Texas.

You can achieve regulatory compliance by implementing the following features in your GPC consent framework:

- By defining the cookie categories to automatically opt-out upon the detection of the GPC signal on the web browser or device of the data subjects.
- By deploying a customizable flyout which notifies the website visitors and data subjects that their GPC signal is detected by your website, and that their device or web browser has been opted-out of all third party cookies that are involved in the sale or sharing of your personal information, or using it for targeted advertising.
- Additionally, this flyout can provide data subjects who visit your website with the opportunity to provide further identifying information by configuring and adding the **Do Not Sell or Share My Personal Information** URL on the flyout that lets data subjects to make a **Do Not Sell or Share (DNSS)** request to opt-out of the sale or sharing of their personal information, or using it for targeted advertising, through the Data Subject Rights (DSR) portal.
- By making the flyout configurable to add URLs in it that reroute the data subjects to the **Privacy Policy** and **Cookie Preferences** of your organization.
- In the instance where a data subject’s privacy choices differ from the GPC, the latest action performed by the data subject (whether it is GPC enabled or explicit opt-in) must be honored. However, the GPC flyout must provide different conflict messages to the data subjects in the following two conflict scenarios:
  - The conflict message that must appear when the web browser has GPC enabled, but the data subject chooses to opt-in to any of the restricted cookie categories later.
  - The conflict message that must appear when the data subject has already opted-in to any of the restricted cookie categories in their previous visit to your website from the same device or browser and saved these cookie preferences, but the GPC signal gets enabled after that.

> [!NOTE]
> **Note**
> 
> The restricted cookie categories here refer to those cookie categories that you have mapped to the GPC signal. These cookie categories are automatically opted-out once the GPC signal gets detected.

Use the following table to understand all U.S. State Privacy laws that mandate honoring GPC:

| Jurisdiction | Universal Opt-out Mechanism Requirement | Effective Date |
| --- | --- | --- |
| California (CPRA) | ✓ | Already in effect |
| Colorado (CoPA) | ✓ | Already in effect |
| Connecticut (CTDPA) | ✓ | Already in effect |
| Delaware (DPDPA) | ✓ | Already in effect |
| Maryland (MODPA) | ✓ | Already in effect |
| Minnesota (MCDPA) | ✓ | Already in effect |
| Montana (MCDPA ) | ✓ | Already in effect |
| Nebraska (NDPA) | ✓ | Already in effect |
| New Hampshire (NHDPA) | ✓ | Already in effect |
| New Jersey (NJDPA) | ✓ | Already in effect |
| Oregon (OCPA) | ✓ | Already in effect |
| Texas (TDPSA) | ✓ | Already in effect |

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

Colorado Privacy Act (CoPA) is a privacy law applicable to a person doing business in Colorado, or producing/delivering products or services intentionally targeted to Colorado residents, if the person processes personal data (PD) of 100,000 consumers in a year or derives profit from sale of PD while processing PD of at least 25,000 consumers.

Connecticut Data Privacy Act (CTDPA) is a privacy law applicable to a person doing business in Connecticut or producing products or services targeted to Connecticut residents, if the person processes personal data (PD) of 100,000 consumers or derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers in a calendar year.

The Delaware Personal Data Privacy Act applies to persons doing business in Delaware or targeting its residents, and which controls or processes data for either 35,000 consumers,excluding payment data, or controls and processes data for 10,000 consumers while earning over 20% of revenue from selling personal data. From Securiti’s Banner Templates Gallery, you can import a ready-to-use system banner template designed specifically for Delaware and apply it to your domains.

The Maryland Online Data Privacy Act (MODPA) is a privacy law applicable to a person who conducts business in Maryland or provide products or services to Maryland residents, and which during the preceding calendar year: (1) controlled or processed the personal data of at least 35,000 consumers, excluding payment data; or (2) controlled or processed personal data of at least 10,000 consumers and derived 20% of revenue from sale of personal data.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Maryland and apply it to your domains.

The Minnesota Consumer Data Privacy Act (MCDPA) is a privacy law applicable to legal entities which conduct business in Minnesota or provide products or services to Minnesota residents, and which satisfy one or more of following thresholds: (1) control or process personal data of at least 100,000 consumers, excluding payment data, during a calendar year; or (2) process or control personal data of 25,000 consumers and derive 25% of revenue from sale of personal data.

From Securiti's **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Minnesota and apply it to your domains.

Montana Consumer Data Privacy Act (MCDPA) is a privacy law applicable to a person doing business in Montana or producing products or services targeted to Montana residents, if the person:

- Controls or processes personal data (PD) of 50,000 consumers in a year.
- Derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Montana and apply it to your domains.

The Nebraska Data Privacy Act (NDPA) is a privacy law applicable to a person, excluding a small business as defined by the Small Business Act, who: (a) conducts business in Nebraska or produces products or services consumed by Nebraska residents; and (b) processes or engages in the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Nebraska and apply it to your domains.

The New Hampshire Data Protection Act (NHDPA) is applicable to persons doing business in New Hampshire or targeting its residents, and which controls or processes the personal data of either 35,000 consumers, excluding payment data; or of 10,000 consumers and deriving 25 percent of revenue from selling personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for New Hampshire and apply it to your domains.

The New Jersey Data Protection Act (NJDPA) is applicable to persons doing business in New Jersey or targeting its residents, and which controls or processes data for either 100,000 consumers, excluding payment data, or for 25,000 consumers while earning revenue or discounts from selling personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for New Jersey and apply it to your domains.

Oregon Consumer Privacy Act (OCPA) is a privacy law applicable to a person doing business in Oregon or producing products or services to Montana residents, if the person during a calendar year:

- Controls or processes personal data (PD) of 100,000 consumers.
- Derives 25% of gross revenue from sale of PD while processing PD of at least 25,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Oregon and apply it to your domains.

Texas Data Privacy and Security Act (TDPSA) is a privacy law applicable to a person, excluding a small business as defined by the United States Small Business Administration, who: (a) conducts business in Texas or produces products or services consumed by residents of Texas; and (b) processes or engages in the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Texas and apply it to your domains.
