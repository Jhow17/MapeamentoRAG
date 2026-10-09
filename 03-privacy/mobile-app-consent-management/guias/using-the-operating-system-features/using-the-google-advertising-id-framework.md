---
title: "Using the Google Advertising ID Framework"
slug: "using-the-google-advertising-id-framework"
updated: 2026-04-06T16:38:42Z
published: 2026-04-06T16:38:42Z
canonical: "helpcenter.securiti.ai/using-the-google-advertising-id-framework"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Google Advertising ID Framework

**Scenario**

As a Data Privacy Officer, you need to meet platform-specific consent requirements for tracking identifiers. For instance, when enabling advertising or analytics SDKs in your mobile apps, platforms such as Apple and Google require explicit consent signals. Without built-in tools, enforcing Apple’s App Tracking Transparency (ATT) or Google Advertising ID (GAID) compliance can be inconsistent. With Securiti’s Mobile App Consent Management module, you can activate ATT or GAID frameworks during setup. This helps you simplify compliance with Apple and Google’s evolving privacy requirements.

For Android applications, Securiti offers the Google Advertising ID functionality. It lets you track data subject engagement while respecting their privacy preferences. The Google Advertising ID is a unique identifier provided by Google Play Services that data subjects can **reset** or **delete** in their device settings to control personalized advertising. If enabled, this feature automatically disables SDK Purposes related to advertising or any other SDK Purpose mapped to the Google Advertising ID when the data subject deletes the advertising ID from the device settings.

To enable the GAID on your Android application:

1. In Securiti, open Mobile App Consent Management and choose **Mobile Consent > Mobile Apps**.
2. On the Mobile Apps page, select the Android application on which you wish to enable the Google Advertising ID Framework.
3. From the left sidebar, navigate to the **OPERATING SYSTEM FEATURES** section, and select **Google Advertising ID**.
4. Enable the **Enable Google Advertising Framework** toggle, as shown below.

![Google-id-step-4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0dd9e680-5363-a1d3-68d3-1f8add38a088.png)
5. From the **Select SDK purpose(s) to map with Google Advertising ID Framework** menu, select the SDK Purpose that you wish to map with Google Advertising ID, as shown below.

![Google-id-step-5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae17d45c-1b1c-308b-dff2-50a44b97b01a.png)

> [!NOTE]
> **Note**
> 
> When you enable the **Enable Google Advertising ID Framework** toggle, the **Targeted Advertising** base Purpose is selected by default. This excludes SDK Purposes with opt-out disabled state.
6. Enable the **Conflict Message** toggle, and add message in the text field, as shown below.

It appears in the mobile applications preference center when a data subject tries to give consent after deleting the advertising ID from their Android device settings for the SDK Purposes that you have mapped in step before.

![Google-id-step-6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-de47c078-4d08-e57e-fcff-6128b8611b24.png)
7. Click **Save Changes** to save this configuration, as shown below.

![Google-id-step-7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cebfa9c-ec2d-d245-1a9d-41d4e6132d5d.png)

> [!NOTE]
> **Note**
> 
> To learn more about the Google Advertising ID Framwork, click **Operating System Guidelines**, as shown below.
> 
> ![Google-id-step-7-note.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6ab01ad9-b185-841b-28bd-e37a77c5558f.png)

The Google Advertising ID (GAID) is an Android identifier used to track user behavior and measure ad performance across mobile apps. Users can reset it anytime to get a new ID or delete it permanently to disable ad tracking. This gives mobile app users more privacy control over personalized advertising.

## Related

- [Using SDK Purposes](/using-sdk-purposes.md)
- [Android SDK integration and implementation guide](/android-sdk-integration-and-implementation-guide.md)
- [Flutter SDK integration and implementation guide](/flutter-sdk-integration-and-implementation-guide.md)
- [React Native SDK integration and implementation guide](/react-native-sdk-integration-and-implementation-guide.md)
