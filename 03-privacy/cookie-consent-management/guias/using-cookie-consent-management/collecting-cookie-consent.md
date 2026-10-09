---
title: "Collecting cookie consent"
slug: "collecting-cookie-consent"
status: "update"
updated: 2026-09-03T06:40:10Z
published: 2026-09-03T06:40:28Z
canonical: "helpcenter.securiti.ai/collecting-cookie-consent"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Collecting cookie consent

Almost every website places cookies on the website visitor’s web browser. Cookies are pieces of tracking data that serve a variety of functions, including tracking whether a data subject is logged into an account, whether they’ve added or removed items from a shopping cart, and to track web browser history to create a more personalized web experience. Most privacy regulations consider personal information collected through cookies to be owned by the data subject, so you must treat this information as personal data.

Although they vary in specific details, most privacy regulations require that your organization obtains the data subject’s consent before your website places cookies in their web browsers. Some go further and also require that you allow data subjects to opt out of cookies.

Securiti's **Cookie Consent Management** module helps you comply with data privacy regulations by:

- Scanning your website to determine what cookies it drops on visitors’ web browsers.

> [!WARNING]
> **Important**
> 
> We identify data subjects, website visitors, and end user based on a unique identifier (UUID) stored in Securiti's [privaci cookies](/v1/docs/categorizing-your-website-cookies).
> 
> Securiti does not consider returning website visitors as new users unless they clear these privaci cookies from their web browser. We consider them a new user only if they clear these cookies and visit the domain again. This results in a new UUID being generated, and the cookie banner appears on your domain again. Maintaining these privaci cookies ensures a seamless experience for returning website visitors without repeatedly showing them the cookie banner.
- Informing data subjects of their rights to accept or opt out of cookies. Securiti's Cookie Consent Management module helps you build a website cookie banner that informs website visitors about the cookies your site uses, and of their rights to accept or decline them.
- Recording data subjects’ consent, or withdrawal of consent, to website cookies. The Securiti consent management tools record each visitor’s consent for cookies, capture the exact text of the agreement to which they consented, and also capture the cookies consented to.

> [!NOTE]
> **Note**
> 
> Securiti collects the consent even in case of network issues such as network failure and unresponsive or down server. When the network goes live again, we retry and record the data subject’s consent.

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.

## Related

- [Using the Cookie Consent Management Legacy Dashboard](/using-the-cookie-consent-management-dashboard.md)
- [Filtering cookie consent records from the Legacy dashboard](/filtering-cookie-consent.md)
