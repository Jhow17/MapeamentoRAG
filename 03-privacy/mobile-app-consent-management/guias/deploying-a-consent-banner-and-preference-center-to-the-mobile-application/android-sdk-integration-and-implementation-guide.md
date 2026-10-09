---
title: "Android SDK integration and implementation guide"
slug: "android-sdk-integration-and-implementation-guide"
updated: 2026-08-31T06:44:03Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/android-sdk-integration-and-implementation-guide"
stale: true
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Android SDK integration and implementation guide

> [!WARNING]
> **Important**
> 
> The SDK supports **Android API level 24 (Nougat; Android 7.0)** as the minimum version, with compatibility for all later versions. Ensure your app targets a minimum of **API level 24 or higher** to maintain compatibility with the Securiti SDK.

## 1(a). Downloading Android Studio

1. Head over to the official Android Studio download page on the [Android Developers website](https://developer.android.com/studio).
2. The website will automatically detect your operating system. Click the **Download Android Studio** button.
3. Review the license agreement and click the checkbox to accept the terms and conditions.
4. Choose the appropriate download option for Mac based on your processor type:

> [!NOTE]
> **Note**
> 
> You can use all previous versions of Android Studio, but we recommend using the latest version.
  1. Mac with **Intel** chip, or
  2. Mac with **Apple** chip.

### Installing Android Studio

1. Once the download is complete, locate the downloaded **DMG** (Mac) or **Zip** (Windows) file (usually in your **Downloads** folder), and open it.
2. Drag the Android Studio icon from the opened `.DMG` file into your Applications folder.
3. Double-click the Android Studio icon in your Applications folder to launch the **Android Studio Setup Wizard**.
4. You might see a warning about installing software from the internet. Accept the installation if prompted.

### Completing the Setup Wizard

1. The Setup Wizard will guide you through the configuration process. You might be asked if you want to import settings from a previous Android Studio installation. Choose accordingly, and click **OK**.
2. The wizard will also handle downloading the Android SDK components needed for development.

> [!NOTE]
> **Note**
> 
> This may take some time depending on your internet speed.

Once the setup is complete, you should be able to launch Android Studio and start developing your Android applications. For more information, watch this video guide on [installing Android Studio on macOS](https://www.youtube.com/watch?v=zbWH50OQvtE).

## 1(b). Setup your project

1. **Launch Android Studio**
  - Open **Android Studio** from your **Applications** folder.
2. **Start a New Project**
  1. On the welcome window, click **Start a new Android Studio project**.
  2. Alternatively, from the menu bar, go to **File → New → Project**.
3. **Choose a Project Template**
  1. In the **New Project** window, select a project template under **Phone & Tablet**.
  2. For a basic demo, **Empty Activity** is a good choice. Click **Next**.
4. **Configure Project Details**
5. **Review and Finish**
  1. Review the project details on the summary screen.
  2. Click **Finish** to create the project.
6. **Explore the Project Structure**

Android Studio will create the project with a standard directory structure. You'll find important files such as:

| File | Description |
| --- | --- |
| `app/manifests/AndroidManifest.xml` | Defines app configuration. |
| `app/java` or `app/ktx` (depending on language) | Contains your app's source code. |
| `app/res` | Stores resources like layouts, images, and strings. |
7. **Run the App (Optional):**

(**Optional**) This creates a basic demo project. You can now start customizing it by adding layouts, writing code, and incorporating features.

For more information, see the following resources:
  - To test your demo app, connect an Android device or launch an Android Virtual Device (AVD).
  - Click **Run** (green play icon) in the toolbar.
  - [Official guide on creating a project](https://developer.android.com/studio/projects/create-project)
  - [Codelab for building a first app with Kotlin](https://developer.android.com/codelabs/basic-android-kotlin-compose-first-app)

## Step 1 - Downloading the Securiti SDK

> [!WARNING]
> Important
> 
> The Android Consent SDK includes `Ktor` as a transitive dependency. If your Android app also declares a `Ktor` dependency, make sure your app uses a `Ktor` version that is compatible with the version listed for the Android Consent SDK in the transitive dependency list.
> 
> Gradle resolves `Ktor` to a single version at build time. If your Android app and the Android Consent SDK use incompatible `Ktor` versions, the app might not work as expected at runtime, even if the build completes successfully.
> 
> The Android Consent SDK uses or includes the following dependency versions:
> 
> - `Ktor` 3.5.2
> - `Kotlin` 2.3.21
> - `Koin` 4.2.2
> - `Compose BOM` 2026.01.01
> - Updated Coroutines dependencies
> - Updated `AndroidX` dependencies
> 
> To compile against the Android Consent SDK, your Android app integration must use **Kotlin 2.2.0** or **later**. Android apps that use `R8` or `ProGuard` for code minification do not need to add new keep rules.

### 1(a). Placing the `AAR `file manually in the `libs `folder

To place the `AAR` in the libs folder:

1. **Download the** `AAR` **file:** Make sure you have the `AAR` file from Securiti management portal.
2. **Locate the** `libs` **folder:** Navigate to your project's root directory in Android Studio. There should be a folder named `libs`. If it doesn't exist, create one.
3. **Copy the** `AAR` **file:** Copy the downloaded `AAR` file into the `libs` folder.
4. **Update** `build.gradle` **(app module):** Open the `build.gradle` file located within your app module directory (usually `app/build.gradle`).
5. **Add dependency line:** Inside the `dependencies` block, add the following line, replacing `consent-sdk-1.127.0.aar` with the actual file name.

```groovy
// for ConsentCore
implementation files("libs/consent-sdk-base-1.127.0.aar")
// for ConsentCore + ConsentUI implementation files("libs/consent-sdk-1.127.0.aar")
// commonimplementation("com.google.android.gms:play-services-ads-identifier:18.1.0")
// Transitive Dependencies for aar: 
// versions < 1.127.0 
implementation(”com.squareup.retrofit2:retrofit:2.11.0”)
implementation(“com.squareup.retrofit2:converter-gson:2.11.0”)
implementation(“com.google.code.gson:gson:2.11.0”)
implementation(“androidx.work:work-runtime-ktx:2.9.1”)
// versions >= 1.127.0 
implementation (“io.insert-koin:koin-android:3.5.3”)
implementation (“io.insert-koin:koin-core-coroutines:3.5.3”)
implementation (“io.insert-koin:koin-androidx-compose:3.5.3”)
implementation (“io.ktor:ktor-client-cio:2.3.12”)
implementation (“io.ktor:ktor-serialization-kotlinx-json:2.3.12”)
implementation (“io.ktor:ktor-client-logging:2.3.12”)
implementation (“io.ktor:ktor-client-content-negotiation:2.3.12”)
//only if you want to use ConsentUI
//if you face any error related to Compose (For old Java/Kotlin 
//Projects):
implementation(platform("androidx.compose:compose-bom:2024.10.00"))
implementation("androidx.compose.ui:ui")
implementation("androidx.compose.ui:ui-graphics")
implementation("androidx.compose.material3:material3")
```
6. **Sync Gradle:** Click **Sync Project with Gradle Files** in Android Studio to refresh the project with the new dependency. Or use the Maven Repository method below.

### 2(b). Maven Repository

If you want to integrate SDK with **Android Maven** library, it is accessible through a Maven repository, from where you can easily incorporate it into your Android Studio project using Gradle:

1. **Add the Maven Repository:** In your project's `build.gradle` file (usually at the root of your project), add the Maven repository to the `repositories` block:

```groovy
repositories {
      mavenCentral() // or any other required repositories
      maven {
            url("https://cdn-prod.securiti.ai/consent/maven")
      }
}
```
2. **Add the Dependency:** In the same `build.gradle` file, add the following dependency to your `dependencies` block:

```groovy
dependencies {
    // for ConsentCore    
implementation("ai.securiti.cmpsdkcorebase:consent-sdk-base:1.127.0")
    // for ConsentCore + ConsentUI    
    implementation("ai.securiti.cmpsdkcore:consent-sdk:1.127.0")
}
```

> [!WARNING]
> **Important**
> 
> Ensure to use the most recent **Maven SDK** version.
3. **Sync Project:** Click the **Sync Now** button in Android Studio to sync your project with the Gradle changes.

## Step 2 - Integration

For manual integration, you can download the latest version of SDKs from the management portal of Securiti's **Mobile App Consent Management** module.

### TV platform support

The Android Consent SDK also supports consent collection for Android TV-based Connected TV (CTV) and Over-the-Top (OTT) apps, including **Android TV**, **Google TV**, and **Amazon Fire TV**.

> [!NOTE]
> Note
> 
> For Android TV-based CTV and OTT apps, you must follow the same implementation steps used for Android mobile apps. No Android-specific changes are required in the implementation workflow.

You can use the Android Consent SDK to extend mobile app consent configuration patterns to CTV apps. This lets CTV users open, close, and revisit the consent banner and preference center to review and update their consent preferences with ease.

The Android TV SDK supports Google Advertising ID (GAID), opens URLs directly through WebView, and supports TV remote and D-pad navigation for consent interactions. When CTV users navigate the consent banner or preference center using a TV remote, actionable items show a focus ring to indicate the currently selected item.

To personalize and activate your consent banner after installing the `SecuritiMobileCmp`, you will require a **Securiti banner configuration account**.

Ensure you have added Internet usage permission in your `Manifest.xml` file.

```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

### Configuration

After completing the integration steps, you can now import and use `SecuritiMobileCmp`.

```kotlin
import android.app.Application
import com.securiti.cmpsdkcore.main.*
class MyApplication : Application() {

   override fun onCreate() {
       super.onCreate()
       // Initialize SDK
       val options     = CmpSDKOptions(
           appURL      = "Add App URL here",
           cdnURL      = "Add CDN URL here",
           appID       = "Paste your application ID here",
           tenantId    = "Paste your tenant ID here",
           loggerLevel = CmpSDKLoggerLevel.DEBUG,
           testingMode = true

       )
       SecuritiMobileCmp.initialize(this, options)
   }
}
```

> [!WARNING]
> Important
> 
> Ensure your **Application** file is named correctly and declared in the `Manifest.xml` file.
> 
> ```xml
> <application 
> android:name=".MyApplication"/>
> ```

For now, you need to initialize `SecuritiMobileCmp` with `ApplicationPackageID`. You can configure more by using the `CmpSDKOptions` class.

In addition to the `ApplicationPackageID`, you can also configure the following options at the project level:

```kotlin
//class CmpSDKOptions(
//    //Your Application URL
//    appURL: String
//
//    //Your CDN URL
//    cdnURL: String
//
//    //Unique ID for tenants while account creation
//    tenantID: String
//

 //Your Application ID
   appID: String

   testingMode: Boolean //true/false
   //Use true for Test records and false for Production records in Portal

   loggerLevel: CmpSDKLoggerLevel {NONE, DEBUG}
   //Used for internal logging and exception handling

   consentsCheckInterval: Int //default value 1800
   //Used for background consents upload interval in seconds - min value 60

   subjectId: "Your Custom Subject Id"
   //This is optional, example: U01

   languageCode: "Your Language Code"
   //This is optional, example: en

   locationCode: "Your Location Code" 
   //This is optional, example: CA#US or US
)
//)
```

## Step 3 - Initialization

Code documentation

```kotlin
import android.app.Application
import com.securiti.cmpsdkcore.main.*
class MyApplication : Application() {
   override fun onCreate() {
       super.onCreate()
       // Initialize SDK
       val options     = CmpSDKOptions(
           appURL      = "Add App URL here",
           cdnURL      = "Add CDN URL here",
           appID       = "Paste your application ID here",
           tenantID    = "Paste your tenant ID here",
           loggerLevel = CmpSDKLoggerLevel.DEBUG,
           testingMode = TestingMode.DRAFT
       )
       MobileCmp.initialize(this, options)
   }
}
```

## Step 4 - Usage

### `ConsentCore` Methods

#### 1. Function `isReady(), isReady() { isReady → { } }`

#### **Purpose**

`isReady()` is a callback function within a CMP that signals to other parts of your application when the CMP has finished initializing and is prepared to handle consent management tasks.

This function ensures that you cannot interact with the CMP's features, such as retrieving consent status or displaying the user interface, until it is fully initialized.

#### **How it works**

1. **Integration**: After initialization, you need to call this method to make sure that your SDK is ready to use.
2. **Initialization**: During the initialization process, the CMP fetches necessary data (such as data subject consent preferences from local storage or a server-side database) and configures itself based on your provided settings.
3. `isReady()`: Once initialization is complete, the CMP invokes the `isReady()` function that you can use for further implementation.

#### Usage

**Define the function**: We provide the `isReady()` function which returns boolean status after CMP initialization. This function serves as your application's way of being notified that the CMP is ready.

**Functionality**: By using the `isReady()` function, you can now safely execute code that interacts with the CMP's features. Common actions might include:

- Retrieving the current data subject's consent status for various purposes such as advertising, analytics, etc.
- Triggering the display of the consent user interface (where data subjects can express their consent preferences).
- Performing actions based on consent choices such as enabling or disabling tracking scripts.

#### 2. Function: `getConsent(purposeId: Int)`

`getConsent(purposeId: Int)`: This function retrieves the data subject or app user's consent status from the CMP SDK. It will return a value indicating whether consent has been given, denied, withdrawn and not-determined depending upon the status of that Purpose.

#### 3. Function**:** `getConsent(permissionId: Int)`

`getConsent(permissionId: Int)`: This function retrieves the permission's consent status from the CMP SDK. It will return a value indicating whether consent has been given, denied, withdrawn, and not determined depending upon the status of that App Permission.

#### 4. Function: `setConsent(purpose: Purpose, consent: ConsentStatus)`

`setConsent(purpose: Purpose, consent: ConsentStatus)`: This function is used to update the app user's consent status within the CMP SDK. The `purpose` argument represents the specific purpose for which consent is being updated, The `consent` argument is probably an object containing details about the app user's consent choices, possibly including specific vendors and purposes they have consented to.

#### 5. Function: `setConsent(appPermission: AppPermission, consent: ConsentStatus)`

`setConsent(appPermission: AppPermission, consent: ConsentStatus)`: This function is used to update the app user's permission consent status within the CMP SDK. The appPermission argument represents the specific appPermission for which consent is being updated. The `consent` argument is probably an object containing details about the mobile app user's current permission consent preferences.

#### 6. Function: `resetConsents()`

`resetConsents()`: This function resets the data subject's consent choices within the CMP SDK integrated into your application (website or mobile app). By resetting consent, all previously granted or denied consents are cleared.

When `resetConsents()` is called, the data subject or app user will be presented with the consent banner again as if they have not made any choices yet. They will need to go through the consent selection process and grant or deny consent to various vendors and purposes again.

#### 7. Function: `addListener(listener: ConsentSdkListener)`

`addListener(listener: ConsentSdkListener)`: This function lets you register a listener object within the CMP SDK integrated into your application (website or mobile app). This listener will be notified whenever there are changes to the data subject's consent status.

#### Parameters

`listener (ConsentSdkListener)`: A reference to a function object that implements the `ConsentSdkListener` interface. This function will be called by the CMP whenever a relevant event is triggered.

#### Event examples

The specific events that the `addListener` function can notify about will vary depending on the CMP SDK you're using. However, some common events might include:

| Event | Description |
| --- | --- |
| `onConsentChanged(newConsent: ConsentData)` | This event is triggered whenever the data subject's consent preferences change within the CMP UI. The `newConsent` parameter provides details about the updated consent state. |
| `onPermissionConsentChanged(newConsent: ConsentStatus)` | This event is triggered whenever the data subject's app permission changes within the CMP UI. The `newConsent` parameter provides details about the updated consent state. |

#### 8. Function: `getPurposes() → List`

#### Purpose

This function retrieves a list of purposes from the CMP SDK integrated into your application (website or mobile app). These purposes represent the different reasons why data might be collected from the data subject.

#### Understanding purposes

- In the context of consent management, purposes define the specific reasons why data is collected from data subject.
- For example, a purpose might be **personalization of advertising** or **fraud prevention**.
- Data subject typically grant or deny consent for these purposes individually through the consent banner provided by the CMP.

#### What the list contains

The list returned by `getPurposes()` likely contains objects representing each available purpose. These objects might include details such as:

| Aspect | Description |
| --- | --- |
| Purpose ID | A unique identifier for the purpose. |
| Purpose Description | A human-readable description of the purpose, explaining why data is collected. |
| (Optional) Legitimate Interest Purposes | This might be a flag indicating if the purpose relies on a legitimate interest legal basis. |

#### Use cases

Use the following table to understand the possible use cases:

| Use Case | Description |
| --- | --- |
| Prepopulating Consent Banner | Your application might use `getPurposes()` to prepopulate the consent banner with the available purposes before presenting it to the data subject or app user. |
| Customizing User Interface | You can use the retrieved purposes to dynamically display information or options within your application's user interface based on data subject consent for specific purposes. |

#### 9. Function: `getSdksInPurpose(purposeId: String) → List`

`addListener(listener: ConsentSdkListener)`: This function lets you register a listener object within the CMP SDK integrated into your application (website or mobile app). This listener will be notified whenever there are changes to the app user's consent status.

#### 10. Function: `getPermissions() → List`

#### Purpose

This function retrieves a list of permissions from the CMP SDK integrated into your application (website or mobile app). These permissions represent the specific data points or functionalities that require data subject consent.

#### Understanding the permissions

- In the context of CMPs, permissions define the granular level of data subject data that can be collected or accessed.
- These permissions might be more specific than purposes and could include things like location data, device identifiers, or access to the data subject's camera.
- Data subjects typically grant or deny consent for these permissions individually through the consent banner provided by the CMP.

#### What the list contains

The list returned by `getPermissions()` likely contains objects representing each available permission. These objects might include details such as:

| Aspect | Description |
| --- | --- |
| Permission ID | A unique identifier for the permission. |
| Permission Description | A human-readable description of the permission, explaining what data is collected or accessed. |
| Purpose Association | A reference to the purpose(s) that this permission is linked to. |

#### Use cases

Use the following table to understand the possible use cases:

| Use Case | Description |
| --- | --- |
| Prepopulating Consent Banner | Your application might use `getPermissions()` to pre-populate the consent banner with the available permissions before presenting it to the data subject. |
| Customizing User Interface | You can use the retrieved purposes to dynamically display information or options within your application's user interface based on data subject consent for specific purposes. |

#### 11. Function: `getBannerConfig() → ConfigObject`

#### Purpose

This function retrieves the configuration settings for the consent banner from the CMP SDK integrated into your application (website or mobile app). The consent banner is the user interface element where data subjects select their consent preferences.

#### Customizing the banner

- CMPs typically provide a customizable consent banner that users interact with to grant or deny consent for various purposes.
- `getBannerConfig()` lets you access the configuration options associated with this banner, enabling you to potentially personalize its appearance and behavior to better integrate with your application's user interface.

#### ConfigurationObject (placeholder)

This represents a placeholder for the data structure containing the configuration settings. The specific format and content will depend on the particular CMP you are using. Use the following table to understand some common configuration options you might be able to access through `getBannerConfig()`:

| Configuration | Description |
| --- | --- |
| Banner Position | Define where the consent banner appears on the screen. Positions such as **top**, **bottom**, **center**, etc. |
| Banner Language | Set the language for the banner text to match your application's locale. |
| Color Scheme | Customize the colors of the consent banner to match your application's branding. |
| Button Text | Modify the text on the consent buttons such as **Accept** or **Reject**. |
| Prefilled Options | Set default selections for certain options within the banner based on your CMP configuration. |

#### Customization benefits

- By using `getBannerConfig()`, you can create a consent banner that is visually consistent with your application's design, improving the overall data subject experience.
- You can also tailor the consent banner's language and phrasing to better resonate with your data subjects.

#### 12. Function: `uploadConsents(request: PostConsentsRequest) -&gt; Boolean`

Asynchronously uploads app consents to a specified URL using a `PostConsentsRequest` object and returns a Boolean which indicates whether the upload was successful or not.

`PostConsentsRequest:`

| Aspect | Description |
| --- | --- |
| `UUID` | A unique identifier for the data subject. |
| `appUUID` | App's UUID which is given by Securiti. |
| `device` | A Device Name from which consents are being uploaded. |
| `version` | Current Consent SDK Version. |
| `purposeConsents` | List of Purpose Consents. |
| `permissions` | List of Permission Consents. |
| `isTestMode` | An identifier for Test Mode Consent. |
| `adId` | Ad ID is applicable only when the Google Advertising ID setting is enabled. |

### `ConsentUI` Methods

#### 1. Function: `presentConsentBanner()`

Presents the consent banner if the app is opened for the first time and consents were not given by the data subject.

> [!NOTE]
> **Note**
> 
> Jetpack Compose also supports this method for declarative UI development. You can also use this method in Jetpack Compose.

Example:

```kotlin
 MobileCmp.isReady{ isReady ->
   if(isReady) {
   	MobileCmp.presentConsentBanner(activity: Activity)
   }
}
```

#### 2. Function: `presentPreferenceCenter()`

Presents the preference center to the data subject, allowing them to manage their consent preferences.

> [!NOTE]
> **Note**
> 
> Jetpack Compose also supports this method for declarative UI development. You can also use this method in Jetpack Compose.

Example:

```kotlin
MobileCmp.isReady{
   MobileCmp.presentPreferenceCenter(activity: Activity)
}
```

#### 3. (Optional) `registerColors(context: Context, colors: CustomColors)`

Registers and overrides the colors that are configured on the management portal.

> [!NOTE]
> **Note**
> 
> Jetpack Compose also supports this method for declarative UI development. You can also use this method in Jetpack Compose.

Example:

```kotlin
MobileCmp.registerColors(
    CustomColors(        
       buttonBackground = "#1414d2",        
       buttonText = "#ffffff",        
       buttonBorder = "#1f2229",        
       bannerBackground = "#ffffff",        
       bannerText = "#4c4e54",        
       bannerLinks = "#1414d2",        
       preferenceCenterFooterBackground = "#f7f4f2",        
       preferenceCenterFooterSelector = "#1414d2"
   )
)
```

#### 4. Function: `registerFonts(context: Context, heading: CustomFont?, body: CustomFont?, subHeading: CustomFont?, subHeadingLight: CustomFont?)`

Registers custom fonts for use in the consent banner and preference center, ensuring your app's typography is consistent with the selected styles.

> [!NOTE]
> **Note**
> 
> Jetpack Compose also supports this method for declarative UI development. You can also use this method in Jetpack Compose.

Example:

```kotlin
MobileCmp.registerFonts(
    context = this,
    heading = CustomFont(
        resId = R.font.neue_plak_text_for_united_sm_bd,
        size = 16.sp,
        type = TextStyle(fontWeight = FontWeight.Bold)
    ),
    body = CustomFont(
        resId = R.font.neue_plak_text_for_united_rg,
        size = 14.sp,
        type = TextStyle(fontWeight = FontWeight.Normal)
    ),
    subHeading = CustomFont(
        resId = R.font.neue_plak_text_for_united_sm_bd,
        size = 14.sp,
        type = TextStyle(fontWeight = FontWeight.Bold)
    ),
    subHeadingLight = CustomFont(
        resId = R.font.neue_plak_text_light,
        size = 12.sp,
        type = TextStyle(fontWeight = FontWeight.Normal)
    )
)
```

#### 5. Function: (Optional) `saveState(activity: Activity, outState: Bundle)`

Saves the current state of the consent banner or preference center before a configuration change occurs, enabling restoration later using `restoreState` method.

```kotlin
// Inside respective Activity
   override fun onSaveInstanceState(outState: Bundle) {
       super.onSaveInstanceState(outState)
//     Save state of consent banner or preference center if it's    
//     shown when configuration change happened or incase of process of death
       MobileCmp.saveState(this, outState)
   }
```

#### 6. (Optional) `restoreState(activity: Activity, savedInstanceState: Bundle?)`

Responsible for restoring the state of the consent banner or preference center after a configuration change, such as **screen rotation** or **process death**. Ensures that UI components re-initialize and display correctly based on the saved state or last active entry point, without requiring manual intervention.

> [!NOTE]
> **Note**
> 
> You must call the `saveState` method beforehand; otherwise, you cannot restore the state.

```kotlin
// Inside respective Activity   
   override fun onCreate(savedInstanceState: Bundle?) {
      // Other code.....
/**  restore the state of consent banner or preference center if 
     it was shown when configuration change happened or incase of 
     process of death **/
MobileCmp.restoreState(this, savedInstanceState)
   }
```

## Demo app preview

Below are the screenshots of the consent banner and preference center, demonstrating their appearance with custom font styles and sizes on Android **mobile**, **tablet**, and **TV** devices.

### Consent Banner and Preference Center on Android mobile device

![Mobile-App-Consent-Banner-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f88b13c3-4309-7987-b914-49b80135c4ce.png)

![Mobile-App-Consent-PC-SDK-Tab-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd8493af-c49c-51be-b766-898867aaacf3.png)

![Mobile-App-Consent-PC-EssentialSDK-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-81be8a59-bf55-3581-94c0-90b19aaefdda.png)

![Mobile-App-Consent-PC-Permissions-Tab-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c5f10251-3a50-b75f-d145-cc9c06c76a4d.png)

### Consent Banner and Preference Center on Android tablet device

![Tablet-App-Consent-Banner-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-41eee6d1-13c9-3113-b9af-ac36b3108223.png)

![Tablet-App-Consent-PC-SDK-Tab-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c74bc2d5-072c-aac3-ee69-b68ba6e87b7e.png)

![Tablet-App-Consent-PC-EssentialSDK-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-db668a05-191b-f0f0-0ff8-817294647588.png)

![Tablet-App-Consent-PC-Permissions-Tab-v2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a9d48a98-d018-803e-2cdb-78174315054c.png)

### Consent Banner and Preference Center on Android TV device

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Layout-2.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Layout-3.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Layout-5.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Layout-7.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Layout-4.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Layout-8.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Layout-6.png)

## Additional Built-in Features

### Secure WebView domain control

The SDK includes a secure WebView configuration that lets applications control which domains the WebView can load. This feature helps prevent malicious redirects, unauthorized script loading, and other WebView-based attacks while ensuring that consent-related content continues to function normally.

Configure this feature using the `webviewConfig` parameter in `CmpSDKOptions`.

#### Configuration

`CmpSDKOptions` supports an optional `WebViewConfig` object with the following parameters:

| Parameter | Type | Description |
| --- | --- | --- |
| allowedDomains | List<String> | Optional list of domains that the WebView can load. |
| blockedPageRes | Int | Optional resource reference to a custom HTML page displayed when you encounter a blocked domain. |

```kotlin
CmpSDKOptions(
    // other config variables
    // webviewConfig is optional here
    webviewConfig = WebViewConfig(
        allowedDomains = listOf(   // allowedDomains is optional
            "united.com"
        ),
        blockedPageRes = R.raw.webview_blocked_page // blockedPageRes is optional
    )
)
```

#### WebView behavior - Case 1: No allowedDomains configured (default behavior)

If you do not configure the allowedDomains parameter, the WebView operates in a standard secure mode with built-in protections. In this mode, the SDK allows commonly used web protocols while blocking schemes that may introduce security risks.

The following URL schemes are allowed:

- URLs using http
- URLs using https

The following schemes are blocked:

- javascript: scheme
- file: scheme
- data: scheme
- Other potentially dangerous schemes

This default behavior ensures that the WebView maintains a secure baseline configuration even when no domain allow list is explicitly defined.

#### WebView behavior - Case 2: allowedDomains configured

If allowedDomains is provided, the SDK creates an effective allow list consisting of multiple trusted sources. In this mode, the WebView loads content only from domains included in this allow-list and from additional trusted sources required for consent functionality.

The effective allow list includes the following trusted sources:

| Trusted source | Description | Examples |
| --- | --- | --- |
| Configured domains | Any domain explicitly specified in allowedDomains is trusted by the WebView. | [united.com](http://united.com) |
| Subdomains of configured domains | When you add a base domain to allowedDomains, the SDK automatically trusts all of its subdomains. | [www.united.com](http://www.united.com) [assets.united.com](http://assets.united.com) [login.united.com](http://login.united.com) |
| URLs from consent configuration | The SDK automatically extracts and trusts URLs that appear in consent configuration content to ensure consent UI elements function correctly. | - Banner text links - Privacy notice links - DSR portal links - Cookie descriptions - Other consent UI links |
| Securiti infrastructure domains | Domains used by Securiti infrastructure are automatically trusted because they are required for SDK functionality. | Securiti service domains required for SDK operation |

#### What gets blocked

Domain restrictions are enforced at **three different layers** to prevent bypass techniques.

To prevent bypass techniques, the SDK enforces domain restrictions at three different layers of WebView interaction, as described below.

| Enforcement layer | Description | Behavior when a blocked domain is detected |
| --- | --- | --- |
| Initial WebView URL | The SDK validates the URL before loading the WebView. | The page does not load, and the WebView immediately displays the blocked page. |
| In-page navigation | The SDK validates links that mobile app users interact with inside the WebView. | Navigation to the blocked domain is prevented, and the blocked page is displayed. |
| Scripts and iframes | The SDK validates external resources loaded by the page. This includes third-party JavaScript files, embedded iframes, and other external page resources. | Resources originating from untrusted domains are blocked. |

This layered validation prevents proxy bypass techniques, such as loading restricted content through embedded resources.

#### Blocked page

When the SDK blocks a domain, the WebView does not display a blank page. Instead, it shows a blocked page that informs the mobile app user that access to the requested URL is restricted.

The SDK supports two ways of displaying this page, as described below.

| Blocked page type | Description | Configuration |
| --- | --- | --- |
| Default blocked page | The SDK includes a default blocked page out of the box. The WebView automatically displays this page whenever a blocked domain is encountered. | No configuration required. |
| Custom blocked page | Applications can override the default page by providing a custom HTML file in res/raw. Using a custom blocked page lets you control branding, messaging, and styling. | Example configuration: ```kotlin WebViewConfig( allowedDomains = listOf("example.com"), blockedPageRes = R.raw.custom_blocked_page ) ``` |

#### Accessing the blocked URL

When the SDK blocks a domain, it securely injects the blocked URL into the blocked page as a JavaScript variable. The custom blocked page can then display the restricted URL to the mobile app user if needed.

Example usage in a custom HTML page:

```kotlin
<div class="url" id="blocked-url"></div>
<script>
(function () {
  if (typeof BLOCKED_URL !== "undefined" && BLOCKED_URL) {
    document.getElementById("blocked-url").textContent = BLOCKED_URL;
  }
})();
</script>
```

This example reads the injected BLOCKED_URL variable and displays the restricted URL on the page.

#### Security considerations

The secure WebView configuration includes the following built-in safeguards designed to protect applications from malicious content, unauthorized redirects, and unsafe resource loading. Use the following table to understand the key security considerations and how Securiti mitigates associated risks.

| Security consideration | How Securiti addresses it |
| --- | --- |
| JavaScript support | JavaScript is enabled in the WebView because most modern websites rely on it for essential functionality such as navigation, form handling, and dynamic content rendering. Disabling JavaScript would prevent many legitimate pages from loading correctly. Instead of disabling JavaScript entirely, the SDK protects the WebView by enforcing strict domain validation and resource filtering. Only content originating from trusted domains is allowed to load, significantly reducing the risk associated with executing JavaScript. |
| Static security scanners | Static application security testing tools, such as Veracode, may report warnings related to WebView configurations. These warnings commonly include: - JavaScript enabled in the WebView - Potential cross-site scripting (XSS) risks In the context of this SDK, these findings may appear as false positives because the WebView operates within a controlled and restricted environment. The SDK mitigates these risks through several security mechanisms: - Domain allow-listing restricts WebView content to trusted domains only. Untrusted resources are blocked, preventing unauthorized scripts, redirects, or embedded content from loading. - Secure URL injection ensures that blocked URLs are safely passed to the blocked page without exposing injection vulnerabilities. These protections ensure that WebView content remains tightly controlled while still allowing legitimate web functionality required for consent interfaces and related content. |

### Language Translations

We use the system-selected language configured in your OS settings for general translations. After retrieving the system language from Android system locales, we map it to the corresponding translation if available; otherwise, we default to the fallback language. To explicitly set a language, use the `languageCode` in the `CmpSDKOptions` class upon initialization.

### Set Up Right-to-Left (RTL) Languages

Ensure the default language of your Android device is set to an RTL language in system settings for the SDK to render correctly.

To set an RTL language as the system default:

1. Navigate to the **System Settings** of your Android device.
2. Select **Languages**, and then click **System Languages**.
3. Select **Arabic** or any **other RTL language** from the list of available languages, as shown below.

![Andorid_System_Settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8b26710-5ac8-70c2-6bc6-a83f367406e0.png)

![Andorid_Language_Setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0f087408-3644-2702-3104-f7467607ef1a.png)

![Andorid_Selected_RTL_Language.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d5001be-fc12-ed6e-4cdd-966f029f59db.png)

#### Consent Banner and Preference Center with RTL Language

![Android-RTL-Consent-Banner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-88145ae4-b243-f3d3-ce67-6f9b888dd948.png)

![Android-RTL-Consent-PC-SDK-Tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-586ed83a-eb0f-890a-72f9-85a8332fb89a.png)

![Android-RTL-Consent-PC-Essential-SDK.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-283e1478-79ce-f6e6-1325-948dd57e3948.png)![Android-RTL-Consent-PC-Permissions-Tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-71454b27-8f70-f4ab-7385-e2292889631a.png)

Connected TV (CTV) refers to a television or television-connected device that connects to the internet and lets users access video content through apps or web-based services. CTV includes smart TVs and televisions connected to devices such as streaming devices, gaming consoles, and set-top boxes.

Over-the-Top (OTT) refers to video content delivered directly to users over the internet rather than through traditional cable, broadcast, satellite, or telecom services. Users can access OTT content through apps or web-based services on devices such as connected TVs, mobile devices, computers, and gaming consoles.

The Google Advertising ID (GAID) is an Android identifier used to track user behavior and measure ad performance across mobile apps. Users can reset it anytime to get a new ID or delete it permanently to disable ad tracking. This gives mobile app users more privacy control over personalized advertising.

A consumer or other member of the general public whose personal data is held by a controller or processor.

## Related

- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
- [Using SDK Purposes](/using-sdk-purposes.md)
- [Using the SDK and Permissions Library](/using-the-sdk-and-permissions-library.md)
