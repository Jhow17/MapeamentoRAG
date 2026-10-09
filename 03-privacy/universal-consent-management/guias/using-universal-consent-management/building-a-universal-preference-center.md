---
title: "Building a universal preference center"
slug: "building-a-universal-preference-center"
status: "update"
updated: 2026-07-21T09:59:19Z
published: 2026-07-21T09:59:19Z
canonical: "helpcenter.securiti.ai/building-a-universal-preference-center"
stale: true
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Building a universal preference center

**Scenario**

As a Data Privacy Officer, you must ensure data subjects can easily manage their consent and communication preferences. Managing consent across systems can be difficult, and delays in updating preferences can create compliance risks if records are not kept current. With Securiti’s Universal Preference Center, you can publish a link on your website where data subjects verify their identity and access a personalized page to update preferences. For instance, a data subject enters their email, receives a single-use link, and chooses to opt out of marketing emails while keeping product updates. Data subjects manage their preferences directly, helping you keep consent records accurate and giving individuals clear control over how their data is used.

Securiti lets you create a preference center that acts as a centralized portal where data subjects can view, manage, and update their consent and communication preferences.

You publish a link to the preference center on your website. When a website visitor clicks on the preference center URL, it asks for their email address or other identification. When the data subject submits identification, Securiti sends them a single-use URL, as shown below.

![Pref-center-DS-link.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-396d1213-3d55-b975-35c3-501cd90869c0.png)

When the data subject follows the link, it takes them to a personalized preference management page where they select their consent preferences, as shown below. The preferences come from the configured form.

![step_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fcf2c5f6-395b-b327-33ea-b0114a8d49c8.png)

### Key Considerations

Consider the following when creating a new preference center:

- When you create a preference center, after configuring **Form Consent** as described in [Collecting form consent](/v1/docs/collecting-form-consent), the processing and consent purposes from it take precedence.

### Procedure

To build a consent preference center:

1. In Securiti, open **Universal Consent**, then choose **Universal Consent > Preference Center**.
2. On the Preference Center Dashboard page, near the upper right corner click **+ Add Preference Center**.
3. Near the upper left corner of the page, click the pencil icon and give the form a convenient name as shown below. Then click the check mark to save the name.

![pref_center_name_step3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef3f701c-7ece-c12e-7df7-6094573d7f9f.png)
4. On the **Select Form Template** tab, choose from among the available style templates for the preferences center.

> [!NOTE]
> **Note**
> 
> If there is only one template available, that one is selected by default.
5. Near the bottom of the page, click **Template Settings** tab, and use:

| **Logo & Branding** |
| --- |
| Logo | Click **Upload Image**, drag or select your logo file in **PNG**, **JPG**, or **GIF** format in the popup, and click **Upload** to complete. > [!NOTE] > Note > > Use a logo size of at least **96 × 96 px** and at most **480 × 480 px** to prevent errors. |
| Text Color | Enter a HEX code, a color name such as Red, Blue, or Violet, or use the color picker that appears when you click the pencil icon. |
| Button Color | Enter a HEX code, a color name such as Red, Blue, or Violet, or use the color picker that appears when you click the pencil icon. |
| **Additional Settings** |
| Hide "Powered by Securiti" | Mark this checkbox to hide the “Powered by Securiti” footer attribution (branding message) that appears on the: - Access screen where data subjects enter their details - Emails containing the verification link to access the preference center - Preference center screen > [!NOTE] > **Important** > > Securiti also offers a platform-level system setting that lets you hide the Securiti branding at the tenant level, removing it from all preference centers within your Securiti tenant, as well as from email notification templates. > > To enable this setting, in Securiti, open **Universal Consent Management**, and choose **Module Configurations > Settings**. From the **Securiti Branding** section, enable the **Hide Securiti Branding** toggle. Once done, from the upper right corner of the **Universal Consent Configurations** page, click **Save**, as shown below. > > ![Enable-Hide-Securiti-Branding.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b0e51c31-a098-9089-f95e-6b519f9b701b.png) |

![template_setting_step5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d2446bf-c901-9fec-b223-bee4716fdd19.png)
  - Features in the **Logo & Branding** section to choose theme elements for the page that data subjects fill out to obtain the one-time URL as described in the table below.
  - Feature(s) in the **Additional Settings** section to hide the "Powered by Securiti" footer attribution (branding message) that appears on mutiple screens as described in the table below.
6. Click the **Customize Verification** tab, and use the tools on that page to customize the page that data subjects fill out to obtain the one-time URL.
  1. Use the Headline tools to customize the text at the top of the form.
  2. Use the Define Form Fields and Requirements area to customize the fields that data subjects fill out, and which Securiti uses to query its consent database. You can click and drag fields to different locations, or add static and custom fields by dragging them onto the form, as shown below.

![customize_verification_step6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-db082af1-ae33-a24d-9672-7cb2fb60206b.png)

See [Customizing your universal preference center](/v1/docs/customizing-your-preference-center) for more information.

The form display on the right half of the page shows you what the form will look like when you publish it.

> [!NOTE]
> **Important**
> 
> Preference Center only uses **one identifier** to query the preferences. It currently defaults to email, which is the only ID that sends a verification link. We strongly recommend you use email as the identifier.
> 
> If you choose a different identifier to query for user’s preferences, it must align with the Primary IDs selected throughout the form configurations.
> 
> The order of priority for identifiers is:
> 
> 1. Any field marked as UUID in the API Type
> 2. Email address
> 3. Mobile phone number
7. Use the preview area on the right half of the page to see what the form looks like on computer, tablet, and phone screens, as shown below.

![preview_step7_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a758194f-f9f0-6909-c0c8-8887b91d80eb.png)

You can validate your added custom fields on the run time by clicking the **Submit Request** button. Use this button to check if the information added in the fields is accurate or not.

![Step7_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dbc31fb8-68f1-73a9-9adc-59e0a0880e17.png)
8. Click the **Customize Content** tab and use the tools on that page to customize the Preference Center where data subjects view and edit the consent they have granted for various purposes.
  - **Location Intelligence** to tailor the preference center experience based on the data subject’s location. Securiti lets you build multiple versions of the preference center that Securiti shows only to data subjects from specific geographic locations based on their IP addresses.
  - **Language Intelligence** to display content and purpose in the data subject’s preferred language. When enabled, the preference center verbiage automatically adapts to the data subject’s web browser language.
  - **Color Branding** to apply your brand colors of your organization to the preference center.
  - **Opt-in Configuration** to define how data subjects opt-in to communications or data processing.
  - **Preference Center Text Options** to customize the headline and body text.
  - **Consent Expiration** to set how long a data subject’s consent stays valid before renewal.
  - **Purpose Tree** to add or manage the processing and consent purposes for which you process personal data and collect consent.

![Customize_Content-step-8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-334144da-1353-a733-fb4e-6713c419bde6.png)

You can add more processing and consent purposes from within the **Purpose Tree** section.

> [!NOTE]
> Note
> 
> - Securiti pulls the processing and consent purposes from the **Form Consent** if you have configured them there.
> - Securiti also lets you change or create a new processing and consent purpose. Click **Edit** (pencil icon) next to the **Purpose Tree** to manually edit the processing and consent purposes.

To add a processing and a consent purpose:

> [!NOTE]
> Note
> 
> You can select multiple processing and consent purposes.

You can also add a new processing purpose or consent purpose if they are not listed in the **Processing Purpose** or **Consent Purpose** menus.

To add a new processing purpose:

To add a new consent purpose:

See [Configuring processing purposes and consent purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes) for information on building a library for processing and consent purposes.

> [!NOTE]
> **Important**
> 
> - Manually editing the Purpose Tree disables dynamic updates of the preference center.
> - In the **Purpose Tree** section, enable the **Hide Processing Purpose Category** toggle to prevent the display of processing purpose category labels on the configured processing purposes. When this toggle is disabled, the **Hide Purpose Headers** toggle also becomes inactive because these features are interconnected.
> 
> ![Toggle-dependency.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-09c1aee6-c11e-046e-2705-24872ea0f515.png)
> 
> You can display either **Purpose Headers** above Consent and Processing Purposes, or **Processing Purpose Category** labels above Processing Purposes only.
    1. Click **+ Add Processing Purpose**, as shown below.

![User interface for a preference center with options for consent and customization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ PC_HC_0(1).png)
    2. Select processing and consent purpose from the **Processing Purpose** and **Consent Purpose** menus, as shown below.

