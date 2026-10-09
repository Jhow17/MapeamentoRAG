---
title: "Risks of using outdated Legacy SDK deployment code"
slug: "risks-of-using-outdated-legacy-sdk-deployment-code"
updated: 2026-04-17T13:47:16Z
published: 2026-04-17T13:47:16Z
canonical: "helpcenter.securiti.ai/risks-of-using-outdated-legacy-sdk-deployment-code"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Risks of using outdated Legacy SDK deployment code

As Securiti continues to innovate and update its Cookie Consent SDK, if you continue using the Legacy SDK on your domains beyond its expiration on **June 30, 2024**, your domain configurations are facing increasing risks.

This help article provides an overview of key functionalities and features that may be compromised with the Legacy SDK, emphasizing the importance of upgrading to ensure compliance and maintain full functionality.

## Functionality limitations for domains using Legacy SDK

Use the following table to understand which key features and functionalities of the Cookie Consent Management module are limited, incompatible, or unavailable with the Legacy SDK deployment option:

| Functionality | Description | Availability Scope with Legacy SDK |
| --- | --- | --- |
| [IAB EU TCF v2.3](/v1/docs/configuring-an-iab-eu-tcf-v22-cookie-consent-banner) | Securiti's latest SDK includes this functionality. It lets you enhance transparency and control over cookie consent management across Europe. You cannot have access to this functionality with the Legacy SDK. | `Unavailable` We recently integrated the IAB EU TCF v2.3 consent framework into our module, which facilitates compliance with the **ePrivacy Directive** and **GDPR** requirements. However, Securiti supports these regulatory updates only in its latest SDKs (Manual and Automatic). Consequently, domains using the Legacy SDK cannot access this functionality. ![IAB_EU_TCF_-_Legacy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6d88bdc-61f1-4d79-2a9e-d274df5d3459.png) |
| [Google Consent Mode v2](/v1/docs/configuring-google-consent-mode) | Google Consent Mode lets you precisely handle the user consents and their implications for Google services. It is not available with the Legacy SDK. This functionality enhances your ability to manage the consent of your data subjects and website visitors across Google products efficiently. It supports a smoother experience for you and your website visitors by respecting consent preferences across their journey. | `Unavailable` Securiti does not offer GCM v2 to domains using the Legacy SDK, as it is designed to be compatible only with the Manual and Automatic SDK deployment options. |
| [Location Override](/v1/docs/configuring-geo-specific-consent-states-for-cookie-categories) feature of the [Opt-out Rules](/v1/docs/configuring-geo-specific-consent-states-for-cookie-categories) functionality | Part of the Opt-out Rules functionality, this feature lets you configure location-based consent management, which you cannot access with the Legacy SDK. | `Partially available` You can configure Opt-in and Opt-out states for cookies at an individual cookie category level. However, **you cannot apply these configurations** to specific geolocations using the **Location Override** feature that lets you comprehensively customize and enhance compliance with regional regulations to improve user experience. |
| Recent enhancements to [Customize Banner and Preference Center](/v1/docs/customizing-your-cookie-banner-and-preference-center) tab | - Hide Cookie Consent Banner - Preference Center Toggle Setting - Alternative Text for Company Logo - Data Subject Request Portal | `Unavailable` If your domain is using the Legacy SDK code, Securiti does not show these recently added settings. For instance: - You cannot hide the cookie consent banner if you do not want to show the cookie consent banner on your domain to your data subjects or website visitors. - You cannot provide a custom alternate label text or use the default “Always Active” label text next to the toggles that appear on the cookie preference center. - You cannot provide an alternative text for your organization's logo. Providing alternative text ensures compliance with the **ADA civil rights law**, enhancing accessibility for data subjects or website visitors using assistive technologies, which narrate the alternative text to describe the organization’s logo. - You cannot embed the link to your organization's Data Subject Rights portal in the **Deny** button or link that appears on the cookie banner. This feature ensures you stop any offline or ongoing sale or sharing of personal information previously collected about the data subjects or website visitors, complying with the **CPRA** and similar U.S. state privacy laws. |
| [Banner Templates Gallery](/v1/docs/using-the-banner-templates-gallery) | This functionality lets you build and manage a library of both **system** and **custom** banner templates for your domains. You can import ready-to-use system banner templates designed to comply with various legal requirements, applying these templates directly to the cookie banners and preference centers of your scanned and published domains. However, these out-of-the-box or custom banner templates cannot be applied to domains that are using the Legacy SDK. | `Limited availability` If your domain uses the Legacy SDK, note that while you can view the out-of-the-box system cookie banner templates in the Banner Templates Gallery, **you cannot apply them to your domain**. This restriction exists because Securiti consistently updates these templates to comply with ongoing regulatory changes, and these system banner templates are only compatible with our latest Manual and Automatic SDKs. The Legacy SDK, being outdated, does not support these updated templates. |
| [Restoring a previous SDK version](/v1/docs/restoring-a-previous-sdk-version) | Securiti's SDK restoration functionality serves as a safety net, letting you revert to the previous stable SDK version when the latest release is incompatible with your domain or exhibits unexpected issues. This functionality ensures that you can maintain operational stability **without waiting for patches** or **fixes**, offering a quick and reliable solution to manage SDK transitions effectively. | `Unavailable` Domains using the Legacy SDK cannot take advantage of our SDK Version Control functionality. This functionality is very useful when the latest SDK version is incompatible with your domain. It lets you quickly restore a previous stable SDK version if the newest one causes issues or fails to meet your needs, eliminating the need to wait for a patch or fix. Because the Legacy SDK uses outdated code and Securiti does not update it with each release, domains using the Legacy SDK cannot access this functionality. This is because there is no option to revert to a previous SDK version, as no updates are available for the Legacy SDK. ![Depolyed_Version_History_-_Legacy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9b94499f-da59-0a82-a9c5-9f119dba4c0d.png) |

