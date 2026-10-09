---
title: "Consent sharing scenarios in Cross-Domain Consent Groups"
slug: "consent-sharing-scenarios-in-cross-domain-consent-groups"
updated: 2026-07-28T10:34:11Z
published: 2026-07-28T10:34:11Z
canonical: "helpcenter.securiti.ai/consent-sharing-scenarios-in-cross-domain-consent-groups"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Consent sharing scenarios in Cross-Domain Consent Groups

Cross-Domain Consent Group (CDCG) evaluates how consent preferences are shared across grouped domains based on how cookie categories compare between domains and the configured Consent Recording Mode, along with signal detection such as GPC. The following scenarios illustrate how CDCG behaves under each condition.

## Cookie category comparison

When a data subject moves from one domain to another within the same group, CDCG compares the cookie categories configured on each domain to determine if consent can be shared and whether a cookie banner needs to appear.

| **Scenario** | **Banner behavior on Website B or Website C** | **Example** |
| --- | --- | --- |
| The source domain and destination domain both have identical cookie categories. | Securiti does not show the cookie banner. Securiti automatically shares the consent preferences. | Website A (`www.securiti.ai`) has Necessary and Analytics. Website B (`privacy.central.com`) has Necessary and Analytics. **Result:** Securiti does not show the cookie banner on Website B. Securiti shares the consent preferences for Necessary and Analytics. |
| The source domain has more cookie categories than the destination domain. | Securiti does not show the cookie banner. Securiti shares consent preferences only for matching cookie categories and ignores extra categories from the source domain. | Website A (`www.securiti.ai`) has Necessary, Analytics, and Marketing. Website B (`privacy.central.com`) has Necessary and Analytics. **Result:** Securiti does not show the cookie banner on Website B. Securiti shares the consent preferences for Necessary and Analytics and ignores Marketing. |
| The destination domain has a net-new cookie category that the source domain does not have. | Securiti shows the full cookie banner on the destination domain. Securiti resets all cookie categories on the destination domain to off, including previously matched categories. | Website A (`www.securiti.ai`) has Necessary and Analytics. Website C (`www.veeam.com`) has Necessary, Analytics, and Marketing. Marketing is a new cookie category. **Result:** Securiti shows the full cookie banner on Website C. Securiti resets Analytics to off because Website C includes a new cookie category. |

## Global Privacy Control (GPC)

> [!WARNING]
> Important
> 
> Securiti currently supports consent sharing only between domains with the same GPC configuration. To ensure consistent consent synchronization, include only GPC-enabled domains together or only non-GPC-enabled domains within the same Cross-Domain Consent Group.
> 
> 
> 
> For instance, if domain A, domain B, and domain C have GPC enabled, group them together. If domain D and domain E do not have GPC enabled, create a separate Cross-Domain Consent Group for those domains. Do not mix GPC-enabled and non-GPC-enabled domains within the same group.

When Global Privacy Control (GPC) is detected, CDCG adjusts consent sharing behavior to honor the data subject's Opt-out signal.

| **Scenario** | **Behavior** |
| --- | --- |
| GPC is enabled on both domains. Data subject visits Website A first, then Website B. | GPC flyout shown on Website A only. GPC floating icon shown on both domains. Opted-out consent from Website A copies over to Website B. > [!WARNING] > Important > > This behavior applies when Website A and Website B both use the same cookie categories and GPC mappings. |

## Implicit consent

When you enable implicit consent on one or both domains in a group, CDCG determines consent sharing based on authentication state and the timing of the implicit consent configuration.

| **Scenario** | **Behavior** |
| --- | --- |
| Implicit consent is enabled on both domains. The data subject visits Website A first, then Website B, where both the landing pages are authenticated. | Securiti does not show the cookie banner on Website B. Securiti copies the consent preferences from Website A to Website B. |
| Implicit consent is enabled on both domains. The data subject visits Website A and Website B, where both the landing pages are unauthenticated. The data subject then logs into both domains. | Securiti shows the cookie banner on Website B. After the data subject logs in, Securiti shares consent based on the Consent Recording Mode selected in the configuration. |
| Implicit consent is enabled on Website A only. The data subject visits Website A first, then Website B. | Securiti does not show the cookie banner on Website B. Securiti copies the consent preferences from Website A to Website B. |
| Implicit consent is enabled on Website B only. The data subject visits Website A first, then Website B. | Securiti does not show the cookie banner on Website B. Securiti copies the consent preferences from Website A to Website B. Website B applies implicit consent to the copied consent preferences based on the cookie banner compliance type configured for Website B. |
| Implicit consent was not enabled on either domain during the first visit. The data subject consented on Website A, then implicit consent was enabled on both domains. The data subject then visits Website B again. | Securiti shows the cookie banner on Website B. Securiti does not copy consent preferences from Website A because the data subject provided the original consent before implicit consent was enabled. |

## Using the latest consent

When the Use Latest Consent mode is active, CDCG always honors the most recent consent choice made across any domain in the group, regardless of which domain the data subject visits next.

| **Scenario** | **Behavior** |
| --- | --- |
| The data subject visits Website A first, then visits Website B and changes consent preferences. | Securiti applies the consent preference update from Website B across the group, overriding the earlier consent preference from Website A. |
| The data subject visits Website B first, then visits Website A and changes consent preferences. | Securiti applies the consent preference update from Website A across the group, overriding the earlier consent preference from Website B. |
| The data subject consents on Website A and never visits Website B. | When the data subject later visits Website B, Securiti applies the latest consent preference from Website A on page load. Securiti does not show the cookie banner. |

For instance, a data subject visits `www.securiti.ai` and opts into Performance, Functionality, and Analytics cookie categories. Days later, they visit `privacy.central.com` for the first time. Those same cookie categories are instantly opted in on page load. No cookie banner appears because Securiti applies the latest known consent choice from `www.securiti.ai`.

## Using consent after login

When the Use Consent After Login mode is active, authenticated consent takes precedence over anonymous consent and syncs across all domains in the group.

| **Scenario** | **Behavior** |
| --- | --- |
| Data subject consents anonymously on Website A, then logs into Website B. | The authenticated consent status from Website B overrides the anonymous consent from Website A and syncs back to Website A. |
| Data subject logs into Website A, then logs into Website B. | Authenticated consent from Website A is propagated to Website B, unless the data subject explicitly changes preferences on Website B. |
| Data subject logs into Website A, then logs into Website B and changes consent. | The updated consent preference on Website B becomes the final consent for both Website A and Website B. The new consent preference syncs back to Website A automatically. |

For instance, a data subject anonymously opts into Performance, Functionality, and Analytics cookie categories on `www.securiti.ai`. They then log into their account on `veeam.central.com`. Their account has a historical opted-out status. That authenticated Opt-out immediately overrides the anonymous opted-in choice and syncs back to `www.securiti.ai`, switching those cookie categories to opted-out there as well.

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

## Related

- [Using Cross-Domain Consent Groups to sync consent across domains](/using-cross-domain-consent-groups-to-sync-consent-across-domains.md)
- [Understanding the Cross-Domain Consent Groups functionality visually](/understanding-the-cross-domain-consent-groups-functionality-visually.md)
