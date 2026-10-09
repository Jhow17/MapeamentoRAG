---
title: "Integrating Google Consent Mode with React Native mobile apps"
slug: "integrating-google-consent-mode-with-flutter-mobile-apps"
updated: 2026-09-04T09:57:09Z
published: 2026-09-04T09:57:09Z
canonical: "helpcenter.securiti.ai/integrating-google-consent-mode-with-flutter-mobile-apps"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Google Consent Mode with React Native mobile apps

## Prerequisites

To successfully configure Google Consent Mode in your React Native application, complete the following platform-specific setup to enable Firebase Analytics support on Android and iOS.

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

### Android

Complete the following steps to configure Google services for Firebase Analytics on Android.

1. To include the Google Services Plugin, add following to your `android/build.gradle` file:

```plaintext
buildscript {
    dependencies {
        classpath("com.google.gms:google-services:4.4.0")
    }
}
```
2. To apply the plugin in your `android/app/build.gradle` file, add:

```plaintext
apply plugin: 'com.google.gms.google-services'
```
3. Place the `google-services.json` in the android/app/ directory. This is the Google Services Configuration file which contains your unique Firebase project configuration.

### iOS

Complete the following steps to configure Google services for Firebase Analytics on iOS.

1. Place `GoogleService-Info.plist` file in the ios/ directory. This file contains your Firebase iOS app configuration.
2. In your `ios/Podfile`, to ensure you use dynamic frameworks, include the following post-install script for compatibility:

```plaintext
# Use dynamic frameworks for Firebase compatibility
use_frameworks! :linkage => :static
post_install do |installer|
  # Enable modular headers for GoogleUtilities to fix Firebase compatibility
  installer.pods_project.targets.each do |target|
    if target.name == 'GoogleUtilities'
      target.build_configurations.each do |config|
        config.build_settings['DEFINES_MODULE'] = 'YES'
      end
    end
  end
end
```

### NPM package dependencies

Add the following dependencies to your `package.json` file for both iOS and Android platforms:

```json
{
  "dependencies": {
    "@react-native-firebase/app": "^23.7.0",
    "@react-native-firebase/analytics": "^23.7.0",
    "securiti-consent-sdk": "^1.140.0"
  }
}
```

## Setup

Follow the steps below to set up Firebase and configure the Securiti Consent SDK in your React Native app.

### Step 1: Install dependencies

Run the following command in your terminal:

```powershell
# Install dependencies
npm install

# For iOS
cd ios && pod install && cd ..
npm run ios

# For Android
npm run android
```

### Step 2: Configure Firebase

Use the following imports to initialize Firebase Analytics and access Google Consent Mode functionality from the Securiti Consent SDK.

```plaintext
import analytics from '@react-native-firebase/analytics';
import {
  getGCMConsents,
  GoogleConsentTypeValues,
} from 'securiti-consent-sdk';
```

The code imports Firebase Analytics for demonstration purposes and pulls the required Google Consent Mode functions from the Securiti Consent SDK. It also imports TypeScript types to enable type-safe access to the GCM configuration.

## Validating Google Consent Mode integration

Understand how the mobile app user interface displays Google Consent Mode information and how color indicators reflect the current consent status for each consent type.

### State management

The following state variables store Google Consent Mode consent data and configuration details used by the application.

```plaintext
const [gcmConsents, setGcmConsents] = useState<Record<string, string>>({});
```

| State variable | Stored information |
| --- | --- |
| `gcmConsents` | Current consent statuses for Google Consent Mode types such as `ad_storage` and `analytics_storage`. |

### SDK initialization

The following example shows how the application initializes the Securiti SDK and waits for it to become ready.

```plaintext
useEffect(() => {
  // Initialize SDK with platform-specific options
  const initOptions: CmpSDKOptions = Platform.OS === 'android'
    ? {
        // Android configuration
        appURL: 'https://dev-intg-2.securiti.xyz',
        cdnURL: 'https://cdn-dev-intg-2.securiti.xyz/consent',
        // ... tenantID, appID, and other options
      }
    : {
        // iOS configuration
        appURL: 'https://cdn-dev-intg-2.securiti.xyz/',
        cdnURL: 'https://cdn-dev-intg-2.securiti.xyz/',
        // ... tenantID, appID, and other options
      };

  initialize(initOptions);

  // Wait for SDK to be ready
  isReady((status) => {
    console.log('SDK ready callback received:', status);
    setSdkReady(status);
    if (status) {
      loadInitialData();
    }
  });
}, []);
```

This logic initializes the SDK using platform-specific configuration for Android and iOS, ensuring the correct options apply to each platform. It then uses the `isReady` callback to wait for the SDK to complete initialization. Once the SDK reports a ready state, the app proceeds to load the required initial data.

### handleGetGCMConsents() method

Calls `getGCMConsents()` method from the SDK and updates the `gcmConsents` state.

```plaintext
const handleGetGCMConsents = async () => {
  // ... loading and error handling logic ...
  try {
    const result = await getGCMConsents();
    setGcmConsents(result);
    // ... update response and console log ...
  } catch (error) {
    // ... error handling ...
  } finally {
    setIsLoading(false);
  }
};
```

Here is an example response:

```plaintext
{
  "ad_storage": "granted",
  "analytics_storage": "granted",
  "ad_user_data": "declined",
  "ad_personalization": "declined"
}
```

### GCM UI section

The UI presents Google Consent Mode data to help you visually verify consent states during testing and troubleshooting. It includes action buttons for fetching consent data, conditional rendering of consent and configuration details, and styled components that make consent states easy to interpret.

### Consent Status display

The following example shows how the application renders Google Consent Mode consent statuses in the user interface and applies specific colors to represent each consent state.

```plaintext
const renderGCMConsentItem = (consentType: string, status: ConsentStatus) => {
  const backgroundColor = STATUS_COLORS[status] || STATUS_COLORS.unset;

  return (
    <View style={styles.gcmItemContainer} key={consentType}>
      <Text style={styles.gcmConsentType}>
        {consentType.replace(/_/g, ' ')} {/* Optional: prettify 'ad_storage' to 'ad storage' */}
      </Text>
      <View style={[styles.gcmStatusBadge, { backgroundColor }]}>
        <Text style={styles.gcmStatusText}>
          {status.toUpperCase()}
        </Text>
      </View>
    </View>
  );
};
```

The `renderGCMConsentItem`() function controls how the UI visually represents consent status by mapping each Google Consent Mode value to a color-coded badge:

| Status | Color | Description |
| --- | --- | --- |
| Granted | Green (#4CAF50) | Consent given |
| Declined | Red (#F44336) | Consent withdrawn |
| Withdrawn | Orange (#FF9800) | Consent revoked |
| Other | Gray (#9E9E9E) | Note determined/ Not set |

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner
