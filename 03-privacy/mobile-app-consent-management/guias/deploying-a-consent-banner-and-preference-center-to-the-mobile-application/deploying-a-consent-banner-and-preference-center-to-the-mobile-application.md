---
title: "Deploying a consent banner and preference center to the mobile application"
slug: "deploying-a-consent-banner-and-preference-center-to-the-mobile-application"
status: "update"
updated: 2026-08-31T21:00:01Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/deploying-a-consent-banner-and-preference-center-to-the-mobile-application"
stale: true
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Deploying a consent banner and preference center to the mobile application

**Scenario**

As a Data Security Officer, you are responsible for integrating privacy controls into your mobile apps. For instance, when preparing for a new mobile app release, unclear SDK implementation steps can delay deployment and consent readiness. Without clear guidance, SDK rollouts can stall. With Securiti's Mobile App Consent Management module, you receive a privacy SDK with step-by-step integration guides tailored to each platform. This helps you integrate smoothly and ensure compliant consent collection before release.

After configuring the SDK Purposes, Permissions, and customizing the consent banner and preference center for your Android or iOS application, you can deploy these configurations to your application.

To deploy a consent banner and preference center to your application:

1. In Securiti, open **Mobile App Consent Management** and choose **Mobile App Consent > Mobile Apps**.
2. On the Mobile Apps page, click the application to which you wish to deploy the consent banner and preference center.
3. From the left sidebar, navigate to the **DEPLOY & IMPLEMENT** section, and select **Deploy Configurations**.
4. From the **SDK Type** menu, select the type of SDK that you wish to integrate with your mobile app.

> [!WARNING]
> **Important**
> 
> Currently, Securiti does not let you select any other option from the menu because we are offering only Native type for now.
5. Mark the **Enable re-consent for users** checkbox if you wish to show the consent banner and preference center to your data subjects again after the deployment.
6. Click **Deploy Test Version** to deploy a test version of the configured consent banner and preference center. Use the Preview feature to review your changes.
7. Click **Deploy Production Version** to deploy the production version of the configured consent banner and preference center.

> [!WARNING]
> **Important**
> 
> Only do this after thoroughly previewing the configuration with the test deployment.
8. Once done, proceed to the **Implement SDK** section.

### Implementing SDK in mobile application using manual method

Securiti supports both mobile apps and Connected TV (CTV) / Over-the-Top (OTT) implementations. To implement the SDK in your **Android** or **iOS** application using the **Manual** method:

1. From the **Implement SDK** section, click **Download Manual** tab, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Implement-SDK-Download-Manual-tab.png)
2. Expand the **Download SDK** accordion, and:
  1. From the **Select SDK Version** menu, select the appropriate SDK version, as shown below.

> [!NOTE]
> Note
> 
> Securiti recommends that you select the latest available SDK version.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select-SDK-Version.png)
  2. Click **Download SDK**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download-SDK(1).png)
3. Expand the **Import SDK** accordion, follow the on-screen instructions, and then click **Mark as done**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-SDK-Mark-as-Done.png)
4. Expand the **Initialize SDK** accordion, follow the on-screen instructions, and then click **Mark as done**.
5. Expand the **Load Consent Screen** accordion, follow the on-screen instructions, and then click **Mark as done**.
6. After following the on-screen instructions from all sections, as shown below, adhere to the following step-by-step integration guides based on your application's platform:
  - [SDK integration an implementation guide for Android mobile applications](/latest/docs/android-sdk-integration-and-implementation-guide)
  - [SDK integration an implementation guide for iOS mobile applications](/latest/docs/ios-sdk-integration-and-implementation-guide) ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Implement-SDK-All-Sections.png)

### Implementing SDK using the Package Manager

Securiti supports both mobile apps and Connected TV (CTV) and Over-the-Top (OTT) implementations. To implement the SDK using the Package Manager route:

- You can use the [Maven Package Manager](/latest/docs/android-sdk-integration-and-implementation-guide#2b-maven-repository1) for your **Android** application
- You can add dependencies for your **iOS** application using:
  - [CocoaPods](/latest/docs/ios-sdk-integration-and-implementation-guide#1-cocoapods2)
  - [Carthage](/latest/docs/ios-sdk-integration-and-implementation-guide#2-carthage2)
  - [Swift Package Manager](/latest/docs/ios-sdk-integration-and-implementation-guide#3-swift-package-manager-spm2)

### Implementing SDK in hybrid mobile application made with Flutter

If your mobile application is built using a hybrid framework such as **Flutter**, Securiti provides an SDK integration and implementation guide for such applications.

- [Integration and Implementation guide for Flutter](/latest/docs/flutter-sdk-integration-and-implementation-guide) ![Flutter-implementation-guide.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-886db012-d58c-27d1-d049-a5b6a036f7aa.png)

Connected TV (CTV) refers to a television or television-connected device that connects to the internet and lets users access video content through apps or web-based services. CTV includes smart TVs and televisions connected to devices such as streaming devices, gaming consoles, and set-top boxes.

Over-the-Top (OTT) refers to video content delivered directly to users over the internet rather than through traditional cable, broadcast, satellite, or telecom services. Users can access OTT content through apps or web-based services on devices such as connected TVs, mobile devices, computers, and gaming consoles.
