---
title: "Best practices for cookie banners and preference centers"
slug: "best-practices-for-cookie-banners-and-preference-centers"
updated: 2026-09-28T08:13:01Z
published: 2026-09-28T08:13:01Z
canonical: "helpcenter.securiti.ai/best-practices-for-cookie-banners-and-preference-centers"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Best practices for cookie banners and preference centers

## General best practices

- Place the cookie banner at the bottom of the page to minimize its impact on the page content.
- To maximize performance, embed the cookie banner directly on the page, not through another script like a tag manager.
- Run your website through quality control and quality assurance measures with the cookie banner in place, so that you are testing in an environment that is realistic and representative of what your data subjects and website visitors experience.

> [!NOTE]
> **Note**
> 
> The Securiti consent script already takes care of global caching and loading asynchronously to help cookie banner performance on your domain.

See the following sections for best practices for the specific type of cookie banner compliance type you use on your website:

### Notice Only

You just tell your website visitors and data subjects that your domain uses cookies. In many locations, you can use this approach if your domain drops only strictly necessary cookies.

> [!CAUTION]
> **Caution**
> 
> The Notice Only cookie banner is not suitable in jurisdictions that require data subjects to provide **explicit consent** or the ability to **opt out** of certain types of data processing. For instance, in the EU, regulations such as the GDPR and ePrivacy Directive require **opt-in consent** for non-essential cookies. In such cases, you must use an Opt-in cookie banner. In the U.S., regulations such the CCPA, CPRA, CPA, and VCDPA require a clear opt-out mechanism. Depending on the type of data collected by cookies on your domain, use either an Opt-out or **Hybrid** compliance type cookie banner.
> 
> Do not use the cookie banner with the Notice Only compliance type in these regions, either alone or in combination with IAB or other consent frameworks.

| Position on page | Display a sufficiently noticeable cookie banner in an intelligible and easily accessible form. |
| --- | --- |
| Learn More link | Link/button guiding the data subject to a more detailed/comprehensive cookie policy. |
| Compliance type | Choose the **Notice Only** option. > [!CAUTION] > Caution > > Notice Only compliance type may not meet the requirements of global privacy laws and consent frameworks. You can use our [Banner Templates Gallery](/v1/docs/using-the-banner-templates-gallery) functionality to use or customize the prebuilt cookie banner templates for different regions. |
| Cookie expiration (when banner re-appears to collect consent again) | Cookie consent expiration refers to the time period after which the cookie banner re-appears on the website to recollect the consent from your data subjects or website visitors. After this period, consent must be taken from the website visitors and your data subjects again. This expiration period is generally based on legal requirements and it ensures that each individual cookie dropped on the browser of the data subject is proportionate to its function and purpose. |
| Banner options | Message | Provide an explanation of strictly necessary cookies and why they are used. > [!WARNING] > **Important** > > **Recommended message:** "This website uses essential cookies to provide you the basic functionalities of the website." |
| Button text | Avoid language such as "I accept," since it gives visitors the impression that the domain only activates cookies if they accept the use of cookies. We suggest "I understand" or "Allow Cookies". |
| Policy link text | You must provide a clearly visible link to the privacy policy/cookie policy that is easily and permanently accessible to data subjects. When the data subjects click on the Policy link text, it leads them to the privacy policy of your organization. |
| Preference Center options | Description | Display cookie properties including retention periods and technical properties of cookies. |

### Opt-out

Your website invites visitors to opt out of having cookies dropped on their web browsers.

| Position on page | Display a sufficiently noticeable cookie banner in an intelligible and easily accessible form. |
| --- | --- |
| Compliance type | Choose the **Opt-out** option. |
| Cookie expiration (when banner re-appears to collect consent again) | All cookies must have a definite expiry date and the lifespan of each individual cookie should be proportionate to its function and purpose. |
| Banner options | Message | In clear, plain, and unambiguous language: - Explain the purpose of strictly necessary cookies and that they are always activated. - Explain the categories of cookies to be collected and their purposes and whether or not personal data is shared or sold. - Provide information on the length of time the business intends to retain each category of personal information, or if not possible, the criteria used to determine such period. - Provide information on visitor's right to opt-out of the sale and sharing of personal information. > [!WARNING] > **Important** > > **Recommended message:** "This website uses cookies to enhance domain navigation, analyse domain usage, assist in our marketing efforts and provide you the best experience." |
| Button text | We suggest: - Close the Banner - Opt out of cookies - Do Not Sell My Personal Information These let visitors opt-out of the sale of their personal information. |
| Policy link text | You must display a link to the organization's privacy policy through a prominent and conspicuous link using the word "privacy". When the data subjects click on the Policy link text, it leads them to the privacy policy of your organization |
| Preference center options | Description | Display individual cookie properties including retention periods and technical properties of cookies. |
| Categorize Cookies | Opt-out setting | > [!WARNING] > **Important** > > Set the default consent status to "Always Active" only for strictly necessary cookies. |

### Opt-in

Your website only drops cookies if visitors explicitly opt-in to cookies. Use this compliance type in countries where prior consent is a legal requirement, or when your domain might involve the sale of personal information belonging to minors.

| Position on page | Display a sufficiently noticeable cookie banner in an intelligible and easily accessible form. |
| --- | --- |
| Button shape | Give equal prominence to accept and reject buttons such that they are of the same color, size, shape, and format. |
| Learn More link | Add a link/button guiding the data subject to the second information layer. When the data subjects click on the Learn More link, it leads them to the privacy policy of your organization |
| Compliance type | Choose the Opt-in option. It allows for individual cookie category selection (based on purposes of cookie categories) for countries where prior consent is a legal requirement. |
| Cookie expiration (when banner re-appears to collect consent again) | Cookie consent expiration refers to the time period after which the cookie banner re-appears on the website to recollect the consent from your data subjects or website visitors. After this period, consent must be taken from the website visitors and your data subjects again. This expiration period is generally based on legal requirements and it ensures that each individual cookie dropped on the browser of the data subject is proportionate to its function and purpose. |
| Banner options | Message | In clear, plain, and unambiguous language: - Explain the purposes of strictly necessary cookies and that they are always activated. - Distinguish between different cookie categories by highlighting their purposes on the first information layer, accompanied by a brief description. Details of the purposes of different cookie categories may be made available under a menu or hypertext link, taking the data subject to the second information layer where a detailed description of purposes is available. Such detailed information must also include information on retention periods of cookie categories. - Do not provide "Accept Cookies" and "Reject Cookies" buttons without distinguishing between different purposes of cookie categories on the first information layer, even if it is possible to select and deselect individual cookie categories on the second information layer. - "Accept Cookies" and "Reject Cookies" buttons should be on the same information layer and should be of the same size, color, shape, and format. - Provide the following information to data subjects: - The data controller's name and identity. - The data processor's name and identity and the recipients of personal data. - Any potential risks in relation to cross-border data transfers, where applicable. - The use of data for automated decision-making, if applicable. - How data subjects can exercise their rights including the right to access data and lodge complaints with a supervisory authority. - Any potential risks associated with allowing third-party cookies. > [!WARNING] > **Important** > > **Recommended message:** "By clicking “Accept Cookies”, you agree to the storing of cookies on your device to enhance domain navigation, analyse domain usage, assist in our marketing efforts and provide you the best experience." |
| Button text | Do not use terms such as "I understand", "OK", "Dismiss" or "Close." Instead, we suggest: - Accept Cookies - Reject Cookies - Cookie Preferences - Continue with only necessary cookies - Allow Selection - Manage Preferences |
| Policy link text | Provide a clearly visible link to the privacy policy/cookie policy that should be easily and permanently accessible to data subjects. |
| Preference center options | Description | Display individual cookie properties including retention periods and technical properties of cookies. |
| Categorize Cookies | Opt-out setting | > [!WARNING] > **Important** > > Set the default consent status to "Always Active" only for strictly necessary cookies. |

### Hybrid

Depending on the type of cookie and the applicable law, your domain (website) may need to apply a mix of opt-in and opt-out consent rules within the same jurisdiction. The Hybrid compliance type lets you set default consent states per cookie category, for instance, "Declined" for cookies that collect sensitive personal information such as **biometrics** or **precise geolocation**, and "Granted" for other cookie categories.

Use Hybrid compliance type when your domain must meet different consent standards within the same region, for instance, many U.S. state privacy laws mandate opt-in consent for processing of sensitive personal data and opt-out consent for processing other types of personal data. This feature offers flexibility while helping you stay compliant with nuanced legal requirements.

| Position on page | Display a sufficiently noticeable cookie banner in an intelligible and easily accessible form. |
| --- | --- |
| Button shape | Give equal prominence to accept and opt-out buttons such that they are of the same color, size, shape, and format. |
| Learn More link | Add a link/button guiding the data subject to the second information layer. When the data subjects click on the Learn More link, it leads them to the privacy policy of your organization. |
| Compliance type | Choose the **Hybrid** option. It lets you apply both opt-in and opt-out consent rules based on cookie categories, helping you comply with nuanced privacy laws, especially for cookies that collect and process sensitive data such as biometrics or precise geolocation. |
| Cookie expiration (when banner re-appears to collect consent again) | Cookie consent expiration refers to the time period after which the cookie banner re-appears on the website to recollect the consent from your data subjects or website visitors. After this period, consent must be taken from the website visitors and your data subjects again. This expiration period is generally based on legal requirements and it ensures that each individual cookie dropped on the browser of the data subject is proportionate to its function and purpose. |
| Banner options | Message | In clear, plain, and unambiguous language: - Explain the purposes of strictly necessary cookies and that they are always activated. - Distinguish between different cookie categories by highlighting their purposes on the first information layer, accompanied by a brief description. Details of the purposes of different cookie categories may be made available under a menu or hypertext link, taking the data subject to the second information layer where a detailed description of purposes is available. Such detailed information must also include information on retention periods of cookie categories. - Do not provide "Accept all" and "Opt out" buttons without distinguishing between different purposes of cookie categories on the first information layer, even if it is possible to select and deselect individual cookie categories on the second information layer. - "Accept all" and "Opt out" buttons should be on the same information layer and should be of the same size, color, shape, and format. - Provide the following information to data subjects: - The data controller's name, identity and the recipients of personal data. - The cookie categories of personal information to be collected including the categories of sensitive personal information. - The purposes for which the personal information is collected and used including the categories of sensitive personal information. - Whether the personal information is sold or shared. - The length of time the business intends to retain each category of personal information or if that is not possible, the criteria used to determine the period of time it will retain. - How data subjects can exercise their rights including the right to access data and lodge complaints with a supervisory authority. > [!WARNING] > **Important** > > **Recommended message:** "By clicking “Accept Cookies”, you agree to the storing of cookies on your device to enhance domain navigation, analyse domain usage, assist in our marketing efforts and provide you the best experience." |
| Button text | Do not use terms such as "I understand", "OK", "Dismiss" or "Close." Instead, we suggest: - Accept all cookies - Opt out of all cookies - Cookie Preferences - Continue with only necessary cookies - Allow Selection - Manage Preferences |
| Policy link text | Provide a clearly visible link to the privacy policy/cookie policy that should be easily and permanently accessible to data subjects. |
| Preference center options | Description | Display individual cookie properties including retention periods and technical properties of cookies. |
| Categorize Cookies | Opt-out setting | > [!WARNING] > **Important** > > Disable Opt-out only for strictly necessary cookies. |

Under the Notice Only compliance type, consent for cookies is enabled by default. This compliance type is not suitable for jurisdictions that require data subjects to either explicitly grant consent, or have the ability to withdraw consent for any non-essential cookies for certain types of data processing.

Under an Opt-in cookie banner compliance type, cookies are not set on the data subject's device until they have explicitly given permission. This means that, except for strictly necessary cookies (which are essential for the basic functioning of the website), no cookies are loaded until the data subject actively consents to them. This approach is particularly common in regions like the European Union, where regulations such as the General Data Protection Regulation (GDPR) require explicit consent for the storage or access of information on a user's device.

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

## Related

- [Customizing your cookie banner and preference center](/customizing-your-cookie-banner-and-preference-center.md)
- [Using custom CSS to customize cookie banner and preference center](/using-custom-css-to-customize-cookie-banner-and-preference-center.md)
- [Deploying your website cookie consent banner](/deploying-your-website-cookie-consent-banner.md)
