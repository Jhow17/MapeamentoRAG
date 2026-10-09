---
title: "Using SDK Purposes"
slug: "using-sdk-purposes"
updated: 2026-09-04T10:14:12Z
published: 2026-09-04T10:14:12Z
canonical: "helpcenter.securiti.ai/using-sdk-purposes"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using SDK Purposes

**Scenario**

As a Data Privacy Officer, you want mobile app users to see sensitive SDK purposes first. For instance, when requesting consent for location tracking or advertising SDKs, you may want these purposes highlighted before others. Manually rearranging consent flows in code can be complex and time-consuming. Securiti’s Mobile App Consent Management interface lets you easily reorder SDK purposes. This helps you tailor consent experiences to match your policy priorities with minimal effort.

Securiti lets you build a library of SDK Purposes for your consent banners and preference centers. You can centralize these SDK Purposes to efficiently assign and manage them across different mobile applications as required.

Using this SDK Purposes library, you can:

- Create and customize SDK Purposes to use them for your mobile app consent banner.
- Filter out SDK Purposes based on different criteria such as:

| Filter | Description |
| --- | --- |
| Purpose Name | Lets you filter the SDK Purpose(s) by typing its name. |
| Opt-out State | Lets you filter the SDK Purpose(s) by selecting the opt-out state such as **Enabled** or **Disabled**. |
| Status | Lets you filter the SDK Purpose(s) by selecting the current status such as **Active** or **Deactivated**. |
- Save filters as **Saved Views** for future use, and also categorize them in different groups for easy access.
- Edit system and customize SDK Purposes to suit your preferences.
- Deactivate a customized SDK Purpose if you want to hide it on the consent banner.

> [!NOTE]
> Note
> 
> Securiti lets you deactivate only customized SDK Purposes, but not out-of-the-box (System) SDK Purposes.

## Creating a new SDK Purpose

To create a new SDK Purpose:

1. In Securiti, open **Mobile App Consent Management**, and choose **Setting > Purposes**.
2. From the upper right corner of the Mobile Apps page, click + **Add SDK Purpose**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create-SDK-step2.png)
3. On the **Create New Purpose** popup:
  1. In the **Purpose Name** text field, enter the name for SDK Purpose.
  2. Add appropriate **Description** for SDK Purpose.
  3. From the **Purpose State** menu, select the state such as **Always Active (Opt-out Disabled)** or **Opt-out Disabled**.
  4. (Optional) add text in the **Opt-out Text** field that appears on the consent preferences for data subjects.
4. Near the bottom of the popup, click **Create New Purpose** to create your SDK Purpose, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cretae-SDK-step4.png)

> [!NOTE]
> Note
> 
> The SDK Purposes dashboard displays 10, 25, or 50 SDK Purposes, with pagination options set at 10, 25, and 50 SDK Purposes per page. At the bottom of the SDK Purposes dashboard, use **Showing** menu to select the number of SDK Purposes you want to preview, such as 10, 25, or 50.

## Editing an SDK Purpose

To edit an SDK Purpose:

1. On SDK Purposes dashboard, from the rightmost side of the SDK Purpose that you want to edit, click **Options** (three dots), and select **Edit**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Edit-step1.png)
2. Update the **Purpose Name**, modify the **Description**, select the **Purpose State**, and (optional) edit the **Opt-out Text**.
3. At the bottom of the popup, click **Update** to apply your changes, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Edit-step2.png)

> [!NOTE]
> Note
> 
> If you edit any SDK Purpose, the changes made in that Purpose are reflected across all the mobile apps where that SDK Purpose is used. This way you don’t need to add changes in each mobile app individually.

SDK Purpose refers to the specific reason an SDK processes data. Assigning a purpose ensures that a mobile app user’s consent is tied to a particular type of data processing, such as advertising or analytics. This approach provides transparency, informing mobile app users precisely why their data is being collected and processed.

## Related

- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
- [Using the SDK and Permissions Library](/using-the-sdk-and-permissions-library.md)
