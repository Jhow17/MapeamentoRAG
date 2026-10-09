---
title: "Unreal Engine SDK integration and implementation guide"
slug: "unreal-engine-sdk-integration-and-implementation-guide"
updated: 2026-09-21T15:14:39Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/unreal-engine-sdk-integration-and-implementation-guide"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Unreal Engine SDK integration and implementation guide

This integration and implementation guide explains how to add the Unreal Engine Consent SDK plugin to an Unreal Engine project, configure the plugin, and use Blueprints to show the consent banner and preference center.

> [!NOTE]
> Note
> 
> This guide applies to Unreal Engine 5.8 projects for Android and iOS.

## Prerequisites

Before you install and configure the Unreal Engine plugin, ensure that your Unreal Engine project, Android build environment, and iOS build environment meet the following requirements.

### Unreal Engine requirements

Use the following table to understand Unreal Engine’s requirements for the Consent SDK:

| Requirement | Description |
| --- | --- |
| Unreal Engine version | Use Unreal Engine 5.8. |
| Plugin package | Download and use the `securiti-consent-unreal-&lt;version&gt;.zip` package for the Consent SDK version you want to integrate. |

### Android requirements

Configure the following Android requirements before building your Unreal Engine project for Android:

| Requirement | Description |
| --- | --- |
| Minimum Android SDK version | Use Android API level 24 or later. |
| Android SDK and NDK | Install the Android SDK and NDK with Unreal Engine Android support. |

### iOS requirements

Configure the following iOS requirements before building your Unreal Engine project for iOS:

| Requirement | Description |
| --- | --- |
| Minimum iOS deployment target | Use iOS 15.0 or later. |
| Xcode | Use Xcode to build the generated iOS project. |
| Build machine | Use a Mac to build the iOS project. |

## Downloading the Unreal Engine plugin package

> [!NOTE]
> Note
> 
> The Unreal Engine plugin package includes the Securiti Consent SDK plugin and the prebuilt native artifacts required for Android and iOS integration.

To download the Unreal Engine plugin package:

1. Open Securiti’s mobile consent SDK [Releases](https://github.com/securitiai/mobile-consent-sdk-ios/releases) page.
2. Select the release for the Consent SDK version you want to integrate.
3. From the release assets, download the `securiti-consent-unreal-&lt;version&gt;.zip` package.

> [!WARNING]
> Note
> 
> Each release can include assets for other frameworks, such as Unity, React Native, Flutter, and iOS. Make sure you download the Unreal Engine package.

1. Unzip the downloaded package.
2. Confirm that the extracted package includes the **SecuritiConsent** folder.

The **SecuritiConsent** folder contains the Unreal Engine plugin and the prebuilt native artifacts required for Android and iOS integration. You do not need to compile the native artifacts manually.

Use the following table to understand the main package contents:

| Package item | Description |
| --- | --- |
| `SecuritiConsent/` | Contains the Unreal Engine plugin. |
| `SecuritiConsent.uplugin` | Defines the plugin metadata and configuration for Unreal Engine. |
| `Source/SecuritiConsent/` | Contains the plugin source files. |
| `ThirdParty/iOS/ConsentUI.xcframework` | Contains the prebuilt iOS framework bundled with the plugin. |
| `ThirdParty/Android/securiti-unreal-bridge.aar` | Contains the prebuilt Android bridge bundled with the plugin. |

> [!NOTE]
> Note
> 
> The native Android and iOS artifacts are already bundled inside the plugin. To begin integration, add the **SecuritiConsent** plugin folder to your Unreal Engine project.

## Installing the Unreal Engine plugin

After you download and unzip the Unreal Engine plugin package, add the plugin to your Unreal Engine project.

To install the plugin:

1. Copy the **SecuritiConsent** plugin folder into your Unreal Engine project's **Plugins** folder, as shown below

> [!NOTE]
> Note
> 
> If the **Plugins** folder does not exist, create it at the project root, and then copy the **SecuritiConsent** folder into it. The final path should be: `&lt;YourProject&gt;/Plugins/SecuritiConsent`

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Plugins folder with SecuritiConsent inside.png)
2. Open your Unreal Engine project in the Unreal Editor.
3. If Unreal Editor prompts you to rebuild missing modules, click **Yes**.
4. From the top left corner, choose **Edit > Plugins**.
5. In the **Search** text field, enter “Securiti Consent SDK”.
6. Mark the checkbox next to the Securiti Consent SDK to enable the plugin, as shown below.

