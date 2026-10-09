---
title: "Ensuring proper implementation of Google Consent Mode (GCM)"
slug: "ensuring-proper-implementation-of-google-consent-mode-gcm"
updated: 2025-10-30T19:46:52Z
published: 2025-11-03T06:12:47Z
canonical: "helpcenter.securiti.ai/ensuring-proper-implementation-of-google-consent-mode-gcm"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Ensuring proper implementation of Google Consent Mode (GCM)

You can verify the proper implementation of GCM (GCM) configuration on your domain using the **Tag Assistant** method with Google Tag Manager (GTM) **Preview** mode.

To verify the GCM configuration using GTM Preview mode:

1. Log into your Google Tag Manager (GTM) account, and from the top panel, click **Preview** to enable the preview mode, as shown below.

![Click-Preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-68e1a7b4-4691-6c45-be24-cbcc44f8d653.png)
2. A **Tag Assistant** debug console appears near the bottom of your domain.
3. Access the debugging window to monitor the tags firing on your domain.
4. From the left sidebar, click **Consent Update**, and ensure that it contains all seven Google Consent Types, as shown below.

![Select-Consent-Update.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-744413fd-8523-4cd7-7305-68d77ead056b.png)

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner
