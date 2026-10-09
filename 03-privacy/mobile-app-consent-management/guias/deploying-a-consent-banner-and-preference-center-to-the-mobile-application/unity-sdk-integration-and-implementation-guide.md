---
title: "Unity SDK integration and implementation guide"
slug: "unity-sdk-integration-and-implementation-guide"
updated: 2026-09-21T11:48:15Z
published: 2026-09-21T11:48:15Z
canonical: "helpcenter.securiti.ai/unity-sdk-integration-and-implementation-guide"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Unity SDK integration and implementation guide

This integration and implementation guide for the Unity Consent SDK covers installation, configuration, and usage of all available methods.

## Prerequisites

Before you install and configure the Unity Consent SDK, ensure that your Unity project, Android build settings, and iOS build environment meet the following requirements.

## Unity requirements

Use the following table to understand the Unity-level requirements for the Unity Consent SDK:

| Requirement | Description |
| --- | --- |
| Unity version | Use Unity 2022.3 LTS or later. > [!NOTE] > Note > > Securiti recommends Unity 6 (6000.x). |
| Scripting backend | Set **Scripting Backend** to IL2CPP for both Android and iOS from **Edit > Project Settings > Player > Platform > Other Settings > Scripting Backend**. The Unity Consent SDK does not support Mono on iOS, and Securiti does not recommend Mono for Android production builds. |
| Newtonsoft.json dependency | Use Unity Package Manager to resolve `Newtonsoft.json` through the package dependency block. You do not need to install it manually. |
| EDM4U | Install External Dependency Manager for Unity (EDM4U) in your project. For more information, see the [Installing EDM4U](/latest/docs/unity-sdk-integration-and-implementation-guide#installing-edm4u) section below. |

## Android requirements

Configure the following Android settings before building your Unity project for Android:

| Requirement | Description |
| --- | --- |
| Minimum Android version | Set Minimum API Level to Android 7.0 Nougat (API level 24) from Player Settings > Android > Other Settings > Minimum API Level. |
| Target API level | Set Target API Level to Android 14 UpsideDownCake (API level 34) or later. |
| Target architecture | Include ARM64 from Player Settings > Android > Other Settings > Target Architectures. > [!NOTE] > Note > > ARMv7 is optional and not required. |
| Gradle version | Use Gradle v8.0 or later. > [!NOTE] > Note > > The Securiti Android AAR uses AGP 8.2 and Kotlin 1.9. If your Unity version bundles an older Gradle version, enable Custom Gradle Version from Player Settings > Android > Publishing Settings > Build, and set the Gradle path to your Gradle v8.x installation. |
| JDK version | Use JDK 17. You can use the JDK bundled with Unity 2022.3 or later, or set it manually from Preferences > External Tools > Android > JDK. |

## iOS requirements

Configure the following iOS settings before building your Unity project for iOS:

| Requirement | Description |
| --- | --- |
| Minimum iOS deployment target | Set Target minimum iOS Version to 15.0 from Player Settings > iOS > Other Settings > Target minimum iOS Version. |
| Xcode version | Use Xcode 14.0 or later to build the generated Xcode project. |
| CocoaPods | Install CocoaPods on the build machine. EDM4U runs `pod install` automatically during the Unity to iOS build. To install CocoaPods, run `sudo gem install cocoapods`. |
| Xcode workspace | After Unity finishes building the iOS project, open the generated `Unity-iPhone.xcworkspace` file in Xcode. |
| Swift support | Keep Swift toolchain components available in your Xcode environment. The Unity Consent SDK uses Swift internally, and Unity generates a dummy `.swift` file in the iOS build to enable Swift support. |

## Installation steps

To install the Unity Consent SDK:

1. Download the latest Unity package `ZIP` file, `securiti-consent-unity-&lt;VERSION&gt;.zip` from the Securiti SDK release page and unzip it.
2. In Unity, choose **Window > Package Manager > + > Add package from disk** and select the `package.json` file from the unzipped folder. Alternatively, drag the **Assets/SecuritiConsent** folder into your project's **Assets/** directory.

## Installing EDM4U

EDM4U handles the native Android Maven dependencies and iOS CocoaPods dependencies for the Securiti SDK.

> [!WARNING]
> Important
> 
> You must install EDM4U before resolving Android packages or building for iOS.

### Check if EDM4U is already installed

Use any of the following methods to check whether EDM4U is already installed:

1. Check whether **Assets > External Dependency Manager** appears in the Unity top menu.
2. Check whether **Assets/ExternalDependencyManager/Editor/<version>/** exists in the file system.
3. Import the Securiti package and check whether the Unity console displays [Securiti Consent] EDM4U detected: `&lt;version&gt;` or a warning message if EDM4U is missing.

### Installing EDM4U

1. Download the latest EDM4U release from the External Dependency Manager for Unity GitHub releases page.
2. Select the `external-dependency-manager-latest.unitypackage` asset from the latest release.
3. Open your Unity project.
4. Import the package using one of the following methods:
  1. Choose **Assets > Import Package > Custom Package**, and select the file.
  2. Alternatively, drag the `external-dependency-manager-latest.unitypackage` file into the open Unity project window.
5. On the **Import Unity Package** popup, leave all items selected and click Import.

After installation, use the checks mentioned in the **Check if EDM4U is already installed** section to verify that EDM4U installed successfully.

## Android installation steps

> [!WARNING]
> Important
> 
> The package includes the `SecuritiConsentDependencies.xml` file, which points EDM4U to the Securiti Maven repository. You do not need to manually edit the `build.gradle` file.

To configure Android installation settings:

1. In Unity, choose **Assets > External Dependency Manager > Android Resolver > Resolve**.
2. In **Player Settings > Player > Android > Other Settings**, set the following values:

| Setting | Value |
| --- | --- |
| Scripting Backend | IL2CPP |
| Target Architectures | ARM64 |

## iOS installation steps

To configure iOS installation settings:

1. In Unity, choose **File > Build Settings > iOS > Build**, and use **Replace** into an empty folder.
2. Open the generated `Unity-iPhone.xcworkspace` in Xcode.
3. In **Player Settings > Player > iOS > Other Settings**, set the following values:

| Setting | Value |
| --- | --- |
| Scripting Backend | IL2CPP |
| Target minimum iOS version | 15.0 |

> [!NOTE]
> Note
> 
> EDM4U automatically runs pod install during the build. The Securiti build processor pins the correct ConsentUI pod version into the generated Podfile.

## Quick configuration

The package includes a `ConsentManager MonoBehaviour` that auto-bootstraps the SDK when the game starts. Follow the steps in this section to initialize the SDK and present the consent banner automatically at app start.

To configure the Unity Consent SDK:

1. In your scene, create an empty GameObject.
2. Click **Add Component**, and add **ConsentManager**.
3. Enter the credential details in the Inspector for Android and iOS. Use the following table to understand the available credential fields:

| Field | Description |
| --- | --- |
| App URL | Base URL for the Securiti application. |
| CDN URL | URL for the Securiti CDN resources. |
| Tenant ID | Your tenant identifier from Securiti. |
| App ID | Your application identifier from Securiti. |
| Testing Mode | Toggle for development builds. |
| Logger Level | Log level values such as `DEBUG`, `INFO`, `WARNING`, or `ERROR`. |

The component initializes the SDK on `Start()` and automatically presents the consent banner when the SDK becomes ready.

## Methods

All public APIs are accessed via the singleton `SecuritiConsentSDK.Instance`.

```csharp
using Securiti.Consent;
var sdk = SecuritiConsentSDK.Instance;
```

### Initialize(options)

Initializes the Consent SDK with configuration options.

> [!NOTE]
> Note
> 
> You must call the `Initialize(options)` method before using any other SDK methods. The `ConsentManager` component calls this method automatically.

#### Parameters

Use the following table to understand the available method parameters:

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `options` | `CmpSDKOptions` | Yes | Configuration options for the SDK |

Use the following table to understand the available `CmpSDKOptions` properties:

| Option | Type | Required | Description |
| --- | --- | --- | --- |
| `AppURL` | `string` | Yes | Base URL for the Securiti application |
| `CdnURL` | `string` | Yes | URL for the Securiti CDN resources |
| `TenantID` | `string` | Yes | Your tenant identifier from Securiti |
| `AppID` | `string` | Yes | Your application identifier from Securiti |
| `TestingMode` | `bool` | Yes | Enable testing mode |
| `LoggerLevel` | `LoggerLevel` | Yes | Log level: `INFO`, `DEBUG`, `INFO`, `WARNING`, `ERROR` |
| `ConsentsCheckInterval` | `int` | No | Time in seconds between consent checks |
| `SubjectId` | `string` | No | User identifier for consent tracking |
| `LanguageCode` | `string` | No | Language code for UI elements such as `en` |
| `LocationCode` | `string` | No | Location code for regional compliance such as US |

#### Return value

This method returns `void`.

#### Example

Use the following example to initialize the SDK:

```csharp
using Securiti.Consent;

var options = new CmpSDKOptions {
    AppURL                = "your APP URL",
    CdnURL                = "your CDN URL",
    TenantID              = "your-tenant-id",
    AppID                 = "your-app-id",
    TestingMode           = false,
    LoggerLevel           = LoggerLevel.DEBUG,
    ConsentsCheckInterval = 60,
    SubjectId             = "user-123",
    LanguageCode          = "en",
    LocationCode          = "US"
};

SecuritiConsentSDK.Instance.Initialize(options);
```

### GetConsentByPurposeId(purposeId)

Retrieves the consent status for a specific purpose by its ID.

#### Parameters

Use the following table to understand the available method parameters:

| Parameter | Type | Description |
| --- | --- | --- |
| `purposeId` | `string` | The unique identifier of the purpose |

#### Return value

This method returns `ConsentStatus`.

Use the following table to understand the available `ConsentStatus` values:

| ConsentStatus | Value |
| --- | --- |
| `NOT_DETERMINED` | 0 > [!NOTE] > Note > > Securiti records the `NOT_DETERMINED` consent status value only for iOS consent records. Android consent records do not use this status. |
| `GRANTED` | 1 |
| `DECLINED` | 2 |
| `WITHDRAWN` | 3 |

#### Example

Use the following example to retrieve the consent status for a specific purpose ID:

```csharp
var status = SecuritiConsentSDK.Instance.GetConsentByPurposeId("12345");
if (status == ConsentStatus.GRANTED) {
    // Consent is granted
}
```

### GetConsentByPermissionId(permissionId)

Retrieves the consent status for a specific app permission by its ID.

#### Parameters

Use the following table to understand the available method parameters:

| Parameter | Type | Description |
| --- | --- | --- |
| `permissionId` | `string` | The unique identifier of the permission |

#### Return value

This method returns `ConsentStatus`.

Use the following table to understand the available `ConsentStatus` values:

| ConsentStatus | Value |
| --- | --- |
| `NOT_DETERMINED` | 0 > [!NOTE] > Note > > Securiti records the `NOT_DETERMINED` consent status value only for iOS consent records. Android consent records do not use this status. |
| `GRANTED` | 1 |
| `DECLINED` | 2 |
| `WITHDRAWN` | 3 |

#### Example

```csharp
var status = SecuritiConsentSDK.Instance.GetConsentByPermissionId("location");
if (status == ConsentStatus.GRANTED) {
    // Permission consent is granted
}
```

### GetPermissions()

Retrieves all available app permissions defined in the consent configuration.

#### Return value

This method returns `AppPermission[]`.

Use the following table to understand the available `AppPermission` properties:

| Property | Type | Description |
| --- | --- | --- |
| `id` | `string` | The permission identifier |
| `name` | `string` | The permission name |
| `description` | `string` | Localized permission description |
| `consent` | `int` | The current consent status |
| `consentString` | `string` | String representation of consent status |

#### Example

Use the following example to retrieve all permissions and filter the granted permissions:

```csharp
var permissions = SecuritiConsentSDK.Instance.GetPermissions();
var granted = permissions
    .Where(p => p.GetConsentStatus() == ConsentStatus.GRANTED)
    .ToArray();
```

### GetPurposes()

Retrieves all available purposes defined in the consent configuration.

#### Return value

This method returns `Purpose[]`.

Use the following table to understand the available `Purpose` properties:

| Property | Type | Description |
| --- | --- | --- |
| `id` | `string` | The unique identifier for the purpose. |
| `name` | `string` | Localized purpose name. |
| `description` | `string` | Localized purpose description. |
| `consent` | `int` | The current consent status (0 to 3). |
| `consentString` | `string` | String representation of consent status. |
| `required` | `bool` | Whether the Purpose is essential. |

#### Example

Use the following example to retrieve all purposes and filter the granted purposes:

```csharp
var purposes = SecuritiConsentSDK.Instance.GetPurposes();
var granted = purposes
    .Where(p => p.GetConsentStatus() == ConsentStatus.GRANTED)
    .ToArray();
```

### GetSdksInPurpose(purposeId)

Retrieves all SDKs associated with a specific purpose.

> [!NOTE]
> Note
> 
> `GetSdksInPurpose(purposeId)` method applies only to Android.

#### Parameters

Use the following table to understand the available method parameters:

| Parameter | Type | Description |
| --- | --- | --- |
| `purposeId` | `string` | The unique identifier of the purpose. |

#### Return value

This method returns `SdkInfo[]`.

#### Example

Use the following example to retrieve all SDKs associated with a specific purpose:

```csharp
var sdks = SecuritiConsentSDK.Instance.GetSdksInPurpose("12345");
```

### SetPurposeConsent(purposeId, status)

Sets the consent status for a specific purpose.

#### Parameters

Use the following table to understand the available method parameters:

| Parameter | Type | Description |
| --- | --- | --- |
| `purposeId` | `string` | The purpose identifier. |
| `status` | `ConsentStatus` | The consent status to set. |

#### Return value

This method returns `bool`.

#### Example

Use the following example to set the consent status for a specific purpose:

```csharp
bool ok = SecuritiConsentSDK.Instance
    .SetPurposeConsent("12345", ConsentStatus.GRANTED);
```

### SetPermissionConsent(permissionId, status)

Sets the consent status for a specific app permission.

#### Parameters

Use the following table to understand the available method parameters:

| Parameter | Type | Description |
| --- | --- | --- |
| `permissionId` | `string` | The permission identifier. |
| `status` | `ConsentStatus` | The consent status to set. |

#### Return value

This method returns `bool`.

#### Example

Use the following example to set the consent status for a specific permission:

```csharp
bool ok = SecuritiConsentSDK.Instance
    .SetPermissionConsent("location", ConsentStatus.GRANTED);
```

### ResetConsents()

Resets all consents to their default state.

#### Return value

This method returns `void`.

#### Example

Use the following example to reset all consent values:

```csharp
SecuritiConsentSDK.Instance.ResetConsents();
```

### IsSdkReady() and OnSDKReadyEvent

Checks whether the SDK is ready to use or subscribes to the SDK ready event callback.

#### Return value

This method returns `bool`. It returns `True` after the SDK initializes and loads the consent data.

#### Example

Use the following example to check whether the SDK is ready and present the consent banner:

```csharp
// Synchronous check
if (SecuritiConsentSDK.Instance.IsSdkReady()) {
    SecuritiConsentSDK.Instance.PresentConsentBanner();
}

// Asynchronous via event
SecuritiConsentSDK.Instance.OnSDKReadyEvent += () => {
    SecuritiConsentSDK.Instance.PresentConsentBanner();
};
```

### GetBannerConfig()

Retrieves the banner configuration.

#### Return value

This method returns `BannerConfig`. If the SDK does not contain a banner configuration, the method returns `null`.

#### Example

Use the following example to retrieve the banner configuration:

```csharp
var config = SecuritiConsentSDK.Instance.GetBannerConfig();
if (config != null) {
    // Use config
}
```

### GetSDKStatus()

Retrieves the current SDK initialization status.

#### Return value

This method returns `SDKStatus`.

Use the following table to understand the available `SDKStatus` values:

| SDKStatus | Value |
| --- | --- |
| `AVAILABLE` | 0 |
| `NOT_AVAILABLE` | 1 |
| `IN_PROGRESS` | 2 |

#### Example

Use the following example to retrieve the current SDK initialization status:

```csharp
 var status = SecuritiConsentSDK.Instance.GetSDKStatus();
```

### GetSettingsPrompt()

Retrieves the settings prompt configuration.

#### Return value

This method returns `SettingsPrompt`. If the SDK does not contain a settings prompt configuration, the method returns `null`.

#### Example

Use the following example to retrieve the settings prompt configuration:

```csharp
var prompt = SecuritiConsentSDK.Instance.GetSettingsPrompt();
```

### UploadConsents(request)

Uploads consent records to the server.

#### Parameters

Use the following table to understand the available method parameters:

| Parameter | Type | Description |
| --- | --- | --- |
| `request` | `PostConsentsRequest` | The consent data to upload. |

#### Return value

This method returns `void`.

#### Example

```csharp
long ts = DateTimeOffset.UtcNow.ToUnixTimeSeconds();  // in seconds

  var request = new PostConsentsRequest {
      Uuid            = "user-123",
      AppUuid         = "app-456",
      Device          = SystemInfo.deviceModel,
      ImplicitConsent = false,
      Version         = 1,
      IsTestMode      = true,
      PurposeConsents = new List<PurposeConsent> {
          new PurposeConsent {
              PurposeId          = 12345,
              ConsentStatusValue = "granted",
              Timestamp          = ts,
              IsEssential        = false
          }
      },
      Permissions = new List<PermissionConsentEntry> {
          new PermissionConsentEntry {
              Permission         = "location",
              ConsentStatusValue = "granted",
              Timestamp          = ts
          }
      },
      AdId       = "00000000-0000-0000-0000-000000000000",
      BannerInfo = "notice-only"
  };

  bool success = await SecuritiConsentSDK.Instance.UploadConsents(request);
  if (success) { /* uploaded */ }
```

### PresentConsentBanner()

Displays the consent banner UI to the mobile app user.

#### Return value

This method returns `void`.

#### Example

Use the following example to display the consent banner UI:

```csharp
SecuritiConsentSDK.Instance.PresentConsentBanner();
```

### PresentPreferenceCenter()

Displays the preference center UI to the mobile app user.

#### Return value

This method returns `void`.

#### Example

Use the following example to display the preference center UI:

```csharp
SecuritiConsentSDK.Instance.PresentPreferenceCenter();
```

### GetGCMConsents()

Retrieves the aggregated Google Consent Mode (GCM) consents.

#### Return value

This method returns `GCMConsent[]`.

Use the following table to understand the available `GCMConsent` properties.

| Property | Type | Description |
| --- | --- | --- |
| `Type` | `string` | GCM consent type, such as `analytics_storage`, `ad_storage`, `ad_user_data`, or `ad_personalization`. You can use these values to forward consent states to Firebase Analytics or Google Consent Mode v2. |
| `Consent` | `int` | Aggregated consent status (0 to 3). |
| `ConsentString` | `string` | String representation of the consent status, such as `GRANTED` or `DECLINED`. |

#### Example

Use the following example to retrieve the aggregated GCM consent values:

```csharp
var consents = SecuritiConsentSDK.Instance.GetGCMConsents();
 foreach (var c in consents)
 {
 	Debug.Log($"{c.Type} = {c.ConsentString}");
 	// Forward c.GetConsentStatus() to Firebase Analytics here
 }
```

### GetGCMConfig()

Retrieves the Google Consent Mode (GCM) configuration. This method describes how purposes map to GCM types, including region-specific overrides.

#### Return value

This method returns `GcmConfig`. If the SDK does not contain a GCM configuration, the method returns null.

Use the following table to understand the available `GcmConfig` properties:

| Property | Type | Description |
| --- | --- | --- |
| `ShowGcmDescription` | `bool` | Indicates whether the SDK shows the GCM-specific description in the consent banner. |
| `GcmDescription` | `Dictionary&lt;string, string&gt;` | Localized description text keyed by locale. |
| `DefaultMapping` | `Dictionary&lt;string, List&lt;int&gt;&gt;` | Default mapping between GCM types and purpose IDs. |
| `RegionOverrides` | `Dictionary&lt;string, Dictionary&lt;string, List&lt;int&gt;&gt;&gt;` | Region-specific overrides for the default mappings keyed by region code. |

#### Example

Use the following example to retrieve the Google Consent Mode configuration and access the default purpose mappings:

```csharp
var gcm = SecuritiConsentSDK.Instance.GetGCMConfig();
 if (gcm != null && gcm.DefaultMapping != null)
 {
 	foreach (var pair in gcm.DefaultMapping)
         Debug.Log($"{pair.Key}: [{string.Join(",", pair.Value)}]");
 }
```

### RemoveListeners()

Removes all internal SDK listeners.

> [!NOTE]
> Your title goes here
> 
> `RemoveListeners()` applies only to iOS and does not perform any action on Android. Call this method before tearing down the SDK to prevent native callback leaks.

#### Return value

This method returns `void`.

#### Example

Use the following example to remove all internal SDK listeners:

```csharp
SecuritiConsentSDK.Instance.RemoveListeners();
```

## Events

Use the following table to understand the available SDK events:

| Event | Signature | Fires when |
| --- | --- | --- |
| `OnSDKReadyEvent` | `Action` | SDK initialization completes and consent data is loaded. |
| `OnErrorEvent` | `Action&lt;string&gt;` | Any SDK call surfaces an error. |
| `OnConsentsResetEvent` | `Action` | `ResetConsents()` completes. |
| `OnConsentsUploadedEvent` | `Action&lt;bool&gt;` | `UploadConsents()` completes. It shows `True` on successful upload. |

Use the following example to subscribe to SDK events in a Unity `MonoBehavior`. The example subscribes to the SDK ready and error events when the component is enabled, and unsubscribes from them when the component is disabled.

When the SDK becomes ready, the example logs the ready state and presents the consent banner. If the SDK returns an error, the example logs the error message in the Unity console.

```csharp
using Securiti.Consent;                                                                                                               
using UnityEngine;

  public class ConsentHooks : MonoBehaviour
  {                                                                                                                                     
      void OnEnable() {                                                                                                                                 
          SecuritiConsentSDK.Instance.OnSDKReadyEvent += OnReady;
          SecuritiConsentSDK.Instance.OnErrorEvent   += OnError;
      }                                                                                                                                 
   
      void OnDisable() {           
          SecuritiConsentSDK.Instance.OnSDKReadyEvent -= OnReady;
          SecuritiConsentSDK.Instance.OnErrorEvent   -= OnError;                                                                        
      }                                                                                                                                 
      void OnReady() {
          Debug.Log("Securiti SDK ready");
          SecuritiConsentSDK.Instance.PresentConsentBanner();                                                                           
      }
                                                                                                                                        
      void OnError(string msg) => Debug.LogError($"Securiti SDK error: {msg}");
  }
```

This pattern helps you register event handlers only while the component remains active and prevents duplicate subscriptions when Unity enables or disables the component.

## Types and Properties

The Unity SDK methods use the following common SDK types, status values, and configuration objects.

### ConsentStatus Values

Use the following table to understand the available `ConsentStatus` values:

| Name | Value |
| --- | --- |
| `NOT_DETERMINED` | 0 |
| `GRANTED` | 1 |
| `DECLINED` | 2 |
| `WITHDRAWN` | 3 |

### LoggerLevel Values

Use the following values to configure the SDK logging level:

- `DEBUG`
- `INFO`
- `WARNING`
- `ERROR`

### SDKStatus Values

Use the following table to understand the available `SDKStatus` values:

| Name | Value |
| --- | --- |
| `AVAILABLE` | 0 |
| `NOT_AVAILABLE` | 1 |
| `IN_PROGRESS` | 2 |

### CmpSDKOptions

For more information, see the [Initialize(options)](/latest/docs/unity-sdk-integration-and-implementation-guide#initializeoptions) section.

### AppPermission

For more information, see the [GetPermissions()](/latest/docs/unity-sdk-integration-and-implementation-guide#getpermissions) section.

### Purpose

For more information, see the [GetPurposes()](/latest/docs/unity-sdk-integration-and-implementation-guide#getpurposes) section.

## Screenshots

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Mobile-App-Consent-Banner(2).png)

Mobile App Consent Banner

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Mobile-App-Consent-Preference-Center-SDK-Purposes-Tab.png)

Mobile App Consent Preference Center - SDK Purposes Tab

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Mobile-App-Consent-Preference-Center-Permissions-Tab.png)

Mobile App Consent Preference Center - Permissions Tab

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Mobile-App-Consent-Preference-Center-Essential-SDK-Expanded.png)

Mobile App Consent Preference Center - Essential SDK Expanded
