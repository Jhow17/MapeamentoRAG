---
title: "Scanning your mobile application for SDKs and Permissions"
slug: "scanning-your-mobile-application-for-sdks-and-permissions"
updated: 2026-06-16T07:40:36Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/scanning-your-mobile-application-for-sdks-and-permissions"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Scanning your mobile application for SDKs and Permissions

**Scenario**

As a Data Privacy Officer, you need visibility into what personal data your mobile apps collect through permissions and third-party SDKs. For instance, when preparing for a compliance review, manually reviewing source code or coordinating with developers can delay risk identification. With Securiti’s Mobile App Consent Management module, you can upload your IPA, APK, or hybrid app’s source file to scan for permissions and SDKs. You quickly identify potential risks and stay ahead of evolving data privacy requirements.

The mobile app scanner identifies SDKs and permissions used in your mobile applications and provides detailed visibility into what each app integrates and requests. To ensure accurate results, Securiti’s mobile app scanner uses multiple signals from production environments and applies AI-assisted filtering before adding detected SDKs to the consent database. It can also suggest additional SDKs and Permissions that may not appear in the initial scan results.

## How the scanner identifies SDKs and permissions

- The scanner collects SDK and permissions-related logs from production environments to ensure broad and up-to-date coverage.
- AI-based filtering evaluates each detected SDK to determine whether it is valid and should be added to the SDK database.
- AI-based suggestions highlight additional SDKs and Permissions that the scan may miss, so you can review and optionally add them.
- Validated SDKs are classified and incorporated into the database, which improves the accuracy of future scans.
- The scanner supports applications across both iOS and Android. It handles non-standard detection patterns in Android apps and consistently detects SDKs in iOS apps where patterns are more predictable.

## Key capabilities of SDKs and Permissions detection

The scanner is designed to provide accurate, reliable, and comprehensive results for each mobile app scan. The table below outlines key aspects of how detection works:

| Benefit | Description |
| --- | --- |
| Improved detection accuracy | AI-assisted filtering validates SDKs and permissions before adding them to the database. |
| More reliable scan results | Continuous log collection increases the accuracy and completeness of detected entries. |
| Better Android coverage | The scanner handles a wide range of Android SDK patterns, even when naming or structure varies. |
| Strong iOS detection | iOS SDKs are detected consistently due to standardized patterns across apps. |
| Reduced chance of missed SDKs | Automated classification ensures that valid SDKs are incorporated into the database instead of being skipped. |
| Key capabilities of SDK and Permissions detection | AI suggests additional SDKs and Permissions that may not appear in the initial scan results, improving consent coverage. |

## Procedure

You scan your mobile application to see what SDKs and Permissions they use to collect information from data subjects. You start by creating mobile applications with respective platforms (Android or iOS), and then scanning each mobile application to see what SDKs and Permissions it uses.

To scan your mobile application:

1. In Securiti, open Mobile App Consent Management, and choose **Mobile App Consent > Mobile Apps**.
2. Create a new mobile application as explained in [Creating a new mobile application](/v1/docs/configuring-mobile-apps-dashboard).
3. Once done, on the Mobile App Configurations page, from the **APPLICATION CONFIGURATION > Source File** section, upload the source file of your mobile application. For instance:

> [!NOTE]
> Note
> 
> Securiti continues file uploads as you navigate within the same organization, including across other Securiti modules and pages. The upload stops if you change the organization, reload the web browser, log out, or if your session expires.
  1. If your mobile application uses the Android platform, upload the `.APK` or `.AAB` source file. Securiti lets you upload the `.IPA` file up to a maximum size of **1 GB**.
  2. If your mobile application uses the iOS platform, upload the `.IPA` source file. Securiti lets you upload the `.IPA` file up to a maximum size of **1 GB**.
4. (Optional) Enable the **Upload ProGuard Mapping File** toggle if you wish to reduce the application size by uploading the mapping file.

