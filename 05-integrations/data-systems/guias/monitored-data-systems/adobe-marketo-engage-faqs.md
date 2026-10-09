---
title: "Adobe Marketo Engage FAQs"
slug: "adobe-marketo-engage-faqs"
updated: 2026-08-28T11:45:01Z
published: 2026-08-28T11:45:01Z
canonical: "helpcenter.securiti.ai/adobe-marketo-engage-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Adobe Marketo Engage FAQs

[1. What happens if a discovery scan hits the Adobe Marketo Engage daily export limit and exhausts its retry attempts?](/latest/docs/adobe-marketo-engage-faqs#faq)

[2. Why doesn't the Activities object appear in DSR requests for Adobe Marketo Engage?](/latest/docs/adobe-marketo-engage-faqs#faq)

### FAQ

#### 1. What happens if a discovery scan hits the Adobe Marketo Engage daily export limit and exhausts its retry attempts?

Securiti automatically restarts the export when the quota resets daily at 12:00 AM CST. The scan continues without user intervention, though it may take a little longer to finish.

For more information, see [Marketo Integration Best Practices](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/marketo-integration-best-practices#api-limits).

#### 2. Why doesn't the Activities object appear in DSR requests for Adobe Marketo Engage?

The Activities object stores behavioral engagement data, such as opens, clicks, and form fills, rather than personal profile data. Because Adobe Marketo Engage's API doesn't support looking it up by data subject identifiers, this data isn't included in DSR requests. The Activities object still appears in the Scope section during a discovery scan, since discovery scans catalog all available objects, as shown below. For more information, see [Marketo Developer Guide](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/lead-database/activities#query-types).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/base64-converted-image-1785830527088.png)
