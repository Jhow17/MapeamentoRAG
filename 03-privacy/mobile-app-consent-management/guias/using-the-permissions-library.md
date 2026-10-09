---
title: "Using the Permissions Library"
slug: "using-the-permissions-library"
updated: 2026-09-03T09:24:11Z
published: 2026-09-03T09:24:11Z
canonical: "helpcenter.securiti.ai/using-the-permissions-library"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Permissions Library

**Scenario**

As a Data Compliance Officer, you need to monitor the permissions your apps request from mobile app users, including those not detected during scans. For instance, when an app update introduces a new permission through an SDK, it can be difficult to track manually. Monitoring these permissions across updates and SDKs without a centralized view is prone to error. Securiti Permissions Library centralizes permission data, letting you add or update entries and keep metadata synchronized. This helps you maintain complete, auditable control over permissions across all your apps.

The Permissions Library lets you manually add, track, and update app permissions to ensure compliance and transparency. It helps **manage undetected permissions**, **integrate third-party** and **proprietary SDKs**, **align with regulatory updates**, and **reflect permission changes** due to **app updates** or **missing initial implementations**.

If you have scanned your mobile app in the module, this library includes all findings from the scan, such as automatically detected Permissions and those you add manually. In this way, it serves as a comprehensive catalog of tracking technologies across all your mobile apps, giving you a single point of control.

> [!NOTE]
> **Note**
> 
> Only the following Securiti user roles in your tenant have permission to perform WRITE actions in the Permissions Library, while all others have READ permissions:
> 
> - Super Admin
> - Org Admin
> - Module Owner

With the Permissions Library, you can perform CRUD and other actions such as:

- Create new permissions.
- Add Permissions to SDKs or mobile apps (individually or in bulk).
- Edit existing Permissions (individually or in bulk).
- Remove Permissions from SDKs or mobile apps.
- Sync existing scan-found Permissions with the latest updates from the backend database.
- View full metadata details of Permissions.
- Filter Permissions based on the platform they belong to such as Android, iOS, or both.
- Leverage an exclusive and detailed audit log of these actions.
- Build queries by combining the following properties to filter out Permissions that exist across all the mobile apps present in your Securiti tenant:
  - Permission Name
  - Permission ID
  - Permissions Group such as Camera, Location, Microphone, SMS, etc.
  - Platform such as Android or iOS
  - SDKs
  - Mobile Apps
  - Source such as Scan and Manual
- Save built queries as **Saved Views** for later use. For instance, once you save a query, it gets saved as a Saved View with the filters you applied and the results that were filtered out. This ensures you can access commonly used searches from the Saved View section, instead of repeatedly searching for SDKs with specific and occasionally used properties.

![Permissions-CRUD-Actions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-274ab2c5-1b37-50e3-035a-d51b9d20cff7.png)

![Permissions-Filters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07e98968-da5e-7486-f059-695730dbf9ea.png)

## Using the top-level filter

With the top-level filter, you can combine different properties of Permissions then filter them out. The top-level filter takes precedence and dictates the behavior of other filters below it, filtering all data from the top down, affecting the result values of both metric tiles and the grid view.

To use the top-level filter:

1. From the upper left corner of the SDK & Permissions Library dashboard, click **+**.
2. On the popup, either search by property name of an SDK or Permissions, or use the out-of-the-box listed properties.

For instance, if you want to filter out SDKs based on the platform category (property), click **Platform**, and from the list of values on the right side, mark the checkbox next to platform categories which you filter the SDKs from. Once selected, near the bottom of the popup, click **Apply**, as shown below.

![Top-level-Filter-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f04f586-51dc-1133-84b9-2ee194f27fe8.png)
3. Repeat the same step for other properties to suit your search needs. Once you apply all required properties, press **Enter**. Securiti builds a query based on your selected properties, and displays the filtered results.

> [!NOTE]
> **Note**
> 
> The top-level filter takes precedence over all other filters, and if there is an overlap of similar filters, Securiti disables the same filter other than the top-level filter. For instance, in the following screenshot, the overlap of **Platform** filters occur, as shown below.
> 
> ![Top-level-Filter-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4426d50c-9144-87b2-1850-b3b753065314.png)

- To clear the top-level filter, from the upper right corner, click **Clear Search**.

## Saving searched views

Securiti lets you save your built queries as **Saved Views** for later use. For instance, once you save a query, it gets saved as a Saved View with the filters you applied and the results that were filtered out. This ensures you can access commonly used searches from the Saved View section, instead of repeatedly searching for Permissions with specific and occasionally used properties.

To save a built query as a saved view:

1. After filtering the SDKs and Permissions from the top-level filter, from the upper right corner, click **Save View**, as shown below.

![Saving-Searched-Views-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4016822-3b6c-9fd0-24f5-17103fe295d2.png)
2. On the Save View side panel:
  1. Select the Group Name or click **Add New** to create a new group name. Type the group name, and press **Enter**.
  2. Enter a name for the view that you want to save.
  3. Enter the description for the view you want to save.
  4. Near the bottom of the side panel, click **Save View**, as shown below.

![Saving-Searched-Views-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4738b769-9443-4680-aa1f-e62634a7794e.png)

Once done, Securiti shows you a success message near the upper right side.
3. To view your saved view, from the upper right corner, click **Saved Views**, as shown below. ![Saving-Searched-Views-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-717f414e-d969-7f43-7012-0a7dc8899a55.png)

## Creating a new Permission and adding it to SDK(s) or App(s)

Securiti lets you easily create new Permissions from the Permissions Library. Once you create a new Permission, you can either add it to SDK(s) and then apply those updated SDK(s) to your mobile apps, or directly add the Permission to your scanned mobile apps. You can create as many Permissions as needed to ensure accurate tracking and categorization across your mobile apps. This functionality provides full control over the management of Permissions.

Use the table below to understand potential use cases for creating and adding new Permissions to the Permissions Library:

| Use Case | Description |
| --- | --- |
| Undetected permissions during mobile app scans | If certain permissions are not detected during the mobile app scan, you can manually add them to the Permissions Library instead of raising a support request. |
| New third-party SDK integrations requiring permissions | When integrating a new third-party SDK that requests specific permissions such as **location access**, **microphone**, **camera**, **contacts**, etc., you can add these permissions to the Permissions Library for tracking and consent management. |
| Custom permissions for proprietary SDKs | If your mobile app includes proprietary SDKs that require special permissions, you can register them in the Permissions Library to maintain transparency and ensure compliance. |
| Regulatory compliance updates | If new regulations mandate additional disclosures or consent requirements for specific permissions, you can add or update them in the Permissions Library to align with compliance standards. |
| Changes in permission usage due to app updates | If a mobile app update modifies permission usage such as adding new permissions or removing previously required ones, you can update the Permissions Library to reflect these changes accurately. |
| Missing permissions from initial implementation | If a permission was not documented or added when first integrating your mobile app with Securiti, you can manually add it later to ensure proper consent tracking. |

The table below provides real-world examples that help you understand how and when to add new Permissions to the Permissions Library:

| Example | Description |
| --- | --- |
| Avoiding service disruptions from undetected permissions | A global e-commerce platform updates its mobile app, adding a new in-app voice search feature powered by a speech recognition SDK. The update introduces a **microphone access permission** that was not automatically detected during the initial app scan. Without adding this permission manually to the Permissions Library, mobile app users may experience unexpected consent prompts or functionality failures. By leveraging the Permissions Library functionality, customers can ensure that **all permissions are accurately listed**, providing a seamless app user experience while maintaining transparency in data collection. |
| Ensuring compliance with evolving privacy regulations | A mobile banking app integrates a third-party fraud detection SDK that requires device location and network state permissions. Due to evolving privacy regulations, the mobile app's compliance team needs to ensure that all permissions are properly tracked and disclosed. With the Permissions Library, you can manually create the permission, then add it to the SDK or directly to the app, and categorize the permissions, ensuring they appear in consent flows and regulatory reports, without waiting for an automatic detection update. This proactive control helps them maintain compliance and avoid regulatory penalties. |

To add a new Permission to the library:

1. In Securiti, open **Mobile App Management**, and choose **Mobile Consent > SDK & Permissions Library**.
2. On the SDK & Permissions Library page, from the upper right corner, click **+ Create Permission**.
3. On the **Create a New Permission** popup, fill out the details for:

| Field | Description |
| --- | --- |
| Platform | From the menu, select one platform for which you are adding this new Permission. For instance, either select Android or iOS. |
| Permission Name | Add an appropriate name for the Permission such as Microphone, Camera, Apple Face ID, or other relevant Permission names. |
| Permission Group | From the menu, select the group that most accurately represents the purpose of this Permission. |
| Permission ID | Enter a unique identifier for this Permission to help track and reference it across systems. For instance: `NSBluetoothAlwaysUsageDescription`. |
| Description | Add some description to clearly specify the purpose of this Permission. |
4. From the **Add Permission to App(s)** section, click one of the following cards to suit:

| Card | Description |
| --- | --- |
| Via SDK(s) | Selecting this option adds the Permission to the SDK(s). Afterward, you can apply the updated SDK(s) with the new Permission to your mobile apps. Once completed, you must redeploy your app configuration(s) to apply the changes in your live app(s). This ensures that the app’s consent banner and preference center reflect the new Permission. |
| Directly to App(s) | Selecting this option directly adds the Permission to the app(s). Afterward, you must redeploy your app configuration(s) to apply the changes in your live app(s). This ensures that the app’s consent banner and preference center reflect the new Permission. |
| Do not Apply | Selecting this option adds the Permission as a free-floating entry in the library, without applying it to any app(s). This lets you modify the Permission details without affecting the live app(s) at this time. |

![Create-Permission-Card-Selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95905303-d643-d76f-0818-e0613afe0abc.png)
5. If you selected **Via SDK(s)** and clicked **Create Permission**:
  1. On the **Add Permission to SDK(s)** popup, mark the checkboxes next to the SDK(s) in which you want to add this newly created Permission, as shown below. Securiti shows only the SDKs that were successfully scanned.

![Add-Permission-to-SDKs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e24eac53-1809-6783-dc03-8541226fe9cd.png)
  2. Enable the **Show selected SDK(s) only** toggle to review your selection before proceeding.
  3. Near the bottom of the popup, click **Apply**.
  4. On the confirmation popup, either click **Dismiss** if you want to end this action here, or click **Yes, Apply to App(s)**, as shown below.

![Apply-Permission-to-Apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bdfd2eab-a282-c928-d193-0cd09c331b06.png)
  5. On the **Apply SDK Updates to App(s)** popup, mark the checkboxes next to the apps where you want to add the updated SDKs. Securiti shows only the apps that were successfully scanned.
  6. Near the bottom of the popup, from the floating tab, click **Apply Update**, as shown below.

![Apply-Update.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4dcd4228-0d54-280f-23d8-f5bc80ea01d5.png)
  7. Do this for all the SDKs in which you added the Permission.
  8. Once done, on the **Changes applied** popup, click **Got it**, as shown below, then go to your mobile apps and deploy them. ![Applied-to-Apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f25608aa-9f12-75fa-7e5f-f1053ca9e103.png)

Securiti displays a success popup with instructions for reflecting the newly added Permission in your live apps.

> [!WARNING]
> **Important**
> 
> This step is crucial. Without deployment, the newly added Permission stays in the SDK(s) and does not appear in the consent preference center of your live app(s). You must redeploy the mobile app configuration(s) for each app individually for this change to take effect in your live apps.
6. If you selected **Directly to App(s)** and clicked **Create Permission**:
  1. On the **Add Permission to App(s)** popup, mark the checkboxes next to the apps where you want to add the Permission, as shown below. Securiti shows only the apps that were successfully scanned. ![Add-Permission-to-Apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b65005a-7ec6-ee0b-72e1-e28fefedd382.png)
  2. Enable the **Show selected apps only** toggle to review your selection before proceeding.
  3. Once done, near the bottom of the popup, click **Add**.
  4. Once done, on the **Changes applied** popup, click **Got it**, as shown below, then go to your mobile apps and deploy them.

Securiti displays a success popup with instructions for reflecting the newly added Permission in your live apps.

> [!WARNING]
> **Important**
> 
> This step is crucial. Without deployment, the newly added Permission stays in the SDK(s) and does not appear in the consent preference center of your live app(s). You must redeploy the mobile app configuration(s) for each app individually for this change to take effect in your live apps.
7. If you selected **Do not Apply** and clicked **Create Permission**, Securiti creates the Permission, adds it to the Permissions Library, and shows you a success message near the upper right corner of the page.

## Syncing Permissions with latest updates

Securiti lets you sync scan-detected Permissions with the latest updates from its proprietary Knowledge Base. When an update is available for a Permission, an orange refresh icon appears, indicating that Securiti's Knowledge Base (KB) team has updated it in the backend. Securiti's KB team continuously researches and updates SDK metadata, and syncing ensures your Permissions always use the latest information.

To sync the Permission with the latest changes:

1. From the upper-right corner of the Permissions Library section, click **Sync All Changes**, as shown below.

![Sync-Permission-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a83768c2-f492-2f38-113c-0915c4514597.png)
2. On the confirmation popup, review the instructions and click **Sync**, as shown below. ![Sync-Permission-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7d436576-7798-c1cf-a4a0-912dfb4d4ddd.png)

## Editing Permissions individually

Securiti lets you edit Permission(s) by modifying their values, including permission name, permission group, and description. You can also update permissions or adjust settings to suit.

To edit a single SDK:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile Consent > SDK & Permissions Library**.
2. From the right side of the Permission that you want to edit, click **Options** (three dots) and select **Edit**, as shown below.

![Edit-Permission-Individually-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a4bfda6d-b37a-7bd1-def9-311d0ee9c36d.png)
3. On the **Edit Permission** popup, modify the required values. Select the appropriate card to choose how you want to apply the updated Permission to your apps. Once the Save Changes button becomes active, click **Save Changes**, as shown below.

![Edit-Permission-Individually-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e48a8443-806b-9fee-37d4-036fd854aea2.png)
4. If you selected **Apply Updates to App(s)** and clicked **Save Changes**:
  1. On the **Apply Permission Updates to App(s)** popup, mark the checkboxes next to the apps where you want to add the updated Permission. Securiti shows only the apps that were successfully scanned.
  2. Enable the **Show selected apps only** toggle to review your selection before proceeding.
  3. Near the bottom of the popup, click **Apply**.
  4. Once done, on the **Changes applied** popup, click **Got it**, then go to your mobile apps and deploy them.

Securiti displays a success popup with instructions for reflecting the updated Permission in your live apps.

> [!WARNING]
> **Important**
> 
> This step is crucial. Without deployment, the updated Permission stays in the configuration of mobile app(s) configuration, and does not appear in the consent preference center of your live app(s). You must redeploy the mobile app configuration(s) for each app individually for this change to take effect in your live apps.

## Editing Permissions in bulk

> [!WARNING]
> **Important**
> 
> Securiti does not let you use bulk actions when editing multiple Permissions if you select Permissions from both platform types, such as Android and iOS. You must select multiple Permissions of the same platform type to use bulk actions.

To edit Permissions in bulk:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile Consent > SDK & Permissions Library**.
2. From the left side, mark the checkboxes next to the names of the Permissions that you want to edit. Then, near the bottom of the page, from the floating tab, click **Edit**, as shown below.

![Edit-Permissions-Bulk-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fd15cb16-bde1-c514-7b30-5ed95788c182.png)
3. On the **Bulk Edit Permission** popup, click **Update** next to the fields, and from the menu, select the updated value. Do this for all selected Permissions. Once done, near the bottom of the popup, click **Save Changes**, as shown below. ![Edit-Permissions-Bulk-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31f95db5-5f15-f7d7-1bcb-47414fa8c0f1.png)

## Removing Permissions from SDK(s) and app(s) individually

Using the Permissions Library, you can remove Permissions from the SDK(s) and also from the mobile apps to manage them effectively. This is useful for removing Permissions that are no longer in use, deprecated, or no longer needed. The removal option helps you keep your mobile apps optimized and up to date.

To remove a Permission from SDK(s) and app(s):

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile Consent > SDK & Permissions Library**.
2. From the right side of the Permission that you want to remove, and click **Options** (three dots), as shown below.

![Remove-permission-from-SDK_s_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-42bc102f-92ec-b458-639c-dee9f85e6a2f.png)
3. From the menu, select **Remove from SDK(s)** if you wish to remove the Permission that is associated with an SDK.
  1. On the **Remove Permission from SDKs(s**) popup, mark the checkboxes next to the SDKs where you want to remove the Permission from.
  2. Enable the **Show selected SDK(s) only** toggle to review your selection before proceeding.
  3. Near the bottom of the popup, click **Remove**.
  4. On the confirmation popup, either click **Dismiss** if you want to end this action here, or click **Yes, Apply to App(s)**.
  5. On the **Apply SDK Updates to App(s)** popup, mark the checkboxes next to the apps which you want to remove the Permission from. Securiti shows only the apps that were successfully scanned, as shown below.

![Choose-app_s_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aba16943-3315-aa32-a599-8c2d6531f66e.png)
  6. Near the bottom of the popup, from the floating tab, click **Apply Update**, as shown below.

![Apply-SDK-updates-to-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5eab250-d320-f3e8-1ed0-b9573a67bddf.png)
  7. Do this for all SDKs you want to remove the Permission from.
  8. Once done, on the **Changes applied** popup, click **Got it**, as shown below, then go to your mobile apps and deploy them.

![Applied-to-Apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f25608aa-9f12-75fa-7e5f-f1053ca9e103.png)

Securiti displays a success popup with instructions for reflecting the removal of Permission from your live apps.

> [!WARNING]
> **Important**
> 
> - Removing a Permission from the SDK(s) keeps it in the library, but removes it from the app's consent banners and preference centers only after you redeploy its configurations.
> - This step is crucial. Without deployment, the removed Permission stays in the SDK(s) associated with the mobile app(s), and still appears in the consent preference center of your live app(s). You must redeploy the mobile app configuration(s) for each app individually for this change to take effect in your live apps.
4. From the menu, select **Remove from App(s)** if you wish to remove the Permission directly from the mobile app, as shown below.

![Remove-permission-from-App_s_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6652afd-1a23-9110-aa38-d269fdff97e9.png)
  1. On the **Remove Permission from App(s**) popup, mark the checkboxes next to the apps where you want to remove the Permission from. Securiti shows only the apps that were successfully scanned.
  2. Enable the **Show selected apps only** toggle to review your selection before proceeding.
  3. Near the bottom of the popup, click **Remove Permission**, shown below.

![Remove-permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d80976f0-9483-3ab6-7af5-58a59ad65b9b.png)
  4. Once done, on the **Changes applied** popup, click **Got it**, then go to your mobile apps and deploy them.

Securiti displays a success popup with instructions for reflecting the removal of Permission from your live apps.

> [!WARNING]
> **Important**
> 
> - Removing a Permission from the mobile app(s) keeps it in the library, but removes it from the app's consent banners and preference centers only after you redeploy its configurations.
> - This step is crucial. Without deployment, the removed Permission stays in the mobile app(s), and still appears in the consent preference center of your live app(s). You must redeploy the mobile app configuration(s) for each app individually for this change to take effect in your live apps.

## Adding Permissions to SDK(s) in bulk

If Permissions exist only in the Permissions Library and are not linked to any SDKs, you can add them SDK(s) in bulk.

> [!NOTE]
> **Note**
> 
> When adding Permissions to SDK(s), Securiti lists only SDKs that match the platform of the selected Permissions. For instance, if you select Android Permissions, Securiti lists only Android SDKs.

To add Permissions to SDK(s) in bulk:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile Consent > SDK & Permissions Library**.
2. Mark the checkboxes next to the Permissions that you want to add to any SDK(s), and from the floating tab, click **+ Add to SDK(s)**, as shown below.

![Add-to-SDK_s_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d088aa48-3a54-1deb-6369-6afc9a192ca0.png)
3. On the **Add Permission(s) to SDK(s)** popup, mark the checkboxes next to the SDKs to which you want to add the selected Permissions.
4. Enable the **Show selected SDK(s) only** toggle to review your selection before proceeding.
5. Near the bottom of the popup, click **Add**, as shown below.

