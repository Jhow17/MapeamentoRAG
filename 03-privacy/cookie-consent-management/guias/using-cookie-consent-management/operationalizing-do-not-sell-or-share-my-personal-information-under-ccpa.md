---
title: "Operationalizing Do Not Sell or Share My Personal Information Under CCPA"
slug: "operationalizing-do-not-sell-or-share-my-personal-information-under-ccpa"
updated: 2026-02-09T20:41:44Z
published: 2026-02-09T22:00:18Z
canonical: "helpcenter.securiti.ai/operationalizing-do-not-sell-or-share-my-personal-information-under-ccpa"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Operationalizing Do Not Sell or Share My Personal Information Under CCPA

**Scenario**

This help article provides guidance for organizations operating in California that qualify as a business under the CCPA and engage in the sale or sharing of personal information of data subjects. It explains how to operationalize a compliant **Do Not Sell or Share (DNSS)** workflow using Securiti’s existing capabilities, including Cookie Consent Management, Data Subject Rights (DSR), and the Privacy Center. This guidance helps clarify common confusion around DNSS implementation by outlining recommended configurations, practical considerations, and current platform limitations, based on real customer scenarios and interactions.

> [!NOTE]
> Disclaimer
> 
> The information in this article is for general informational purposes only and does not constitute legal advice. Regulatory obligations vary based on specific facts, jurisdictions, and risk posture. Consult your legal counsel to evaluate how this guidance applies to your organization and to make decisions aligned with your legal and strategic goals.

## Do Not Sell or Share (DNSS) Under CCPA

The **Do Not Sell or Share My Personal Information** (DNSS)) right lets data subjects direct businesses not to sell or share their personal information with third parties under the California Consumer Privacy Act (CCPA).

## Regulatory overview

The CCPA requires businesses to honor DNSS requests by providing a clear and conspicuous **Do Not Sell or Share My Personal Information** link on their internet homepages. This link must direct data subjects, or their authorized agents, to a page where they can opt out of the sale or sharing of personal information.

## Guidance from CCPA regulations

### DNSS request methods

If your business sells or shares personal information, you must provide at least two designated methods for submitting DNSS requests. At least one method must reflect how you primarily interact with data subjects. For online interactions, this includes support for an opt-out preference signal and at least one additional method, such as:

- An interactive opt-out form accessible through the DNSS link
- An alternative opt-out link
- The privacy policy, if you process opt-out preference signals in a frictionless manner

### Cookie-Based and Non-Cookie DNSS

CCPA regulations clarify that cookie notifications, such as a cookie banner or consent preferences, do not by themselves satisfy DNSS requirements. Cookies address the collection of personal information, not the sale or sharing of personal information. DNSS methods must explicitly address sale and sharing.

### Opt-out confirmation

Businesses must provide a way for data subjects to confirm that the business honored their DNSS request or global preference signal.

## Scope of the DNSS Right

DNSS is an individual right under the CCPA. However, because tracking technologies and data ecosystems operate differently, businesses must implement two complementary mechanisms to fully honor DNSS:

- **Cookie-based DNSS**, implemented through the cookie banner and consent preferences
- **Non-cookie (offline) DNSS**, implemented through a dedicated opt-out web form

Businesses must make both mechanisms available to data subjects to fully comply with DNSS requirements, in line with regulatory guidance and recent enforcement actions by the California Attorney General.

## Securiti DNSS best practice guide

Use the following best practices to align your DNSS workflow with CCPA requirements:

- Scan your domain to identify and categorize cookies and tracking technologies involved in the sale or sharing of personal information.
- Based on cookie categorization, deploy the **Opt-out banner** compliance type for CCPA. Disable the close (X) button on the cookie banner. Enable the option to embed the DSR opt-out portal URL in the cookie banner deny button or link.
- Keep the **Cookie Consent Preferences** accessible through the website footer by adding the revoke consent code snippet. When a data subject opts out of cookies, Securiti displays a confirmation message in the consent preferences.
- Add a dedicated **“Do Not Sell or Share My Personal Information”** link in the website footer that directs data subjects to the DSR opt-out form. When the [DSR–Cookie integration](/latest/docs/configuring-signal-to-cookie-consent-in-dsr-form) is enabled for DNSS, submitting a DNSS request also opts the data subject out of non-essential cookies. Securiti then tracks and manages non-cookie DNSS preferences through the DSR workflow.
- Automate and honor the **Global Privacy Control** (GPC) signal and propagate it across online and offline data ecosystems.
- Keep cookie workflows separate from DNSS workflows. Clearly inform data subjects that cookie-based opt-outs apply only to cookies and that they must use the DNSS link to opt out of non-cookie-based sale or sharing.

## Opt-Out confirmation notifications

Securiti displays an opt-out confirmation notification when a data subject opts out through the cookie banner, consent preferences, a DNSS request, or an honored GPC signal. Confirmation messages in consent preferences apply only to cookie-based opt-outs. For non-cookie DNSS requests, businesses must configure a separate workflow and provide a confirmation message after honoring the request.

## Global Privacy Control (GPC) handling

Several U.S. states require businesses to honor GPC signals. When Securiti detects a GPC signal, the GPC flyout appears. Cookie categories mapped to DNSS under GPC are automatically opted out at the browser or device level, and the flyout provides opt-out confirmation.

The GPC flyout also includes a DNSS DSR link that lets data subjects submit a DNSS request for non-cookie-based sale or sharing. This workflow collects additional identifying information, such as email address, so businesses can apply DNSS to backend and offline data. At this time, GPC detection does not automatically generate a DNSS request for offline data.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GPC-Flyout.png)

A consumer right under the California Consumer Privacy Act (CCPA) that lets data subjects direct businesses to stop selling or sharing their personal information with third parties, including for targeted advertising or cross-context behavioral advertising.

The California Consumer Privacy Act (CCPA) was the first state-level comprehensive privacy law in the United States. It applies broadly to for-profit businesses that collect personal information from California consumers, creating certain rights for consumers and obligations for businesses in relation to personal data processing. It was amended by the California Privacy Rights Act (CPRA) in 2020.

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences
