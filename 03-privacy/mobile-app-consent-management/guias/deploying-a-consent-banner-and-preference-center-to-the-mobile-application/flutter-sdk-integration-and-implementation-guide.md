---
title: "Flutter SDK integration and implementation guide"
slug: "flutter-sdk-integration-and-implementation-guide"
updated: 2026-08-10T10:50:56Z
published: 2026-08-10T10:50:56Z
canonical: "helpcenter.securiti.ai/flutter-sdk-integration-and-implementation-guide"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Flutter SDK integration and implementation guide

This ntegration and implementation guide contains information related to Flutter-Consent-SDK by Securiti, including installation instructions, configuration details, and available API methods.

### Prerequisites

#### Android

- Minimum Android SDK Version must be 24. You can change it in `android/app/build.gradle`.

```gradle
defaultConfig {
  // other code.....
  minSdk = 24
}
```

- The `securiti_consent_sdk` requires `FlutterFragmentActivity` because:
  - It likely uses fragments to display consent UI components, such as banners, dialogs, and preference centers.
  - These UI elements must be embedded within the app's view hierarchy.
  - Modern consent management UIs often use fragment-based architecture for flexible positioning and lifecycle management.
- Inside your main activity:

```gradle
//please add these imports
import io.flutter.embedding.android.FlutterActivity
import io.flutter.embedding.android.FlutterFragmentActivity
// extend MainActivity with FlutterFragmentActivity instead of FlutterActivity
class MainActivity: FlutterFragmentActivity()
```

#### iOS

- In Podfile, minimum iOS version must be 15. You can change it in `ios/Podfile`.

```ruby
platform :ios, '15.0'
```

### Installing package in the Flutter app

1. Add the following entry to the `dependencies` block of your `pubspec.yaml` file:

```gradle
dependencies:
  consent_sdk_plugin: ^1.130.0
```
2. Run the following command in your terminal:

```gradle
flutter pub get
```

#### Android installation steps

1. Open your `android/app/build.gradle` file:
2. Add the following repository configuration above the `dependencies` block:

```gradle
repositories {
    google()
    mavenCentral()
    maven {
        url 'https://cdn-prod.securiti.ai/consent/maven'
    }
}
```

#### iOS installation steps

1. Update the Podfile in your iOS project to specify the minimum iOS version:

```plaintext
platform :ios, '15.0'
```
2. Navigate to iOS folder and install pods:

```plaintext
platform :ios, '15.0'
```

### SDK Methods

The Flutter Consent SDK provides the following methods:

#### 1.`setupSDK(Map options)`

Initializes the Consent SDK with configuration options. This method must be called before using any other SDK methods. It configures the SDK with server URLs, tenant information, and mobile app user-specific settings.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `options` | Map | Configuration options for the SDK. You can create it using CmpSDKOptions or directly as a Map. |

**Other Map Parameters**

| Option | Type | Required | Description |
| --- | --- | --- | --- |
| `appURL` | String | Yes | Base URL for the Securiti application. |
| `cdnURL` | String | Yes | URL for the Securiti CDN resources. |
| `tenantID` | String | Yes | Your tenant identifier from Securiti. |
| `appID` | String | Yes | Your application identifier from Securiti. |
| `testingMode` | bool | No | Set to true to enable testing mode (default: false). |
| `loggerLevel` | String | No | Log level for debugging: "DEBUG", "INFO", "WARNING", "ERROR" (default: "DEBUG"). |
| `consentsCheckInterval` | int | No | Time in seconds between consent checks (default: 1800). |
| `subjectId` | String | No | User identifier for consent tracking. |
| `languageCode` | String | No | Language code for UI elements (e.g., "en"). |
| `locationCode` | String | No | Location code for regional compliance (e.g., "US"). |

**Return type:** void

**Example**

```dart
import 'package:consent_sdk_plugin/cmp_sdk_options.dart';
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'dart:io' show Platform;
final consentSdk = ConsentSdkPlugin();
// Setup using CmpSDKOptions object
    String appURL = 'your iOS App URL';
    String cdnURL = 'Your iOS CDN URL';
    String tenantID = 'Your iOS Tenant ID';
    String appID = 'Your iOS App ID';
    String locationCode = 'iOS Location Code';
    if (Platform.isAndroid) {
      appURL = 'your Android App URL';
      cdnURL = 'Your Android CDN URL';
      appID = 'Your Android App ID';
      locationCode = 'Android Location Code';
    }
    CmpSDKOptions options = CmpSDKOptions(
      appURL: appURL,
      cdnURL: cdnURL,
      tenantID: tenantID,
      appID: appID,
      testingMode: true,
      loggerLevel: CmpSDKLoggerLevel.debug,
      consentsCheckInterval: 60,
      subjectId: 'flutterSubject',
      languageCode: 'en',
      locationCode: locationCode,
    );
consentSdk.setupSDK(options.toMap());
```

#### 2. `presentConsentBanner()`

Displays the consent banner UI to the mobile app user. This banner presents consent options based on the configuration and lets mobile app users to provide their consent preferences. Typically called after the SDK is ready.

**Parameters:** None

**Return Value:** void

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:flutter/services.dart';
final consentSdk = ConsentSdkPlugin();
// Show the consent banner
consentSdk.presentConsentBanner();
// Typically used after SDK is ready
const EventChannel _eventChannel = EventChannel('ai.securiti.consent_sdk_plugin/isSDKReady');
_eventChannel.receiveBroadcastStream().listen((event) {
  bool isReady = event as bool;
  if (isReady) {
    // Show consent banner when SDK is ready
    consentSdk.presentConsentBanner();
  }
});
```

#### 3. `presentPreferenceCenter()`

Opens the preference center UI where mobile app users can review and modify their consent choices in detail. This provides a more comprehensive interface compared to the initial consent banner.

**Parameters:** None

**Return Value:** void

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:flutter/material.dart';
final consentSdk = ConsentSdkPlugin();
// Show the preference center when button is pressed
ElevatedButton(
  onPressed: () {
    consentSdk.presentPreferenceCenter();
  },
  child: const Text('Manage Preferences'),
)
```

#### 4. `getConsent(dynamic identifier)`

Retrieves the current consent status for a specific purpose or permission. This can be used to check if a mobile app user has granted or denied consent for a specific data processing purpose or device permission.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `identifier` | Dynamic | Either a purpose ID (int) or a permission ID (String) to check consent status for. |

**Return Value:** ConsentStatus (an enum with values: granted, denied, not_determined).

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/models/consent_status.dart';
final consentSdk = ConsentSdkPlugin();
// Get consent for a purpose ID
Future<void> checkPurposeConsent() async {
  final purposeId = 1;
  final ConsentStatus status = await consentSdk.getConsent(purposeId);
  print('Consent for purpose $purposeId: $status');
  // Check if consent is granted
  if (status == ConsentStatus.granted) {
    // Proceed with purpose-related functionality
  }
}
// Get consent for a permission ID
Future<void> checkPermissionConsent() async {
  final permissionId = "android.permission.CAMERA";
  final ConsentStatus status = await consentSdk.getConsent(permissionId);
  print('Consent for permission $permissionId: $status');
}
```

#### 5. `getPermissions()`

Retrieves a list of all permissions available in the SDK. These represent device-level permissions (e.g., camera access) that your app might request from the mobile app user.

**Parameters:** None

**Return Value:** List <AppPermission> - A list of permission objects with the following properties.

| Property | Type | Description |
| --- | --- | --- |
| `permissionId` | String | Unique identifier for the permission. |
| `name` | String | Display name of the permission. |
| `description` | String | Description of what the permission is used for. |
| `required` | bool | Whether the permission is required for app functionality. |

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/models/app_permission.dart';
final consentSdk = ConsentSdkPlugin();
Future<void> listPermissions() async {
  final List<AppPermission> permissions = await consentSdk.getPermissions();
  // Display all permissions
  for (var permission in permissions) {
    print('Permission: ${permission.name}');
    print('ID: ${permission.permissionId}');
    print('Description: ${permission.description}');
    print('---');
  }
}
```

#### 6. `getPurposes()`

Retrieves a list of all consent purposes available in the SDK, each representing a specific reason for data processing that mobile app users may approve or reject.

**Parameters:** None

Return Value: List<Purpose> - A list of purpose objects with the following properties:

| Property | Type | Description |
| --- | --- | --- |
| `purposeId` | int | Unique identifier for the purpose. |
| `purposeName` | Map<String, String> | Localized names for the purpose (key is language code). |
| `description` | Map<String, String> | Localized descriptions for the purpose. |
| `isRequired` | bool | Whether consent for this purpose is required. |
| `isDefault` | bool | Whether this purpose has default consent. |

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/models/purpose.dart';
final consentSdk = ConsentSdkPlugin();
Future<void> listPurposes() async {
  final List<Purpose> purposes = await consentSdk.getPurposes();
  // Display all purposes
  for (var purpose in purposes) {
    print('Purpose: ${purpose.purposeName?['en'] ?? 'Unknown'}');
    print('ID: ${purpose.purposeId}');
    print('Description: ${purpose.description?['en'] ?? 'No description'}');
    print('---');
  }
}
```

#### 7. `getSdksInPurpose(int purposeId)`

Retrieves the list of SDKs associated with a specific purpose. This shows which third-party SDKs are used for each purpose category.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| purposeId | int | The ID of the purpose to get associated SDKs. |

**Return Value:** List<dynamic> - A list of SDK information objects.

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
final consentSdk = ConsentSdkPlugin();
Future<void> listSdksForPurpose() async {
  final int purposeId = 1;
  final List<dynamic> sdks = await consentSdk.getSdksInPurpose(purposeId);
  print('SDKs associated with purpose $purposeId:');
  for (var sdk in sdks) {
    print('- $sdk');
  }
}
```

#### 8. `setConsent(dynamic entity, ConsentStatus status)`

Sets the consent status for a specific purpose or permission. This lets you programmatically updating mobile app user consent settings.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `entity` | dynamic | Either a Purpose object, AppPermission object, purpose ID (int), or permission ID (String). |
| `status` | ConsentStatus | The consent status to set (granted, denied, not_determined). |

**Return Value:** Future(void)

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/models/consent_status.dart';
import 'package:consent_sdk_plugin/models/purpose.dart';
import 'package:consent_sdk_plugin/models/app_permission.dart';
final consentSdk = ConsentSdkPlugin();
// Set consent for a purpose by ID
Future<void> setPurposeConsent() async {
  final purposeId = 1;
  await consentSdk.setConsent(purposeId, ConsentStatus.granted);
  print('Consent for purpose $purposeId set to GRANTED');
}
// Set consent for a permission by ID
Future<void> setPermissionConsent() async {
  final permissionId = "android.permission.CAMERA";
  await consentSdk.setConsent(permissionId, ConsentStatus.granted);
  print('Consent for permission $permissionId set to GRANTED');
}
```

#### 9. `resetConsents()`

Resets all consent settings to their default values. This clears any mobile app user-provided consent preferences.

**Parameters:** None

**Return Value:** Future<void>

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
final consentSdk = ConsentSdkPlugin();
Future<void> resetAllConsents() async {
  await consentSdk.resetConsents();
  print('All consent settings have been reset to default values');
}
```

#### 10. `getBannerConfig([MainConfiguration? cdn])`

Retrieves the configuration for the consent banner UI. This includes texts, buttons, and styling information.

**Parameters**

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `cdn` | MainConfiguration | No | Optional custom CDN configuration. |

**Return Value:** Future<BannerConfig> - The banner configuration object or null if not available.

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/models/banner_config.dart';
import 'package:consent_sdk_plugin/models/main_configuration.dart';
final consentSdk = ConsentSdkPlugin();
// Get banner config with default settings
Future<void> getDefaultBannerConfig() async {
  final BannerConfig? config = await consentSdk.getBannerConfig();
  if (config != null) {
    print('Banner title: ${config.title?['en']}');
    print('Banner description: ${config.description?['en']}');
    print('Has accept button: ${config.acceptButton != null}');
    print('Has reject button: ${config.rejectButton != null}');
  } else {
    print('Failed to retrieve banner configuration');
  }
}
// Get banner config with custom CDN settings
Future<void> getCustomBannerConfig() async {
  final MainConfiguration customCdn = MainConfiguration(
    appURL: "https://custom-url.securiti.xyz",
    cdnURL: "https://custom-cdn.securiti.xyz",
  );
  final BannerConfig? config = await consentSdk.getBannerConfig(customCdn);
  // Process configuration...
}
```

#### 11. `getSettingsPrompt()`

Retrieves the configuration for the settings prompt UI. This includes titles, descriptions, and button texts for the settings interface.

**Parameters:** None

**Return Value:** Future<SettingsPrompt> - The settings prompt configuration or null if not available.

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/models/settings_prompt.dart';
final consentSdk = ConsentSdkPlugin();
Future<void> retrieveSettingsPrompt() async {
  final SettingsPrompt? prompt = await consentSdk.getSettingsPrompt();
  if (prompt != null) {
    print('Settings title: ${prompt.title?['en']}');
    print('Settings description: ${prompt.description?['en']}');
    print('Settings button text: ${prompt.buttonTitle?['en']}');
  } else {
    print('Settings prompt configuration not available');
  }
}
```

#### 12. `uploadConsents(PostConsentsRequest request)`

Uploads the mobile app user's consent settings to the server. This synchronizes local consent choices with the backend system.

**Parameters**

| Parameter | Type | Description |
| --- | --- | --- |
| `request` | PostConsentsRequest | Object containing purpose consents, permission consents, and metadata. |

**PostConsentsRequest Properties**

| Property | Type | Description |
| --- | --- | --- |
| `purposeConsents` | Map<String, ConsentStatus> | Map of purpose IDs to consent statuses. |
| `permissionConsents` | Map<String, ConsentStatus> | Map of permission IDs to consent statuses. |
| `metadata` | Map<String, dynamic> | Additional metadata for the request. |

**Return Value:** Future<bool> - Success (true) or failure (false) of the upload operation.

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/models/post_consents_request.dart';
import 'package:consent_sdk_plugin/models/consent_status.dart';
final consentSdk = ConsentSdkPlugin();
Future<void> uploadUserConsents() async {
  // Create consent request with user preferences
  final PostConsentsRequest request = PostConsentsRequest(
    purposeConsents: {
      "1": ConsentStatus.granted,
      "2": ConsentStatus.denied,
      "3": ConsentStatus.granted
    },
    permissionConsents: {
      "android.permission.CAMERA": ConsentStatus.granted,
      "android.permission.LOCATION": ConsentStatus.denied
    },
    metadata: {
      "deviceId": "device-123",
      "platform": "Android",
      "version": "1.0"
    }
  );
  final bool success = await consentSdk.uploadConsents(request);
  if (success) {
    print('Consents uploaded successfully');
  } else {
    print('Failed to upload consents');
  }
}
```

#### 13. `SDK Ready Event`

The SDK provides an event channel to notify when it has completed initialization and is ready for use.

**Event Channel:** 'ai.securiti.consent_sdk_plugin/isSDKReady'

**Event Value:** bool - true when the SDK is ready, false otherwise.

**Example**

```dart
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:flutter/services.dart';
const EventChannel _eventChannel = EventChannel('ai.securiti.consent_sdk_plugin/isSDKReady');
void setupSDKReadyListener() {
  _eventChannel.receiveBroadcastStream().listen(
    (dynamic event) {
      final bool isReady = event as bool;
      print('Consent SDK is ready: $isReady');
      if (isReady) {
        // SDK is initialized and ready to use
        // You can now safely call SDK methods
      }
    },
    onError: (dynamic error) {
      print('Error in SDK ready listener: $error');
    }
  );
}
```

### Basic SDK usage example

```dart
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';
import 'package:consent_sdk_plugin/consent_sdk_plugin.dart';
import 'package:consent_sdk_plugin/cmp_sdk_options.dart';
import 'package:consent_sdk_plugin/models/consent_status.dart';
import 'dart:io' show Platform;
void main() {
  runApp(const MyApp());
}
class MyApp extends StatefulWidget {
  const MyApp({super.key});
  @override
  State<MyApp> createState() => _MyAppState();
}
class _MyAppState extends State<MyApp> {
  final _consentSdkPlugin = ConsentSdkPlugin();
  bool _isSDKReady = false;
  @override
  void initState() {
    super.initState();
    String appURL = 'your iOS App URL';
    String cdnURL = 'Your iOS CDN URL';
    String tenantID = 'Your iOS Tenant ID';
    String appID = 'Your iOS App ID';
    String locationCode = 'iOS Location Code';
    if (Platform.isAndroid) {
      appURL = 'your Android App URL';
      cdnURL = 'Your Android CDN URL';
      appID = 'Your Android App ID';
      locationCode = 'Android Location Code';
    }
    CmpSDKOptions options = CmpSDKOptions(
      appURL: appURL,
      cdnURL: cdnURL,
      tenantID: tenantID,
      appID: appID,
      testingMode: true,
      loggerLevel: CmpSDKLoggerLevel.debug,
      consentsCheckInterval: 60,
      subjectId: 'flutterSubject',
      languageCode: 'en',
      locationCode: locationCode,
    );
    _consentSdkPlugin.setupSDK(options.toMap());
    // Listen for SDK ready event
    const EventChannel _eventChannel = 
      EventChannel('ai.securiti.consent_sdk_plugin/isSDKReady');
    _eventChannel.receiveBroadcastStream().listen((event) {
      setState(() {
        _isSDKReady = event as bool;
        if (_isSDKReady) {
          // Show consent banner when SDK is ready
          _consentSdkPlugin.presentConsentBanner();
        }
      });
    });
  }
  void _openPreferenceCenter() {
    _consentSdkPlugin.presentPreferenceCenter();
  }
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Consent SDK Example'),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Text(
                'SDK is ${_isSDKReady ? "ready" : "not ready"}',
                style: TextStyle(
                  color: _isSDKReady ? Colors.green : Colors.red,
                  fontWeight: FontWeight.bold,
                ),
              ),
              const SizedBox(height: 20),
              ElevatedButton(
                onPressed: _isSDKReady ? _openPreferenceCenter : null,
                child: const Text('Open Preference Center'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

### Screenshots

![Banner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a2dcd27-4dc4-2893-cae0-02ec1b6ba47d.png)

*Mobile App Consent Banner*

![SDK_Purposes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-796b604e-0b90-e99b-7c2a-a0068e241b09.png)

*Mobile App Consent Preference Center - SDK Purposes Tab*

![Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66e5f766-c7f9-95e6-96a6-8f70bb13f1a0.png)

*Mobile App Consent Preference Center - Permissions Tab*

![Essential_SDK_Expanded.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e2cd266-3f96-3b08-3703-d2c8200fe208.png)

*Mobile App Consent Preference Center - Essential SDK Expanded*

## Related

- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
- [Using SDK Purposes](/using-sdk-purposes.md)
- [Using the SDK and Permissions Library](/using-the-sdk-and-permissions-library.md)
