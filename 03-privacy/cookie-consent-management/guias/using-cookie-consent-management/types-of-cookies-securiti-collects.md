---
title: "Types of cookies Securiti collects"
slug: "types-of-cookies-securiti-collects"
updated: 2025-11-03T10:37:02Z
published: 2025-11-03T10:37:02Z
canonical: "helpcenter.securiti.ai/types-of-cookies-securiti-collects"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Types of cookies Securiti collects

Securiti's cookie scanners collect all types of cookies. When you provide consent through the cookie consent banner, Securiti collects the following types of cookies.

| Types of cookies | Description |
| --- | --- |
| First-party cookies | These are dropped by the website itself. |
| Third-party cookies | These are dropped by third parties such as social media platforms like Facebook, Twitter, and YouTube. |
| Cookies with security attributes | Security attributes such as `httpOnly=true` or `secure=true` etc. |
| Tracking pixels | A trackable 1x1 pixel transparent image that you inject into the HTML being rendered by some data subject in order to track their actions on specific events such as clicking an embedded link in an email. A cookie is considered an **Image Beacon** only when: - Images of type `.png`, `.jpg`, `.jpeg`, `.svg`, and `.gif` are fetched on a particular webpage scan - The **pageURL’s** response header has `image/*` as its **contentType** Securiti considers the filtered cookies as Image Beacons when the aforementioned conditions are met and one of the following is true: - The host of **pageURL** is one of **TopTrackers** - The width and height of the image is 1x1 - The width and height of the image is 0x0 > [!NOTE] > **Note** > > Cookie scanner also scans the websites and captures image beacons along with pixels. |
| Local storage items | Local Storage lets JavaScript websites and apps save key-value pairs in a web browser with no expiration date. |
| Session storage items | Session storage objects store data only for a single session. Once you close the web browser, the stored data is automatically deleted. |

Securiti then enriches these collected cookies with category and description information in its cookie database.

A web beacon is a small, usually transparent image embedded on a website or email that tracks the behavior of data subjects.

Local storage item stores the data in a persistent manner until the user manually clears the browser cache or until the web application clears the data.

Session storage item stores the data in a persistent manner only until the window or tab is closed.
