---
title: "Customizing the consent banner and preference center for mobile application"
slug: "customizing-the-consent-banner-and-preference-center-for-mobile-application"
status: "update"
updated: 2026-09-08T11:54:04Z
published: 2026-09-08T11:54:04Z
canonical: "helpcenter.securiti.ai/customizing-the-consent-banner-and-preference-center-for-mobile-application"
area: privacy
modulo: mobile-app-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Customizing the consent banner and preference center for mobile application

You can customize the appearance of your mobile application's consent banner and preference center, and also have multiple versions of the consent banner that Securiti shows only to data subjects from specific geographic locations based on their IP addresses.

To customize your mobile application's consent banner and preference center:

1. In Securiti, open **Mobile App Consent Management** and choose **Mobile App Consent > Mobile Apps**.
2. On the **Mobile Apps** page, click the application whose consent banner and preference center you wish to customize.
3. From the left sidebar, navigate to the CUSTOMIZE BANNER & PREFERENCE CENTER section, from its upper right corner, click **Add** (+ icon), and select **+ Add Banner Template** option, as shown below.

![Add-Banner-Template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-acf3d727-28c1-6a76-857b-b0385726df8a.png)
4. On the Select Templates page:
  1. Mark the checkbox next to the consent banner template(s) that you want to use based on your jurisdiction.
  2. Once selected, near the bottom of the page, click **Add Templates** to add them to the application configuration, as shown below.

![Select-Banner-Template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85a42f23-74ed-c8be-06fa-37a6454701fe.png)
5. Customize Banner & Preference Center section is further divided into three tabs that you can use to thoroughly tailor the consent banner and preference center of your mobile application:
  - [Basic Configurations](/latest/docs/customizing-the-consent-banner-and-preference-center-for-mobile-application#customizing-basic-configurations2)
  - [Content & Preferences](/latest/docs/customizing-the-consent-banner-and-preference-center-for-mobile-application#customizing-content-and-preferences2)
  - [Banner Styling](/latest/docs/customizing-the-consent-banner-and-preference-center-for-mobile-application#customizing-banner-styling2)

![Customization-Tabs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c4496dfe-c412-16f9-87fb-643001346afe.png)
6. Once you have thoroughly customized the consent banner and preference center for your mobile application, navigate to **ASSIGN SDK PURPOSES** section from the left sidebar to proceed.

## Customizing basic configurations

To customize the basic configurations of your consent banner and preference center:

1. From the **Template Name** text field, change the name of banner template. We recommend you include the applicable locations in the consent banner name.
2. From the **Location Intelligence** area of the central panel, mark the radio button for **Show only in**, and use the menu to build a list of countries and states, provinces, or regions.

If you have a default consent banner, it is shown in all other locations.
3. In the **Banner Reappearance Time** section, select the appropriate values from the menus. These defined values determine when the consent banner and preference center are reshown in your mobile application.
4. Enable the **Record Consent Upon App Start** toggle to capture a consent record when the mobile application starts. Once the data subject navigates away from the app, the banner will not be presented again until they clear consent for the SDKs.
5. Click **Save and Continue**. Securiti automatically redirects your to the **Content & Preferences** tab.

## Customizing content and preferences

> [!NOTE]
> Note
> 
> Securiti displays an alert when a mobile app user attempts to interact with a disabled toggle. For instance, if a user tries to switch the **Essential SDKs** toggle to the OFF state in the consent preference center, Securiti displays the alert “You cannot opt out from this Purpose.” This message clearly explains why the action is not allowed.

To customize the content and preferences of your consent banner and preference center:

1. From the **Compliance Type** section, select an appropriate compliance type for your consent banner and preference center:

| Compliance type | Description |
| --- | --- |
| Tell users that we use SDKs & Permissions | It is a basic compliance type that simply lets your data subjects know that you use SDKs and Permissions in your mobile application. > [!CAUTION] > Caution > > - For **California**, using the **Notice Only** compliance type may risk non-compliance. We recommend using the **Opt-out** compliance type to align with state privacy requirements. > - For the **EU**, using the **Notice Only** or **Opt-out** compliance types may risk non-compliance. We recommend using the **Opt-in** compliance type to meet GDPR consent requirements. |
| Let users opt out of SDKs | This is the Opt-out compliance type. If you select this compliance type, the consent of your data subject is assumed at the time of collection of their personal data, and they are shown an option on the preference center to opt out at any time. |
| Ask user to opt into SDK | This is the Opt-in compliance type. If you select this compliance type, your data subjects must provide consent via the consent banner and preference center before you collect and process their personal data. |
2. From the **Banner Contents** section, configure the:
  - Banner Heading
  - Banner Text
  - Accept Button Text
  - Reject Button Text
  - Preference Center Link
  - Privacy Notice Link
  - (Toggle) Enable the **Embed DSR portal URL in the Reject button** toggle, and enter the link to your organization's Data Subject Rights (DSR) portal.
  - (Toggle) Enable the **Hide Close Button** toggle to hide the close (X) button from the consent banner.

> [!WARNING]
> **Important**
> 
> The close button captures the default consent preference of the mobile app user upon click, depending on the Opt-in and Opt-out compliance types:
> 
> - For the Opt-in compliance type consent banner, only essential SDKs are granted.
> - For the Opt-out compliance type consent banner, all essential and non-essential SDKs are granted.
3. From the **Preference Center Text Options** section, configure the:
  - Preference Center Title
  - Preference Center Description
4. From the **SDK Tab** section, configure the:
  - SDK Tab Heading
  - Enable the **Hide Toggle for Essential SDKs** toggle to hide the toggle from the essential SDKs (Purpose) and mark it as "Always active"
5. From the **Permission Tabs** section, configure the:
  - Permissions Tab Heading
  - Permissions Tab Description
6. Click **Save and Continue**. Securiti automatically redirects your to the **Banner Styling** tab.

## Customizing banner styling

> [!CAUTION]
> Caution
> 
> When using custom styles, you must ensure that your color selections meet applicable accessibility guidelines to maintain readability and usability for all mobile app users.

To customize the banner styling of your consent banner and preference center:

1. From the **Banner Position** section, select either the **Bottom** or **Center** option to determine where the consent banner appears in the mobile application.
2. From the **Button Shape** section, select either one of the following options to determine the button's appearance in the consent banner and preference center:
  - Rounded
  - Square
  - Pill
  - Outlined
3. From the **Palette** section:
  1. Select **System Palettes** to choose one of the pre-defined color palettes offered by Securiti, or
  2. Select **Use Custom Styles** to create a fully bespoke color scheme for your consent banner.

> [!NOTE]
> Note
> 
> Securiti offers standardized toggle color behavior in the management portal UI across the Mobile App Consent Management module:
> 
> - When a toggle is enabled and in ON state, it appears without a border.
> - When you disable a toggle, Securiti dims its appearance by applying 65% opacity of the primary toggle color. In the OFF state, this applies to the border and thumb, and in the ON state, to the background.
> 
> This ensures consistent visual behavior across all consent preference center states.

Use the following table to understand how each color configuration option affects the appearance of the consent banner and preference center:

| Color configuration option | Description |
| --- | --- |
| Button Background | Defines the background color of primary action buttons displayed on the consent banner and preference center. |
| Button Text | Sets the text color for labels shown on primary action buttons, such as **Accept** or **Save**. |
| Button Border | Controls the border color of buttons where a border is displayed. |
| Banner Background | Specifies the background color of the consent banner shown to the mobile app users. |
| Banner Text | Determines the text color used for the main content displayed on the consent banner. |
| Banner Links | Sets the color of clickable links within the consent banner, such as policy links. |
| Preference Center Footer Background | Defines the background color of the footer section in the consent preference center. |
| Preference Center Footer Selected | Controls the highlight color used for selected actions or states within the consent preference center footer. |
| Toggle Primary | Controls the toggle **On** state background color and the **Off** state thumb color and stroke color for the primary switch. |
| Toggle Secondary | Controls the toggle **Off** background color and **On** state thumb color. |
| Purpose Disclaimer Text | Controls the text color used for opt-out or purpose disclaimer messaging. |
| Purpose Disclaimer Background | Controls the background color of the Opt-out or purpose disclaimer area. |
4. From the **Company Logo** section, upload your organization's logo in either `PNG` (recommended), `JPG`, or `GIF` image formats with the appropriate image dimensions listed on the UI.
5. From the **Additional Settings** section:
  1. Enable the **Show Powered by Securiti.ai** toggle to display the "Powered by Securiti" text on your mobile application's consent preference center.
  2. Enable the **Show description text with preference center toggles** toggle to display the status texts, which indicate the toggle state (Accepted or Rejected). These toggles are located next to the SDK Puproses on the consent preference center.
6. Click **Save**, and proceed to [Assigning SDK Purposes](/v1/docs/assigning-sdk-purposes).

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

## Related

- [Deploying a consent banner and preference center to the mobile application](/deploying-a-consent-banner-and-preference-center-to-the-mobile-application.md)
- [Assigning SDK Purposes](/assigning-sdk-purposes.md)
