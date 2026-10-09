---
title: "Understanding the Cross-Domain Consent Groups functionality visually"
slug: "understanding-the-cross-domain-consent-groups-functionality-visually"
updated: 2026-07-20T17:16:59Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/understanding-the-cross-domain-consent-groups-functionality-visually"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Understanding the Cross-Domain Consent Groups functionality visually

The following flow diagram illustrates how cross-domain consent synchronizes a data subject's consent across multiple domains (websites) in a Cross-Domain Consent Group (CDCG). Although each domainwebsite can use its own cookie category names, every cookie category is mapped to a Securiti Standard Cookie Category. These mappings create a common framework that lets Securiti synchronize consent consistently across every participating website without requiring identical cookie category names.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cross-Domain-Consent Group-Visual-Design.png)

## How cross-domain consent works

Cross-domain consent uses **Securiti Standard Cookie Categories** as a common mapping layer between all domains in a Cross-Domain Consent Group.

Instead of mapping cookie categories directly between domains, each domain maps its cookie categories to the appropriate Securiti Standard Cookie Category. This creates a centralized relationship that Securiti uses to synchronize consent across every domain in the group.

For instance, one domain may use **Strictly Necessary**, another may use **Necessary**, while another uses **Required**. Although these cookie category names are different, they can all be mapped to the **Essential** Securiti Standard Cookie Category. When a data subject updates their consent for that cookie category on one domain, Securiti automatically synchronizes the corresponding consent decision to the mapped cookie categories on every other domain in the Cross-Domain Consent Group.

The same behavior applies to every mapped cookie category. After you configure the mappings, Securiti automatically synchronizes consent whenever a data subject updates their consent on any domain in the group.

## Understanding the diagram

The flow diagram includes four domains (websites) participating in the same **Cross-Domain Consent Group (CDCG)**.

- **Website A (**`www.securiti.ai`**)** contains the cookie categories Strictly Necessary, Performance, Advertising, Preferences, and Personalization.
- The center column represents the **Cross-Domain Consent Group (CDCG)**.
  - Every website maps its cookie categories to the appropriate Securiti Standard Cookie Categories.
  - These mappings serve as the common layer that Securiti uses to synchronize consent across every website in the group.
- **Website B (**`privacy.central.com`**)**, **Website C (**`www.veeam.com`**)**, and **Website D (**`veeam.central.com`**)** each use their own cookie category names and structures. Their cookie categories do not need to match those used by Website A as long as they are mapped to the appropriate Securiti Standard Cookie Category.

For instance, if a data subject updates their consent preferences on Website A (`www.securiti.ai`). Securiti first identifies the Securiti Standard Cookie Categories associated with the selected cookie categories. It then identifies every mapped cookie category across the remaining websites in the Cross-Domain Consent Group and synchronizes the same consent decision to those mapped cookie categories.

For instance:

- **Strictly Necessary** on Website A maps to the **Essential** Securiti Standard Cookie Category, which also maps to **Necessary** on Website B, **Required** on Website C, and **Essential** on Website D.
- **Advertising** on Website A maps to the corresponding Securiti Standard Cookie Category and synchronizes with the mapped cookie categories on the other participating websites.
- **Preferences** on Website A maps to the **Marketing** Securiti Standard Cookie Category, which synchronizes with the corresponding mapped cookie category on Website D.
- **Performance** on Website A maps to the **Functional** Securiti Standard Cookie Category, which synchronizes with the corresponding mapped cookie category on Website C.

As a result, every participating domain maintains its own cookie category names while sharing a consistent consent experience.

> [!WARNING]
> Important
> 
> Cookie category names do not need to be identical across participating websites. Securiti synchronizes consent based on the configured Securiti Standard Cookie Category mappings.

## Keeping cookie category mappings up to date

Whenever you add, rename, remove, or reorganize cookie categories on a participating domain, you must also review the corresponding mappings in the Cross-Domain Consent Group.

Securiti synchronizes consent only for cookie categories mapped to a Securiti Standard Cookie Category. If you do not map a cookie category, Securiti does not synchronize consent for that cookie category across the remaining domains in the group.

This is particularly important when you introduce new cookies or trackers, reorganize cookie categories, or update your consent strategy. Keeping cookie category mappings up to date helps ensure that Securiti continues to synchronize consent correctly across the Cross-Domain Consent Group.

## Related

- [Using Cross-Domain Consent Groups to sync consent across domains](/using-cross-domain-consent-groups-to-sync-consent-across-domains.md)
- [Consent sharing scenarios in Cross-Domain Consent Groups](/consent-sharing-scenarios-in-cross-domain-consent-groups.md)