> [!NOTE]
> Note
> 
> Restart the Unreal Editor if prompted. Restarting the editor lets Unreal Engine load the enabled plugin, register its Blueprint nodes, and apply the plugin configuration to the project. If the plugin nodes or settings do not appear after enabling the plugin, close and reopen the Unreal Editor.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Plugins window with Securiti Consent SDK enabled.png)

## Configuring the Unreal Engine plugin

> [!NOTE]
> Note
> 
> When **Auto Initialize On Startup** is enabled, the plugin initializes the Unreal Engine Consent SDK automatically when the Unreal Engine app starts.

To configure the Consent SDK:

1. In Unreal Editor, from the top left corner, choose **Edit > Project Settings**.
2. In the **Plugins** section, select **Securiti Consent SDK**.
3. Enter the connection details for each platform, as shown below.

> [!NOTE]
> Note
> 
> The Android and iOS sections include the same connection fields, but each section applies to its own platform.
> 
> - The **Android** section applies to Android builds and the editor or desktop environment.
> - The **iOS** section applies to iOS builds.
> 
> You can use different tenant or app values for each platform if required.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Project Settings - Plugins - Securiti Consent SDK, iOS and Android sections filled in.png) Use the following table to understand the platform-specific connection settings:

| Setting | Description |
| --- | --- |
| App URL | Securiti app URL for the selected platform, such as `https://&lt;env&gt;.securiti.xyz`. |
| CDN URL | CDN URL for the selected platform, such as `https://cdn-&lt;env&gt;.securiti.xyz/consent`. |
| Tenant ID | Tenant GUID for the selected platform. |
| App ID | App GUID for the selected platform. |
| Testing Mode | Turns on testing mode for development and testing for the selected platform. |

1. Configure the common settings that apply to both platforms.

Use the following table to understand the common settings:

| Setting | Description |
| --- | --- |
| Auto Initialize On Startup | Initializes the Consent SDK automatically when the app starts. Securiti recommends enabling this setting for static configuration values. |
| Logger Level | Sets the logging level, such as **Debug**, **Info**, **Warning**, or **Error**. |
| Consents Check Interval | Sets the background consent recheck interval in seconds. Use `0` to apply the Consent SDK default. |
| Subject Id | Optional subject identifier override. Use this only when the value is known before app startup. |
| Language Code | Optional language override. |
| Location Code | Optional location override. |
2. Save the project settings.

> [!NOTE]
> Note
> 
> Unreal Engine saves these values in `Config/DefaultGame.ini`.

## How initialization works

When **Auto Initialize On Startup** is enabled, the plugin reads the configuration section for the running platform and initializes the Unreal Engine Consent SDK at app startup.

- For iOS builds, the plugin reads the **iOS** section.
- For Android builds and the editor or desktop environment, the plugin reads the **Android** section.

> [!NOTE]
> Warning
> 
> If you configure only the Android section, the Consent SDK remains unconfigured for iOS builds and the consent banner does not appear on iOS. Make sure you also configure the iOS section when building for iOS.

If the required fields, such as App URL, Tenant ID, or App ID, are blank for the running platform, the plugin skips initialization and logs a warning that identifies the missing configuration section.

You can also initialize the SDK from Blueprint with dynamic values. For more information, see the Using dynamic values at runtime section.

## Dynamic values at runtime

Project Settings values are written to `DefaultGame.ini` at build time, so use them for static values. For instance, if your Subject Id, Language Code, or Location Code is available only at runtime, such as after the player signs in, initialize the Consent SDK from Blueprint instead.

To initialize the Consent SDK with dynamic values:

1. Disable **Auto Initialize On Startup**.

> [!NOTE]
> Note
> 
> This prevents the Consent SDK from initializing before the runtime value is available.
2. When the runtime value becomes available, call the **Initialize Consent SDK** node.
3. In the **Initialize Consent SDK** node's Advanced rollout, pass the runtime Subject Id, Language Code, or Location Code.
4. Call **Present Consent Banner When Ready** node.

Example Blueprint flow:

```plaintext
Event, such as On Login Success
  -> Initialize Consent SDK
     Subject Id = <your runtime id>
     App URL, Tenant ID, and App ID = values from your configuration
  -> Present Consent Banner When Ready
```