![Add-Permission_s_-to-SDK_s_-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-27cc048f-354e-d2ee-5280-1fdca57055f3.png)

> [!WARNING]
> **Important**
> 
> Securiti only lists mobile apps that match the platform type of the selected Permissions when adding them to app(s). For instance, if you select Permissions belonging to the iOS platform to add to app(s), Securiti lists only iOS apps, not a mix of iOS and Android apps.
6. On the confirmation popup, either click **Dismiss** if you want to end this action here, or click **Yes, Apply to App(s)**, as shown below.

![Apply-to-App_s_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f34fed2-cadb-06f3-d49d-bc682dd1c524.png)
7. On the **Apply SDK Updates to App(s)** popup, mark the checkboxes next to the apps to which you want to add the updated SDKs. Securiti shows only the apps that were successfully scanned, as shown below.

![Apply-SDK-Updates-to-App_s_-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-586d530d-a848-db67-3cd6-390a07308fb1.png)
8. Near the bottom of the popup, from the floating tab, click **Apply Update**, as shown below.

![Apply-update.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e9422e7-07fd-13a6-51d7-f9c25fb44a17.png)
9. Do this for all updated SDKs you want to add to the apps.
10. Once done, on the **Changes applied** popup, click **Got it**, as shown below, then go to your mobile apps and deploy them.

![Applied-to-Apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f25608aa-9f12-75fa-7e5f-f1053ca9e103.png)

Securiti displays a success popup with instructions for reflecting the updated SDKs in your live apps.

> [!WARNING]
> **Important**
> 
> - Adding Permissions to the SDK(s) stores them there, but they appear in the app’s consent banner and preference center only after you redeploy the app’s configurations.
> - This step is crucial. Without deployment, the newly added Permissions remain only in the SDK(s) linked to your mobile app(s) and do not appear in the consent preference center of your live apps. You must redeploy the configuration for each app individually for the changes to take effect.

## Adding Permissions to app(s) in bulk

If Permissions exist only in the Permissions Library and are not linked to any apps, you can add them to your mobile app(s) in bulk.

> [!NOTE]
> **Note**
> 
> Securiti lists only mobile apps that match the platform type of the selected Permissions when adding them to app(s). For instance, if you select Permissions for the iOS platform, Securiti lists only iOS apps, not a mix of iOS and Android apps.

To add Permissions to app(s) in bulk:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile Consent > SDK & Permissions Library**.
2. Mark the checkboxes next to the Permissions that you want to add to any SDK(s), and from the floating tab, click **+ Add to App(s)**, as shown below.

![Add-to-app_s_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-703ce400-a006-7c45-969e-3b69334f7477.png)
3. On the **Add Permission(s) to Apps(s)** popup, mark the checkboxes next to the apps to which you want to add the selected Permissions.
4. Enable the **Show selected apps only** toggle to review your selection before proceeding.
5. Near the bottom of the popup, click **Add**, as shown below.

![Add-Permission_s_-to-App_s_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b7f4c17-342c-fc33-06a0-8161d1f8675f.png)

> [!WARNING]
> **Important**
> 
> Securiti only lists mobile apps that match the platform type of the selected Permissions when adding them to app(s). For instance, if you select Permissions belonging to the iOS platform to add to app(s), Securiti lists only iOS apps, not a mix of iOS and Android apps.
6. On the confirmation popup, click **Got it**, and then go to your mobile apps and deploy them, as shown below. ![Changes-applied.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0497ec2-496f-4125-86db-bd7a52ceb9b0.png)

> [!WARNING]
> **Important**
> 
> - Adding Permissions to the app(s) stores them, but they only appear in the consent banner and preference center of mobile apps after you redeploy the apps' configurations.
> - This step is crucial. Without deployment, the newly added Permissions do not appear in the consent preference center of your live apps. You must redeploy the configuration for each app individually for the changes to take effect.

## Related

- [Using the SDK and Permissions Library](/using-the-sdk-and-permissions-library.md)
- [Managing Permissions for mobile applications](/managing-permissions-for-mobile-applications.md)
- [Using SDK Purposes](/using-sdk-purposes.md)
- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
