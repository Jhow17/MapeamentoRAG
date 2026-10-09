---
title: "iOS SDK integration and implementation guide"
slug: "ios-sdk-integration-and-implementation-guide"
updated: 2026-09-01T07:03:46Z
published: 2026-09-01T07:03:46Z
canonical: "helpcenter.securiti.ai/ios-sdk-integration-and-implementation-guide"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# iOS SDK integration and implementation guide

### Prerequisites

- Ensure you have a **Mac** computer.
- Ensure you have an active **Apple Developer Account**.
- Download and install **Xcode** for free from the Apple App Store on your Mac computer.

> [!WARNING]
> **Important**
> 
> The SDK supports **iOS 15** as the minimum version, with compatibility for all later versions. Ensure your app targets iOS 15 or higher to maintain compatibility with the Securiti SDK.

### Installing Xcode

1. Apple App Store: Download Xcode from the App Store. The store will notify you when updates are available, or you can set macOS to update automatically.

![1-Install-Xcode.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21bd9a9c-de3f-152d-dec6-884524423b8c.png)
2. The latest beta version and previous versions of Xcode can be downloaded from the [Apple Developer Downloads](https://developer.apple.com/download/all/?q=xcode) (requires Apple account). Run it by double-clicking the downloaded **Xcode.app**.

(Optional) To show the downloaded **Xcode.app** in **Applications**, drag it into your Applications folder. ![2-installing_xcode_beta_versions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bab79666-f8fe-46d2-0a66-e2df449666fe.png)

### Creating an Xcode project for your iOS app

1. **Create a New Project:** Open Xcode, and click **Create a New Xcode Project**, as shown below.

![1-create_new_project.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-946df6a6-7aca-d80d-7e67-a725f2d96d53.png)
2. **Select a Template:** Choose a template (e.g., iOS App), as shown below.

![2-select_template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c74a8ad8-a02a-bad9-97ad-722a8e1b6117.png)
3. **App Information:** Provide information about your app, such as **Product Name**, **Organization Name**, and **Organization Identifier**, as shown below.

![3-app_information.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b53ed8d0-f77e-2599-b868-5a818245d85c.png)

For more detailed steps, refer to the [official Apple guide](https://developer.apple.com/documentation/xcode/creating-an-xcode-project-for-an-app).

### Setting up Xcode and Simulators

1. **Open Xcode:** Open Xcode for the first time, and it will prompt you to check **Simulator Runtimes** and continue. This step sets up Xcode and downloads the necessary simulators.
2. **Download and setup Simulators:** Open Xcode and navigate to **Settings**. On the **Platforms** popup, select **iOS <latest version>**, and from the right side, click **Get** to download the necessary simulators, as shown below. ![1-download_and_setup_simulator.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b44dd5a0-858c-d438-1878-b7705f934928.png)

### Publishing your iOS app to the Apple App Store

1. **Prepare for Publishing:** Ensure your app meets Apple's guidelines. For more information, check all the requirements from [this link](https://developer.apple.com/app-store/review/guidelines/).
2. **Select the Right Target:** Make sure the correct target is selected and it is signed by a team with an Apple Developer account, as shown below.

![2-select_right_target.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-41a2785c-f8b6-eb33-f5a0-c787ab7464d8.png)
3. **Archive Your App:** Go to **Product → Archive**. This generates an archive ready for publishing, as shown below.

![3-archive_your_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99ddec31-78c6-2bb6-a932-b6b299883352.png)
4. **Distribute Your App:** Once the archive is generated, a prompt will be shown:

For detailed instructions, see the [official Apple guide on submitting apps](https://developer.apple.com/ios/submit/).
  - Click **Distribute Content**.
  - Select **App Store Connect**.
  - To publish your app to the Apple App Store, click **Distribute**.

![4-distribute_your_app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-58b3597a-d09d-5d2a-0e3f-bd3350dde6f3.png)

## iOS Native - Integration guide

Integrating the Securiti's SDK into your Native Swift iOS project can be done using several methods.

> [!WARNING]
> **Important**
> 
> The SDK names and links provided in this document are subject to change and not final.

Following are the most commonly used approaches:

### 1. CocoaPods

[CocoaPods](https://cocoapods.org/) is a dependency manager for **Swift** and **Objective-C Cocoa** projects. It simplifies the process of integrating third-party libraries.

1. **Install** [**CocoaPods**](https://guides.cocoapods.org/using/getting-started.html) **(if you haven't already):** Open terminal, and run command: `sudo gem install cocoapods`, as shown below.

![1-_Install-Cocoapods.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-49df2618-50d2-f988-aee1-a0944ae18ae0.png)
2. **Initialize CocoaPods in your project (if you haven't already):** Open terminal, cd to the root of your project, and run command: `pod init`, as shown below.

![2-_Initialize-Pod.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2fc44cb1-d3f8-9922-9383-6fcf08a98a8e.png)
3. **Edit the Podfile:** Open the Podfile, and add the desired third-party frameworks. For instance:

```ruby
target 'YourProjectName' do
use_frameworks!
  		# if you want to use ConsentCore SDK
		pod 'ConsentCore', 'LATEST_VERSION'
		# or you want to use ConsentUI SDK
		Pod 'ConsentUI', 'LATEST_VERSION'
End
# Check for latest version on 
# https://github.com/securitiai/mobile-consent-sdk-ios/releases
```

![3-_Edit-Pod-File.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1d3d5d7-0a3f-6764-7d16-646d61f09a20.png)
4. **Install the pods:** Run command: `pod install`, as shown below.

![4-_Install-Pods.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7820d4fc-0c8f-3fab-1a31-268f84b7a0e9.png)
5. **Open the .xcworkspace file:** After installation, always open the `.xcworkspace` file, not the `.xcodeproj` file. ![5-_Open-Xcworkspace.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f8520e18-0b64-2540-d430-30f29391065d.png)

### 2. Carthage

Carthage is another dependency manager that provides a simpler integration approach compared to CocoaPods.

1. **Install** [**Carthage**](https://github.com/Carthage/Carthage): Open terminal, and run command: `brew install carthage`, as shown below. ![1-install-carthage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef8ff617-e686-7317-b0f9-90ce4a543bd9.png)
2. **Create a Cartfile:** In the root of your project, create a file named **Cartfile**, and add the desired frameworks. For instance:

```plaintext
# if you want to use ConsentCore SDK
binary
 "https://github.com/securitiai/mobile-consent-sdk-ios/ConsentCore.json" == LATEST_VERSION
# or you want to use ConsentUI SDK
binary
 "https://github.com/securitiai/mobile-consent-sdk-ios/ConsentUI.json" == LATEST_VERSION
# Check for latest version on 
# https://github.com/securitiai/mobile-consent-sdk-ios/releases
```

![2-create-cartfile-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12ea15e3-ae5f-32c6-3a51-749b22d69e0f.png) ![2-create-cartfile-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e61b3e8d-c894-821f-37a9-c4017520b098.png)
3. **Build the frameworks:** Open terminal, cd to the root of your project, and run command: `carthage build --platform ios --use-xcframeworks`, as shown below. ![3-build-framework.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16f0d9f9-a480-4456-2ef2-e9d52446b685.png)
4. **Drag and Drop the framework:** Drag the **.xcframework** file or the folder containing the source code "`Carthage/Build`" files into the **Frameworks** group in your Xcode project. Ensure to select the "Copy items if needed" option in the dialog that appears, then click **Finish**, as shown below. ![4-drag-and-drop-framework-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2dac9e1-19a7-c9ef-4ef8-06be711a3433.png) ![4-drag-and-drop-framework-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-16e7c26d-e61f-dee7-7a30-b4b5f42d476f.png)
5. **Link and Embed the framework:** Ensure that the framework is also listed under the **Frameworks**, **Libraries**, **Embedded Content** section. If it is not, click **Add** (+ icon) to add it. Ensure to select **Embed & Sign** for the **XC****framework**, as shown below. ![5-link-and-embed-framework.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5073f5fd-527c-e0e5-951b-fd899cbca170.png)
6. **Set the Framework Search Path:** Click **All**, and then in the search bar, type "Framework Search Paths", and add the path to the directory containing the **.xcframework** file.

For instance, the framework is in a **Frameworks** folder within your project, you might add `$(SRCROOT)/Frameworks`, as shown below. ![6-set-framework-search-path.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a4c9f62f-353f-7042-1a9e-2861255f1ca0.png)

### 3. Swift Package Manager (SPM)

[Swift Package Manager](https://docs.swift.org/latest/documentation/packagemanagerdocs/) is built into Xcode and offers a straightforward way to manage dependencies.

1. **Add a Package Dependency:** In Xcode, go to **File > Add Package Dependencies**, as shown below. ![1-add_package_dependency.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-69fa6386-acb2-1d4d-6b23-b709a42196d6.png)
2. **Enter the repository URL and select the desired version:** Enter the URL of the package repository that you wish to add.

For instance, add `https://github.com/securitiai/mobile-consent-sdk-ios`, and then choose the version or branch of the package you wish to integrate, as shown below. ![2-enter_repo_url_and_select_desired_version.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b045b42-8e46-9dbf-d085-fa05a3470b96.png)
3. **Add the package:** Xcode handles the rest, integrating the package into your project. ![3-add-the-package.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-372d4a0e-51f8-dc5d-0955-bf7d263abd11.png)

> [!NOTE]
> **Note**
> 
> Select one based on your mobile application's requirement. For more information, see [Types and Methods](https://docs.google.com/document/d/1BdDkttXU-yLw2sXMvkWGKTwXc5am0RareJNNv_8BdF0/edit#heading=h.p8lktqlp3hyo).

### 4. Manual Integration

To incorporate Securiti's framework manually:

1. **Download the Framework**
  1. Navigate to the official website [Releases | securitiai/mobile-consent-sdk-ios](https://github.com/securitiai/mobile-consent-sdk-ios/releases). ![1-gotoofficialwebsiteanddownload.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e3cf7d0-6b5b-dd9f-9a56-b72eb40eeafb.png)

> [!NOTE]
> **Note**
> 
> The SDK versions are subject to change with each Securiti release. Ensure to use the most recent SDK version. Access the provided link to download the latest version. The screenshot reflects the version available at the time of capture.
  2. Download and unzip the compiled framework, it is usually a **.xcframework** file. ![2-downloadandunzipxcframework.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-20d7ead0-66f6-1a75-641f-3ffa622c3555.png)
2. **Add the Framework to Your Xcode Project**
  1. **Open Your Xcode Project:** Launch Xcode and open your existing project or create a new project, as shown below. ![1-open_xcode_project.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-803a7171-ece7-13d6-849a-d0f65c9c00bf.png)
  2. (Optional) Create a Frameworks Group: To keep your project organized, you might want to create a new group (folder) in your Xcode project for third-party frameworks, as shown below. ![2-create_frameworks_folder_or_group.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa6998cf-60a2-f551-6d21-2b43f6eaefe6.png)
  3. Right-click the project navigator, select **New Group**, and name it **Frameworks**.
  4. **Drag and Drop the Framework:** Drag the downloaded **.xcframework** file or the folder containing the source code files into the **Frameworks** group in your Xcode project, as shown below. Ensure to select the "Copy items if needed" option in the dialog that appears, then click **Finish**, as shown below. ![3-drag_and_drop_framework_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5e16bea-3d5b-ba5a-7d59-0d4114b17ed2.png) ![3-drag_and_drop_framework_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a9990b4-111a-e1cf-fb41-9056cc672083.png)
3. **Link the Framework**
  1. **Select Your Project Target:** In the project navigator, select your project, and then select your app target under the **TARGETS** section, as shown below. ![1-select_project_target.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a5d4143-3231-60e7-ec0a-10395e2bafe5.png)
  2. **Go to the General Tab:** Click the **General** tab, as shown below. ![2-go_to_general_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e85bf9ca-82f2-20d7-753e-bedecb7e2319.png)
  3. **Add to Linked Frameworks and Libraries:** Ensure that the framework is also listed under the **Frameworks**, **Libraries**, **Embedded Content** section. If it is not, click Add (+ icon) to add it. Ensure to select **Embed & Sign** for the **.xcframework**, as shown below. ![3-add_linked_frameworks_and_libraries.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4771052d-f958-97e5-d7ad-c1dabf0bd99c.png)
4. **Configure Build Settings > Frameworks Path**
  1. **Select Your Project Target:** In the project navigator, select your project, then select your app target under the **TARGETS** section, as shown below. ![1-select_project_target.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a6091f6-0bdb-24f6-7527-7194299a4547.png)
  2. **Go to the Build Settings Tab:** Click on the **Build Settings** tab, as shown below. ![2-go_to_build_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9d246089-d354-560f-f481-efc8a7733d6c.png)
  3. **Search for Framework Search Paths:** Click **All**, and then in the search bar, type "Framework Search Paths", as shown below. ![3-search_for_framework_search_paths.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-977d581a-155c-5dc5-13f4-117eab86a309.png)
  4. **Add the Path to the Framework:** Double-click the value column next to **Framework Search Paths** and add the path to the directory containing the **.xcframework** file. For instance, if the framework is in a **Frameworks** folder within your project, you might add `$(SRCROOT)/Frameworks`, as shown below. ![4-add_path_to_framework.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ef2b432-cc6a-9527-1216-f25de8f6168e.png)
5. **Import the Framework in Your Code**
  1. **Open a Swift File:** Open any Swift file where you wish to use the framework, as shown below. ![1-open_any_swift_file.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-277d911e-568d-2145-5edb-01f5dc495b79.png)
  2. **Import the Framework:** At the top of the file, add an import statement for the framework. For instance, either type `import ConsentCore` or `import ConsentUI`, as shown below. ![2-import_framework.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-52a4236a-cf15-f295-7a28-e6d7cd11d5a8.png)
6. **Verify the Integration**
  1. **Use the Framework:** Start using the framework in your code.

For instance, use `ConsentSDK.shared.setupSDK(options: SDKOptions)` to set up the SDK ideally when your application starts. ![1-build_project.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1fcbdf4-6197-41fe-ef84-3d79ed164883.png)
  2. **Build Your Project:** Press **Command+B** to build your project, and ensure there are no errors, as shown below. ![2-use_the_framework.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05bbf086-8eba-3951-6a42-b3d55654d5b7.png)

## iOS Native - Implementation guide

Securiti's iOS SDK is a comprehensive toolkit for integrating privacy and consent management features into iOS applications. The SDK is designed to help developers comply with regulations such as the **General Data Protection Regulation (GDPR), California Consumer Privacy Act (CCPA)**, and other privacy laws that require data subject consent for data processing activities.

### TV platform support

The iOS Consent SDK also supports consent collection for Apple TV-based Connected TV (CTV) and Over-the-Top (OTT) apps.

> [!NOTE]
> Note
> 
> For Apple TV-based CTV and OTT apps, you must follow the same implementation workflow used for iOS mobile apps. In the relevant implementation sections, select the **CTV/OTT** tab instead of the **Mobile** tab to view TV-specific code.

You can use the iOS Consent SDK to extend mobile app consent configuration patterns to CTV apps. This lets CTV users open, close, and revisit the consent banner and preference center to review and update their consent preferences with ease.

The iOS Consent SDK supports Apple's App Tracking Transparency (ATT) framework and provides QR code-based access for URL-driven consent experiences. It also supports Siri Remote and focus-engine navigation for consent interactions. When CTV users navigate the consent banner or preference center using the Siri Remote, actionable items show a focus state to indicate the currently selected item.

#### Types and methods

Use the following table to understand the **SDK types**, their **supported architectures**, and **total sizes** before and after the deployment:

| Type | Description | Supported Architectures | Total SDK Size |
| --- | --- | --- | --- |
| `ConsentCore` | This is a lightweight version of the SDK that provides core functionalities without a user interface. It's suitable for the tenants who want to create their own UI or have size constraints. | - **ios-arm-64:** Any real iOS device (SDK Size: 1.2 MBs) - **ios-arm-64-x86_64:** Any iOS Simulator Device (SDK Size: 2.3 MBs) | **3.5 MBs** when integrated. In production, only the ios-arm-64 architecture is retained, reducing the size to 1.2 MBs. |
| `ConsentUI` | This version includes all the features of ConsentCore plus a pre-built user interface for consent banners and a preference center which are configured on the management portal. | - **ios-arm-64:** Any real iOS device (SDK Size: 1.8 MBs) - **ios-arm-64-x86_64:** Any iOS Simulator Device (SDK Size: 3.5 MBs) | **5.3 MBs** when integrated. In production, only the ios-arm-64 architecture is retained, reducing the size to 1.8 MBs. |

> [!WARNING]
> **Important**
> 
> The `ConsentUI` method is an extension of the `ConsentCore` method. Ensure that you use only one **xcframework** at a time.

### `ConsentCore` Methods

#### `setupSDK(_ options: ConsentSDKOptions)`

Initializes the SDK with the provided options.

**Responsibilities:**

- Loads and caches the configuration. In **Live** mode, the cache lasts for 1 hour. In **Testing** mode, the cache lasts for the entire app session.
- Starts periodic checks to monitor the consent status of data subjects. If any consent changes, the SDK automatically uploads the updated consents.
- Initializes the **Network Utility**, which attempts to upload any pending consents as soon as network connectivity is restored.

> [!WARNING]
> **Important**
> 
> This method is mandatory, and you must call it when the application starts.

Example:

```swift
ConsentSDK.shared.setupSDK(
      options: SDKOptions(
            appUrl: "Your App URL", 
            cdnUrl: "Your CDN URL", 
            tenantId: "Your Tenant ID", 
            appId: "Your App ID", 
            testingMode: false, 
            logLevel: .debug, 
            consentsCheckInterval: 1800,
            subjectId: "Your Custom Subject Id",//this is optional,
      example: U01
            languageCode: "Your Language Code", //this is optional,
      example: enlocationCode: "Your Location Code" //this is optional,
      example: CA#US or US
      )
)
```

**Additional Information:**

- `logLevel` with possible values such as .debug, .info, .warning, .error
- `testingMode` with possible values such as true == .draft, or false == .live
- `consentsCheckInterval`: Checks the interval of consents in seconds
- (Optional) `subjectId`: Overrides the subject identity
  - Example: `U01`
- (Optional) `languageCode`: Overrides the language of the device.
  - Example: `en` or `fr`
- (Optional) `locationCode`: Overrides the location of the data subject.
  - Example: `CA#US` or `US`

> [!NOTE]
> **Note**
> 
> If you provide an invalid `subjectId`, the SDK logs the issue and reverts to the default `subjectId`, which is automatically generated by Securiti.

**Validity conditions for** `subjectId`

- It must not contain any **non-UTF-8** characters.
- It must be **alphanumeric**, though it can include special symbols like underscores.
- It must not contain whitespaces, angle brackets (`&lt;&gt;`), or similar characters.

Asynchronously uploads app consents to a specified URL using a `PostConsentsRequest` object.

> [!NOTE]
> **Note**
> 
> Securiti also lets you upload partial consents, enabling you to submit just the consents that have changed.

Example:

```swift
Task {
	var purposeConsents : [PurposeConsent] = []
	//prepare purpose consents
	for purpose in purposes {
		purposeConsents.append(PurposeConsent(purposeId:
 purpose.purposeId, consentStatus: purpose.consentStatus, timestamp:
 Date().currentTimeSeconds(), isEssential: purpose.disableOutPut ==
 true))
       }
       var permissionConsents : [PermissionConsent] = []
       //prepare permission consents
       for permission in permissions {
             permissionConsents.append(PermissionConsent(permission:
 permission.permissionId, consentStatus:
 permission.consentStatus,
 timestamp: Date().currentTimeSeconds()))
       }
       let device = await UIDevice.current.name
       let uuid = //get your User's UUID
	// build request
	let request = PostConsentRequest(uuid: uuid, appUUID:
 consentSDKOptions.appID, device: device, purposeConsents:
 purposeConsents, permissions: permissionConsents)
	//call upload Consents method
        await ConsentSDK.shared.uploadConsents(url:
 consentSDKOptions.appURL, request: request)
}
```

Use the following table to understand the **Model Classes**:

| Model Class | Parameter | Description |
| --- | --- | --- |
| `PurposeConsent` | `purposeId` | Expects an integer value |
| `consentStatus` | Expects a `ConsentStatus` type with possible values such as **granted**, **declined**, **withdrawn**, **not_determined** |
| `timestamp` | Expects a timestamp in seconds |
| `isEssential` | Expects a boolean (Bool) which determines whether it is an Essential purpose or not |
| `PermissionConsent` | `permission` | Expects a `PrivaciKey` Type which is any valid Permission in iOS such as **.cameraUsageDescription** |
| `consentStatus` | Expects a `ConsentStatus` type with possible values such as **granted**, **declined**, **withdrawn**, **not_determined** |
| `timestamp` | Expects a timestamp in seconds |
| `PostConsentRequest` | `uuid` | Expects a string with a data subject UUID that identifies the data subject uniquely |
| `appUUID` | Expects a String with app's UUID (located on the management portal) |
| `device` | Expects a String with the device name |
| `purposeConsents` | Expects a list of `PurposeConsent` type |
| `permissions` | Expects a list of `PermissionConsent` type |

#### `isReady(callback: (SDKStatus) → Void)`

Registers a callback to receive real-time updates about the SDK's status such as inProgress, available, notAvailable, etc.

Example:

```swift
//Usually set up when the app starts but you can declare it anywhere
and get realtime updates.
// you can receive every new state of ConsentSDK here in "state" 
object, and  // you can do whatever you want with the SDK based on
status
ConsentSDK.shared.isReady() { state in
      print(state.status())
       if state == .available {
            ConsentSDK.shared.presentConsentBanner()
       }
}
```

#### `getStatus() → SDKStatus`

Returns the current status of the SDK at that time.

Example

```swift
// you can check the Status of an SDK anytime and anywhere like this
// Note: does not return real-time consent status - it returns status
 at that // time of call.
if ConsentSDK.shared.getStatus() == .available {
    ConsentSDK.shared.presentConsentBanner()
}
```

#### `removeListeners()`

Removes any existing listeners or callbacks.

Example:

```swift
//you might want to call this to remove any existing "isReady" 
listeners //manually.
ConsentSDK.shared.removeListeners()
```

#### `getPermissionConsents() → [AppPermission]`

Asynchronously returns a list of app permissions with their consent statuses.

Example:

```swift
Task {
      let permissions : [AppPermission] = await
ConsentSDK.shared.getPermissionConsents()
	//use "permissions" list to populate the permissions list 
view
}
```

Use the following table to understand the `AppPermission` details:

| Parameter | Description | Type |
| --- | --- | --- |
| `id` | Permission ID from database | Integer |
| `name` | Name of the permission | String |
| `permissionId` | `permissionID` which is identifiable by iOS system. You can read its status from iOS system | PrivaciKey |
| `description` | Gives the translated description of the permission | `[String:String]` where key is language code and value is `description` |
| `group` | Gives the group of the permission | String |
| `groupId` | Gives the group id of the permission | Integer |
| `consentStatus` | Gives the current consent status of the permission | `ConsentStatus` |

#### `getPurposeConsents() → [Purpose]`

Asynchronously returns a list of purposes with their consent statuses.

Example:

```swift
Task {
      let purposes : [Purpose] = await
ConsentSDK.shared.getPurposeConsents()
	//use "purposes" list to populate the purposes list view
}
```

Use the following table to understand the `Purpose` details:

| Parameter | Description | Type |
| --- | --- | --- |
| `purposeId` | ID of the purpose | Integer |
| `purposeName` | Gives translated name of the purpose | `[String:String] `where key is language code and value is the `purposeName` |
| `purposeDescription` | Gives translated description of the purpose | `[String:String]` where key is language code and value is `purposeDescription` |
| `sdks` | Gives the list of SDKs associated with a purpose | [SDK] |
| `consentStatus` | Gives the current consent status of a permission | `ConsentStatus` |
| `disableOutPut` | Gives whether Opt-out is disabled for this purpose or not | Bool |
| `isATTMapped` | Gives whether this purpose is mapped with ATT or not | Bool |
| `attDescription` | gives translated description for ATT which is set on the management portal | `[String:String]` where key is language code and value is `attDescription` |

#### `setConsent(purpose: Purpose, consent: ConsentStatus) → Bool`

Sets the consent status for a given purpose and returns a Boolean indicating success or failure.

Example:

```swift
let result = ConsentSDK.shared.saveConsent(purpose: purpose, consent: 
consent)
```

Use the following table to understand `Purpose` and `ConsentStatus` details:

| **Parameter** | **Description** | **Type** |
| --- | --- | --- |
| `purpose` | Expects a `Purpose` whose consent is going to change | `Purpose` |
| `consentStatus` | Expects a `ConsentStatus` type with possible values such as granted, declined, withdrawn, or notDetermined | `ConsentStatus` |

#### `setConsent(permission: AppPermission, consent: ConsentStatus) → Bool`

Sets the consent status for a given permission, and returns a Boolean indicating success or failure.

Example:

```swift
let result = ConsentSDK.shared.saveConsent(permission: permission, 
consent: consent)
Note: permission expects a AppPermission type
```

Use the following table to understand the `AppPermission` details:

| Parameter | Description | Type |
| --- | --- | --- |
| `permission` | Expects an `AppPermission` type whose consent is going to change | `AppPermission` |
| `consent` | Expects a `ConsentStatus` type with possible values such as **granted**, **declined**, **withdrawn**, **notDetermined** | `ConsentStatus` |

#### `getBannerConfig() → BannerConfig?`

Asynchronously returns the consent banner configuration based on **location**, optionally with the main configuration.

Example:

```swift
Task {
	let bannerConfig : BannerConfig? = await 
ConsentSDK.shared.getBannerConfig()
         //Configure Consent Banner or Preference Center with 
"bannerConfig"
}
```

Use the following table to understand the `BannerConfig` details:

| Parameter | Description | Type |
| --- | --- | --- |
| `hideCloseButton` | Gives you whether the Close button is visible or not on the consent banner | Bool |
| `hideAcceptButton` | Gives you whether the Accept button is visible or not on the consent banner | Bool |
| `recordConsentUponAppStart` | Gives you whether SDK can record the default consents at the app start or not | Bool |
| `hideToggleForEssentialCategories` | Gives you whether to hide toggles for the Essential Purposes or not | Bool |
| `name` | Gives you the current consent banner config name which you configured from the management portal | String |
| `embedDSRPortalLink` | Gives you whether the DSR portal link is embedded or not | Bool |
| `dsrPortalLink` | Gives you a link to the DSR portal, which you can open up when data subjects decline the consents | String |
| `complianceType` | gives you the compliance type of the banner with possible values such as **noticeOnly**, **.optIn**, **.optOut** | `ComplianceType` |
| `bannerReappearanceTime` | Gives you the time when should the banner reappear in given format: [1 to 12] [month or year] example: 5 year | String |
| `privacyNoticeLink` | Gives you the privacy notice link to open when data subject clicks on Privacy Notice link | String |
| `accept` | Gives you the translated text for the Accept button | `[String:String]` where key is language code and value is translated `accept` text |
| `reject` | Gives you the translated text for Reject button | `[String:String]` where key is language code and value is translated `reject` text |
| `bannerText` | Gives you the translated text for the consent banner | `[String:String]` where key is language code and value is translated `bannerText` |
| `bannerHeading` | Gives you the translated text for the heading of consent banner | `[String:String]` where key is language code and value is translated `bannerHeading` text |
| `sdkTabHeading` | Gives you the translated text for the heading of SDK | `[String:String]` where key is language code and value is translated sdkTabHeading text |
| `privacyNoticeText` | Gives you the translated text for Privacy Notice button | `[String:String]` where key is language code and value is translated `privacyNoticeText` |
| `permissionsTabHeading` | gives you the translated text for the heading of Permissions tab | `[String:String]` where key is language code and value is translated `permissionsTabHeading` text |
| `preferenceCenterHeading` | gives you the translated text for the heading of the preference center | `[String:String]` where key is language code and value is translated `preferenceCenterHeading` text |
| `permissionsTabDescription` | Gives you the translated text for the description of Permissions tab | `[String:String]` where key is language code and value is translated `permissionsTabDescription` text |
| `preferenceCenterDescription` | Gives you the translated text for the description of the SDK tab | `[String:String]` where key is language code and value is translated `preferenceCenterDescription` text |
| `showPoweredBySecuritiLogo` | Gives you whether the Securiti logo is shown at the end of the list of Purpose/Permission or not | Bool |
| `showDescriptionTextWithPrefCenterToggle` | Gives you whether the Securiti logo is shown at the end of the list of Purpose/Permission or not | Bool |
| `paletteTheme` | Lets you know whether it's a system palette or not | Int, -1 if custom palette |
| `bannerPosition` | Gives you the position of the consent banner | `BannerPosition` with possible values such as **.center**, **.bottom**, etc. |
| `buttonShape` | Gives you the button shape to be used in consent banner and preference center | `ButtonShape` with possible values such as **.rounded**, **.square**, **.pill**, **.outlined**, etc. |
| `companyLogo` | Gives you the image link of organization's logo | String |
| `customPaletteTheme` | Gives you the colors in HEX format which are configured in the management portal | `CustomTheme` with color values such as **buttonBackground**, **buttonText**, **buttonBorder**, **bannerBackground**, **bannerText**, **bannerLinks**, **preferenceCenterFooterBackground**, **preferenceCenterFooterSelector** |

#### `removeConsents()`

Removes all previously given consents by the data subject.

Example:

```swift
ConsentSDK.shared.removeConsents()
```

Returns the consent status for a given privacy key.

Example:

```swift
let cameraPermissionConsent = ConsentSDK.shared.getConsent(privaciKey: 
.cameraUsageDescription)
//customize "cameraPermissionConsent" to suit
cameraPermissionConsent possible values: granted, declined, withdrawn, 
notDetermined
```

#### `getConsent(purposeId: Int) → ConsentStatus`

Returns the consent status for a given purpose ID.

Example:

```swift
let analyticsPurposeID = 1
let analyticsPurposeConsent = ConsentSDK.shared.getConsent(purposeId: 
analyticsPurposeID)
//customize "analyticsPurposeConsent" to suit
//example: if analyticsPurposeConsent != .granted then don't collect 
data for //analytics
analyticsPurposeConsent possible values: granted, declined, withdrawn, 
notDetermined
```

### `ConsentUI` Methods

#### (Optional) `registerFonts(heading: CustomFont, body: CustomFont, subHeading: CustomFont, subHeadingLight: CustomFont)`:

Registers custom fonts for use in the consent banner and preference center, ensuring your application's typography is consistent with the selected styles.

Example:

```swift
// Make sure Tenant's app must have ttf/otf files and registered them in 
their // iOS project
// Use this method to integrate custom font into ConsentUI SDK before 
loading // the consent banner or preference center
let isiPhone = UIDevice.current.userInterfaceIdiom == .phone
if isiPhone {
      ConsentSDK.shared.registerFonts(
        heading: CustomFont(name: "font's PostScript name", size: 16, 
type: .headline),
        body: CustomFont(name: "font's PostScript name", size: 13, type: 
.footnote),
        subHeading: CustomFont(name: "font's PostScript name", size: 13, 
type: .footnote),
        subHeadingLight: CustomFont(name: "font's PostScript name", 
size: 12, type: .caption2)
      )
    } else {
      ConsentSDK.shared.registerFonts(
        heading: CustomFont(name: "font's PostScript name", size: 24, 
type: .title2),
        body: CustomFont(name: "font's PostScript name", size: 18, type: 
.body),
        subHeading: CustomFont(name: "font's PostScript name", 
size: 18, type: .body),
        subHeadingLight: CustomFont(name: "font's PostScript name", 
size: 15, type: .footnote)
      )
    }
```

Use the following table to understand the `CustomFont` details:

| Parameter | Description |
| --- | --- |
| Name | Name of your registered font's PostScript |
| Size | Size of the desired font in points |
| Type | `Font.TextStyle` with possible values such as **.largeTitle**, **.title**, **.title2**, **.title3**, **.headline**, **.subheadline**, **.body**, **.callout**, **.footnote**, **.caption**, and **.caption2** |

> [!NOTE]
> **Note**
> 
> The font sizes demonstrated in the examples may appear differently on iOS devices, such as iPhones or iPads.

## Demo app preview

Below are the screenshots of the consent banner and preference center, demonstrating their appearance with custom font styles and sizes on **iPhone**, **iPad**, and **AppleTV** devices.

#### Consent Banner and Preference Center on iPhone (mobile) devices

![iOS-Consent-Banner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-274d9af6-3864-dee5-9afc-54f1e5990ba9.png)

![iOS-Preference-Center-SDK.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a013ab13-995a-7f45-e709-8c740120cd75.png)

![iOS-Preference-Center-Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-820a0519-ccb9-41f0-194d-92cbdaf564ce.png)

#### Consent Banner and Preference Center on iPad (tablet) device

![iPad-Consent-Banner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b351ffa-a697-0b9e-f2a4-45071de868e1.png)

![iPad-Preference-Center-SDK.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-255dd12c-42ad-f5b7-0ae2-7a23495b71e3.png)

![iPad-Preference-Center-Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37fe67ae-f152-04ea-4ef0-725add94f78a.png)

#### Consent Banner and Preference Center on AppleTV devices

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Frame 6.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Frame 1.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Frame 2.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Frame 3.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Frame 4.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Frame 5.png)

#### `(Optional) registerColors(colors: CustomColors)`

Registers and overrides the colors that are configured on the management portal.

Example:

```swift
ConsentSDK.shared.registerColors(colors: 
      CustomColors(
            buttonBackground: "#hexcode",
            buttonText: "#hexcode",
            buttonBorder: "#hexcode",
            bannerBackground: "#hexcode",
            bannerText: "#hexcode",
            bannerLinks: "#hexcode",
            preferenceCenterFooterBackground: "#hexcode",
            preferenceCenterFooterSelector: "#hexcode"
      )
)
```

#### `presentConsentBanner()`

Presents the consent banner if the application is opened for the first time and consents were not given by the data subject.

Example:

```swift
// ideally, you should call it only when SDK is available, otherwise it 
may not // work as expected
if ConsentSDK.shared.getStatus() == .available {
    ConsentSDK.shared.presentConsentBanner()
}
```

#### `presentPreferenceCenter()`

Presents the preference center to the data subjects, allowing them to manage their consent preferences.

Example:

```swift
// ideally, you should call it only when SDK is available, otherwise it 
may not // work as expected
if ConsentSDK.shared.getStatus() == .available {
    ConsentSDK.shared.presentPreferenceCenter()
}
```

### Additional Built-in Features

#### Set Up Right-to-Left (RTL) Languages

To support RTL languages in your project:

1. Ensure your application supports **RTL languages** and **regions** by configuring these aspects in the `Info.plist` file, as shown below.
2. Your device must have an RTL language set as the **default**. For instance, you must set your device language to Arabic to support it.

![1-setup-right-to-left.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fb2b63be-ad53-5109-5d97-d84490d1d947.png)

![2-setup-right-to-left.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-62253154-bb32-e505-259f-a4490dc6cde5.png)

![3-setup-right-to-left.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8bdbe388-beae-c632-c1be-d93ed022fabd.png)

![4-setup-right-to-left.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10bab958-a7da-268a-1496-91e43ccee8f8.png)

We have designed our Securiti SDK to be flexible, allowing your iOS developers to either use the provided UI components or to build their own using the core functionality provided by **ConsentCore**. The methods for managing **consents**, **permissions**, and **purposes** are asynchronous, which is typical for modern iOS development to avoid blocking the main thread.

To use this SDK, you would need to integrate it into your Xcode project, set up the SDK with their specific options, and then use the provided methods to manage data subject consents in accordance with privacy regulations.

Connected TV (CTV) refers to a television or television-connected device that connects to the internet and lets users access video content through apps or web-based services. CTV includes smart TVs and televisions connected to devices such as streaming devices, gaming consoles, and set-top boxes.

Over-the-Top (OTT) refers to video content delivered directly to users over the internet rather than through traditional cable, broadcast, satellite, or telecom services. Users can access OTT content through apps or web-based services on devices such as connected TVs, mobile devices, computers, and gaming consoles.

Apple's App Tracking Transparency (ATT) framework requires iOS apps to explicitly ask for a mobile app user's permission to track their activity across other mobile apps. The iOS app must display a standard popup before it accesses the Identifier for Advertisers (IDFA) for ad targeting. However, if the mobile app user denies permission, the app cannot access the IDFA.

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

## Related

- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
- [Using SDK Purposes](/using-sdk-purposes.md)
- [Using the SDK and Permissions Library](/using-the-sdk-and-permissions-library.md)