> [!NOTE]
> Note
> 
> Calling **Initialize Consent SDK** node reinitializes the Unreal Engine Consent SDK if it is already running. You can enable **Auto Initialize On Startup** and reinitialize the SDK after login with a runtime Subject Id, but initializing the SDK once, after the value is available, keeps the implementation cleaner. The Unreal Engine SDK does not provide a separate **Set Subject Id** node. To use a new Subject Id, initialize the SDK again with the updated value.

## Showing the consent banner and preference center from Blueprints

The Unreal Engine Consent SDK provides global Blueprint nodes under the Securiti Consent SDK category. You can search for and use these nodes in any Blueprint graph, including the Level Blueprint and widget Blueprints.

### Showing the consent banner on level start

To show the consent banner when the level starts:

1. In Unreal Editor, choose **Blueprints > Open Level Blueprint**.
2. Add the **Event BeginPlay** node.
3. Connect **Event BeginPlay** node to the **Present Consent Banner When Ready** node.

Example Blueprint flow:

```plaintext
Event BeginPlay
  -> Present Consent Banner When Ready
```

The **Present Consent Banner When Ready** node waits until the Consent SDK is ready, and then shows the consent banner over the running level, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Level Blueprint with Event BeginPlay connected to Present Consent Banner When Ready.png)

When the node runs successfully, Securiti shows the consent banner over the Unreal Engine app, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Unreal-Engine-Consent-Banner.png)

### Adding a Manage Consent Preferences button

You can add a button that lets mobile app users reopen the preference center and update their consent preferences.

#### Creating the widget

To create the widget:

1. In the **Content Browser** menu, choose **Add > User Interface > Widget Blueprint**.
2. Name the widget `WBP_ConsentMenu`.
3. Open `WBP_ConsentMenu`.
4. From the **Palette**, drag a **Canvas Panel** to the widget root.

> [!NOTE]
> Note
> 
> Add the Canvas Panel before adding the button. If you add a button without a Canvas Panel, the button might stretch across the full screen.
5. Drag a Button into the Canvas Panel.
6. Drag Text onto the button.
7. Set the button text to Manage Consent Preferences.
8. Select the button.
9. In **Details > Slot** **(Canvas Panel Slot)**, set **Anchors** to a fixed point, such as top-center.
10. Set a fixed value for **Size X** and **Size Y**, such as 340 x 64, so the button does not stretch across the screen, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/WBP_ConsentMenu designer with the Manage Consent Preferences button.png)

#### Wiring the button

To open the preference center from the button:

1. Select the button.
2. In **Details > Events**, click the **+** icon next to **On Clicked**.
3. In the widget graph, connect **On Clicked** to the **Present Preference Center** node.
4. Click **Compile**.
5. Click **Save**.

Example Blueprint flow:

```plaintext
On Clicked
  -> Present Preference Center
```

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/WBP_ConsentMenu graph with On Clicked connected to Present Preference Center.png)

### Showing the widget in the level

After you create and wire the widget, add it to the level from the Level Blueprint.

To show the widget when the level starts:

1. Open the **Level Blueprint**.
2. Add the **Create Widget** node.
3. Set **Class** to `WBP_ConsentMenu`.
4. Connect the **Return Value** widget to the **Add to Viewport** widget.
5. Chain the nodes after **Present Consent Banner When Ready** node.

Example Blueprint flow:

```plaintext
Event BeginPlay
  -> Present Consent Banner When Ready
  -> Create Widget
     Class = WBP_ConsentMenu
  -> Add to Viewport
```

> [!NOTE]
> Tip
> 
> When testing on desktop or in Play In Editor (PIE), add `Get Player Controller` and set `Show Mouse Cursor` to `True` so you can click the button. On mobile devices, touch input works directly.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Level Blueprint with consent banner, Create Widget, and Add to Viewport nodes.png)

After the widget appears in the level, mobile app users can click **Manage Consent Preferences** to reopen the preference center and update their consent preferences, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Unreal-Engine-Consent-Preference-Center.png)

## Blueprint API reference

All Blueprint nodes are available in the **Securiti Consent SDK** category. You can call these nodes directly from any Blueprint graph. Each node includes an automatic **World Context** pin that Unreal Engine fills in. The tables below omit this pin.

### Methods

Use the following table to understand the available Blueprint methods:

> [!NOTE]
> Note
> 
> *(adv)* indicates that the parameter appears in the node’s **Advanced** rollout. Expand the arrow at the bottom of the node to view advanced parameters.

| Node | Parameters | Returns | Description |
| --- | --- | --- | --- |
| Initialize Consent SDK | `AppURL : String`, `CdnURL : String`, `TenantID : String`, `AppID : String`, `bTestingMode : bool = true`, `LoggerLevel : EConsentLogLevel = Debug`, `ConsentsCheckInterval : int32 = 0` *(adv)*, `SubjectId : String = ""` *(adv)*, `LanguageCode : String = ""` *(adv)*, `LocationCode : String = ""` *(adv)* | — | Initializes the Consent SDK with explicit values passed through Blueprint pins. Use this node when configuration values are available only at runtime, such as a runtime Subject Id. For static configuration values, Securiti recommends using **Project Settings**. |
| Initialize Consent SDK From Settings | (none) | — | Initializes the Consent SDK using the values configured in **Project Settings > Plugins > Securiti Consent SDK**. |
| Present Consent Banner When Ready | (none) | — | Waits until the Consent SDK is ready, and then shows the consent banner. |
| Present Preference Center | (none) | — | Shows the preference center so the mobile app user can review or update consent preferences. |
| Is Consent Ready | (none) | `bool` | Returns `true` when the Consent SDK has loaded the CDN configuration and is ready to support consent actions. |
| Get Consent SDK Status | (none) | `EConsentSDKStatus` | Returns the current Consent SDK readiness state. |
| Get Consent By Purpose Id | `PurposeId : int32` | `EConsentStatus` | Returns the current consent status for the specified Purpose ID. |
| Set Purpose Consent | `PurposeId : int32`, `Status : EConsentStatus` | `bool` | Sets consent for the specified Purpose ID and returns `true` when the action succeeds. Essential purposes with `disableOptOut:true` cannot be declined, and the call returns `false`. |
| Get Consent By Permission Id | `PermissionKey : String` | `EConsentStatus` | Returns the current consent status for the specified Permission. Pass the `permissionKey` value from **Get Consent Permissions (JSON)** instead of the `id` value. |
| Set Permission Consent | `PermissionKey : String`, `Status : EConsentStatus` | `bool` | Sets consent for the specified Permission by `permissionKey` and returns `true` when the action succeeds. |
| Get Consent Purposes (JSON) | (none) | `String` (`JSON`) | Returns the available Purposes as a `JSON` array. For the response schema, see the [JSON payload schema](/latest/docs/unreal-engine-sdk-integration-and-implementation-guide#64-json-payload-schema) section. |
| Get Consent Permissions (JSON) | (none) | `String` (`JSON`) | Returns the available Permissions as a `JSON` array. For the response schema, see the [JSON payload schema](/latest/docs/unreal-engine-sdk-integration-and-implementation-guide#64-json-payload-schema) section. |
| Get Banner Config (JSON) | (none) | `String` (`JSON`) | Returns the banner configuration object as JSON. Returns an empty string (`""`) if the configuration is not available or the Consent SDK is not ready. |
| Get Settings Prompt (JSON) | (none) | `String` (`JSON`) | Returns the settings prompt configuration object as JSON. Returns an empty string (`""`) if the configuration is not available or the Consent SDK is not ready. |
| Get GCM Config (JSON) | (none) | `String` (`JSON`) | Returns the Google Consent Mode (GCM) configuration as `JSON`, including the Purpose-to-type mapping. Returns an empty string (`""`) if no GCM configuration is available. |
| Get GCM Consents (JSON) | (none) | `String` (`JSON`) | Returns aggregated GCM consent values as `[{type,consent,consentString}]` for Firebase. |
| Get SDKs In Purpose (JSON) | `PurposeId : int32` | `String` (`JSON`) | Returns the SDKs configured under the specified Purpose ID. This node works on both Android and iOS. It returns `[]` if the Purpose ID has no SDKs or is not found. |
| Upload Consents | `RequestJson : JSON` | `bool` | Uploads a consent record using the request `JSON` schema described in the [Upload Consents request JSON](/latest/docs/unreal-engine-sdk-integration-and-implementation-guide#65-upload-consents-—-request-json) section. Returns `true` when the request is dispatched. |
| Reset Consents | (none) | — | Clears all stored consent records. |
| Get Consent Subsystem | (none) | Consent Subsystem > [!NOTE] > Note > > The **Consent Subsystem** object also exposes an **Is Initialized** node. This node returns `true` after initialization runs, whether initialization is automatic or manual. The subsystem object also exposes the same methods listed above as member calls. | Returns the Consent Subsystem object. Use this object to bind the events described in [Events](/latest/docs/unreal-engine-sdk-integration-and-implementation-guide#62-events) section. |

### Events

Drag off **Get Consent Subsystem** and select an **Assign** or **Bind Event** node.

Use the following table to understand the available events:

| Event | Payload | Fires when |
| --- | --- | --- |
| On Ready | `bReady : bool` | The Consent SDK finishes loading and becomes ready to show consent UI. |
| On Consent Changed | `ConsentJson : String` | A Purpose or Permission consent value changes. The payload contains `JSON` that describes the change. |
| On Error | `Message : String` | The native SDK reports an error. The payload contains the error message or `JSON` details. |

### Enum values

Use the following table to understand the available enum values:

| Enum | Values |
| --- | --- |
| `EConsentStatus` | `Not Determined` (0), `Granted` (1), `Declined` (2), `Withdrawn` (3) |
| `EConsentLogLevel` | `DEBUG`, `INFO`, `WARNING`, `ERROR` |
| `EConsentSDKStatus` | `Available` (0), `Not Available` (1), `In Progress` (2) |

### JSON payload schema

**Get GCM Consents (JSON)** returns an array of `{ "type": string, "consent": int, "consentString": string }`, where `type` is `analytics_storage`, `ad_storage`, `ad_user_data`, or `ad_personalization`.

Use the following table to understand the fields in the response:

| Field | Type | Description |
| --- | --- | --- |
| `id` | `string` | Purpose ID. |
| `name` | `string` | Localized display name of the Purpose. |
| `description` | `string` | Localized display name of the Purpose. |
| `consent` | `int` | Consent status value. This value maps to **EConsentStatus** values `0` through `3`. |
| `consentString` | `string` | Text representation of the consent status, such as `GRANTED`, `DECLINED`, `WITHDRAWN`, or `NOT_DETERMINED`. |
| `disableOptOut` | `bool` | Native flag that indicates whether the Purpose is essential. - A value of `true` means the data subject cannot opt out and the Purpose remains granted. - A value of `false` means the Purpose is toggleable. If you call **Set Purpose Consent** to decline a Purpose with `disableOptOut:true`, the Consent SDK does not apply the change. |

**Get GCM Consents (JSON)** returns an array of `{ "type": string, "consent": int, "consentString": string }`, where `type` is `analytics_storage`, `ad_storage`, `ad_user_data`, or `ad_personalization`.

Use the following table to understand the fields in the response:

| Field | Type | Description |
| --- | --- | --- |
| `id` | `string` | Permission id (numeric on iOS, native string on Android — not portable) |
| `permissionKey` | `string` | Stable key for the permission. Pass this to Get Consent By Permission Id / Set Permission Consent. |
| `name` | `string` | Display name |
| `description` | `string` | Localized description |
| `consent` | `int` | Matches EConsentStatus (0–3) |
| `consentString` | `string` | GRANTED / DECLINED / WITHDRAWN / NOT_DETERMINED |

**Get Banner Config (JSON)**, **Get Settings Prompt (JSON)**, and **Get GCM Config (JSON)** return the native configuration object as JSON. Some fields can be platform-specific. An empty string (`""`) means the configuration is not available or the Consent SDK is not ready.

### Upload Consents request JSON

**Upload Consents** takes a `JSON` string in the following shape. Omit `platform` and `sdk_version` because the Consent SDK sets these values. `consent_status` must be one of `granted`, `declined`, `not_determined`, or `withdrawn`. `timestamp` uses Unix seconds.

> [!NOTE]
> Note
> 
> On iOS, the upload URL comes from the Unreal Engine Consent SDK’s configured **App URL**. The returned `bool` means the request was dispatched. It does not confirm that the server acknowledged the request.

```json
{
  "uuid": "user-123",
  "app_uuid": "app-456",
  "device": "iPhone14,2",
  "implicit_consent": false,
  "version": 1,
  "is_test_mode": true,
  "ad_id": "",
  "banner_info": "notice-only",
  "purpose_consents": [
    { "purpose_id": 7, "consent_status": "granted", "timestamp": 1733500000, "is_essential": false }
  ],
  "permissions": [
    { "permission": "location", "consent_status": "granted", "timestamp": 1733500000 }
  ]
}
```

## Packaging notes

Review the following packaging notes before building your Unreal Engine project for Android or iOS.

### Android

Configure the following Android packaging settings before you package the app:

| Setting | Description |
| --- | --- |
| Package data inside APK | Turn on this setting from **Project Settings > Android** when you want to sideload a single self-contained `APK` to a device. For store releases, turn it off and ship an `OBB` or `AAB` instead. |
| Minimum SDK version | Use Android API level 24 or later. |

### iOS

Configure the following iOS packaging settings before you package the app:

> [!NOTE]
> Warning
> 
> Set the **Bundle Identifier** and **Signing Team** in **Project Settings > Xcode Projects**, not directly in the generated Xcode project. Unreal Engine can overwrite changes made directly in the generated Xcode project when it regenerates project files. Values set from **Project Settings > Xcode Projects** persist in `Config/DefaultEngine.ini` under `[/Script/MacTargetPlatform.XcodeProjectSettings]`, so packaging and Project Launcher builds can reuse them.

| Setting | Description |
| --- | --- |
| Minimum iOS Version | Set **Minimum iOS Version** to 15.0 or later from Project **Settings > Platforms > iOS**. |
| Bundle Identifier | Set the **Bundle Identifier** from **Project Settings > Xcode Projects**. |
| Signing Team | Set your **Apple Team ID** from **Project Settings > Xcode Projects**. |

> [!NOTE]
> Note
> 
> A free or Personal Apple ID team can build only to a connected device. It cannot create a simulator distribution build.

#### iOS framework and orientation behavior

The `ConsentUI.xcframework` is embedded and code-signed into the app automatically through `bCopyFramework`. You do not need to complete a manual Xcode step for this framework.

The consent UI appears in its own window and follows your app’s orientation. For example, if your game supports landscape only, the consent banner appears in landscape. You do not need to enable portrait orientation. Earlier builds could throw `UIApplicationInvalidInterfaceOrientation`; the shipped framework now handles this behavior internally.

## Troubleshooting

Use the following table to troubleshoot common Unreal Engine Consent SDK integration issues:

| Issue | Resolution |
| --- | --- |
| Nodes or settings do not appear. | Restart Unreal Editor after enabling the plugin. New C++ reflection does not always hot-reload reliably. |
| The app shows "Failed to open descriptor file …uproject" on the device. | The `APK` might have been packaged without data inside it. Enable **Package data inside APK** and repackage the app, or install the app using the generated install script. |
| The consent banner appears over a black screen. | Make sure the consent banner appears on the game's own activity. This is the plugin's default behavior on Android. |
| The app shows "No purposes loaded yet". | The call ran before the Consent SDK was ready. Trigger the call from **On Ready**. |
| Nothing happens when you initialize the SDK. | Confirm that App URL, Tenant ID, and App ID are configured in Project Settings. |
| The iOS app crashes at launch with a MarketplaceKit or FOnlineSubsystemIOS::Init error. | Add `[OnlineSubsystem] DefaultPlatformService=Null` to `DefaultEngine.ini`. |
| The iOS bundle ID or signing team resets when you use Project Launcher. | Set the values in **Project Settings > Xcode Projects**, not in the generated Xcode project. |
| The iOS consent banner crashes with UIApplicationInvalidInterfaceOrientation. | The current framework handles this behavior by adopting the host app orientation. Make sure you use the shipped `ConsentUI.xcframework` from the release package. |
| The iOS consent banner or preference center leaves the screen dimmed, or input remains stuck after closing. | Rebuild against the latest release. The current framework tears down the overlay window on every dismiss path. |

## Verifying with logs

You can review device logs to confirm Unreal Engine Consent SDK activity, such as CDN fetches, consent reads, consent writes, and errors. The plugin logs use the `LogSecuritiConsent` category.

### Android

To review Android logs, run the following commands while you trigger the consent flow:

```plaintext
adb logcat -c
adb logcat -v time | grep -iE "Consent|Securiti"
```

### iOS

To review iOS logs, stream the device log or go to **Xcode > Window > Devices and Simulators > View Device Logs**. You can also use macOS **Console.app** with the device selected.

To stream logs from the command line, run the following command:

```plaintext
idevicesyslog | grep -iE "Consent|Securiti"
```

> [!NOTE]
> Note
> 
> The `idevicesyslog` command requires `libimobiledevice`. To install it, run the following command:
> 
> ```plaintext
> brew install libimobiledevice
> ```
