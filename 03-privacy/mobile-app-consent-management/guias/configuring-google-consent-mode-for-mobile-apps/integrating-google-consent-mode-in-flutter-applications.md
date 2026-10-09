---
title: "Integrating Google Consent Mode with Flutter mobile apps"
slug: "integrating-google-consent-mode-in-flutter-applications"
updated: 2026-09-04T09:55:25Z
published: 2026-09-04T09:55:25Z
canonical: "helpcenter.securiti.ai/integrating-google-consent-mode-in-flutter-applications"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Google Consent Mode with Flutter mobile apps

## Prerequisites

To successfully configure Google Consent Mode in your Flutter application, complete the following platform-specific setup to enable Firebase Analytics support on Android and iOS.

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

### Firebase integration

To integrate with Firebase Analytics, follow these steps:

1. Create a project at [Firebase Console](https://console.firebase.google.com/).
2. Provide the iOS Bundle ID or Android Package Id.
3. Enable Google Analytics, as Google Consent Mode requires it.
4. Place the Firebase configuration files in the appropriate platform directories:
  1. For iOS: Place `GoogleService-Info.plist` in ios/Runner/
  2. Android: Place g`oogle-service.json` in android/app/
5. Add the following dependencies to `pubspec.yaml`:

```yaml
dependencies:
  firebase_core: ^2.24.2
  firebase_analytics: ^10.8.0
```
6. Provide the Android Package Name.

### Required imports

Include these imports in your Dart files to access the SDK functionality:

```dart
import 'package:securiti_consent_sdk/consent_sdk_plugin.dart';
import 'package:securiti_consent_sdk/models/google_consent_type.dart';
import 'package:securiti_consent_sdk/models/purpose.dart';
import 'package:securiti_consent_sdk/models/gcm_config.dart';
import 'package:firebase_core/firebase_core.dart';
import 'package:firebase_analytics/firebase_analytics.dart';
```

## Setup

Follow the steps below to set up Firebase and configure the Securiti Consent SDK in your Flutter app.

### Step 1: Install dependencies

Run the following command in your terminal:

```powershell
cd flutter-app
flutter pub get
```

The Flutter app already includes the necessary dependencies in its configuration:

```plaintext
dependencies:
  firebase_core: ^2.24.2
  firebase_analytics: ^10.8.0
  securiti_consent_sdk:
    path: ../
```

### Step 2: Configure Firebase

Configure Firebase for the Flutter project so the app can use Firebase Analytics. Run the FlutterFire CLI to generate Firebase configuration:

1. Install FlutterFire CLI:

```plaintext
dart pub global activate flutterfire_cli
```
2. Configure Firebase for your project:

```plaintext
cd flutter-app
flutterfire configure
```
3. This command creates `lib/firebase_options.dart` with your Firebase configuration.

### Step 3: Update SDK configuration

Open `flutter-app/lib/main.dart` and update the SDK setup (around line 137) with your Securiti details:

```dart
void main() async {
  // Ensures Flutter widget bindings are initialized before calling native code
  WidgetsFlutterBinding.ensureInitialized();
  // Initialize Firebase
  // Note: Requires google-services.json (Android) and GoogleService-Info.plist (iOS)
  try {
    await Firebase.initializeApp();
    developer.log('Firebase initialized successfully');
  } catch (e) {
    developer.log('Firebase initialization failed: $e');
    developer.log(
        'Note: Add Firebase configuration files to run with Firebase Analytics');
  }
  runApp(const MyApp());
}
```

```plaintext
Future<void> _setupSDK() async {
  try {
    CmpSDKOptions options = CmpSDKOptions(
      appURL: 'https://YOUR_APP_URL.securiti.xyz',     // ← Update this
      cdnURL: 'https://YOUR_CDN_URL.securiti.xyz',     // ← Update this
      tenantID: 'YOUR_TENANT_ID',                      // ← Update this
      appID: 'YOUR_APP_ID',                            // ← Update this
      testingMode: true,
      loggerLevel: CmpSDKLoggerLevel.debug,
      consentsCheckInterval: 60,
    );

    await _consentSdkPlugin.setupSDK(options.toMap());
  } catch (e) {
    developer.log('Error setting up SDK: $e');
  }
}
```

### Step 4: Run the app

Once the setup is complete, run the Flutter app on your target platform. Use the following commands based on the platform you want to test:

```powershell
# iOS
flutter run -d ios

# Android
flutter run -d android
```

## Validating Google Consent Mode integration

Understand how the application user interface displays Google Consent Mode information and how color indicators reflect the current consent status for each consent type.

### SDK Status card

The SDK Status card helps you confirm that the Securiti SDK initialized successfully and that the app applied consent signals to Firebase Analytics.

```plaintext
SDK Status
Ready: true
Firebase Consent Applied: true
```

| Status label | Meaning |
| --- | --- |
| Ready | Confirms that the Securiti SDK has initialized successfully. |
| Firebase Consent Applied | Confirms that the app has applied the current consent state to Firebase Analytics. |

### getGCMConsents() method

Use the following example to retrieve the current Google Consent Mode consent states from the SDK and log them for validation.

```plaintext
Future<void> _getGCMConsents() async {
  try {
    // Get consents from SDK
    Map<GoogleConsentType, ConsentStatus> gcmConsents =
        await _consentSdkPlugin.getGCMConsents();

    // Check specific consent
    ConsentStatus analyticsConsent =
        gcmConsents[GoogleConsentType.analyticsStorage] ??
        ConsentStatus.notDetermined;

    print('Analytics Storage: ${analyticsConsent.value}');

    // Process all consents
    gcmConsents.forEach((type, status) {
      print('${type.value}: ${status.value}');
    });
  } catch (e) {
    print('Error: $e');
  }
}
```

### GCM Consents card

The GCM Consents card displays the current consent state for each Google Consent Mode type returned by the SDK.

```plaintext
GCM Consents
analytics_storage         [GRANTED]
ad_storage                [DECLINED]
ad_user_data              [GRANTED]
ad_personalization        [DECLINED]
```

The UI uses color indicators to make consent states easy to interpret.

| Color indicator | Meaning |
| --- | --- |
| Green badge | Consent granted |
| Red badge | Consent declined, withdrawn, or not determined |

### getGCMConfig() method

Use the following example to retrieve the active Google Consent Mode configuration, including default purpose mappings and region-specific overrides.

```plaintext
Future<void> _getGCMConfig() async {
  try {
    GcmConfig? gcmConfig = await _consentSdkPlugin.getGCMConfig();

    if (gcmConfig == null) {
      print('No GCM config available');
      return;
    }

    // Access configuration
    print('Show Description: ${gcmConfig.showGcmDescription}');

    // Access default mappings
    if (gcmConfig.defaultMapping != null) {
      print('Analytics Purpose IDs: ${gcmConfig.defaultMapping!.analyticsStorage}');
    }

    // Access regional overrides
    if (gcmConfig.regionOverrides != null) {
      gcmConfig.regionOverrides!.forEach((region, mapping) {
        print('Region: $region');
        print('Analytics: ${mapping.analyticsStorage}');
      });
    }
  } catch (e) {
    print('Error: $e');
  }
}
```

### GCM Configuration card

The GCM Configuration card shows how the SDK maps internal consent purposes to Google Consent Mode types.

```plaintext
GCM Configuration
Show Description: true
Default Mapping:
  Analytics: [101, 102]
  Ad Storage: [201, 202]
  Ad User Data: [301]
  Ad Personalization: [401, 402]
Regions: EU, US, CA
```

| Configuration element | Value |
| --- | --- |
| Show Description | `true`true |
| Regions | `EU`, `US`, `CA` |

This view helps verify that the backend configuration aligns with the expected regional consent behavior.

## Debugging

Use the following steps to validate Google Consent Mode behavior and Firebase Analytics integration during testing.

### Enable debug logging

Configure the SDK to output debug logs by setting the logger level and testing mode in CmpSDKOptions:

```plaintext
CmpSDKOptions(
  loggerLevel: CmpSDKLoggerLevel.debug,
  testingMode: true,
)
```

### Verify Firebase Integration

Use Firebase DebugView to confirm that consent signals reach Firebase Analytics correctly.

1. Enable Debug Mode:
  1. iOS: Add the following launch argument in Xcode:

```plaintext
-FIRDebugEnabled
```
  2. Android: Run the following command:

```plaintext
adb shell setprop debug.firebase.analytics.app com.securiti.consent_sdk_plugin_example
```
2. View Events:
  1. Open Firebase Console > Analytics > DebugView.
  2. Watch for `consent_update` events.

1. Verify Consent Parameters: Check for the following user properties to confirm consent status propagation:

- `analytics_storage_consent_granted`
- `ad_storage_consent_granted`
- `ad_user_data_consent_granted`
- `ad_personalization_signals_consent_granted`

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner
