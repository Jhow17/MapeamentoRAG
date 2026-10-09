---
title: "Mobile Consent App Management release notes"
slug: "mobile-consent-app-management-release-notes"
updated: 2026-09-22T08:03:53Z
published: 2026-09-22T08:03:53Z
canonical: "helpcenter.securiti.ai/mobile-consent-app-management-release-notes"
area: privacy
modulo: mobile-app-consent-management
tipo: release
data_captura: 2026-10-08
---

# Mobile Consent App Management release notes

## 1.151

### Release updates - September 2026

#### Support for the Unreal Engine gaming framework

Securiti now supports the **Unreal Engine** gaming framework in its Mobile App Consent Management module, helping gaming teams bring consent management capabilities to Unreal Engine-based mobile applications with a consistent in-app experience.

This update extends Securiti’s mobile consent capabilities to Unreal Engine-based apps on both Android and iOS platforms through native SDK integration. If you offer Unreal Engine-based apps, you can now display consent banners and preference centers and capture consent preferences. Your users can manage SDK Purposes and Permissions directly in the app.

> [!WARNING]
> Important
> 
> The Unreal Engine integration supports **Unreal Engine 5.8** for Android and iOS apps.
> 
> - For Android builds, your project must use minSdk 24 and includes the Android SDK and NDK installed with Unreal Engine Android support.
> - For iOS builds, make sure your project supports iOS 15.0 or later and uses Xcode on a Mac.

For more information, see [Unreal Engine SDK Integration and Implementation Guide](/latest/docs/unreal-engine-sdk-integration-and-implementation-guide).

---

## 1.150

### Release updates - August 2026

#### Extending mobile app consent to Android TV and Apple TV

Securiti has introduced support for connected TV (CTV) apps in its Mobile App Consent Management module, helping you deliver consistent consent experiences across **Android TV** and **Apple TV** environments. With dedicated TV SDKs, you can extend familiar mobile app consent configuration patterns to CTV apps, letting CTV users open, close, and revisit the consent banner and preference center to review and update their preferences.

Use the following table to understand the supported TV platform capabilities:

| Platform | Description |
| --- | --- |
| Android | Supports consent collection for Android TV-based platforms, including **Android TV**, **Google TV**, and **Amazon Fire TV**, through a dedicated Android TV SDK. It supports Google Advertising ID Framework (GAID) consent framework, opens URLs directly through WebView, and supports TV remote and D-pad navigation for consent preference interactions. |
| iOS | Supports consent collection for Apple TV applications through a dedicated **Apple TV** SDK for tvOS. It supports Apple’s App Tracking Transparency Framework (ATT) consent framework and provides QR code-based access for URL-driven consent experiences. |

For more information, see [Android SDK integration and implementation guide](/latest/docs/android-sdk-integration-and-implementation-guide) and [iOS SDK integration and implementation guide](/latest/docs/ios-sdk-integration-and-implementation-guide).

#### Exporting mobile app consent data across custom date ranges

Securiti now lets you export mobile app consent data from its Mobile App Consent Management module for a selected date range. This update helps you retrieve consent data for reporting, compliance, and internal audits.

> [!NOTE]
> Note
> 
> Only the Super Admin user role can initiate mobile app consent data exports, and each export includes data from all organizational units present in your Securiti tenant by default.

Use the following table to understand the available export capabilities:

| Capability | Description |
| --- | --- |
| Date range selection | Exports mobile app consent data for any selected historical date range. |
| Large data handling | Splits large datasets into multiple `CSV` files and bundles them into a single `ZIP` file. |
| Email delivery | Processes the export in the background and sends an email notification when the export completes. The email includes a secure download link to the exported data or notifies you if no data is available for the selected date range. > [!NOTE] > Note > > Securiti retains exported data for **30 days** and then automatically deletes it. |
| Job status tracking | Tracks export status as “In Progress”, “Completed”, or “Failed”. |

For more information, see [Exporting mobile app consent data](/latest/docs/exporting-mobile-app-consent-data).

#### Improved Android Consent SDK integration compatibility

Securiti has updated the Android Consent SDK dependencies and build toolchain in its Mobile App Consent Management module to improve compatibility with newer Android application environments and help reduce dependency version conflicts during integration.

This update includes the following dependency upgrades:

- `Ktor` 3.5.2
- `Kotlin` 2.3.21
- `Koin` 4.2.2
- `Compose BOM` 2026.01.01
- Coroutines and `AndroidX` dependencies

Use the following table to understand the action required based on your upgrade path:

| Upgrade path | Required action | Impact |
| --- | --- | --- |
| Continue using the existing Android Consent SDK version. | No action required, unless you update your app's other dependencies independently. | Existing integrations continue to work as expected. |
| Upgrade to the updated Android Consent SDK version. | Update the required dependencies in your Android app before implementing or initializing the updated Android Consent SDK. | Skipping the dependency update step will cause the integration to fail. |

> [!WARNING]
> Important
> 
> - To compile against the updated Android Consent SDK, Android app integrations must use `Kotlin` **2.2** or **later**. Review and complete the Android Consent SDK dependency update steps before upgrading.
> - This update does not add embedded `ProGuard` or `R8` keep-rule requirements for minified Android applications.

Securiti has also verified the updated Android Consent SDK with demo mobile apps on **API 24** and **API 36** with no runtime crashes so you can upgrade with confidence across these Android versions.

For more information, see [Android SDK integration and implementation guide](/latest/docs/android-sdk-integration-and-implementation-guide).

---

## 1.149

### Release updates - August 2026

No updates

---

## 1.148

### Release updates - July 2026

No updates

---

## 1.147

### Release updates - June 2026

#### Controlling System Library SDK visibility in mobile app scans

Securiti has added a new configuration in the Mobile App Consent Management module that lets you control whether mobile app scans include System Library SDKs in scan results. This update helps teams tailor scan results to their review needs and reduce unnecessary SDK management effort when System Library SDKs do not need consent review.

After uploading the application source file in the **Source File** tab, select the **Include System Library SDKs in scan results** checkbox, as shown below. When selected, Securiti includes detected System Library SDKs alongside other SDKs in the scan results.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Include-System-Library-SDKs-RN(1).png)

For more information, see [Scanning your mobile application for SDKs and Permissions](/latest/docs/scanning-your-mobile-application-for-sdks-and-permissions).

Connected TV (CTV) refers to a television or television-connected device that connects to the internet and lets users access video content through apps or web-based services. CTV includes smart TVs and televisions connected to devices such as streaming devices, gaming consoles, and set-top boxes.

The Google Advertising ID (GAID) is an Android identifier used to track user behavior and measure ad performance across mobile apps. Users can reset it anytime to get a new ID or delete it permanently to disable ad tracking. This gives mobile app users more privacy control over personalized advertising.

Apple's App Tracking Transparency (ATT) framework requires iOS apps to explicitly ask for a mobile app user's permission to track their activity across other mobile apps. The iOS app must display a standard popup before it accesses the Identifier for Advertisers (IDFA) for ad targeting. However, if the mobile app user denies permission, the app cannot access the IDFA.
