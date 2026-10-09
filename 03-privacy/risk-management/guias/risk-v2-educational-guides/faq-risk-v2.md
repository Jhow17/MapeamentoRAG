---
title: "Frequently asked questions (FAQs)"
slug: "faq-risk-v2"
updated: 2026-06-16T07:17:44Z
published: 2026-06-16T07:17:44Z
canonical: "helpcenter.securiti.ai/faq-risk-v2"
area: privacy
modulo: risk-management
tipo: guia
data_captura: 2026-10-08
---

# Frequently asked questions (FAQs)

---

### FAQ

#### Can I roll back Risk V2?

No. You cannot roll back Risk V2 at this time. Customers must update and align their existing risks with the Risk V2 model.

#### Can I edit Risk Settings?

No. You cannot edit Risk Settings at this time. We are stabilizing customers on Risk V2 and plan to release this feature in production 1.148.

#### Where can I find the enablement webinar recording?

[Customer Enablement Session](https://helpcenter.securiti.ai/docs/risk-management-v2)

#### How are Risk V2 settings determined?

Risk V2 settings follow the configuration from Risk V1.

If all risks in the tenant used a simple linear scale such as high, medium, and low, Risk V2 uses the same linear model. If users selected a 3x3, 4x4, or 5x5 matrix in Risk V1, Risk V2 uses that same matrix.

#### What are the differences between Risk V1 and Risk V2 matrix scores?

There are no differences. Risk V1 and Risk V2 matrix scores are identical for each matrix.

For example, a 3x3 matrix in Risk V1 has the same scores as its Risk V2 counterpart. The same applies to 4x4 and 5x5 matrices.

#### When are risk scores recalculated?

Risk scores are recalculated only when a historical risk uses a different matrix size than the selected settings.

For example, a customer enables a 3x3 matrix and creates a risk. Later, they change the settings to 5x5. During the V2 migration, the system converts the 3x3 risk to 5x5 and recalculates the score.

This ensures all risks follow a unified framework in Risk V2 and supports consistent reporting across historical risks.
