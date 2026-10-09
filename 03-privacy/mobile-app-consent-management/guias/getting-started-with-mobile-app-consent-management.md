---
title: "Getting started with Mobile App Consent Management"
slug: "getting-started-with-mobile-app-consent-management"
updated: 2026-06-19T15:39:22Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/getting-started-with-mobile-app-consent-management"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Getting started with Mobile App Consent Management

Securiti’s Mobile App Consent Management module helps you manage the in-app consent lifecycle, from scanning mobile applications for SDKs and Permissions to configuring consent experiences, deploying the Securiti SDK, and monitoring consent activity.

With this module, you can scan Android, iOS, and hybrid mobile applications, review detected SDKs and Permissions, tailor consent banners and preference centers, configure SDK Purposes, deploy platform-specific SDKs, enable consent framework and add-on settings, and monitor mobile app consent data.

This guide provides an overview of the main steps involved in configuring Mobile App Consent Management.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MACM_GS-r.1.147.svg)

## Step 1 - Scan Mobile Application

Securiti lets you scan your mobile application to detect SDKs, Permissions, and other consent-related findings.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Platform.png) | **Platform** Select the platform for the mobile application that you want to scan. You can choose native Android or iOS, or Hybrid-based on the app type. [Learn more](/latest/docs/configuring-mobile-apps-dashboard) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Upload-Scan.png) | **Scan** Upload and scan the mobile application so Securiti can identify SDKs, Permissions, and related findings. [Learn more](/latest/docs/scanning-your-mobile-application-for-sdks-and-permissions) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-AI-SDKs-Permissions.png) | **AI-assisted SDK and Permission Discovery** Enable AI-assisted discovery to identify additional SDKs and Permissions that the standard mobile app scan may miss. After the scan completes, review the AI-suggested SDKs and Permissions, validate them for accuracy, and add the relevant items to the app’s consent preference center and SDK and Permissions Library. [Learn more](/latest/docs/scanning-your-mobile-application-for-sdks-and-permissions#procedure) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Include-System-Library-SDKs-RN(2).png) | **System Library SDKs** Securiti lets you control whether mobile app scans include System Library SDKs in the scan results. This helps you tailor scan results to your review needs and reduce unnecessary SDK management effort when System Library SDKs do not require consent review. [Learn more](/latest/docs/scanning-your-mobile-application-for-sdks-and-permissions#procedure) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Scan-and-AI-Reports.png) | **Scan and AI Reports** Download scan reports to review or share detected SDKs, Permissions, scan findings, and AI-suggested items. This helps you keep a record of scan results and review additional SDKs or Permissions that may require validation before adding them to the app’s consent configuration. [Learn more](/latest/docs/scanning-your-mobile-application-for-sdks-and-permissions#mobile-application-scanning-and-reporting) |

## Step 2 - Tailor Consent Banner and Preference Center

Securiti lets you tailor the consent banner and preference center according to your mobile app consent requirements.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Add-Template.png) | **Banner templates** Add or select a consent banner template for the mobile application. You can use the available template options to start configuring the mobile consent experience. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Location-Intelligence.png) | **Location Intelligence** Configure Location Intelligence to control where the consent banner and preference center appear based on the mobile app user’s location. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Compliance-Type.png) | **Compliance type** Select the compliance type that determines how mobile app users provide consent for SDKs and Permissions. You can use a notice-only experience, let mobile app users opt out of optional SDKs, or ask them to opt in by showing equally prominent accept and reject options. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Banner-Styling.png) | **Customize consent banner styling** Customize the appearance of the consent banner, including supported styling options such as layout, colors, buttons, verbiage and other visual UI elements. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Customize-Banner-Content.png) | **Customize consent banner and preference center content** Update the text, labels, and verbiage shown in the consent banner and preference center so they align with your organization’s consent requirements. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |

## Step 3 - Configure SDK Purposes and Permissions

Securiti lets you configure SDK Purposes and Permissions to organize SDKs and app Permissions into the right consent categories.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Reassign-SDK-Purpose.png) | **Reassign SDKs between Purposes** Reassign SDKs between SDK Purposes to keep each SDK aligned with the correct data processing activity, consent category, and privacy requirement. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Customize-Purpose.png) | **Customize SDK Purpose details** Customize SDK Purpose details, such as the Purpose name, state, description, Opt-out text, and SDK visibility in the consent preference center, so mobile app users can clearly understand the data processing activity. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Create-New-Purpose.png) | **Create new SDK Purpose** Create a new SDK Purpose when the default Purposes do not cover a specific data processing activity in your mobile app consent configuration. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-SDK-Permissions-Library.png) | **SDK and Permissions Library** Use the SDK and Permissions Library to manage SDKs and Permissions across your tenant. You can review scanned and manually added SDKs and Permissions, create new SDKs and Permissions, sync changes, filter records by platform or source, and apply updates across mobile applications from one centralized location. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |

## Step 4 - Deploy and Implement SDK

Once you configure the mobile consent experience, Securiti lets you deploy the configuration and implement the SDK in your mobile application.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Android.png) | **Android (Native)** Use the native Android SDK option to configure consent collection, consent banner display, preference center access, and consent record handling for Android applications. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-iOS.png) | **iOS (Native)** Use the native iOS SDK option to configure consent collection, consent banner display, preference center access, and consent record handling for iOS applications. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Flutter.png) | **Flutter** Use the hybrid Flutter SDK option to implement Securiti consent collection in mobile applications built with the Flutter framework. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-React-Native.png) | **React Native** Use the hybrid React Native SDK option to implement Securiti consent collection in mobile applications built with the React Native framework. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Unity.png) | **Unity** Use the hybrid Unity SDK option to implement Securiti consent collection in mobile applications built with Unity. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |

## Step 5 - Configure Consent Framework and Add-on Settings

Securiti lets you configure additional consent frameworks and add-on settings to support platform-specific and regulatory consent requirements.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-GAID.png) | **Google Advertising ID (GAID) Framework** Configure Google Advertising ID Framework settings for Android applications when your consent implementation needs to address advertising identifier access. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-ATT.png) | **Apple’s App Tracking Transparency (ATT) Framework** Configure Apple’s App Tracking Transparency Framework settings for iOS applications when your consent implementation needs to address app tracking transparency requirements. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-GCM.png) | **Google Consent Mode (GCM) v2** Enable Google Consent Mode v2 to control how Google tags and SDKs behave in your mobile app based on user consent. You can map Google consent types to SDK Purposes, add a consent mode description to the preference center, and configure location overrides for region-specific mappings. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Settings-Prompt.png) | **Settings Prompt** Enable Settings Prompt when you want to guide mobile app users to device settings for Permissions or tracking controls that require operating system-level action. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |

## Step 6 - Monitor and Report Mobile App Consent Data

After you deploy the consent experience, Securiti also lets you monitor consent activity and generate reports for your audit and compliance needs.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Dashboard-MACM.png) | **Mobile App Consent Dashboard** Use the Mobile App Consent Dashboard to view and manage live and test consent records for your mobile applications. You can search and filter records and then download reports for audit, compliance, or internal review. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GS-Consent-Usage-Metrics.png) | **Mobile App Consent Usage Metrics** Use Mobile App Consent Usage Metrics to monitor how consent data flows across your mobile application. You can review usage trends over selectable time periods, analyze consent reads and writes, track available and used mobile apps, and export usage metric widgets as `PDF` or `PPTX` reports to share with internal or external stakeholders. [Learn more](/docs/getting-started-with-mobile-app-consent-management#) |