## Action required

Securiti will auto-migrate only the UI SDK deployment option from **Legacy SDK** to **Automatic SDK** once the upcoming Securiti release **1.120** goes live on 06 August 2024, for the domains using Legacy SDK in your Securiti tenant, as shown below.

![UI-Migration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a410adc7-f7ee-9416-1a04-cb3a2ddbd253.png)

> [!CAUTION]
> **Warning**
> 
> This will only be an management portal UI change. Securiti **will not** deploy the Automatic SDK code to your domains.
> 
> You must copy the **Deployment Code** (located in the UI of **Consent Code** tab), and paste it at the beginning of the `&lt;head&gt;` tag in your domain.
> 
> ![Deployment-Code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1efacc9d-1188-2fc1-83c2-a86c29f38007.png)

If you continue using the Legacy SDK deployment option beyond its expiration on June 30, 2024, Securiti will automatically migrate the UI option from Legacy SDK to the Automatic SDK deployment option.

This automatic migration of the UI deployment option will reveal all the latest features and functionalities previously incompatible with the Legacy SDK, which were hidden or disabled in the management portal. You will be able to see and interact with these features and functionalities, but leveraging them will not be possible. Using these features will cause conflicts on your domain, as it will still be using the Legacy SDK deployment code that does not support these new features and functionalities.

After configuring these features, you can preview them in the management portal using the **Preview** capability, and they may appear fine in the preview. However, as soon as you deploy them to your domain, which still operates under the outdated Legacy SDK deployment code, conflicts will arise. You will not see the results of these changes you configured from the management portal, because your domain continues to use the old and outdated Legacy SDK code.

A key factor is that when you make changes in the management portal and deploy them to your domain, Securiti updates the `en.json` file with your latest cookie configuration changes. However, since your domain still operates on the outdated Legacy SDK, these updates in the `en.json` file will conflict with it. As a result, you will not be able to leverage the new features and functionalities. For more information, see [Example scenarios and corner cases](/v1/docs/risks-of-using-outdated-legacy-sdk-deployment-code).

Securiti **strongly advises** you to migrate immediately to either the **Manual** or **Automatic SDK** deployment option. This action includes adding the updated **Deployment Code** (located in the UI of **Consent Code** tab) at the beginning of the `&lt;head&gt;` tag of your domain.

![Deployment-Code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1efacc9d-1188-2fc1-83c2-a86c29f38007.png)