> [!NOTE]
> Note
> 
> Securiti lets you upload the `.TXT` format for the mapping file for up to a maximum size of **1 GB**.
5. (Optional) To view AI-based suggestions for additional SDKs and Permissions, mark the **Enable AI to discover additional SDKs and Permissions** checkbox.

> [!CAUTION]
> Caution
> 
> AI can make mistakes. You must validate all suggested SDKs and Permissions before adding them to avoid adding inaccurate tracking technologies to your scan results.
6. (Optional) To include system library SDKs in scan results, mark the **Include System Library SDKs in scan** results checkbox.

> [!NOTE]
> Note
> 
> When enabled, Securiti includes system library SDKs detected in the mobile app alongside other detected SDKs in the scan results.
7. Once the source file uploads successfully, near the bottom of the page, click **Start Scanning** to initiate the mobile application scan, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Click-Start-Scanning.png)

After initiating the mobile application scan, Securiti automatically redirects you to the **APPLICATION CONFIGURATION > Scan & Reports** section, as shown below.

![Scan-and-Reports-Section.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a81b8518-7f25-3bbf-1c80-9d079ea5868f.png)

## Mobile application scanning and reporting

In the **Scan & Reports** section, Securiti provides an aerial view of all the SDKs and Permissions identified during the mobile application scan. You can explore the results through the following tabs:

| Tab | Description |
| --- | --- |
| Overview | Displays a two-column layout: - The first column shows the total number of SDKs along with a list of all SDKs categorized based on the application scan. - The second column presents the total number of Permissions, along with a list of all permissions grouped according to the application scan. ![1-Scan-Overview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ac0ab1f-bfa4-ea74-4cbb-c04010efe3c2.png) |
| SDKs | Displays the statistics of SDKs found during the application scan based on: - Total number of SDKs - SDKs found from the scan of your application - Manually added SDKs - Hidden SDKs ![2-Scanned-SDKs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-61b8e1b8-4fe4-dbe3-b030-7a4f0151b292.png) |
| Permissions | Displays the statistics of Permissions found during the application scan based on: - Total number of Permissions - Permissions found from the scan of your application - Manually added Permissions ![3-Scanned-Permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1a9874cd-ca3c-64d9-8cb7-7eabcad93fc8.png) |
| AI Suggestions | > [!NOTE] > Note > > You see this tab only if you enable the **Enable AI to discover additional SDKs and Permissions** checkbox after uploading the source file. Displays AI-suggested SDKs and permissions. Review and select suggested items to add them to your mobile application’s consent preference center and SDK & Permissions Library to suit. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/AI-Suggestion-HC.png) |

> [!NOTE]
> Note
> 
> The **Overview** subtab in **Scans & Reports** does not initially show AI-suggested SDKs or permissions. Once you add any suggested items to the app, they appear in the Overview as part of the scan results.

Securiti also lets you download a report of your mobile application's scan results. From the upper right corner of the Scan & Reports section, click **Download Report**, as shown below.

![Download-Scan-Report.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b93a98dd-68e6-f856-8451-c95a0387a95b.png)

Securiti emails you a download link for your scan report. It is a `CSV` file containing the scan results, as shown below.

![Scan-Report-Email.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-72ff0852-7697-23d4-4dcd-bb9ccbd0437b.png)

To learn how to customize the consent banner and preference center for your mobile application, see [Customizing the consent banner and preference center for mobile application](/v1/docs/customizing-the-consent-banner-and-preference-center-for-mobile-application).

A Software Development Kit (SDK) is a set of tools that help developers build platform-specific mobile applications and implement new features in existing mobile apps. This saves significant time and effort, enabling developers to focus on the mobile app’s core functionality and user experience.

A permission is an authorization that an app requests from a mobile app user to access certain features, such as location or camera, or data on their device. Users grant or deny permissions from within the app, and can review or update their choices anytime through the consent preference center or the device settings panel.

## Related

- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
- [Using SDK Purposes](/using-sdk-purposes.md)
- [Using the SDK and Permissions Library](/using-the-sdk-and-permissions-library.md)
