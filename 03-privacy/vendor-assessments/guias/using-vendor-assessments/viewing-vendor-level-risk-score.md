---
title: "Viewing vendor-level risk score"
slug: "viewing-vendor-level-risk-score"
updated: 2025-10-30T19:53:05Z
published: 2025-11-03T06:12:21Z
canonical: "helpcenter.securiti.ai/viewing-vendor-level-risk-score"
area: privacy
modulo: vendor-assessments
tipo: guia
data_captura: 2026-10-08
---

# Viewing vendor-level risk score

The Vendor Assessments module shows the vendor-level scores based on your vendor assessments. These scores let you glance at the vendors in your vendor assessments for evaluation.

It's different from Securiti Rating system on the Vendor Explorer page. Each available vendor score is the sum of average risk scores divided by the number of assessments across all of the vendor's assessments.

To view vendor-level scores, in Securiti, open Vendor Assessments page. In the vendors' list on the left-hand side, you can see vendors with assessment risks. They are marked with a score in a violet circle.

Securiti calculates vendor-level risk using the below formula which gives you average risk score per assessment:

∑ (rs1 ÷ r1 + ... + rsn ÷ rn)

> [!NOTE]
> **Note**
> 
> Where *rs* = *sum of risk scores* and *r* = *number of risks* in an assessment, respectively.

See [Assessing and managing risks in vendor assessments](/v1/docs/assessing-and-managing-risks-in-vendor-assessments) for more information.
