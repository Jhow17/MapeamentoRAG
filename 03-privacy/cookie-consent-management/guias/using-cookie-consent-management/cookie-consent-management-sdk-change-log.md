---
title: "Cookie Consent Management SDK change log"
slug: "cookie-consent-management-sdk-change-log"
updated: 2026-09-22T20:07:39Z
published: 2026-09-22T20:07:39Z
canonical: "helpcenter.securiti.ai/cookie-consent-management-sdk-change-log"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Cookie Consent Management SDK change log

> [!WARNING]
> Important
> 
> Refer to the [status page](/latest/docs/about-new-securiti-releases#status-pages) to check when these updates becomes available on your production cloud.

## 1.151.0 - September 2026

### New

- Added the **Cookie Consent Browser Assistant** extension to simplify Cookie Consent SDK debugging with a dedicated DevTools panel, real-time event tracking, and new programmatic events for the Auto-Blocking SDK.

### Fixes (Management Portal)

- No updates

### Fixes (Accessibility)

- No updates

---

## 1.150.0 - August 2026

### New

- Enhanced the **Show Banner Again** checkbox to support additional consent scenarios, including GPC and Implicit Consent, for more consistent cookie banner redisplay behavior.

### Fixes (Management Portal)

- Fixed an issue where the Cookie Consent SDK failed to load when the initiator used a specific numeric format, such as `23:23:234:0`, by adding safeguards to prevent blocking and rendering failures (PRIV-254836).

### Fixes (Accessibility)

- No updates

---

## 1.149.0 - August 2026

### New

- No updates

### Fixes (Management Portal)

- Fixed a UI issue in the cookie preference center where the Always Active toggle overlapped with longer cookie category names, such as Performance and Functionality, when Georgian was selected as the language (PRIV-212360).

### Fixes (Accessibility)

- No updates

---

## 1.148.0 - July 2026

### New

- Added support for Cross-Domain Consent Groups (CDCG), enabling the SDK to synchronize data subject consent across grouped domains based on configured Securiti Standard Cookie Category mappings. Once configured, a consent decision captured on one participating domain is automatically synchronized to the corresponding mapped cookie categories on the other domains in the group (PRIV-235375).
- Enhanced CSS compatibility with Adobe Experience Manager (AEM) websites. The SDK now uses dedicated container classes for the cookie banner and preference center to reduce CSS conflicts with existing website styles (PRIV-245728).

### Fixes (Management Portal)

- No updates

### Fixes (Accessibility)

- No updates

---

## 1.147.0 - June 2026

### New

- No updates

### Fixes (Management Portal)

- No updates

### Fixes (Accessibility)

- No updates
