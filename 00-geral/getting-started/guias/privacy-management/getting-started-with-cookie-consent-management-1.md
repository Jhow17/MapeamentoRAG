---
title: "Getting Started with Cookie Consent Management"
slug: "getting-started-with-cookie-consent-management-1"
status: "update"
updated: 2026-10-07T14:24:53Z
published: 2026-10-07T14:24:53Z
canonical: "helpcenter.securiti.ai/getting-started-with-cookie-consent-management-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Cookie Consent Management

Securiti's Cookie Consent Management module lets you fully automate your cookie consent lifecycle, from scanning to cookie classification and reporting. With this module, you can scan your domains and subdomains, auto-classify domain cookies, create and deploy custom cookie banners and preference centers on your domains. This guide details the complete process for scanning your domains and deploying cookie banners and preference centers on your domains.

![Flowchart of the 8-step CCM workflow: Setup Domain, Scan, Categorize Cookies, Tailor Banner, Add-on Features, Preview, Deploy, Monitor.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CCM-GS-Updated-Workflow-1.150.svg)

### Step 1 - Set Up Your Domain

Securiti lets you add your domain group and domain for scanning.

| [01 - Configure the initial website scan settings](https://player.vimeo.com/video/842085814?title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479) | **Domain Group** You can quickly scan your websites to check what cookies they drop in the data subjects’ web browsers. [Learn more](/latest/docs/scanning-your-website-for-cookies) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step1-Labels.png) | **Labels** (Optional) You can add domain labels for easier grouping and filtering. [Learn more](/latest/docs/scanning-your-website-for-cookies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step1-Add-Owners.png) | **Primary and Co-Owners** Securiti lets you add primary owners and additional Securiti users as co-owners for your domain. [Learn more](/latest/docs/scanning-your-website-for-cookies) |

### Step 2 - Scan Your Domain

Securiti offers below functionalities to initiate the domain scanning process:

| [Embedded content](https://player.vimeo.com/video/842085814?title=0&amp;byline=0&amp;portrait=0&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479) | **Scan Behind Login** Securiti offers a two-step login workflow for domain(s) that first shows users a screen to enter their username, followed by a second screen to enter their password before submitting or logging in. [Learn more](/latest/docs/scanning-your-website-for-cookies) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step2-Scan-Subdomain.png) | **Subdomain(s) Scanning** (Optional) You can also add and scan multiple subdomain(s) simultaneously while scanning your base domains. [Learn more](/latest/docs/scanning-your-website-for-cookies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step2-Sitemap-Scanning.png) | **Sitemap Scanning** (Optional) You can specify the exact pages to be scanned by either a hosted sitemap URL or uploading a sitemap `XML`​ file. [Learn more](/latest/docs/scanning-your-website-for-cookies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step2-Auto-scan.png) | **Schedule Automatic Scan** This feature lets you automatically schedule monthly domain scans. It repeats the scan every month from the date your domain was created. [Learn more](/latest/docs/scanning-your-website-for-cookies) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Step1-Download-Report.png) | **Download Cookie Report** You can download the scanned cookie reports in multiple formats such as `Excel`, `JSON`, and `CSV`. [Learn more](/latest/docs/scanning-your-website-for-cookies) |

### Step 3 - Categorize Your Cookies

You can categorize cookies and make select cookie categories as Essential, and also configure geo-specific Opt-out rules for your cookies banners.

| **Configure Cookies and Category Details** |
| --- |
| [Embedded content](https://player.vimeo.com/video/842085814) | **Reassign Cookie between Categories** Securiti lets you reassign the cookies between different categories, such as first-party and third-party cookies. [Learn more](/latest/docs/categorizing-your-website-cookies) |
| ![Create_Custom_Cookie_Categories.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-38ccfe26-01c0-3d70-52e9-c65b3102739e.png) | **Create Custom Cookie Categories** It lets you create custom cookie categories where you can add **cookie name**, **description**, and **Opt-out text**. You can also add custom translations to your cookie categories belonging to your domains. [Learn more](/v1/docs/categorizing-your-website-cookies) |
| ![Resolve_Auto-blocking_Conflicts.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76a76fd8-1212-d99a-dce0-e3888e2a6751.png) | **Resolve Auto-blocking Conflicts** This feature offers the capability to resolve auto-blocking conflicts that occur when an initiator script drops several cookies that span multiple cookie categories. [Learn more](/latest/docs/resolving-cookie-categorization-conflicts-in-auto-blocking) |
| ![Import___Export_Cookie_Categories.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-65ba91b1-c8b9-7138-f90a-94373428c0f9.png) | **Import and Export Cookie Categories** It lets you import and export cookie categories in `JSON` format. [Learn more](/latest/docs/importing-and-exporting-cookie-categorizations) |
| **Apply Opt-out Rules** |
| ![Import___Export_Cookie_Categories.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-65ba91b1-c8b9-7138-f90a-94373428c0f9.png) | **Global Opt-out Rules Mappings** You can map Opt-out rules to cookie categories in your domain's cookie banner and preference center for data subjects and website visitors worldwide. [Learn more](/latest/docs/configuring-geo-specific-consent-states-for-cookie-categories) |
| ![location_wise.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c70c883c-772d-8cba-6dcd-50d5998b1545.png) | **Region-specific Opt-out Rules Mappings** Securiti lets you map Opt-out rules to cookie categories in the cookie banner and preference center based on specific countries, states, provinces, or regions. This ensures your cookie banners comply with relevant regulations and jurisdictions. [Learn more](/latest/docs/configuring-geo-specific-consent-states-for-cookie-categories) |
| **Using the Cookie and Tracker Library** |
| ![Cookie_and_tracker_library.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7771467b-643a-5599-1a76-9dcba46f9a99.png) | **Cookie and Tracker Library** Securiti lets you manage cookies and trackers through a central library. You can add, edit, or delete trackers individually or in bulk. It also lets you use the top-level filter to refine cookies and trackers based on different properties. [Learn more](/latest/docs/using-the-cookie-and-tracker-library) |
| ![Manage_audit_log.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07060b70-1dd7-558d-e37b-358405652fa5.png) | **Manage Cookies and Trackers** It lets you apply trackers to specific domains and filter them by application status. A detailed audit log records all actions, ensuring transparency. [Learn more](/latest/docs/using-the-cookie-consent-management-audit-log) |

### Step 4 - Tailor Your Cookie Banner and Preference Center

You can customize your cookie banner and preference center according to your website requirements.

| [Embedded content](https://player.vimeo.com/video/839686116) | **Language Intelligence** Securiti lets you enable specific geolocation for your cookie banner to create multiple versions that display only to your website visitors according to location based on their IP address. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| --- | --- |
| ![Brand_Styling.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-43e6151f-e704-cb76-2183-d65f78bfe0f4.png) | **Brand Styling** You can select a custom style for the UI elements of your cookie banner and preference center including banner position, button shape, text, border, background color, and preference center footer background and many more. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| ![Cookie_Banner_Compliance_Type.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0a30974-319e-fb12-3c0c-9fc5354c4b51.png) | **Cookie Banner Compliance Type** It lets you choose between informing data subjects about cookie usage or allowing them to opt out or opt in. Opt-out assumes consent with an option to opt out anytime, while Opt-in requires explicit consent before data collection. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| ![Legal_Verbiage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-efea26b7-8ead-7461-0cf3-2e524ceff859.png) | **Legal Verbiage** It lets you update banner messages, dismiss action text, accept button text, policy link text, preference center title, first and third party description. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| ![Cookie_Consent_Expiration_Duration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ac7535b-971c-8ef3-d3b6-0a40ff70be33.png) | **Cookie Consent Expiration Duration** You can set the cookie consent expiration duration to make it reappear on your domain and recollect consent from your data subjects or website visitors. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| ![DSR_Portal_Link.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-002b5ac1-cbe1-334a-179d-964ed8c54e03.png) | **DSR Portal Link** It lets you embed the DSR portal link in the cookie banner's **Deny** button. Data subjects can then opt out of non-essential cookies and submit Opt-out requests directly, ensuring compliance with privacy laws. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| ![Create_Geolocated_Cookie_Banners.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f55147d-f7d2-de35-46dd-7ad56d64aa51.png) | **Create Geolocated Cookie Banners** It lets you create and configure multiple cookie banners for the specific location according to your need. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| ![Import___Export_Cookie_Banners.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-17c79996-018b-8c68-04a7-34442634cbbb.png) | **Import and Export Cookie Banners** It lets you import and export cookie banners in `JSON` format. [Learn more](/v1/docs/importing-and-exporting-cookie-consent-banners) |
| ![System_or_Custom_Cookie_Banner_Template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9bf9ac7e-6972-83e8-c06c-c5f987d9423e.png) | **System or Custom Cookie Banner Template** You can also import the default system or custom cookie banner templates depending on consent requirements of the particular jurisdiction. [Learn more](/docs/using-the-cookie-consent-banner-templates.html) |

### Step 5 - Apply Add-on Features

You can configure different frameworks by using the following options:

| **Enable IAB Consent Frameworks** |
| --- |
| [Embedded content](https://player.vimeo.com/video/842085979) | **MSPA** **U.S. National Approach** Securiti supports the IAB MSPA to collect and share U.S. visitors' consent preferences for advertising through the GPP, making sure you meet all legal requirements. [Learn more](/v1/docs/configuring-an-iab-mspa-us-national-cookie-consent-banner) |
| ![EU_TCF_v2_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8700dbd5-39c0-2a3e-b633-087df39ad6e7.png) | **EU** [**TCF**](/v1/docs/securiti-pods-and-elastic-pods) **v2.3** also supports IAB **EU** TCF **v2.3** consent framework that lets you comply with the ePrivacy Directive and GDPR to collect the consent of your data subjects for all purposes. [Learn more](/v1/docs/configuring-an-iab-eu-tcf-v22-cookie-consent-banner) |
| **Enable Global Privacy Control (GPC)** |
| [Embedded content](https://player.vimeo.com/video/842085979) | **Global Privacy Control (GPC)** You can enable the GPC consent framework to detect GPC signals on data subjects' browsers and devices, ensuring their Opt-out cookie preferences are honored. [Learn more](/v1/docs/configuring-the-gpc-consent-framework-and-flyout) |
| **Configure Google Consent Mode (GCM)** |
| ![Updated_GTM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12013c2c-d6b6-0e40-80c7-935d604b9162.png) | **GTM Template** We offer a **GTM Template** implementation option to integrate GCM (GCM) with your domain. [Learn more](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtm-template) |
| ![Updated_gtag.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16087e97-a30b-b03e-54a9-c5eefd6f4afc.png) | `gtag.js` You can also integrate Google Consent Mode (GCM) with your domain using the `gtag.js` implementation option. [Learn more](/v1/docs/integrating-securiti-with-google-consent-mode-using-gtagjs) |
| ![Custom.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4316093f-6e3f-312b-278e-cd9969739fdf.png) | **Custom** We also offer a **Custom** implementation option to integrate Google Consent Mode (GCM) with your domain, giving you the flexibility to use an implementation approach that suits your business needs. |

### Step 6 - Preview Your Cookie Banner and Preference Center

You can preview how your custom cookie consent banner and preference center will look through the following options:

| ![location.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2420e6c-c9b3-ac92-553c-7e8207b30230.png) | **Location-wise** Securiti lets you preview your customized cookie banner and preference center for a specific location, showing exactly how it appears in that specific region. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |
| --- | --- |
| ![language.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1d8f673-4b8c-7df4-cbae-6d6c9f79020a.png) | **Language-wise** Securiti also lets you preview your customized cookie banner and preference center in a particular language, showing how it appears to data subjects in that language. [Learn more](/v1/docs/customizing-your-cookie-banner-and-preference-center) |

### Step 7 - Deploy Cookie Banner to Your Domain

Once you have configured and preview your cookie banner, you can deploy it to your domain.

| **Deploy via** |
| --- |
| ![Automatic-SDK.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3d5a42bc-6317-222c-b942-fcca9da710d8.png) | **Automatic SDK Deployment** You can deploy the cookie configuration to your domain by using the **Automatic SDK deployment** option. This way you automatically receive the latest updates for the SDK with each Securiti release. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |
| ![Manual-SDK.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3aab95c2-bedf-a991-d274-97804920bcfd.png) | **Manual SDK Deployment** You can also deploy your cookie banner through the **Manual SDK deployment** option for all existing and new domains. It lets you pin your domain to a specific SDK version, and you don't receive the latest updates to the SDK automatically with each Securiti release. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |
| **Additional Security and Compliance Features** |
| ![Strict-CSP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bbd5486d-edd5-70c4-142a-475796168e04.png) | **Strict Content Security Policy (CSP)** Enable the **strict CSP** feature if your domain enforces strict content security policies. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |
| ![ADA-Compliance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a798f951-30e2-594a-2410-800c3580050f.png) | **ADA Compliance** Securiti lets you make your cookie consent banners and preference centers ADA accessible. Visitors can use features like screen reader support and keyboard navigation for interacting with banner elements. [Learn more](/v1/docs/making-cookie-consent-banners-ada-compliant) |
| ![Top-Level-Domain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84a229d3-fa66-a0bb-84bc-3d6037233083.png) | **Consent Record Tracking via Base Domain** You can also enable top-level domain tracking functionality to track the consent record through the base domain. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |
| ![Google_Tag_Manager__GTM__Integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b2d39933-4064-78cc-5a28-5f89dd4fb9a0.png) | **Google Tag Manager (GTM) Integration** Securiti lets you integrate your GTM with the Cookie Consent Manager module to control the blocking or firing of tags. When your website uses GTM to deploy third-party libraries, it ensures they only trigger after visitors consent to the use of cookies. [Learn more](/v1/docs/integrating-securiti-with-google-tag-manager) |
| ![enable-auto-blocking.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2c6d352a-5e7a-9620-b307-7530029f7e4d.png) | **Enable Auto-blocking** It lets you automatically block scripts from dropping cookies if the data subject opts out. [Learn more](/v1/docs/automatically-blocking-scripts-from-dropping-cookies) |
| ![initiators.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7838041a-cb58-2fb7-f4d2-19c9b9f40bbe.png) | **Categorize Cookie Initiators** It lets you set a root URL for a particular cookie from the scanned group by adding its path to a specific cookie category. For example, reclassifying GTM-initiated cookies as Essential ensures smooth operation of GTM and its integrations. [Learn more](/v1/docs/automatically-blocking-scripts-from-dropping-cookies) |
| ![Share_SDK_Code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-710eef98-b9a3-b004-121a-6adfe13edfec.png) | **Share SDK Code** It also lets you share the consent deployment codes with internal and external members of your organization directly from the UI via email. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |
| ![Download_SDK_Code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-19c9c21a-cba1-d1e7-685f-720806ad729b.png) | **Download SDK Code** You can also download the SDK code in a text file to your local machine, which contains all the consent deployment codes. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |
| ![Custom_CSS.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3d01f147-9f6e-5fea-e0b2-c485779d2aa9.png) | **Using Custom CSS** Securiti lets you easily style cookie banners and preference centers while ensuring security and compliance. You can use a structured class system to apply **scoped styles**, maintain **responsive layouts**, and **prevent conflicts**. Instantly preview issues with invalid CSS highlighted in red. [Learn more](/v1/docs/using-custom-css-to-customize-cookie-banner-and-preference-center) |
| **SDK Code Deployment** |
| ![testing-code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34856f75-2f22-895a-b3af-b27f9877556b.png) | **Testing Code for Stage or QA Environment** It lets you test your changes in your native staging or QA environment using **Testing Code**, especially if you are using highly customized CSS or performing manual CSS overrides. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |
| ![deploment-code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-867d4097-f59d-83d4-10d7-0a066543da57.png) | **Deployment Code for Live or Production Environment** After successfully testing changes in your stage or QA environment, Securiti lets you deploy your cookie banner in your production environment using the Deployment Code. [Learn more](/v1/docs/deploying-your-website-cookie-consent-banner) |

### Cookie Consent Management API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Cookie Consent Management API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details:

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints, and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/cookie-consent/apidocs/index.html#section/Getting-Started) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide a Postman collection if you prefer to use it for testing and executing APIs. This collection contains a set of preconfigured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/cookie-consent/apidocs/index.html#section/Getting-Started/Import-Postman-Collection) | ![CCM_APIs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-319da778-b7a7-b4fc-abb3-c4daf9a2fb1e.png) |

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

A consumer or other member of the general public whose personal data is held by a controller or processor.

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The Multi-State Privacy Agreement (MSPA) serves as a contractual framework designed to aid IAB publishers, advertisers, agencies, and ad tech intermediaries. Its purpose is to facilitate compliance with distinct U.S. state privacy laws. This is achieved by sending, receiving, and honoring standardized opt-out consent signals through the GPP.

The Global Privacy Platform (GPP) is a protocol designed by the Interactive Advertising Bureau (IAB) Tech Lab to streamline and standardize the transmission of consumer consent choice signals from websites and applications to IAB enrolled providers. The framework enables user consent signals to be communicated throughout the digital ad supply chain

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.

An EU regulation that governs the confidentiality of electronic communications and the use of cookies and similar technologies. It requires consent from data subjects before storing or accessing information on their devices, except when strictly necessary for providing a service. It works alongside the GDPR and applies to domains targeting individuals in the EU.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

## Related

- [Using the Cookie Consent Domains dashboard](/using-the-cookie-consent-domains-dashboard.md)
- [Cookie Consent Management API reference](/cookie-consent-management-api-reference.md)
