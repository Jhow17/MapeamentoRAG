---
title: "Understanding changes to cookie banner compliance type after deployment"
slug: "understanding-changes-to-cookie-banner-compliance-type-after-deployment"
updated: 2026-08-31T10:26:08Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/understanding-changes-to-cookie-banner-compliance-type-after-deployment"
stale: true
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Understanding changes to cookie banner compliance type after deployment

You can change the cookie banner’s compliance type even after the cookie banner goes live and data subjects provide consent under a previous configuration. The following scenarios explain how Securiti realigns existing consent records to comply with the updated compliance type.

## Changing the cookie banner compliance type to a stricter one

When you change your current cookie banner compliance type to a more strict one, the resulting cookie consent behavior depends on whether you mark the **Show Banner Again** checkbox.

### Scenario 1: When you don’t mark the Show Banner Again checkbox

If you change the compliance type to a more strict compliance type, for instance, from Opt-out to Opt-in, and do not mark the **Show Banner Again** checkbox in the management portal, Securiti:

- Creates a new consent record to comply with Opt-in requirements and the transparency requirements across various privacy laws
- Adjusts cookie behavior and auto-blocking settings

Cookie categories that data subjects previously granted consent for revert to a declined state in line with strict compliance type requirements (such as Opt-in or Hybrid compliance type). Data subjects must provide consent again by interacting with the cookie banner or preference center. Securiti applies this adjustment to meet consent requirements across different privacy laws.

### Scenario 2: When you mark the Show Banner Again checkbox

If you change the compliance type to a more strict compliance type and also mark the **Show Banner Again** checkbox in the management portal, Securiti:

- Does not create a new consent record
- Adjusts cookie behavior and auto-blocking settings

Cookie categories that data subjects previously granted consent for revert to a declined state in line with strict compliance type requirements (such as Opt-in or Hybrid compliance type). Data subjects must provide consent again by interacting with the cookie banner or preference center. Securiti applies this adjustment to meet consent requirements across different privacy laws.

## Changing the cookie banner compliance type to a less strict one

When you change your current cookie banner compliance type to a less strict one, the resulting cookie consent behavior depends on the target compliance type and whether implicit consent is enabled.

### Scenario 1: Standard consent behavior

If you change the compliance type from strict to a less strict compliance type, for instance, from Opt-in to Opt-out, regardless of whether you mark the **Show Banner Again** checkbox in the management portal, Securiti:

- Keeps the existing consent record collected under the Opt-in standard
- Continues cookie and tracking behavior based on previously granted consent

> [!CAUTION]
> Caution
> 
> This behavior does not apply when you change the compliance type to Notice Only. Securiti does not recommend using the Notice Only compliance type because it does not meet consent requirements under various privacy laws. However, Securiti updates consent records to align with Notice Only functionality when you select this option.

### Scenario 2: Implicit consent behavior

> [!WARNING]
> Important
> 
> Securiti strongly recommends that you consult your privacy legal team to ensure that any transition to implicit consent complies with applicable privacy law requirements.

If you enable implicit consent and whether you mark the **Show Banner Again** checkbox in the management portal or not, you must consider the following scenarios:

- If the transition is to a more strict compliance type (for instance, from Opt-out to Opt-in), Securiti adjusts the behavior of cookies and the consent record in line with the more strict compliance type.
- If the transition is to a less strict compliance type (for instance, from Opt-in to Opt-out), Securiti adjusts the behavior of cookies and the consent record in line with the less strict compliance type.

## Behavior of cookies and consent records after changing the compliance type

The following table explains how cookies and consent records behave when you change the compliance type:

| Compliance type transition | When you mark the Show Banner Again checkbox | When you don’t mark the Show Banner Again checkbox |
| --- | --- | --- |
| **Transition to a more strict compliance type** |
| Notice Only to Opt-in | - The data subject can see the cookie banner. - Blocks non-essential cookies based on Opt-in compliance type. | - Blocks non-essential cookies based on compliance type. - Creates an automatic new consent record written in the database and shown in the Cookie Consent Dashboard. |
| Notice Only to Hybrid | - The data subject can see the cookie banner. - Adjusts the behavior of non-essential cookies according to the new Hybrid banner configuration. | - Adjusts the behavior of non-essential cookies according to the new Hybrid banner configuration. - Creates an automatic new consent record written in the database and shown in the dashboard. |
| Notice Only to Opt-out | - The data subject can see the cookie banner. - Non-essential cookies remain active unless the data subject opts out. | - Non-essential cookies remain active unless the data subject opts out. |
| Opt-out to Opt-in | - The data subject can see the cookie banner. - Blocks non-essential cookies based on Opt-in compliance type. | - Blocks non-essential cookies based on compliance type. - Creates an automatic new consent record written in the database and shown in the dashboard. |
| Opt-out to Hybrid | - The data subject can see the cookie banner. - Adjusts the behavior of non-essential cookies according to the new Hybrid banner configuration. | - Adjusts the behavior of non-essential cookies according to the new Hybrid banner configuration. - Creates an automatic new consent record written in the database and shown in the dashboard. |
| Hybrid to Opt-in | - The data subject can see the cookie banner. - Blocks non-essential cookies based on Opt-in compliance type. | - Blocks non-essential cookies based on compliance type. - Creates an automatic new consent record written in the database and shown in the dashboard. |
| **Transition to a less strict compliance type** |
| Opt-in to Opt-out | - The data subject can see the cookie banner. - Honors existing consent records collected under the Opt-in compliance type. | - Honors existing consent records collected under the Opt-in compliance type. |
| Opt-in to Hybrid | - The data subject can see the cookie banner. - Honors existing consent records collected under the Opt-in compliance type. | - Honors existing consent records collected under the Opt-in compliance type. |
| Hybrid to Opt-out | - The data subject can see the cookie banner. - Honors existing consent records collected under Hybrid compliance type. | - Honors existing consent records collected under the Hybrid compliance type. |
| Any compliance type (Opt-in, Opt-out or Hybrid) to Notice Only | - The data subject can see the cookie banner. - Consent status is granted for all cookie categories because all categories are deemed Essential. - A new consent record is automatically written to the database and visible in the dashboard. | - The data subject does not see the cookie banner. - Consent status is granted for all cookie categories because all categories are deemed Essential. - A new consent record is automatically written to the database and visible in the dashboard. |

> [!WARNING]
> Important
> 
> For all compliance type transitions, Securiti honors Global Privacy Control (GPC) when a data subject enables GPC signals in their web browser. Securiti records the data subject’s consent preferences based on the detected GPC signal and automatically opts out all cookie categories mapped to GPC.
