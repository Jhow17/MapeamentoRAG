---
title: "Managing Permissions for mobile applications"
slug: "managing-permissions-for-mobile-applications"
updated: 2026-09-03T09:16:19Z
published: 2026-09-03T09:16:19Z
canonical: "helpcenter.securiti.ai/managing-permissions-for-mobile-applications"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Managing Permissions for mobile applications

In Mobile App Consent Management, Permission refers to the specific authorizations that an application requests from data subjects to access certain functionalities or data on their devices. This can include access to **location services**, **camera**, **contacts**, **storage**, or other sensitive information that the application needs to function correctly.

Use the following list to draw a parallel:

- Permissions = Access Rights
  - Permissions represent the rights that data subjects grant to the application, letting it perform specific actions or access particular data on their devices.
- SDK Purposes = Cookie Categories
  - Just as cookie categories specify the reasons for collecting data and managing consent from data subjects, permissions delineate the specific requests made by an app to access particular features or data on a device. This alignment ensures that both SDK purposes and permissions clearly communicate the rationale behind data collection and usage, fostering transparency and trust between the application and the data subjects.
- SDKs = Cookies
  - SDKs (Software Development Kits) serve as the tools that enable applications to integrate specific functionalities, similar to how cookies are used to manage data subject interactions and preferences.

On the **Add Permission** popup, fill out the following fields:

| Permission Detail | Description |
| --- | --- |
| Permission Name | Specify the name of the Permission that you are adding. |
| Permission Group | Select the name of the group the Permission belongs to. |
| Permission ID | Enter the Permission ID. |
| Description | Enter the purpose and usage of the Permission. |

Near the bottom of the popup, click **Add**. You can add as many permissions as needed for the SDK.

## Adding a new Permission

If any Permissions are missing, you can manually add them from the **All Permissions** section located in the PERMISSIONS section of the left sidebar.

To add a new Permission:

1. In Securiti, open **Mobile App Consent Management** and choose **Mobile App Consent > Mobile Apps**.
2. On the **Mobile Apps** page, click the application in which you wish to add a new Permission(s).
3. From the left sidebar, navigate to the **PERMISSIONS** section, and click **All Permissions**.
4. From the upper right corner of the Permissions section in the center of the page, click **+ Add Permission**, and then select **+ Add New Permission**, as shown below.

![Adding-New-Permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9b97a8d-5e5a-0164-ef80-5b51600beb10.png)
5. On the **Add Permission** popup, fill out the following fields:

| Permission Detail | Description |
| --- | --- |
| Permission Name | Specify the name of the Permission that you are adding. |
| Permission Group | Select the name of the group the Permission belongs to. |
| Permission ID | Enter the Permission ID. |
| Description | Enter the purpose and usage of the Permission. |
6. Near the bottom of the popup, click **Add**. Add as many Permissions as needed for the SDK.

A permission is an authorization that an app requests from a mobile app user to access certain features, such as location or camera, or data on their device. Users grant or deny permissions from within the app, and can review or update their choices anytime through the consent preference center or the device settings panel.

## Related

- [Using the Permissions Library](/using-the-permissions-library.md)
