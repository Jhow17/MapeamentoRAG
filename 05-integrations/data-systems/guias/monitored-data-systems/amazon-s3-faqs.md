---
title: "Amazon S3 FAQs"
slug: "amazon-s3-faqs"
updated: 2026-04-27T12:12:07Z
published: 2026-04-27T12:12:07Z
canonical: "helpcenter.securiti.ai/amazon-s3-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon S3 FAQs

This article covers frequently asked questions (FAQs) for Amazon S3 data system connector:

****Why was the “Last Modified” timestamp updated after applying labeling policy in Amazon S3?****

Amazon S3 automatically updates the Last Modified timestamp whenever an object is modified. Applying a data labeling policy results in a change to the object, which triggers S3 to assign a new Last Modified value.

****Is it possible to retain the original “Last Modified” timestamp after applying data labeling policy in Amazon S3?****

No, the Last Modified attribute is fully managed by Amazon S3 and is updated automatically upon any modification. External platforms, including Securiti, cannot preserve or override the original timestamp once a change has occurred.
