---
title: "Understanding the Hybrid compliance type"
slug: "understanding-the-hybrid-compliance-type"
updated: 2026-04-06T15:49:03Z
published: 2026-04-06T15:49:03Z
canonical: "helpcenter.securiti.ai/understanding-the-hybrid-compliance-type"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Understanding the Hybrid compliance type

**Scenario**

As a Data Privacy Officer, you must align cookie consent with U.S. state laws that differentiate between sensitive and general data. For instance, certain laws may require sensitive categories to be declined by default while allowing other categories to remain enabled. A one-size-fits-all consent approach does not work in these cases. Securiti’s Hybrid compliance type for cookie banners lets you set Declined for sensitive categories and Granted for others by default. This helps you stay compliant with nuanced laws while simplifying cookie banner logic.

The requirement for a Hybrid compliance type stems from U.S. state privacy laws. Certain cookie categories, such as **Biometrics** or **Precise Geolocation**, may collect personal information of data subjects that is considered sensitive under U.S. state privacy laws and requires prior Opt-in consent of the Data subject.

The Hybrid compliance type functionality provides flexibility, letting you set the default consent state for cookies that handle sensitive personal information to Declined, while setting the default consent state for other cookie categories to Granted.

U.S. state privacy laws let data controllers rely on an implied or Opt-out mode of consent for some cookie categories. At the same time, these regulations require an explicit or opt-in mode of consent for categories such as biometrics, precise geolocation, or other sensitive personal information. Therefore, Securiti recommends configuring a cookie banner and preference center using the Hybrid compliance type in such locations to address:

- Cookie categories for which the default consent state is **Always Active (Essential)**
- Cookie categories for which the default consent state is **Granted**
- Cookie categories for which the default consent state is **Declined**

### How the Hybrid cookie preference center works

The Hybrid cookie preference center supports multiple consent states and jurisdiction-based compliance with global privacy laws. Each cookie category in the preference center can be associated with one or more consent states, such as **Always Active**, **Declined**, or **Granted**. You should determine the default consent state for each category based on the data subject’s geographic location and the applicable legal requirements.

For instance, the default cookie banner and preference center configuration for **Virginia** would look like this:

| Cookie category | Consent state of cookie category |
| --- | --- |
| Essential | Always Active |
| Advertisement | ✓ Granted Always Active Declined |
| Performance | ✓ Granted Always Active Declined |
| Analytics | ✓ Granted Always Active Declined |
| Precise Geolocation | Granted Always Active ✓ Declined |
| Biometrics | Granted Always Active ✓ Declined |

### When to use the Hybrid compliance type

Based on relevant privacy laws and regulations, Securiti recommends using the Hybrid compliance type in the following locations (segregated by U.S. states, Canadian provinces, and countries):

| Location category | Name |
| --- | --- |
| Country | Australia |
| Canadian provinces | Quebec |
| U.S. States | - Colorado - Connecticut - Delaware - Florida - Indiana - Kentucky - Maryland - Minnesota - Montana - Nebraska - New Hampshire - New Jersey - Oregon - Rhode Island - Tennessee - Texas - Virginia |

Use the Hybrid compliance type to comply with the privacy laws and regulations in the listed locations. These laws let you set the default state to **Granted** for some cookie categories while setting it to **Declined** for cookie categories such as Biometrics, Precise Geolocation, or other sensitive personal information.

### Scenarios where the Hybrid compliance type does not apply

You **must not** use the Hybrid compliance type in the following scenarios:

- Where the privacy laws or regulations require prior explicit consent for all cookie categories and the default consent state for all categories must be **Declined**.
- Where the privacy laws or regulations only require implied consent for all cookie categories and the default consent state for all categories is **Granted**.
- If, during a domain scan, Securiti's cookie scanner does not detect any cookies that require a hybrid cookie banner, such as those related to biometric data, precise geolocation, or other sensitive personal information.

### Cookie category mapping for the Hybrid compliance type

> [!NOTE]
> Note
> 
> The Precise Geolocation and Biometrics cookie categories default to a **Declined** consent state under Hybrid compliance to align with regulatory expectations for sensitive personal data. You can still modify cookie category settings to suit.

Use the following table to understand the mapping of cookie categories under the Hybrid compliance type:

| Location | Mapping description |
| --- | --- |
| U.S. States | For Colorado, Connecticut, Delaware, Florida, Indiana, Kentucky, Maryland, Minnesota, Montana, Nebraska, New Hampshire, New Jersey, Oregon, Rhode Island, Tennessee, Texas, Virginia, the default consent state for biometrics, precise geolocation is **Declined**, while the recommended state for remaining cookie categories is **Granted**. |
| Quebec (Canada) | The default consent state for biometrics and precise geolocation cookies is **Declined**. For the remaining cookie categories, the recommended state is **Granted**. |
| Australia | The default consent state for biometrics cookies is **Declined**. For remaining cookie categories, the recommended state is **Granted**. |

Under a hybrid compliance type, data subjects can manage both opt-in and opt-out consent within the same jurisdiction, depending on the type of cookie and applicable laws. You can configure default consent states for different cookie categories, such as setting sensitive data cookies to **Declined** and others to **Granted**. This ensures compliance with varying consent requirements under different privacy laws.

Under an Opt-in cookie banner compliance type, cookies are not set on the data subject's device until they have explicitly given permission. This means that, except for strictly necessary cookies (which are essential for the basic functioning of the website), no cookies are loaded until the data subject actively consents to them. This approach is particularly common in regions like the European Union, where regulations such as the General Data Protection Regulation (GDPR) require explicit consent for the storage or access of information on a user's device.

A consumer or other member of the general public whose personal data is held by a controller or processor.

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

## Related

- [Categorizing your website cookies](/categorizing-your-website-cookies.md)
- [Configuring geo-specific consent states for cookie categories](/configuring-geo-specific-consent-states-for-cookie-categories.md)
