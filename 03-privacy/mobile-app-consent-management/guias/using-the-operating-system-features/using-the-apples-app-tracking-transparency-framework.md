---
title: "Using the Apple's App Tracking Transparency Framework"
slug: "using-the-apples-app-tracking-transparency-framework"
updated: 2026-04-06T16:39:17Z
published: 2026-04-06T16:39:17Z
canonical: "helpcenter.securiti.ai/using-the-apples-app-tracking-transparency-framework"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Apple's App Tracking Transparency Framework

**Scenario**

As a Data Privacy Officer, you need to meet platform-specific consent requirements for tracking identifiers. For instance, when enabling advertising or analytics SDKs in your mobile apps, platforms such as Apple and Google require explicit consent signals. Without built-in tools, enforcing Apple’s App Tracking Transparency (ATT) or Google Advertising ID (GAID) compliance can be inconsistent. With Securiti’s Mobile App Consent Management module, you can activate ATT or GAID frameworks during setup. This helps you simplify compliance with Apple and Google’s evolving privacy requirements.

For iOS applications, Securiti includes Apple's App Tracking Transparency (ATT) functionality. It lets you honor a mobile app user’s tracking preferences. When enabled, it automatically **enables** or **disables** the SDK Purposes related to advertising or any other SDK Purpose mapped to Tracking based on the data subject’s choice regarding Tracking in the device settings. Mobile app users can control their preferences only through the device settings or the iOS-generated ATT prompt.

To enable the Apple's ATT Framework on your iOS application:

1. In Securiti, open Mobile App Consent Management and choose **Mobile Consent > Mobile Apps**.
2. On the Mobile Apps page, select the iOS application on which you wish to enable the Apple's ATT Framework.
3. From the left sidebar, navigate to the **OPERATING SYSTEM FEATURES** section, and select **Apple's ATT Prompt**.
4. Enable the **Enable ATT Framework** toggle, as shown below.

![step-4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10192d41-08a4-0229-84ff-b0e091a5ebe8.png)
5. From the **Select SDK purpose(s) to map to Tracking iOS device setting** menu, select the SDK Purpose that you wish to map to the Apple's ATT Framework, as shown below.

![step-5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c6fcb5f-6e32-4fc8-4cb3-02a18a72591f.png)

> [!NOTE]
> **Note**
> 
> The SDK Purposes mapped here appear as disabled in the mobile application's preference center if the data subjects have disabled tracking for your app in their iOS **Privacy & Security > Tracking** settings. This excludes SDK Purposes with opt-out disabled state.
6. Enable the **Show Information on preference center** toggle, and in the **Informational Text** field, add your message, as shown below.

It appears in the mobile application's preference center.

![step-6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1a5e0cc-f156-4a3c-7fd7-f5b3eafba99e.png)
7. Click **Save Changes** to save this configuration, as shown below.

![step-7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea35d0e1-a56f-e6d1-6492-094eb153361a.png)

> [!NOTE]
> **Note**
> 
> To learn more about the Apple's ATT Framework, click **Operating System Guidelines**, as shown below.
> 
> ![step-7-note.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e470e69-29dc-7739-f0d9-eacf532b34ca.png)

## Related

- [Using SDK Purposes](/using-sdk-purposes.md)
- [iOS SDK integration and implementation guide](/ios-sdk-integration-and-implementation-guide.md)
- [Flutter SDK integration and implementation guide](/flutter-sdk-integration-and-implementation-guide.md)
- [React Native SDK integration and implementation guide](/react-native-sdk-integration-and-implementation-guide.md)
