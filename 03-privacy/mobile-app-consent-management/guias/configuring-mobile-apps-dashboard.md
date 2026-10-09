---
title: "Configuring Mobile Apps dashboard"
slug: "configuring-mobile-apps-dashboard"
updated: 2026-09-04T09:53:07Z
published: 2026-09-04T09:53:07Z
canonical: "helpcenter.securiti.ai/configuring-mobile-apps-dashboard"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring Mobile Apps dashboard

**Scenario**

As a Data Privacy Officer, you oversee privacy risks across multiple mobile apps. For instance, when a new app build is released, waiting for engineering teams to review it can delay the identification of potential privacy risks. With Securiti’s Mobile App Consent Management module, you upload IPA or APK source files directly, including Flutter and React Native apps, to scan for permissions and SDKs. This gives you quick visibility into how apps access data without relying on developers.

The Mobile Apps dashboard shows you the library of your scanned and uploaded mobile applications in the module at a glance.

From this dashboard you can:

- Create new mobile applications that you wish to scan now or in the future.
- Filter out mobile applications based on different criteria such as:

| Filter | Description |
| --- | --- |
| App Name | Lets you filter the mobile application(s) by typing its name. |
| Platform | Lets you filter the mobile application(s) by selecting the platform such as **Android** or **iOS**. |
| App Status | Lets you filter mobile application(s) by selecting the scan status such as **Published** or **Draft**. |
| Last Scanned | Lets you filter mobile application(s) by selecting a specific time when it was scanned. |
- Save filters as **Saved Views** for future use, and also categorize them in different groups for easy access.
- Export the data of your mobile applications as a report in the following file formats:

> [!NOTE]
> **Note**
> 
> Securiti sends you an email containing the download link of the report.
  - `Excel`
  - `JSON`
  - `CSV`
- Delete the mobile applications from the dashboard if you wish to create a new version and start their scan from scratch.

## Creating a new mobile application

Securiti lets you create a new application that you wish to scan before actually scanning it. You must also select the platform for your application before scanning it.

To create a new mobile application:

1. In Securiti, open **Mobile App Consent Management**, and choose **Mobile App Consent > Mobile Apps**.
2. From the upper right corner of Mobile Apps page, click **+ New Application**, as shown below.

![Create-New-App.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d05ddbaf-07f9-df8d-1946-4569514a8186.png)
3. On the New Application popup:
  1. In the **Mobile Application Name** text field, enter the name of your mobile application.
  2. From the **Platform** menu, select the platform such as **Android** or **iOS**.
4. Near the bottom of the popup, click **Create Application** to save your application, as shown below.

![New-App-Popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21f7b67d-0ead-f96c-15aa-ddb9dc538cd7.png)

To learn how to initiate a scan on your mobile application, see [Scanning your mobile application for SDKs and Permissions](/v1/docs/scanning-your-mobile-application-for-sdks-and-permissions).

## Related

- [Scanning your mobile application for SDKs and Permissions](/scanning-your-mobile-application-for-sdks-and-permissions.md)
- [Customizing the consent banner and preference center for mobile application](/customizing-the-consent-banner-and-preference-center-for-mobile-application.md)
