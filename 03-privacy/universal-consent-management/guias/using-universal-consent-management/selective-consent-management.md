---
title: "Selective consent management"
slug: "selective-consent-management"
status: "update"
updated: 2026-03-31T12:08:06Z
published: 2026-03-31T12:08:34Z
canonical: "helpcenter.securiti.ai/selective-consent-management"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Selective consent management

**Scenario**

As a Data Privacy Officer, you must ensure that data subjects can easily manage their consent preferences and exercise their rights without friction. However, if data subjects cannot quickly unsubscribe or resubscribe to specific communications, they may raise support requests, increasing operational effort. For example, when a data subject receives a marketing email but wants to unsubscribe from promotional messages while still receiving product updates, they should be able to update their preferences instantly. With Selective Consent Management, you can create success pages via API that generate links allowing data subjects to easily unsubscribe from or resubscribe to their preferences through the consent preference center. This provides a seamless experience, reduces support requests, and ensures that choices are respected and enforced accurately.

Selective consent management lets the data subjects to quickly revoke from and resubscribe to their consent preferences via the consent preference center. Securiti lets you create your consent success pages only via API. For more information see [Universal Consent Management API reference](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Generate_narrow_path_link).

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

When this feature is enabled on your Securiti tenant, you see a system generated default success page which is in a draft state for you to edit and publish. You cannot delete the system generated default success page from your tenant.

![1__Selective_consent_management.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f1503a6-9b64-e32e-d173-316a182c19cc.png)

Selective consent management lets you send a link to the data subjects via email to quickly opt-out (unsubscribe) from the prior given consents. Once the data subjects click the link, they are immediately opt-out (unsubscribed) from the set of processing purposes and consent purposes provided at the time of narrow path link generation and rerouted to a new webpage that shows the Success Page containing the buttons **Resubscribe** and **Manage all my preferences**. You can fully customize the **Unsubscribe Success Page** and **Resubscribe Success Page** tabs to suit your organizational preferences. For instance, you can add a custom logo, headlines, message, and the title of the **Unsubscribe**, **Resubscribe**, and **Manage all my preferences** buttons for the email to align with the branding of your organization.

> [!NOTE]
> **Important**
> 
> Securiti detects network issues such as network failure, API gateway failure and unresponsive or down servers when recording the consent of data subjects via the consent success pages. We display an error message to let the data subjects know that their network is not working. The data subjects must retry and record their consent when the network goes back live again.

With success pages dashboard, you can:

- Add success pages.
- Edit, clone, and delete existing success pages.
- View unique IDs in the UUID column for each record.
- Filter out success pages from the dashboard by using a single property or combining multiple properties:
  - Success Page Title
  - UUID
  - Version
  - Date Created
  - Date Published
- Set pagination options to control the number of IDs per page view.

### Using the top-level filter

The top-level filter lets you combine different properties of the Success Page Dashboard and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Success Page dashboard, click **+**, as shown below.

![1-Search_for_Success_Page_Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-51f8845e-8494-2200-35c2-51084612809f.png)
2. On the popup, search success page by success page title, UUID, version, date created, or date published.

For instance, if you want to filter success page by success page title (property), click **Success Page Title**, and from the right, type the title of the success page and press **Enter**. Once done, near the bottom of the popup, click **Apply**, as shown below.

![2-Search_for_Success_Page_Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ad7dcfa-96d0-6f05-4383-5bd8667c3788.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below.

![3-Search_for_Success_Page_Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-337e14f9-6c06-27e1-8d49-f93d15c4bbaf.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![4-Search_for_Success_Page_Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-670d720d-5963-fa94-2ce6-8d87397dd1e9.png)

### Configuring success page dashboard

You can create a success page to manage the selective consent management functionality from the **Consent Success Pages** dashboard as shown below.

![configuring_success_page_dash.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0902ea9-c384-eb9f-01da-b59f585c6f73.png)

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Consent Success Pages**.
2. On the top right side of the page, click **+ Add Success Page** as shown below.

![3__Add_Success_Page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-672bfc9b-4c30-24c8-4347-bb2c7df2844a.png)
3. Click the **pencil** icon to rename your success page to suit as shown below.

![Screenshot_2022-11-01_at_12_28_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78d380cc-a901-7174-817b-5e2425e22c58.png)
4. Go to the **Unsubscribe Success Page** tab and configure the following settings as shown below.

![Screenshot_2023-02-10_at_2_04_07_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e19eecf2-e235-2ead-a985-9cc1d060f75e.png)
  - Logo and branding
  - Language Intelligence (toggle)
    - Enable this toggle to activate the translation mapping for both of your Success Pages.
    - Once enabled, the **Provide Translation Mapping** feature automatically translates the success pages. This translation is based on the exclusive language translations you provide for a specific language that you can select from the menu below this toggle, during the configuration of the success page as shown below.

![Screenshot_2023-02-10_at_1_48_11_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c1f13d3-70c3-68c5-1c5c-c62e5f593dbb.png)

![Screenshot_2023-02-10_at_1_50_49_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e5f6354f-f958-68cb-c80d-35db7037fd93.png)
    - The language translation provided by you overrides the automated web browser translations in case the same language is selected in the translation mapping feature.

> [!NOTE]
> **Note**
> 
> If you have not provided any exclusive translation, the success pages are translated based on the language selected in the data subject’s web browser.
  - Headline text
  - Body text
  - Resubscribe button text
  - Resubscribe button background color
    - You can either use **Hex code** or common **color names** such as red, yellow, green, etc. to change the button background color.
  - Preference button text
  - Preference link text color
    - You can either use **Hex** **code** or common **color names** such as red, yellow, green, etc. to change the link text color.
  - Manage all of my contact preferences link
    - Select the appropriate published preference center from the menu to link with your consent success page.

Once you link your published preference center with the success page, Securiti adds a link to that preference center on the hosted success page. The data subjects can click this link to request for another link to access the preference center where they previously gave their consent. Once the data subjects receive the requested link and click it, this link opens up the hosted preference center of your organization for them to interact with their previous given consents and change their preferences to suit.
  - Communication status text
  - Footer
5. After configuring all settings for the **Unsubscribe Success Page** tab, switch to the **Resubscribe Success Page** tab as shown below.

![Screenshot_2023-02-10_at_2_01_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-932f23e6-4731-ee02-199e-ccdac2a567cb.png)
6. Configure the following settings and click **Publish** on the top right side of the dashboard to publish your success page as shown below.

![Screenshot_2022-11-01_at_12_24_53_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cfaaf3bd-7b3b-0340-155b-024cf35c0745.png)
  - Logo and branding
  - Headline
  - Body text
  - Preference button text
  - Footer

> [!NOTE]
> **Note**
> 
> You can preview your changes in real time during the configuration of your success page in both **Unsubscribe** and **Resubscribe Success Page** tabs on the right side of the dashboard. You can also build and host success pages with a different UI that includes custom color scheme and round shaped buttons as shown below.
> 
> ![Screenshot_2023-02-10_at_1_58_55_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70c9c802-664c-3fda-446b-e911b70f31ea.png)
> 
> The custom UI feature is only available by subscription. If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

## Related

- [Filtering selective consent management](/filtering-selective-consent-management.md)
