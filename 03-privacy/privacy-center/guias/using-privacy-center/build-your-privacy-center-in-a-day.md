---
title: "Build your Privacy Center in a day"
slug: "build-your-privacy-center-in-a-day"
updated: 2026-04-15T07:50:51Z
published: 2026-04-15T07:50:51Z
canonical: "helpcenter.securiti.ai/build-your-privacy-center-in-a-day"
area: privacy
modulo: privacy-center
tipo: guia
data_captura: 2026-10-08
---

# Build your Privacy Center in a day

**Scenario**

As a Data Privacy Officer, you must ensure that your organization provides clear and accessible privacy experiences for data subjects while maintaining compliance with global privacy regulations. However, managing privacy notices, cookie banners, consent preference centers, and data subject request forms across different platforms and touchpoints can become fragmented and challenging to maintain consistently. For instance, when a data subject wants to review your privacy notice, manage cookie preferences, and submit a data subject request, they may need to navigate multiple pages or platforms, creating a complex experience. Securiti’s Privacy Center provides a centralized location where you can configure and manage Privacy Notices, Cookie Banners, Preference Centers, Universal Preference Centers, and DSR Forms in one place. This lets you create a unified and customized privacy hub, making it easier for data subjects to access privacy options while helping your organization maintain consistent and compliant privacy experiences.

Privacy Center is a centralized location to access and try out several features of the Securiti modules that ensure global privacy and compliance for your organization.

This module lets you build a customized Privacy Center for your organization in less than a day. All you have to do is sign up with Securiti and fill out a registration form.

> [!NOTE]
> **Note**
> 
> When creating a new Privacy Center with a domain that you have already scanned in the Cookie Consent Management module, Securiti automatically links that domain and all its associated configurations with the new Privacy Center that you are creating. This ensures a swift and seamless setup, maintaining the continuity of your domain settings when setting up a new Privacy Center.

![Screenshot_2023-07-11_at_12_50_50_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2bf26ed3-a628-479f-177b-8ab661a1abf6.png)

Securiti lets you build a privacy center in your preferred languages by searching within the **Language** menu. The search bar auto-suggests languages as you type. The menu lists each language in the `name - locale name` format. For instance, Securiti lists language names in English and their native locale name, such as `German - Deutsch`.

You can build your privacy centers in the following languages:

| Language | Language code |
| --- | --- |
| Arabic | `ar-AE` |
| Chinese (Simplified) | `zh` |
| Chinese (Traditional) | `zh-tw` |
| Dutch | `nl-NL` |
| English | `en` |
| French | `fr-FR` |
| German | `de-DE` |
| Hindi | `hi-IN` |
| Italian | `it-IT` |
| Japanese | `ja-JP` |
| Norwegian Bokmål | `no-NO` |
| Brazilian Portuguese | `pt-BR` |
| Spanish | `es-ES` |
| Filipino, Tagalog | `fil` |

Once you create your Privacy Center with a specific language, you see all UI elements of your Privacy Center in that language as shown below.

![1st-SS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-149a231a-e686-6e3a-13b6-1536d741fb65.png)

> [!WARNING]
> **Warning**
> 
> Securiti does not let you change this language afterwards. Your Privacy Center remains in the language you selected during the Privacy Center creation stage.

The foundation for your Privacy Center is created based on the information you provide in the signup form. To customize it, you now tailor the Privacy Center to suit your needs.

Privacy Center offers five distinct features that let you take care of the privacy and security of your organization as shown below:

![Screenshot_2022-11-23_at_10_29_25_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cfde5d9a-f87d-cbed-f750-eacc80b8fe79.png)

| Feature | Description |
| --- | --- |
| Cookies Preferences | Offers a cookie banner to collect both first and third-party cookie consent from your data subjects. |
| Individual Data Requests | Features a Data Subject Rights (DSR) form that your data subjects can fill and submit to file different types of Data Subject Requests or Customer Data Requests. Enterprises are accountable to fulfill such requests promptly. > [!NOTE] > **Note** > > - Securiti lets you link both **standard** and **universal** DSR forms with your Privacy Center. You can link one DSR form (either standard or universal DSR form) at a time. The universal DSR forms are intelligently mapped to specific geographic locations, ensuring that data subjects see the appropriate DSR form based on the region detected during their access. > - It may take up to **10 minutes** for a newly created universal DSR form to be published and appear in the form selection menu. When you publish the Privacy Center, the Universal DSR form requires some time to become available. During this period, Securiti temporarily hides the Individual Data Requests tab. |
| Privacy Notice | Lets you build and publish customized Privacy Notices for your data subjects quickly on your website. These custom notices comply with applicable regulations for your location. |
| Consent Preferences | Consent Preferences lets you host a preference center over your website via which the data subjects can give consent to specific consent purposes such as marketing emails and weekly newsletters, etc. |
| Do Not Sell or Share | The CCPA statute makes it compulsory to host a **Do Not Sell or Share** **My Personal Information** banner or link on your websites. With this feature, the data subjects can opt in and opt out of the sale of their personal data. > [!NOTE] > Note > > Enabling the **Do Not Sell or Share** toggle in a Privacy Center automatically declines all non-essential cookie categories. Note that this behavior applies only to embedded implementations, and the standalone Privacy Center does not support it. |

