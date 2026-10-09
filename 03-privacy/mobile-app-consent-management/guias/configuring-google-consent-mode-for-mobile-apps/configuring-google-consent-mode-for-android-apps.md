---
title: "Integrating Google Consent Mode with Android mobile apps"
slug: "configuring-google-consent-mode-for-android-apps"
updated: 2026-09-04T10:10:41Z
published: 2026-09-04T10:10:41Z
canonical: "helpcenter.securiti.ai/configuring-google-consent-mode-for-android-apps"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Google Consent Mode with Android mobile apps

## Prerequisites

To successfully configure Google Consent Mode with your Android application, you must have:

- The Firebase Analytics SDK included in your application, as Google Consent Mode uses it to manage and communicate user consent status to Google services.

### Backend configuration

The SDK requires you to configure Google Consent Mode (GCM) mapping in your Securiti backend for it to function correctly.

1. Open your CMP configuration in the Securiti management portal.
2. Enable Google Consent Mode for the application.
3. Map your internal consent purposes to the four supported GCM types.

| Google Consent Mode type | Description |
| --- | --- |
| `analytics_storage` | Stores analytics identifiers, such as device IDs, for measurement. |
| `ad_storage` | Stores advertising identifiers or permissions used for tracking. |
| `ad_user_data` | Sends mobile app user data to Google for advertising purposes. |
| `ad_personalization` | Uses mobile app user data to enable personalized advertising. |
4. Publish the configuration and ensure it applies to the required geographic locations.

> [!WARNING]
> Important
> 
> If a location-specific mapping does not exist, Google Consent Mode falls back to the default mapping.

### Adding Firebase Analytics dependency

To integrate the required Firebase Analytics dependency:

1. In your project-level `build.gradle` or `build.gradle.kts` file (the one in the root of your project), add the Google services plugin and the Firebase Android BoM (Bill of Materials).
  1. Groovy ( `build.gradle`):

```kotlin
buildscript {
    dependencies {
        // ...
        classpath 'com.google.gms:google-services:4.4.4' // Check for the latest version
    }
}
allprojects {
    repositories {
        // ...
        google() // Google's Maven repository
        mavenCentral()
    }
}
```
  2. Kotlin DSL (`build.gradle.kts`)

```kotlin
buildscript {
    dependencies {
        // ...
        classpath("com.google.gms:google-services:4.4.4") // Check for the latest version
    }
}
allprojects {
    repositories {
        // ...
        google()
        mavenCentral()
    }
}
```
2. In your project-level build file, make sure the following is present:

```kotlin
// project-level build.gradle
// ...
plugins {
    // ...
    id 'com.google.gms.google-services' version '4.4.0' apply false // Apply false here
}
// ...
```
3. In your module-level `build.gradle` or `build.gradle.kts` file (usually `app/build.gradle`), add the Google services plugin and the Firebase Analytics library.
  1. Groovy (`app/build.gradle`):

```kotlin
// Apply the plugin at the bottom of the file
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services' // Must be applied here

dependencies {
    // ...
    // Import the Firebase BoM (Bill of Materials) - LATEST VERSION: 34.5.0
    implementation platform('com.google.firebase:firebase-bom:34.5.0') 
    // Add the dependency for Firebase Analytics (version is managed by BoM)
    implementation 'com.google.firebase:firebase-analytics'
}
```
  2. Kotlin DSL (`app/build.gradle.kts`)

```kotlin
plugins {
    // ...
    id("com.android.application")
    id("com.google.gms.google-services") // Must be applied here
}
dependencies {
    // ...
    // Import the Firebase BoM (Bill of Materials) - LATEST VERSION: 34.5.0
    implementation(platform("com.google.firebase:firebase-bom:34.5.0"))
    // Add the dependency for Firebase Analytics (version is managed by BoM)
    implementation("com.google.firebase:firebase-analytics")
}
```
4. Sync your project with the Gradle files to download the new dependency.
5. Ensure you have added the `google-services.json` file to your mobile app's module directory. This file is obtained from the Firebase console when you register your Android app.