![Form section for selecting processing purposes like email marketing and lead generation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ PC_HC_00.png)
    1. Navigate to the end of the Processing Purpose menu items and click **+ Add New Processing Purpose**, as shown below.

![Options for consent expiration and processing purposes in a digital interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PC_HC_1.png)
    2. In the **Add Processing Purpose** popup, type the processing purpose, and description. You can also enter **External ID** (optional), select **Processing Purpose Category**, set translation languages.

After adding these details, click **Save**, as shown below.

![Form for adding processing purpose in email marketing with fields and buttons.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PC_HC_2.png)
    1. Navigate to the end of the Consent Purpose menu items and click **+ Add New Consent Purpose**.
    2. In the **Add Consent Purpose** popup, type the consent purpose, description, **External ID** (optional), set translation languages and then click **Save**, as shown below.

![Form for adding consent purpose with options for offers and translations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PC_HC_3.png)
9. Near the bottom of the page, click the **Customize Email** tab, and use:

| **Email Content** |
| --- |
| Enable Templates (toggle) | Lets you select an email template created in the **UCM Preference Center Email Templates** setting, as shown below. ![Select_Email_Templates.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f25d1aec-f077-4886-bb38-5dd7e4b077a5.png) Custom email templates provide more control over the layout and content, improving communication with data subjects through your preference center. > [!NOTE] > **Important** > > - When you enable the **Enable Templates** toggle, the first email template created in the **UCM Preference Center Email Templates** setting is automatically selected. However, you can choose a different template from the **Select Email Template** menu. Once you publish your preference center with a selected email template, Securiti retains and honors that selection for future use. > - Enabling the **Enable Templates** toggle automatically hides the **Email Settings** section and its checkboxes. This is because when you select an email template, all layout-related elements, such as the subject line, body text, CTA buttons, preference center link, and tenant details, are already configured in the template. To avoid confusion, Securiti hides the Email Settings section. For more information, see [Customizing Preference Center Email Templates](/v1/docs/customizing-preference-center-email-templates). |
| **Email Settings** |
| Use Preference Center Title in Email Subject Field (checkbox) | Mark this checkbox to include the name of your preference center as the **email subject** for the access emails that your data subjects receive to access the preference center. |
| Hide Tenant Name and Tenant Domain (checkbox) | Mark this checkbox to hide your Securiti tenant details, such as **tenant name** and **domain**, in the email that goes out to your data subject to access the preference center. |

![customize_email.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c64564e2-3751-06ed-f7f8-e6c5f9f90e0f.png)
  - Feature in the **Email Content** section to choose an email template from the menu that you created using the **UCM Preference Center Email Templates** setting as described in the table below.
  - Features in the **Email Settings** section to choose which details to include or hide in the access emails sent to data subjects for accessing the preference center as described in the table below.
10. Review the form, if it looks good then click **Publish**.

If not, go back and make any necessary changes.
11. On the **Preference Center Dashboard** page, find the entry for the new form and click the **Clipboard** (copy) icon to copy the published preference center link to the clipboard for later use. This is the link that you publish on your website for your data subjects if they want to configure their consent preferences.

![Copy-Preference-Cente.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d22c374-4146-b962-b248-acf80504e019.png)
12. Work with your website team to publish the link to the preferences center form on your website.
13. The final layout of your preference center is based on two columns. The first column represents the processing purposes along with mapped processing purpose category labels, and the second one represents consent purposes as shown below.

![step_12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-45fcda65-47bf-6f01-2cff-40bfdbaa33d9.png)

> [!NOTE]
> **Note**
> 
> Securiti collects the consent given by data subjects via the preference center even in case of network issues such as network failure and unresponsive or down servers. We show an error message on the console letting the data subjects know that their network is not working, as shown below. The data subjects must record their consent again via the preference center when the network goes live again.
> 
> ![Offline-pref-center.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4475afa8-cbbc-0117-924d-d98ac1248324.png)

Securiti completely translates content of received email for verification and the verification tabs along with other elements of the preference center such as the title, buttons, processing and consent purpose columns, based on the language selected in the web browser, as shown below.

![Screenshot_2022-12-07_at_7_42_34_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab2a7ebb-4825-10d0-3810-217dbf6a7bc3.png) ![Screenshot_2022-12-07_at_7_43_37_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83de442d-1f89-2cad-bbfa-11043846c5cc.png)
14. You can also build and host a preference center with a different custom UI to align Securiti's preference center with your organizational branding. This version of the preference center includes a **custom color scheme** and **round shaped buttons**, as shown below.

![step13_1_Customize_Content.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e3ffaff-91f4-1545-684a-4a42888aaadf.png)

![step_13_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ea958d5-af06-4b21-6a1a-e895861d224f.png)

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
15. Securiti lets you build a preference center with **Single Opt-in**, **Double Opt-in**, and [**Explicit Consent**](/v1/docs/configuring-an-explicit-consent-preference-center) configurations, as shown below.

![Step_15_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf0bdf50-feeb-5857-806e-5a83181a3b4f.png)
  1. Choose single opt-in configuration if you want to build and host a preference center where Securiti captures the consent given by your data subjects either as **granted** or **declined** based on their preferences.
  2. Choose the Double Opt-in configuration option to build and host a preference center where your data subjects must give consent and then confirm it for it to be considered as granted as shown below. For more information, see [Configuring a double opt-in preference center](/v1/docs/configuring-a-double-opt-in-preference-center).

![step_15_b-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6a8c33b-a924-735d-6566-03401c57977f.png)

![step_15_b2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2064fb2d-1bff-d72f-e8d6-2fd027a04b49.png)

The consent goes in a **pending** state when the data subject marks the checkbox for one or more consent purposes, but does not click **confirm** on the **Confirm Consent** popup upon submitting their preferences as shown below. ![step_15_b3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fed5e0c6-7d97-d62a-7294-e693a58658dd.png)

> [!NOTE]
> **Note**
> 
> - Securiti records the state of unmarked consent purposes as **declined** when the data subjects interact with the preference center for the first time.
> - You can also filter out consent records through the filter panel on the main dashboard. For instance, you can filter out consent records based on different statuses such as **granted**, **declined**, **withdrawn** or **pending**.
  3. From the **Double Opt-in Modal Configuration** section, you can also customize the following content for the confirm popup:
    - Headline text
    - Body text

> [!NOTE]
> **Note**
> 
> Securiti only displays a variable number of lines (ranging from 5 to 7) for the body text description on the deployed preference center. This variation is dependent on the screen size through which your data subjects interact with the preference center. If the text exceeds the range of 5-7 lines, it gets truncated. However, your data subjects can still read the entire body text description by simply hovering over the ellipsis (three dots), as shown below.
> 
> ![step_15_c1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2c35ede-f634-8b40-b87c-f80640f9ad02.png)
> 
> 
> 
> ![step_15_c2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b2904dd2-a892-3e1e-6254-a2a8588e8032.png)
    - Confirm button text
    - Cancel button text

Securiti lets you add custom translations for your single or double opt-in preference centers. From the Preference Center Text Options section, enable the **Provide Translation Mapping** toggle and from the **Select Language** menu, select a language for which you want to add your custom translation, as shown below.

![2nd-last.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e460f5d-d0a3-eee0-cf4a-507048846127.png)

![last_ss.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97f1801f-2da1-2923-f395-d4a0f00c3415.png)

### Preference Center legal obligations

The preference center lets data subjects select their opt-in and opt-out consent choices for various data processing operations. It is available at all times for the data subjects and helps organizations immediately and adequately honor consent revocations across multiple systems.

To fulfill your privacy legal obligations, ensure that your preference center adheres to these privacy legal obligations:

- Ensure granularity in consent opt-ins. You must seek consent for different processing purposes by providing separate opt-ins for each purpose.

For instance, opt-in for newsletter subscription must be separate from that of email subscription to allow users to give specific consent for other purposes.
- You must provide an easily accessible **Privacy Policy URL** next to or within your preference center detailing how the personal data of your data subjects is handled and what rights they have in connection to their personal data.
- Ensure fulfillment of consent obligations applicable and relevant to your particular jurisdiction.

## Related

- [Customizing your universal preference center](/customizing-your-preference-center.md)
- [Configuring a double opt-in preference center](/configuring-a-double-opt-in-preference-center.md)
- [Configuring an explicit consent preference center](/configuring-an-explicit-consent-preference-center.md)
