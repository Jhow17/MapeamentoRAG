---
title: "Assigning SDK Purposes"
slug: "assigning-sdk-purposes"
updated: 2026-09-03T09:15:17Z
published: 2026-09-03T09:15:17Z
canonical: "helpcenter.securiti.ai/assigning-sdk-purposes"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Assigning SDK Purposes

**Scenario**

As a Data Security Officer, you must ensure that third-party SDKs in your mobile apps align with your organization’s privacy policies. For instance, when preparing for a security or privacy audit, manually tracking the purpose of each SDK can slow down the review process. With Securiti’s Mobile App Consent Management module, SDKs are automatically classified by purpose, and you can adjust the classification as needed. This improves visibility into third-party data access and reduces the risk of non-compliant data sharing.

According to most data privacy laws, consent of the mobile app user must be given in relation to one or more specific purposes. SDK Purposes define why the mobile app user’s personal data is collected, processed, or shared.

In Mobile App Consent Management, SDKs must be grouped into Purposes so that the mobile app user’s consent remains specific to specific data processing activities. Clearly defining purposes ensures transparency and compliance with privacy regulations as it lets you collect a mobile app user’s consent specific and granular to a data processing activity within the mobile application.

By default, Securiti has classified the SDKs in the following base Purposes:

| Base Purpose | Base ID | Description |
| --- | --- | --- |
| Essential | 1 | Consists of strictly necessary SDKs that ensure the smooth delivery and security of the service. |
| Analytics | 2 | Consists of SDKs that analyze the mobile application’s performance, feature usage, traffic count and sources. This helps you measure and improve the performance of the application. |
| Targeted Advertising | 3 | Consists of SDKs that can build a profile of user’s interests and show them targeted and personalized advertisements based on their interests. |
| Performance & Functionality | 4 | Consists of SDKs that enable the app to provide enhanced functionality and personalization. They may be set by you or by your third-party providers whose services you have added to the application. |
| Social | 5 | Consists of SDKs that are set by a range of social media services to enable you to share your content with end-user’s friends and network on their social media. |
| Unclassified | 6 | These SDKs have not been classified into a specific purpose. You must move all SDKs to another SDK purpose as displaying SDKs as unclassified on the preference center is not compliant with privacy laws. |
| Geolocation | 7 | Consists of SDKs that collect and use your geolocation information. |

From the ASSIGN SDK PURPOSES section, Securiti lets you:

- Reassign SDKs between different Purposes
- Add new SDKs to Purposes
- Hide a specific SDK belonging to a Purpose in the preference center
- Customize the following details of a Purpose:
  - Purpose Name
  - Purpose State
  - Description
  - Opt-out Text
  - Hide all the information about the SDKs for the Purpose in the preference center
- Search for a specific SDK within a Purpose
- Create a new Purpose

## Reassigning an SDK to a different Purpose

To reassign an SDK to a different Purpose:

1. In Securiti, open **Mobile App Consent Management** and choose **Mobile App Consent > Mobile Apps**.
2. On the **Mobile Apps** page, click the application whose SDK(s) you want to reassign to a different Purpose.
3. From the left sidebar, navigate to the **ASSIGN SDK PURPOSES** section, and select the **Purpose**. For instance, select **Analytics**.
4. Scroll down to the SDKs section.
5. Locate the SDK that you want to reassign to a different Purpose. From the right side of that SDK, click **Options** (three dots), and from the menu, select **Change Purpose**, as shown below.

![Assigning-Purpose-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c043cddd-8d35-5676-fda9-f8589a79198e.png)
6. From the menu of Purposes, select the **Purpose** that you want to assign to the selected SDK, as shown below.

![Assigning-Purpose-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60faa11c-ebf2-37d9-5e25-c88d344e73fc.png)

Securiti automatically assigns this SDK to the selected Purpose, and shows you a success message at upper right corner of the page.

## Adding a new SDK to a Purpose

If any SDKs are missing, you can manually add them from the SDKs section located in the ASSIGN SDK PURPOSES section of the left sidebar.

To add a new SDK to a Purpose:

1. In Securiti, open **Mobile App Consent Management** and choose **Mobile App Consent > Mobile Apps**.
2. On the **Mobile Apps** page, click the application whose SDK(s) you want to reassign to a different Purpose.
3. From the left sidebar, navigate to the **ASSIGN SDK PURPOSES** section, and select the Purpose. For instance, select Analytics.
4. Scroll down to the SDKs section.
5. From the upper right corner of the SDKs section, click **+ Add SDK**, and then select **+ Add New SDK**, as shown below.

![Add_SDK.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-036cee6f-1fc1-31f1-235e-81746599c96f.png)
6. On the **Add SDK** popup, fill out the following text fields:

| SDK Detail | Description |
| --- | --- |
| Platform | Preselected based on the application's platform. |
| SDK Name | Enter the name for the SDK. |
| Application ID | Enter the ID of your mobile application. |
| Vendor | Enter the name of the vendor. |
| Release Date | Select the release date using the calendar widget. |
| Version | Enter the version number for the SDK. |
| Developer URL | Enter the URL of the developer who developed the SDK. > [!NOTE] > Note > > The URL is displayed as a link in the deployed banner, allowing mobile app users to directly access the developer’s website. |
| License | Enter the license of the SDK. |
| Purpose | Preselected based on the Purpose you are adding an SDK in. |
| Category | Select a relevant category from the menu that best fits this SDK. |
| Description | Enter a description for the SDK that explains its purpose and how it is used. |
7. Once done, near the bottom of the popup, from the **Permissions** section, click **+ Add Permission**, and select **+ Add New Permission**, as shown below.

![Add-Permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be5c150a-4487-9837-673d-e23bf36a2376.png)
8. On the **Add Permission** popup, fill out the following fields:

| Permission Detail | Description |
| --- | --- |
| Permission Name | Specify the name of the Permission that you are adding. |
| Permission Group | Select the name of the group the Permission belongs to. |
| Permission ID | Enter the Permission ID. |
| Description | Enter the purpose and usage of the Permission. |
9. Near the bottom of the popup, click **Add**. You can add as many permissions as needed for the SDK.
10. On the **Add SDK** popup, near the bottom corner, click **Add SDK** to save it in the Purpose.

## Creating a new SDK Purpose

To create a new Purpose, see [Creating a new SDK Purpose](/v1/docs/using-sdk-purposes).

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

## Related

- [Using SDK Purposes](/using-sdk-purposes.md)
