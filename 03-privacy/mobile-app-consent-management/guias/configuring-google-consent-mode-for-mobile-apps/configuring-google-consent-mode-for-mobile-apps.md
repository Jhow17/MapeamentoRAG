---
title: "Configuring Google Consent Mode for mobile apps"
slug: "configuring-google-consent-mode-for-mobile-apps"
status: "update"
updated: 2026-09-03T09:16:56Z
published: 2026-09-03T09:16:56Z
canonical: "helpcenter.securiti.ai/configuring-google-consent-mode-for-mobile-apps"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring Google Consent Mode for mobile apps

**Scenario**

As a Data Compliance Officer, you need to align mobile app tracking with consent signals required by Google. Implementing Google Consent Mode manually across apps and releases adds operational overhead. Securiti’s Mobile App Consent Management simplifies this by providing built-in support for Google Consent Mode. You meet platform requirements consistently without writing additional code.

Securiti lets you integrate Google Consent Mode v2 with its Mobile App Consent Management module, helping you manage data subject consent consistently across mobile applications and Google services. This integration enables you to honor mobile app user consent preferences across supported mobile platforms while maintaining accurate measurement and compliance with privacy requirements.

Google Consent Mode lets Google’s measurement system track consent state throughout a mobile app user’s journey. It enables Google and third-party SDKs to automatically adjust their behavior based on the consent preferences of the mobile app user. For instance, if a mobile app user denies consent for ad storage, Google services adapt by limiting data collection and signaling consent status without using identifiers. This ensures that the mobile app user’s consent preferences are respected while still allowing you to collect aggregated and compliant measurement data.

The Mobile App Consent Management module supports Google Consent Mode v2 across the following platforms:

- Native Android
- Native iOS
- Flutter
- React Native

Use the following table to understand the key offerings of Google Consent Mode for mobile applications.

| **Feature** | Description |
| --- | --- |
| Multi-platform mobile support | Integrate Google Consent Mode with Securiti’s Mobile App Consent Management module across native iOS, native Android, Flutter, and React Native applications. |
| Automated consent-driven behavior | Google SDKs and supported services automatically adjust data collection based on the mobile app user’s consent preferences. |
| Privacy-aligned measurement | Continue to collect generalized and compliant measurement data while honoring the mobile app user’s consent preferences within the apps. |

> [!WARNING]
> Important
> 
> For more information about how Google processes personal information, see [Google’s Privacy Policy](https://policies.google.com/privacy) and [Google’s Use of Information](https://policies.google.com/technologies/partner-sites).

Use the **Consent Frameworks Settings** section to configure Google Consent Mode for Android, iOS, Flutter, or React Native.

To configure the Google Consent Mode v2 on your mobile app:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent > Mobile Apps**.
2. On the **Mobile Apps** page, click the application you want to enable Google Consent Mode for.
3. From the left panel, navigate to the **Consent Frameworks Settings** section and select **Google Consent Mode**.
4. Near the center of the page, enable the **Enable Google Consent Mode (GCM)** toggle, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/GCM(1).png)
5. Click the **implementation guide** link to open the integration guide corresponding to the platform for your application, such as Android or iOS.
6. In the **Consent Type and Purpose Mapping** section, for each Google Consent Type, select the default purpose from the **Select Purpose** menu, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/purpose-mapping.png)

Use the following table to understand each Google Consent Mode type:

| Google Consent Mode type | Description |
| --- | --- |
| `analytics_storage` | Stores analytics identifiers, such as device IDs, for measurement. |
| `ad_storage` | Stores advertising identifiers or permissions used for tracking. |
| `ad_user_data` | Sends mobile app user data to Google for advertising purposes. |
| `ad_personalization` | Uses mobile app user data to enable personalized advertising. |
7. (Optional) Enable **Show Google Consent Mode Description** if you want to display explanatory text to mobile app users in the consent preference center, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/show-gcm-description.png)

> [!NOTE]
> Note
> 
> Review and update the Google Consent Type Description to ensure it clearly explains how Google Consent Mode processes mobile app users’ consent preferences. If your disclosure requirements apply, include a link to Google’s Privacy Policy in the description.
8. To override the four google consent types based on the location, in the **Location Override** section, click the plus icon, as shown below.

> [!CAUTION]
> Caution
> 
> Only perform this action if you want to set a distinct default state for consent types based on specific countries and/or their regions.
> 
> For instance, if you select **France** with the **Paris** region, Securiti prioritizes the category you've mapped, and the default consent state with Google consent type. However, it applies only when a mobile app user from this region uses your app, and gives consent via the consent banner and preference center.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/add-location-override.png)
9. On the **Location Override** popup, from the **Select Locations** menu, mark the checkbox against specific country, region, state, or province name to select it, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/select-region.png)
10. To apply the location override, from the bottom right of the **Select Locations** menu, click the **Add** button.
11. From the **Mapping** section, click the **Add Mapping** button, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/click-add-mapping.png)
12. From the **Add Mapping** menu, select up to four Google's consent types, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/select-consent-type.png)
13. From the bottom of the **Add Mapping** menu, click **Add** to apply the category mapping.
14. For each Google Consent Type, select the purpose from the **Select Purpose** menu, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/select-purpose.png)
15. From the bottom of the **Location Override** popup, click **Save**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/save-location-override.png)
16. From the bottom, click **Save Changes** to save your configured changes, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/save-changes.png)

After you configure and save Google Consent Mode settings in the Securiti management portal, complete the setup in your app’s code by following the integration guide for your mobile platform. Each guide explains how to apply the configured consent signals within your application.

Follow the guide that matches your application’s platform:

| Platform | Integration guide link |
| --- | --- |
| Native Android | [Integrating Google Consent Mode with Android mobile apps](/latest/docs/configuring-google-consent-mode-for-android-apps) |
| Native iOS | [Integrating Google Consent Mode with iOS mobile apps](/latest/docs/configuring-google-consent-mode-for-ios-apps) |
| Flutter | [Integrating Google Consent Mode with Flutter mobile apps](/latest/docs/integrating-google-consent-mode-in-flutter-applications) |
| React Native | [Integrating Google Consent Mode with React Native mobile apps](/latest/docs/integrating-google-consent-mode-with-flutter-mobile-apps) |