Once you create your Privacy Center in any organizational unit of your Securiti tenant, the domain scanning process starts immediately in the servers and databases at the backend. Securiti shows the current status of the domain scanning on the **Cookie Preferences** tab, providing quick insights into the progress of scanning, as shown below.

![domain-scaning.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-46fa15af-4aac-0996-4377-c7edb287e575.png)

Use the following table to understand the statuses related to domain scanning progress:

| **Status** | **Description** |
| --- | --- |
| Domain not scanned yet | Lets you know that you must initiate a domain scan from the cookie preferences tab to proceed. |
| Scan requested | Lets you know the domain scan starts shortly after initiation. |
| Domain scanning in progress | Lets you see that the domain scan is in progress; please wait until it completes. |
| Script not deployed | Lets you know that the domain scan is complete and ready for cookie script deployment. |
| Domain scan aborting | Lets you know that Securiti is aborting your domain scan because either you have cancelled it or some error has occurred. |
| Last domain scan aborted successfully | Lets you know the domain scan was aborted and remains incomplete, requiring you to reinitiate the domain scan. |
| Domain scan failed | Lets you know the domain scan failed; you must initiate a new scan shortly. |

Once the domain scan is completed at the backend, Securiti shows the current status of cookie script deployment on the Cookie Preferences tab. It provides a quick view of the deployment state, offering insights into the progress of script deployment, as shown below.

![3rd-SS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-950d7d0a-5a1a-5a05-630d-e9853cb586fd.png)

Use the following table to understand the statuses of cookie script deployment:

| **Status** | **Description** |
| --- | --- |
| Script not deployed | Lets you know if the domain is not deployed. It also serves as the default status displayed on the cookies preferences tab immediately after creating a new privacy center. |
| Script deployed | Lets you see when the domain is scanned and the script is deployed successfully. |
| Domain scan timeout error | Lets you identify when the domain is too large or requires more time than the permitted scanning duration. |
| Domain does not exist | Lets you know if the linked domain does not exist. |

The status changes to **Script deployed** once you deploy the cookie script (code) in your organization’s website with which you have associated the Privacy Center.

> [!NOTE]
> **Important**
> 
> Securiti does not show the Cookie Preferences tab in your hosted Privacy Center if you have not deployed the cookie script in your domain as shown below.
> 
> ![Screenshot_2023-08-04_at_1_32_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0da46d0-0523-ff8e-9728-2e7a52c62103.png)

Even after embedding the cookie script on your domain, if the **Cookie Preferences** tile shows **Not Ready** or **Script not deployed**, use the **Actions** menu. From there, select **Refresh Status** to retry automatic detection of the script, or **Force Deploy** to manually trigger the deployment. This ensures the Privacy Center is published correctly despite detection issues, as shown below.

![Privacy Center dashboard displaying cookies preferences and data request options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/build_pc_hc.png)

Securiti lets you customize your Privacy Center, including background color, text color, button shapes, fonts, and your logo. For more information, see [Customizing your Privacy Centers](/latest/docs/customizing-your-privacy-center).

You can also apply color and styling in bulk from the Privacy Center dashboard. For more information, see [Customizing Privacy Center in bulk](/latest/docs/customizing-privacy-centers-in-bulk).

Cookies preferences are user settings that dictate how websites use and store data through cookies, providing control over tracking, personalized content, and site functionality. In the Privacy Center module, you can use the Cookies Preferences section to build and customize a cookie banner and preference center for your domain(s). Cookie banner and preference center enhance the data subject’s control over data, ensuring personalized online experiences while respecting privacy.

A Data Subject Request (DSR), also referred to as a Customer Data Request, is a formal inquiry made by an individual, known as the data subject or customer, under contemporary privacy regulations like GDPR and CCPA. Depending upon their locations, the data subjects can request access to their data being processed or held by organizations or businesses. The data subjects can request access to their data, ask for data deletion, or request to stop processing their personal data.

Consumer requests to access their data, stop processing it, or delete it, that enterprises collect from them and about them. See Using Data Subject Rights for more information.

Privacy notice is a formal statement or document that communicates how the platform collects, processes, stores, and shares user data. It serves as a transparent disclosure of your organization’s privacy practices, detailing the types of information collected, the purposes for which it is used, and the security measures in place to protect the personal data of your data subjects.

Consent preferences refer to the specific choices data subjects make regarding the collection, processing, and use of their personal information. Data subjects actively decide on data permissions, indicating their agreement or refusal for specific purposes, such as targeted advertising or analytics. Respecting and managing these preferences are vital for organizations to align with privacy regulations and establish transparent, user-centric practices in handling sensitive information.

The California Consumer Privacy Act (CCPA) mandates organizations to prominently feature a Do Not Sell My Personal Information link. This link provides guidance on opting out of the sale of data of individuals such as data subjects or website visitors etc. Using Privacy Center, you can enable or disable this option for your data subjects.

The California Consumer Privacy Act (CCPA) was the first state-level comprehensive privacy law in the United States. It applies broadly to for-profit businesses that collect personal information from California consumers, creating certain rights for consumers and obligations for businesses in relation to personal data processing. It was amended by the California Privacy Rights Act (CPRA) in 2020.

## Related

- [Building multiple Privacy Centers](/building-multiple-privacy-centers.md)
- [Customizing your Privacy Center](/customizing-your-privacy-center.md)
- [Customizing privacy notices in bulk](/customizing-privacy-notices-in-bulk.md)