For detailed migration instructions and further assistance, refer to our [migration guide](/v1/docs/deploying-your-website-cookie-consent-banner) or contact [support@securiti.ai](mailto:support@securiti.ai).

## Example scenarios and corner cases

### Example scenario

This example scenario demonstrates the changes you may observe in your cookie banners and preference centers following Securiti's auto-migration from the Legacy SDK to the **Automatic SDK** deployment option.

Previously, domains using the Legacy SDK displayed elements in this order on the second page of **multi-level layout** configured cookie preference centers:

1. Cookie Category Name
2. Cookie Category Description
3. Cookie Category Opt-out Text

After the migration to the Automatic SDK deployment option, the sequence on the same page has been altered to:

1. Cookie Category Name
2. Cookie Category Opt-out Text
3. Cookie Category Description

![Multi-level_Pref_Center-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-779eb18b-9870-7880-103e-feaa17251de5.png)![Multi-level_Pref_Center-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c4b528d0-9678-caaf-0ea2-747fc70e37ba.png)

While this change in UI layout may seem erratic, it is intentional. To ensure smooth functionality of the latest features, it is essential to add the new **Deployment Code** at the beginning of the `&lt;head&gt;` tag in your domain. This code is crucial for integrating all updated functionalities seamlessly.

### Corner case for using the Preview feature

This corner case addresses the specific scenario of using the latest **Preview** feature from domains that have remained inactive since their creation before the [SDK Version Control](/v1/docs/restoring-a-previous-sdk-version) functionality was rolled out.

| Old Preview (Legacy SDK) | New Preview (Automatic and Manual SDK) |
| --- | --- |
| The previous version of the Preview feature served as a basic portal preview, letting you to view changes, but not providing a true representation of the final appearance for the cookie banner and preference center. ![Preview-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76ff15c4-99bf-f967-00cb-1eea32db843e.png)![Legacy-Preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0778ba91-e6bf-2429-0127-99b4a36beb48.png) | The newly redefined Preview feature lets you see live changes, providing an accurate representation of how your cookie banner and preference centers will appear. This ensures that what you see in the previews matches the actual look once deployed to your domains. ![Preview-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76ff15c4-99bf-f967-00cb-1eea32db843e.png)![Preview-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ec0c1df-bc76-d527-f731-5249d292516e.png) |

If you added and scanned a domain before **22 August, 2023**, before the introduction of the **SDK Version Control** functionality in the Cookie Consent Management module, and have not used that domain since, you must adhere to the following steps.

To enable the Preview feature introduced in the module after August 22, 2023:

1. Update the **Cookie Configuration** from the management portal:
  - Access the management portal and make any change to the domain's cookie configuration. Ensure you **save** these changes.

This step is essential to generate the necessary **CDN files**, which might be missing due to the lack of updates since the domain's initial setup.
2. Add and deploy the new **Deployment Code**:
  1. After updating the Cookie Configuration, you must copy the **Deployment Code** (located in the UI of **Consent Code** tab), and paste it at the beginning of the `&lt;head&gt;` tag in your domain. This code is crucial for integrating the latest cookie consent SDK in your domain.
  2. Deploy these changes from the management portal. This action activates the updated configuration and ensures that the domain can use the new **Preview** feature effectively.

## Impact on Privacy Centers deployed on domains using Legacy SDK

All the limitations mentioned above also apply to Privacy Centers deployed on domains that use the Legacy SDK.

It is imperative to redeploy your Privacy Center after you migrate from the Legacy SDK to either the **Manual** or **Automatic SDK** deployment option. This action is essential to ensure that your Privacy Centers operate smoothly and remain compliant without any issues.

For detailed instructions on how to migrate to the new SDK deployment options, see the [migration guide](/v1/docs/deploying-your-website-cookie-consent-banner). In case you need further assistance, you must contact the Customer Success Manager or Account Representative.

An EU regulation that governs the confidentiality of electronic communications and the use of cookies and similar technologies. It requires consent from data subjects before storing or accessing information on their devices, except when strictly necessary for providing a service. It works alongside the GDPR and applies to domains targeting individuals in the EU.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.
