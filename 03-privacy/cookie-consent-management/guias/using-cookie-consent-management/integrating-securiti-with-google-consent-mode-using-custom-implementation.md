---
title: "Integrating Securiti with Google Consent Mode using Custom implementation"
slug: "integrating-securiti-with-google-consent-mode-using-custom-implementation"
updated: 2026-02-24T16:54:41Z
published: 2026-02-24T16:54:41Z
canonical: "helpcenter.securiti.ai/integrating-securiti-with-google-consent-mode-using-custom-implementation"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Securiti with Google Consent Mode using Custom implementation

Securiti also lets you implement GCM (GCM) using the Custom implementation option. This option gives you the flexibility to use any implementation approach that suits your business needs, whether it is Google Tag Manager (GTM), gtag, or a custom solution.

With the custom implementation option, you can have more control over how GCM integrates with your domains, enabling you to tailor the implementation to your specific requirements and scale more effectively.

To integrate Google Consent Mode with your domain if you are using the Custom implementation option:

1. Configure Google Consent Mode from the management portal by following the procedure as explained in [Configuring Google Consent Mode](/latest/docs/configuring-google-consent-mode).

> [!WARNING]
> **Important**
> 
> When you use the Custom implementation option, Securiti ignores the **Default Google Consent States** and **Region Overrides** set in the management portal.
2. Set up your custom implementation method to integrate Google Consent Mode with your domain. Ensure that your custom setup aligns with your selected implementation framework, such as a custom script or a third-party tag management solution.
3. Test the implementation to verify that the correct data layer events are triggered for consent actions. Use your web browser's developer tools or a tag debugging tool to confirm that consent-related data is passed as expected according to your custom setup.

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner
