---
title: "Using the SDK and Permissions Library"
slug: "using-the-sdk-and-permissions-library"
updated: 2026-09-08T10:09:25Z
published: 2026-09-08T10:09:25Z
canonical: "helpcenter.securiti.ai/using-the-sdk-and-permissions-library"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the SDK and Permissions Library

**Scenario**

As a Data Security Officer, you must track third-party SDKs across multiple mobile apps. Without centralized visibility, audits become slow and fragmented. Securiti’s SDK Library catalogs all scanned and manually added SDKs across platforms, with edit and sync controls. You gain a single point of control to manage SDK risks and stay compliant across your app ecosystem.

The SDK and Permissions Library functionality streamlines and simplifies your mobile app consent management by providing a centralized catalog of all SDK and Permissions across your Securiti tenant in one place. This library acts as a centralized hub for the management of SDKs and Permissions, and lets you streamline and simplify your consent management process.

If you have scanned your mobile app in the module, this library includes all findings from the scan, such as SDKs and permissions, along with any SDKs and permissions you add manually. This way it serves as a comprehensive catalog of all tracking technologies such as SDKs and Permissions across all your mobile apps, providing you with a single point of control.

> [!NOTE]
> **Note**
> 
> Only the following Securiti user roles in your tenant have permission to perform WRITE actions in the SDK Library, while all others have READ permissions:
> 
> - Super Admin
> - Org Admin
> - Module Owner

With the SDK Library, you can:

- Add new SDKs to the library.
- Edit existing SDKs (individually or in bulk).
- Remove SDKs (individually or in bulk) from mobile apps.
- Add SDKs to mobile apps (individually or in bulk).
- Sync existing scan-found SDKs with the latest updates from the backend database.
- Filter SDKs based on the platform they belong to such as **Android**, **iOS**, or both.
- Leverage an exclusive and detailed audit log of these actions.
- Build queries by combining the following properties to filter out SDKs that exist across all the mobile apps present in your Securiti tenant:
  - SDK Name
  - Mobile Application ID/Bundle ID
  - Platform
  - Purpose Name
  - Vendor
  - Mobile Apps
  - Source such as Scan and Manual
- Save built queries as **Saved Views** for later use. For instance, once you save a query, it gets saved as a Saved View with the filters you applied and the results that were filtered out. This ensures you can access commonly used searches from the Saved View section, instead of repeatedly searching for SDKs with specific and occasionally used properties.

## Using the top-level filter

With the top-level filter, you can combine different properties of SDKs and Permissions then filter them out. The top-level filter takes precedence and dictates the behavior of other filters below it, filtering all data from the top down, affecting the result values of both metric tiles and the grid view.

To use the top-level filter:

1. From the upper left corner of the SDK & Permissions Library dashboard, click **+**.
2. On the popup, either search by property name of an SDK or Permissions, or use the out-of-the-box listed properties.

For instance, if you want to filter out SDKs based on the platform category (property), click **Platform**, and from the list of values on the right side, mark the checkbox next to platform categories which you filter the SDKs from. Once selected, near the bottom of the popup, click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Platform-filter-iOS.png)
3. Repeat the same step for other properties to suit your search needs. Once you apply all required properties, press **Enter**. Securiti builds a query based on your selected properties, and displays the filtered results.

> [!NOTE]
> **Note**
> 
> The top-level filter takes precedence over all other filters, and if there is an overlap of similar filters, Securiti disables the same filter other than the top-level filter. For instance, in the following screenshot, the overlap of **Platform** filters occur, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Expression-Builder-Admonition.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**.

## Saving searched views

Securiti lets you save your built queries as **Saved Views** for later use. For instance, once you save a query, it gets saved as a Saved View with the filters you applied and the results that were filtered out. This ensures you can access commonly used searches from the Saved View section, instead of repeatedly searching for SDKs and Permissions with specific and occasionally used properties.

To save a built query as a saved view:

1. After filtering the SDKs and Permissions from the top-level filter, from the upper right corner, click **Save View**, as shown below.

![Save-view.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9dac28ce-890e-08e2-2b7e-0cddfe63ae38.png)
2. On the Save View side panel:
  1. Select the Group Name or click **Add New** to create a new group name. Type the group name, and press **Enter**.
  2. Enter a name for the view that you want to save.
  3. Enter the description for the view you want to save.
  4. Near the bottom of the side panel, click **Save View**, as shown below.

![Saved-view-details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-429c2773-6b1b-4256-d31c-42f5de6bf43b.png)

Once done, Securiti shows you a success message near the upper right side.
3. To view your saved view, from the upper right corner, click **Saved Views**, as shown below. ![Saved-Views.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2768da32-20a8-a82b-d628-9f66539379ac.png)

## Adding a new SDK

Securiti lets you easily add new SDKs to the SDK Library. You can add as many SDKs as needed to ensure accurate tracking and categorization across your mobile apps. This functionality provides full control over the management of SDKs.

Use the table below to understand potential use cases for adding new SDKs to the SDK Library:

| Use Case | Description |
| --- | --- |
| Undetected SDKs during mobile app scans | If certain SDKs are not detected during the mobile app scan, you can manually add them to the SDK Library instead of raising a support request. |
| New third-party SDK integrations | When integrating a new third-party SDK such as analytics, advertising, push notifications, etc., you can add it to the SDK Library for tracking and consent management. |
| Custom SDKs for internal use | If your mobile app includes proprietary SDKs, you can register them in the SDK Library to maintain transparency and control over data processing. |
| Regulatory compliance updates | If new regulations require additional SDK disclosures or modifications in consent handling, you can add or update SDKs to stay compliant. |
| Changes in SDK vendors | If you switch from one SDK provider to another such as migrating from one analytics or advertising SDK to a different one, you can add the new SDK and manage its properties. |
| Missing SDKs from initial implementation | If an SDK was not documented or added when first integrating your mobile app with Securiti, you can manually add it later to ensure it appears in consent management workflows. |

To add a new SDK to the library:

1. In Securiti, open **Mobile App Management**, and choose **Mobile App Consent Configurations > SDK & Permissions Library**.
2. On the **SDK & Permissions Library** page, from the upper right corner, click **+ Create SDK**.
3. On the **Create a New SDK** popup, fill out the details for:

| Field | Description |
| --- | --- |
| Platform | From the menu, select one platform for which you are adding this new SDK. For instance, either select Android or iOS. |
| SDK Name | Add an appropriate name for the SDK such as Google Firebase, Marketo Schema, etc. |
| Application ID or Product Bundle ID | Add the unique ID for the app associated with this SDK. For instance: - For Android, provide the Application ID such as `com.platform-name.gsm.vision`. - For iOS, provide the Product Bundle ID such as `com.platform-name.app`. |
| Vendor | Add the name of the vendor, such as Google, Apple, etc., from which this SDK is originally sourced. |
| Release Date | Select the release date using the calendar widget. |
| Version | Add the version number of the SDK. |
| Developer URL | Add the link to the URL of the SDK developer’s website. |
| License | Add the license type for the SDK. For instance, **Apache 2.0**, **MIT**, or **GPL**, etc. |
| Purpose Name | Select an appropriate SDK Purpose name from the menu. For instance, choose the one that best matches the purpose of this SDK. |
| Category | From the menu, select one SDK Purpose category to organize the SDK. |
| Description | Add some description to clearly specify the purpose of the SDK. |
4. Near the bottom of the popup, click **Add**.
5. On the confirmation popup, click **Dismiss** to add the SDK to the library only. If you want to apply the SDK to your mobile app, click **Yes, Apply to App(s)**.
6. On the **Add SDK to Mobile App(s)** popup, mark the checkboxes next to the apps where you want to add the SDK, as shown below. Securiti shows only the apps that were successfully scanned. Enable the **Show selected apps only** toggle to review your selection before proceeding.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-SDK-to-Mobile-App-popup.png)
7. Once done, near the bottom of the popup, click **Add SDK**.
8. Securiti displays a success popup with instructions for reflecting the newly added SDK in your live apps. Click **Got it**, as shown below, then go to your mobile apps and deploy them.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Changes-Applied.png)

> [!WARNING]
> **Important**
> 
> This step is crucial. Without deployment, the newly added SDK stays in the SDK Library and does not appear in the consent preference center of your live app(s). You must redeploy the mobile app configuration(s) for each app individually for this change to take effect in your live apps.

## Syncing SDKs with latest updates

Securiti lets you sync scan-detected SDKs with the latest updates from its proprietary Knowledge Base. When an update is available for an SDK, an orange refresh icon appears, indicating that Securiti's Knowledge Base (KB) team has updated it in the backend. Securiti's KB team continuously researches and updates SDK metadata, and syncing ensures your SDK always uses the latest information.

To sync the SDK with the latest changes:

1. From the upper right corner of the SDK Library section, click **Sync All Changes**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Sync-All-Changes-button.png)
2. On the confirmation popup, review the instructions and click **Sync**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Sync-popup.png)

## Editing SDKs individually

Securiti lets you edit SDK(s) by modifying their values, including vendor name, release date, version, developer URL, license, purpose name, and category. You can also update permissions or adjust settings to suit.

To edit a single SDK:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent Configurations > SDK & Permissions Library**.
2. From the right side of the SDK that you want to edit, click **Options** (three dots) and select **Edit**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Edit.png)
3. On the **Edit an SDK** popup, modify the required values. Once the Save Changes button becomes active, click **Save Changes**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Edit-An-SDK-popup.png)

## Editing SDKs in bulk

> [!WARNING]
> **Important**
> 
> Securiti does not let you use bulk actions when editing multiple SDKs if you select SDKs from both platform types, such as Android and iOS. You must select multiple SDKs of the same platform type to use bulk actions.

To edit SDKs in bulk:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent Configurations > SDK & Permissions Library**.
2. From the left side, mark the checkboxes next to the name of SDKs that you want to edit. Then, near the bottom of the page, from the floating tab, click **Edit**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bulk-Edit.png)
3. On the **Bulk Edit SDK** popup, click **Update** next to the fields, and from the menu, select the updated value. Do this for all selected SDKs. Once done, near the bottom of the popup, click **Save Changes**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bulk-Edit-SDK-popup.png)

## Removing SDKs from apps individually

Using the SDK Library, you can remove SDKs from your mobile apps to manage them effectively. This is useful for removing SDKs that are no longer in use, deprecated, or no longer needed. The removal option helps you keep your mobile apps optimized and up to date.

To remove a single SDK:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent Configurations > SDK & Permissions Library**.
2. From the right side of the SDK that you want to remove, click **Options** (three dots) and select **Remove from App(s)**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Remove-from-App.png)
3. On the **Remove SDK from App(s)** popup, search for the app name or mark the checkbox next to the app(s) from which you want to remove the SDK. Once done, click **Remove SDK**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Remove-SDK-from-App-popup.png)

> [!WARNING]
> **Important**
> 
> Removing an SDK from an app keeps it in the library but removes it from the mobile app's consent banners and preference centers only after you redeploy its configurations.

## Removing SDKs from apps in bulk

> [!WARNING]
> **Important**
> 
> - Securiti does not let you use bulk actions when removing multiple SDKs from mobile apps if you select SDKs from both platform types, such as Android and iOS. You must select multiple SDKs of the same platform type to use bulk actions.
> - Securiti only lists mobile apps that match the platform type of the selected SDKs when removing SDKs from apps. For instance, if you select multiple iOS SDKs, Securiti lists only iOS apps, not a mix of iOS and Android apps.

To remove SDK in bulk:

1. In Securiti, open Mobile App Consent Management, and choose **Mobile App Consent Configurations > SDK & Permissions Library**.
2. From the left side, mark the checkboxes next to the SDK name that you want to remove. Then, near the bottom of the page, from the floating tab, click **Remove from App(s)**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Remove-from-App-button.png)
3. On the **Remove SDK from App(s)** popup, search for the SDK name that you want to remove and then mark the checkbox next to the app(s) from which you want to remove the SDK. Once selected, click **Remove SDK(s)**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Remove-SDK-from-App.png)

## Adding an SDK to app(s)

If an SDK exists only in the SDK library and is not linked to any mobile apps, you can add it to one or multiple apps.

To add an SDK to one or multiple apps:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent Configurations > SDK & Permissions Library**.
2. From the right side of the SDK that you want to add to any app(s), click **Options** (three dots), and select **Add to App(s)**.
3. On the **Add SDK to Mobile App(s)** popup, mark the checkboxes next to the apps where you want to add the SDK, as shown below. Securiti shows only the apps that were successfully scanned. Enable the **Show selected apps only** toggle to review your selection before proceeding.

> [!WARNING]
> **Important**
> 
> Securiti only lists mobile apps that match the platform type of the selected SDK when adding it to the app(s). For instance, if you select an iOS SDK to add to app(s), Securiti lists only iOS apps, not a mix of iOS and Android apps.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-SDK-to-Mobile-App.png)
4. Once done, near the bottom of the popup, click **Add SDK**.
5. Securiti displays a success popup with instructions for reflecting the newly added SDK in your live apps. Click **Got it**, as shown below, then go to your mobile apps and deploy them. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-to-App-Changes-Applied.png)

## Adding SDKs to app(s) in bulk

If SDKs exist only in the SDK library and are not linked to any mobile apps, you can add them to one or multiple apps in bulk.

To add SDKs to one or multiple apps in bulk:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent Configurations > SDK & Permissions Library**.
2. From the left side, mark the checkboxes next to the SDKs that you want to add to any app(s). Then, near the bottom of the page, from the floating tab, click **+ Add to App(s)**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Bulk-Add-to-App.png)
3. On the **Add SDK to Mobile App(s)** popup, mark the checkboxes next to the apps where you want to add these SDKs, as shown below. Securiti shows only the apps that were successfully scanned. Enable the **Show selected apps only** toggle to review your selection before proceeding.

> [!WARNING]
> **Important**
> 
> Securiti only lists mobile apps that match the platform type of the selected SDKs when adding them to the apps. For instance, if you select iOS SDKs to add to apps, Securiti lists only iOS apps, not a mix of iOS and Android apps.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-SDK-to-Mobile-App-Bulk.png)
4. Once done, near the bottom of the popup, click **Add SDK**.
5. Securiti displays a success popup with instructions for reflecting the newly added SDK in your live apps. Click **Got it**, as shown below, then go to your mobile apps and deploy them. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-to-App-Changes-Applied-Bulk.png)

## Related

- [Using SDK Purposes](/using-sdk-purposes.md)
- [Using the Permissions Library](/using-the-permissions-library.md)
