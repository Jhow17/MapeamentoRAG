---
title: "User Personas"
slug: "user-personas"
updated: 2026-09-22T06:04:27Z
published: 2026-09-22T06:04:27Z
canonical: "helpcenter.securiti.ai/user-personas"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# User Personas

Use the following table to understand the roles of different types of users and what they are responsible for in the Cookie Consent Management module. From the **Responsibilities** column, use the links of the relative help topics to learn more about the responsibilities of the following roles.

| Role | Title in the module | Responsibilities |
| --- | --- | --- |
| Web Developer (Internal to your organization) | - Organization Admin - Module Owner | - Implementing Consent SDK in your domain's codebase. - Collaborating with other internal stakeholders of your organization involved in setting up the Cookie Configuration: - [Deploying the consent SDK or deployment code](/v1/docs/deploying-your-website-cookie-consent-banner) - [Deploying the autoblocking deployment code](/v1/docs/automatically-blocking-scripts-from-dropping-cookies) - [Debugging autoblocking scripts](/v1/docs/auto-blocking-script-debug-methods) - [Customizing cookie banner and preference center](/v1/docs/customizing-your-cookie-banner-and-preference-center) - [Importing and exporting the cookie banners in JSON file format](/v1/docs/importing-and-exporting-cookie-categorizations) - [Reviewing dropped cookies and initiators via developer tools](/v1/docs/unknown-initiators) - [Implementing advanced cookie banner scripting](/v1/docs/advanced-cookie-banner-scripting) |
| Integration Specialist (Internal to your organization) | - Organization Admin - Module Owner | - Planning, coordinating, and executing all activities from scanning the domain, categorizing cookies, customizing cookie consent banner and preference center to deploying consent SDK on the domain. - Collaborating with other internal stakeholders of your organization involved in setting up the Cookie Configuration: - [Categorizing cookies](/v1/docs/categorizing-your-website-cookies) - [Deploying the consent SDK or deployment code](/v1/docs/deploying-your-website-cookie-consent-banner) - [Deploying the autoblocking deployment code](/v1/docs/automatically-blocking-scripts-from-dropping-cookies) - [Debugging autoblocking scripts](/v1/docs/auto-blocking-script-debug-methods) - [Customizing cookie banner and preference center](/v1/docs/customizing-your-cookie-banner-and-preference-center) - Configuring consent frameworks such as [IAB EU TCF v2.3](/v1/docs/configuring-an-iab-eu-tcf-v22-cookie-consent-banner), [IAB U.S. National](/v1/docs/configuring-an-iab-mspa-us-national-cookie-consent-banner), and [Global Privacy Control (GPC)](/v1/docs/configuring-the-gpc-consent-framework-and-flyout) - [Encoding or decoding the consent information via commands](/v1/docs/iab-gpp-commands-for-eu-tcf-v22-and-mspa-us-national-approach) for the for TCF v2.3 and U.S. National consent frameworks - Integrating Securiti with the following third-party tools: - [Google Tag Manager](/v1/docs/integrating-securiti-with-google-tag-manager) - [Wix website](/v1/docs/using-a-securiti-cookie-consent-banner-on-a-wix-website) - [WordPress website](/v1/docs/using-a-cookie-consent-banner-on-a-wordpress-website) |
| Data Protection Officer (DPO) | Super Admin | - Supervising the integration of the module. - Keeping an [audit trail](/latest/docs/using-the-cookie-consent-management-audit-log) of all the steps taken to comply with the request, to prove compliance in case of legal issues. |
| System Administrator or Portal Administrator | - Super Admin - Organization Admin - Module Owner | - Planning, coordinating, and supervising all activities related to the integration of the Cookie Consent Manangement module. - Evaluate any sensitive or confidential information that may need special handling, and apply appropriate measures to protect that sensitive data and information such as consent records of the data subjects during disclosure. - Populating the [banner templates gallery](/v1/docs/using-the-banner-templates-gallery) with system and custom banner templates. - Enabling the [basic consent configurations](/v1/docs/configuring-consent-configurations). |

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.