> [!NOTE]
> Note
> 
> For the most up-to-date and detailed instructions, refer to the official Firebase documentation: [Get started with Google Analytics](https://firebase.google.com/docs/analytics/get-started?platform=android) for Android.

## Setting default consent in Google Consent Mode

To ensure Google services operate with a baseline understanding of mobile app user’s consent before the Securiti Consent SDK initializes and communicates the mobile app user's consent preferences, tenants must set default consent states directly in the Android application.

By default, without configuration, Google Consent Mode values are not set. You must explicitly define the initial consent state for your application by modifying the `AndroidManifest.xml` file.

1. Open your app's `AndroidManifest.xml` file.
2. Add the consent mode key-value pairs. The key specifies the consent type, and the value indicates the default consent state. The valid values are:

| Key value | Meaning | Description |
| --- | --- | --- |
| `true` | Granted by default | Sets the default consent state to **Granted** for the specified consent type. |
| `false` | Denied by default | Sets the default consent state to **Denied** for the specified consent type. |
| `eu_consent_policy` | Conditionally denied | Denies consent only for mobile app users in regions subject to the EU User Consent Policy. Applies to `ad_user_data` and `ad_personalization_signals`. |

1. Set the following required keys:

- `google_analytics_default_allow_analytics_storage`
- `google_analytics_default_allow_ad_storage`
- `google_analytics_default_allow_ad_user_data`
- `google_analytics_default_allow_ad_personalization_signals`

To grant all parameters by default, insert the following `&lt;meta-data&gt;` tags within the `&lt;application&gt;` element of your `AndroidManifest.xml`:

```plaintext
<meta-data android:name="google_analytics_default_allow_analytics_storage" android:value="true" />
<meta-data android:name="google_analytics_default_allow_ad_storage" android:value="true" />
<meta-data android:name="google_analytics_default_allow_ad_user_data" android:value="true" />
<meta-data android:name="google_analytics_default_allow_ad_personalization_signals" android:value="true" />
```

1. Save your changes. After setting the default consent values, the Securiti Consent SDK will initialize. The SDK determines the mobile app user's final consent status, either from a cached user choice or the regional default mandated by the portal configuration. It then uses this status to override the temporary manifest settings by calling the setConsent method of the Google Mobile Ads SDK. This ensures all subsequent Google tag behavior is governed by the mobile app user's definitive choices, as retrieved via the configured mapping and CDN data.

## Validating Google Consent Mode integration

Verify that the Google Consent Mode consent data is correctly retrieved and mapped for the mobile app user based on their location and current consent preferences.

### getGCMConsents() method

The `getGCMConsents()` method acts as a **smart lookup system** to find out which consent purposes correspond to which Google Consent Types, and what the mobile app user's current preference is for them.

The following method signature shows how the SDK exposes this functionality:

```kotlin
public func getGCMConsents() async -> [GoogleConsentType: ConsentStatus]
```

When the SDK processes Google Consent Mode, it first checks whether Google Consent Mode is enabled. If it is disabled, the SDK stops processing and returns an empty map. If it is enabled, the SDK retrieves the mobile app user’s consent preferences and the configured GCM mapping rules.

The SDK then determines the mobile app user’s location, since consent rules often vary by region, and selects the set of rules that links Google’s consent types to your internal consent choices. Finally, it creates a list that shows each Google Consent Type mapped to the internal Consent Purpose, along with the user’s current consent status, for instance **Granted** or **Denied**.

The following example shows how to retrieve and inspect Google Consent Mode consent data using the Android SDK.

```kotlin
// Get all GCM-mapped purposes with their consent statuses
val gcmConsents: Map<GoogleConsentType, Purpose> = SecuritiMobileCmp.getGCMConsents()
// Access specific consent types
gcmConsents[GoogleConsentType.ANALYTICS_STORAGE]?.let { purpose ->
    println("Analytics Storage: ${purpose.name}, Status: ${purpose.consentStatus}")
}
gcmConsents[GoogleConsentType.AD_STORAGE]?.let { purpose ->
    println("Ad Storage: ${purpose.name}, Status: ${purpose.consentStatus}")
}
```

The SDK returns different results depending on the Google Consent Mode configuration state:

| Condition | Return value | Details |
| --- | --- | --- |
| GCM disabled or not configured | Empty Map | Returns emptyMap<GoogleConsentType, Purpose>(). |
| GCM enabled and configured | Map<GoogleConsentType, Purpose> | Contains entries only for the purposes that are explicitly mapped to GCM types for the mobile app user's determined location. |
| Purpose object | Included Data | Each Purpose object in the map is complete, including its current consentStatus, purposeId, name, and other metadata. |

This method provides a convenient, single-call interface to retrieve all GCM-related purposes and their consent statuses, facilitating the integration with Google Consent Mode functionality.

## Automatic consent synchronization

When Google Consent Mode is enabled and configured in the portal, the Securiti Consent SDK for Android automatically synchronizes consent changes with Firebase Analytics.

The SDK performs this synchronization in the following scenarios:

- The mobile app user adds or updates consent preferences via the consent banner or preference center.
- The app sets consent programmatically using the setConsent method.
- The SDK records implicit consent on mobile app start, if configured.

The Securiti SDK uses an internal utility class to communicate with Firebase Analytics without creating a hard dependency. The SDK retrieves the current consent status and then uses the result to call the necessary Firebase Analytics APIs.

> [!WARNING]
> Important
> 
> If the application does not include the required Firebase Analytics SDK dependency, synchronization calls fail silently and Google Consent Mode does not function.

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner
