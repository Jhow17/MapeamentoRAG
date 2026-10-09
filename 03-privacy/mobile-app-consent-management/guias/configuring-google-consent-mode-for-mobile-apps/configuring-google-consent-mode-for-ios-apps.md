---
title: "Integrating Google Consent Mode with iOS mobile apps"
slug: "configuring-google-consent-mode-for-ios-apps"
updated: 2026-09-04T10:11:38Z
published: 2026-09-04T10:11:38Z
canonical: "helpcenter.securiti.ai/configuring-google-consent-mode-for-ios-apps"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Google Consent Mode with iOS mobile apps

## Prerequisites

To successfully configure Google Consent Mode with your iOS application, you must have:

- The Firebase Analytics SDK version 10.0 or later included in your application, as GCM uses it to manage and communicate user consent status to Google services.
- An application running on iOS 15.0 or later with a Securiti Consent SDK version 1.141.0 or later.

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

To add the required Firebase Analytics dependency, use CocoaPods, which is the recommended approach. Follow the steps below to complete the setup.

1. Add the Firebase Analytics pod to your `Podfile`:

```ruby
# Podfile
platform :ios, '15.0'

target 'YourAppTarget' do
  use_frameworks!

  # Add Firebase Analytics
  pod 'Firebase/Analytics'

  # Your other pods...
  # pod 'SecuritiConsentSDK'
end
```
2. Run the following command:

```powershell
pod install
```

Alternatively, you can also integrate the Firebase Analytics dependency using Swift Package Manager or Carthage.

### Add Firebase SDK using Swift Package Manager

To use Swift Package Manager:

1. In Xcode, select **File > Add Packages**.
2. Enter the [Firebase GitHub repository URL](https://github.com/firebase/firebase-ios-sdk).
3. Select the **Firebase Analytics** package.
4. Choose your target and click **Add Package**.

### Add Firebase SDK using Carthage

To use Carthage:

1. Add the Firebase Analytics binary to your `Cartfile`:

```plaintext
binary "https://dl.google.com/dl/firebase/ios/carthage/FirebaseAnalyticsBinary.json"
```
2. Run the following command:

```powershell
carthage update --platform iOS
```

### Add `GoogleService-Info.plist`

To enable Firebase Analytics for your iOS app, download and add the GoogleService-Info.plist file to your Xcode project.

1. Register your iOS app in the [Firebase Console](https://console.firebase.google.com/).
2. Download the `GoogleService-Info.plist` file.
3. Add the file to your Xcode project root.
4. Mark the **Copy items if needed** checkbox.
5. Ensure it's added to your app target.

### Initialize Firebase in your mobile app

Initialize Firebase at your app’s entry point to ensure Firebase Analytics is ready before Google Consent Mode synchronization begins. Choose the example that matches your app setup.

#### UIKit

Use this approach if your app uses `AppDelegate` as the main entry point.

```swift
import UIKit
import Firebase
import FirebaseAnalytics

@main
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(_ application: UIApplication,
                     didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {

        // Initialize Firebase
        FirebaseApp.configure()
Analytics.setAnalyticsCollectionEnabled(true)

        // Initialize your Securiti SDK after Firebase
        // ConsentSDK.shared.setupSDK(options: yourOptions)

        return true
    }
}
```

#### SwiftUI (iOS 14 and later)

Use this approach if your app is built with `SwiftUI` and uses an `App` struct as the entry point.

```swift
import SwiftUI
import Firebase

@main
struct YourApp: App {

    init() {
        // Initialize Firebase
        FirebaseApp.configure()
    }

    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

#### Objective-C

Use this approach if your app is written in Objective-C.

```objectivec
@import Firebase;

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    // Initialize Firebase
    [FIRApp configure];

    return YES;
}
```

### Verify installation

Build and run your app to confirm that Firebase Analytics initializes successfully.

Check the Xcode console for the following Firebase Analytics initialization log:

```plaintext
[Firebase/Analytics][I-ACS023007] Firebase Analytics v.X.X.X started
```

This log entry confirms that the Firebase Analytics SDK is installed correctly and ready to receive consent signals from Google Consent Mode.

> [!NOTE]
> Note
> 
> For the most up-to-date and detailed instructions, refer to the official Firebase documentation: [Get started with Google Analytics](https://firebase.google.com/docs/analytics/get-started?platform=ios) for iOS.

## Setting default consent in Google Consent Mode

To ensure Google services operate with a baseline understanding of a mobile app user’s consent before the Securiti Consent SDK initializes, you must set **default consent states** directly in your iOS application.

By default, Google Consent Mode does not set any consent values. You must explicitly define the initial consent state by updating the `Info.plist` file.

Follow the steps in the sections below in sequence.

### Open your app's Info.plist file

Locate the `Info.plist` file in your Xcode project.

### Add the consent mode key-value pairs

The key specifies the consent type, and the value indicates the default consent state. The valid values are:

- **YES** or **true**: Consent is granted by default.
- **NO** or **false**: Consent is denied by default.

### Set the required keys

Add these keys to your Info.plist:

| Key | Type | Default value |
| --- | --- | --- |
| `GOOGLE_ANALYTICS_DEFAULT_ALLOW_ANALYTICS_STORAGE` | Boolean | YES/NO |
| `GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_STORAGE` | Boolean | YES/NO |
| `GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_USER_DATA` | Boolean | YES/NO |
| `GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_PERSONALIZATION_SIGNALS` | Boolean | YES/NO |

The following example shows setting all parameters to YES (Granted) by default:

#### Using Xcode's Property List editor

1. Open `Info.plist` in Xcode.
2. Right-click and select **Add Row**.
3. Add each key with type **Boolean** and value **YES**.

#### Using XML editor

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_ANALYTICS_STORAGE</key>
    <true/>
    <key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_STORAGE</key>
    <true/>
    <key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_USER_DATA</key>
    <true/>
    <key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_PERSONALIZATION_SIGNALS</key>
    <true/>

    </dict>
</plist>
```

The following example shows setting all parameters to No (Denied) by default:

```xml
<key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_ANALYTICS_STORAGE</key>
<false/>
<key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_STORAGE</key>
<false/>
<key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_USER_DATA</key>
<false/>
<key>GOOGLE_ANALYTICS_DEFAULT_ALLOW_AD_PERSONALIZATION_SIGNALS</key>
<false/>
```

### Save your changes

After setting the default consent values, the Securiti Consent SDK initializes. It determines the mobile app user's final consent status (from a cached user choice or regional default) and then overrides the temporary `Info.plist` settings by calling the `setConsent` method of the Firebase Analytics SDK. This ensures subsequent Google tag behavior is governed by the mobile app user's definitive choices.

## Validating Google Consent Mode integration

Verify that the Google Consent Mode consent data is correctly retrieved and mapped for the mobile app user based on their location and current consent choices.

### getGCMConsents() method

Use the getGCMConsents() method to retrieve the current consent status for all Google Consent Mode types that are mapped in your configuration.

The following method signature shows how the SDK exposes this functionality:

```swift
public func getGCMConsents() async -> [GoogleConsentType: ConsentStatus]
```

When the SDK builds the Google Consent Mode payload, it first checks whether Google Consent Mode is enabled; if not, it returns an empty dictionary. It then fetches the mobile app user’s consent choices and the GCM mapping rules, determines the user’s location, and selects the appropriate mapping for that location. Finally, it creates a dictionary that links each Google Consent Type to the internal Consent Purpose.

The method allows for easy retrieval and examination of the consent status for all purposes relevant to GCM. The following examples show how to retrieve and inspect Google Consent Mode consent data using the SDK.

```swift
import ConsentCore

// Get all GCM-mapped purposes with their consent statuses
let gcmConsents: [GoogleConsentType: Purpose] = await ConsentSDK.shared.getGCMConsents()

// Access specific consent types
if let analyticsStoragePurpose = gcmConsents[.analyticsStorage] {
    print("Analytics Storage: \(analyticsStoragePurpose.purposeName ?? [:]), Status: \(String(describing: analyticsStoragePurpose.consentStatus))")
}

if let adStoragePurpose = gcmConsents[.adStorage] {
    print("Ad Storage: \(adStoragePurpose.purposeName ?? [:]), Status: \(String(describing: adStoragePurpose.consentStatus))")
}

// Iterate through all GCM consents
for (consentType, purpose) in gcmConsents {
    print("\(consentType.rawValue): \(purpose.purposeName ?? [:]) - \(String(describing: purpose.consentStatus))")
}
```

```objectivec
@import ConsentCore;

// Get all GCM-mapped purposes with their consent statuses
[ConsentSDK.shared getGCMConsentsWithCompletionHandler:^(NSDictionary<NSNumber *,Purpose *> * _Nonnull gcmConsents) {

    // Access specific consent types
    Purpose *analyticsStoragePurpose = gcmConsents[@(GoogleConsentTypeAnalyticsStorage)];
    if (analyticsStoragePurpose) {
        NSLog(@"Analytics Storage: %@, Status: %@",
              analyticsStoragePurpose.purposeName,
              @(analyticsStoragePurpose.consentStatus));
    }

    Purpose *adStoragePurpose = gcmConsents[@(GoogleConsentTypeAdStorage)];
    if (adStoragePurpose) {
        NSLog(@"Ad Storage: %@, Status: %@",
              adStoragePurpose.purposeName,
              @(adStoragePurpose.consentStatus));
    }
}];
```

The SDK returns different results depending on the Google Consent Mode configuration state:

| Condition | Return value | Details |
| --- | --- | --- |
| GCM disabled or not configured | Empty dictionary | Returns [:], which represents an empty dictionary. |
| GCM enabled and configured | [GoogleConsentType: Purpose] | Contains entries only for the purposes that are explicitly mapped to GCM types for the mobile app user's determined location. |
| Purpose object | Included data | Each Purpose object is complete, including its current `consentStatus`, `purposeId`, `purposeName`, and other metadata. |

### GoogleConsentType enum

The GoogleConsentType method provides a convenient, single-call interface to retrieve all GCM-related purposes and their consent statuses. The iOS SDK provides the following Google Consent Mode types:

```swift
public enum GoogleConsentType: String, Codable, Hashable, Equatable, CaseIterable {
    case analyticsStorage = "analytics_storage"
    case adStorage = "ad_storage"
    case adUserData = "ad_user_data"
    case adPersonalization = "ad_personalization"
}
```

These values correspond directly to the Google Consent Mode signals used by Google services.

## Automatic consent synchronization

The Securiti Consent SDK for iOS automatically synchronizes consent changes with Firebase Analytics when you enable Google Consent Mode. The SDK performs this synchronization in the following scenarios:

- The mobile app user changes consent via the preference center.
- The app sets consent programmatically using `setConsent(purpose:consent:)`.
- The SDK records implicit consent on mobile app start, if configured.
- Periodic consent checks detect changes.

To support this behavior, the SDK communicates with Firebase Analytics through the `GoogleConsentModeHelper` class without creating a hard dependency.

> [!WARNING]
> Important
> 
> If the application does not include the required Firebase Analytics SDK dependency, synchronization calls fail silently and Google Consent Mode does not function.

```swift
// Example: Setting consent programmatically
let result = ConsentSDK.shared.setConsent(purpose: myPurpose, consent: .granted)

// The SDK automatically syncs with Firebase Analytics if GCM is enabled
// No additional code needed!
```

## Migrating existing iOS mobile apps to GCM

To update an existing iOS app to support Google Consent Mode, complete the following steps:

1. Update Securiti SDK to the latest version that includes GCM support.
2. Add Firebase Analytics following the steps given above.
3. Configure `Info.plist` with default consent values.
4. Enable GCM in the Securiti management portal and configure purpose mappings.
5. Test thoroughly across different mobile app user scenarios and regions.

> [!NOTE]
> Note
> 
> You do not need to make any code changes. The SDK automatically manages all synchronization for you.

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner
