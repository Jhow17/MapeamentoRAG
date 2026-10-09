---
title: "Impact analysis of Legacy SDK's retirement"
slug: "impact-analysis-of-legacy-sdks-retirement"
updated: 2026-04-17T13:48:19Z
published: 2026-04-17T13:48:19Z
canonical: "helpcenter.securiti.ai/impact-analysis-of-legacy-sdks-retirement"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Impact analysis of Legacy SDK's retirement

This help topic outlines the possible critical consequences of using the Legacy SDK deployment option for your domains within the Cookie Consent Management module after its expiration. As Securiti phases out this option, it is essential for you to understand the impact of not transitioning to either the **Automatic** or **Manual SDK** deployment option.

The Legacy SDK deployment was a temporary solution to ensure stability and continuity for existing configurations after facing challenges with the initial SDK version control functionality. However, continuing on this legacy option may adversely affect the functionality and effectiveness of your domain's cookie configurations.

This impact document serves as a crucial call to action for all stakeholders to assess their current SDK deployment and plan for necessary upgrades to align with the best practices of Securiti’s Cookie Consent Management module.

## Consequences of staying on the Legacy SDK deployment option

Use the following table to clearly grasp the consequences and implications of not transitioning from the Legacy SDK deployment option:

| Impact Category | Description |
| --- | --- |
| Outdated Functionality | Domains using the Legacy SDK deployment option will not receive latest Securiti updates, which include enhancements and new functionalities available with each Securiti release. This limitation restricts your ability to use the latest advancements in cookie management technology. |
| Potential Compliance Issues | The cookie banner and preference center configurations may become outdated, potentially leading to non-compliance with new privacy laws and regulations. As legal standards evolve, staying updated is crucial to ensure compliance. |
| Degraded User Experience | Over time, the Legacy SDK may not interact well with new web technologies or updates to existing technologies. This misalignment can lead to issues such as broken layouts or malfunctioning consent banners, directly impacting user experience. |
| Security Vulnerabilities | Without regular and latest SDK updates, the Legacy SDK might be exposed to security vulnerabilities that are typically addressed in newer versions of the cookie consent SDK. Continuing to use an unsupported version can pose significant security risks to your domain and user data. |
| Devoid of Support | Future support and troubleshooting efforts will focus on the **Automatic** and **Manual SDK** deployment options. Support for issues arising from the Legacy SDK **will not be available**, which could lead to extended downtimes and increased operational risk. |
| Incompatibility with New Features | New functionalities and enhancements that improve the efficiency and effectiveness of the cookie consent process will not be compatible with the Legacy SDK. This incompatibility means missing out on features designed to enhance user consent experiences and operational ease. |
| Reduced Analytics Accuracy | Sticking to the Legacy SDK can lead to inaccuracies in analytics, as newer analytic tools or updates may not be compatible. Inaccurate data can affect decision-making and hinder the ability to track user engagement effectively. |
| Cost Inefficiencies | Continuously managing and troubleshooting older technology often leads to higher operational costs. Transitioning to updated SDK versions can help optimize resources and reduce long-term expenses associated with maintaining outdated technology. |
| Decreased Market Competitiveness | Remaining on a legacy system may cause your site to lag behind competitors who adopt newer technologies, potentially leading to a decrease in user trust and a loss of market share. |

## Domain configuration specific examples

Use the following table to understand the impact of not migrating from the Legacy SDK deployment option before its expiration on June 30, 2024.

| Example | Explanation |
| --- | --- |
| Conflicts with New Configuration Files | Securiti will auto-migrate only the UI SDK deployment option from Legacy SDK to Automatic SDK once legacy SDK expires, as shown below. ![Legacy-UI-options-move.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b47be4c3-33e0-2355-b62d-0fafd61108d7.png) > [!CAUTION] > **Warning** > > This will only be an management portal UI change. We will not deploy the Automatic SDK code to your domains. You must copy the **Deployment Code**, and paste it at the beginning of the `&lt;head&gt;` tag in your domain’s HTML once Legacy SDK expires. If you continue using the Legacy SDK deployment option after its expiration, Securiti will automatically migrate the UI option from Legacy SDK to the Automatic SDK deployment option. This automatic migration of the UI deployment option can cause conflicts on your domain because it will still be using the Legacy SDK deployment code. Whenever you make changes in the management portal and deploy them to your domain, Securiti updates the `en.json` file with your latest cookie configuration changes. If your domain is still using the old Legacy SDK code, these new changes in the `en.json` file will conflict with the outdated Legacy SDK code.Therefore, once the Legacy SDK expires, you must copy the new **deployment code** for the **Automatic SDK** from the management portal, and paste it at the beginning of the `&lt;head&gt;` tag in your domain’s HTML. |
| Quality Assurance (QA) and Quality Control (QC) Testing Limitations | Securiti will not conduct QA/QC testing for the legacy SDK option. Our testing efforts will focus solely on the functionalities of the **Automatic** and **Manual SDK** options to ensure they are thoroughly vetted before release. This means that any issues or bugs related to the Legacy SDK will not be addressed by our testing processes. |
| Impact on Auto-Blocking Functionality | The auto-blocking functionality associated with the old Legacy SDK option may adversely affect your domains. This can lead to cookie banners breaking, which will cause difficulties in maintaining proper cookie consent management. There will be consent collection and banner appearance issues on your domains. Transitioning to the new SDK deployment options will help avoid these issues. |

## Securiti’s Recommendation

To avoid these potential risks and ensure a seamless, compliant, and secure user experience, **we strongly recommend** transitioning from the Legacy SDK deployment option to either the **Automatic** or **Manual SDK** deployment option. After this transition, you must copy the new **deployment code** for the **Automatic** or **Manual SDK** (whichever you selected) from the management portal, and paste it at the beginning of the `&lt;head&gt;` tag in your domain’s HTML.

This transition will enable access to the latest functionalities, ensure compliance with evolving regulations, and provide better support and security updates.
