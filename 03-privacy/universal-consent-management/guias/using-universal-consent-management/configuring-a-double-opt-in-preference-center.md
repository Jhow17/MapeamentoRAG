---
title: "Configuring a double opt-in preference center"
slug: "configuring-a-double-opt-in-preference-center"
updated: 2026-08-25T05:15:19Z
published: 2026-08-25T05:15:19Z
canonical: "helpcenter.securiti.ai/configuring-a-double-opt-in-preference-center"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring a double opt-in preference center

Many organizations and businesses want to enforce a policy of double opt-in to reduce the spam consent records and verify the identity of their data subjects when they provide consent (opt-in). With the implementation of double opt-in mechanism, when the data subjects provide consent and identifying information to the organization or business, the business sends out a confirmation email or shows a confirmation popup to the data subjects based upon the identifying information provided by them. The data subjects are only considered truly opted in once they have confirmed their given consent via the confirmation email or confirmation popup.

> [!NOTE]
> **Note**
> 
> Securiti lets you configure double opt-in using either email confirmation or a confirmation popup, with **email confirmation as the recommended method**.

To build a double opt-in preference center:

1. In Securiti, open **Universal Consent Management**, and choose **Explorers > Preference Center**.
2. On the Preference Center Dashboard page, near the upper right corner click **+ Add** **Preference Center** and create a preference center as explained in the [Building a universal preference center](/v1/docs/building-a-universal-preference-center).

![Dashboard displaying preference center statistics, including published and draft counts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/double_optin_1.png)
3. From the Opt-in Configuration section, mark the **Double Opt-in** radio button to build and host a double opt-in preference center where your data subjects must give their consent and then confirm it for it to be considered as granted, as shown below.

![step_3a.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b63b94ea-f7d9-e514-f18e-13e1c2ac8414.png)

Securiti provides two methods for consent confirmation, **Email (Recommended)** and **Popup,** as shown below.

![Configuration options for email double opt-in settings and marketing preferences.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/double_optin_2(1).png)

> [!NOTE]
> Note
> 
> Securiti recommends using **email confirmation** for double opt-in to verify that the data subject has explicitly confirmed their consent.

For email confirmation, select the [**Email Template**](/latest/docs/customizing-preference-center-email-templates) and [**Consent Confirmation Page**](/latest/docs/creating-double-opt-in-confirmation-page) and **Link Expiration Time** from their respective fields, as shown below.

![Configuration options for double opt-in email settings and preference center text options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_1.png)

And for the **Popup**, provide the headline, body, and confirmation button text as shown below.

![Consent form with options for email marketing and buttons to confirm or cancel submission.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/doi_2.png)

For more information on creating an email templates and double opt-in confirmation pages, see the [Customizing universal preference center email templates](/latest/docs/customizing-preference-center-email-templates) and [Creating double opt-in confirmation page](/latest/docs/creating-double-opt-in-confirmation-page).

The consent goes in a **pending** state when the data subject confirms preferences from the preference center and does not from confirmation email or popup.

> [!NOTE]
> **Note**
> 
> - Securiti records the state of unmarked consent purposes as **declined** when the data subjects interact with the preference center for the first time.
> - You can also filter out consent records through the filter panel on the main dashboard. For instance, you can filter out consent records based on different statuses such as **granted**, **declined**, **withdrawn** or **pending**.
4. From the Double Opt-in Modal Configuration section, you can customize the following content for the confirmation popup:
  - Headline text
  - Body text

> [!NOTE]
> **Note**
> 
> Securiti only displays a variable number of lines (ranging from 5 to 7) for the body text description on the deployed preference center. This variation is dependent on the screen size through which your data subjects interact with the preference center. If the text exceeds the range of 5-7 lines, it gets truncated. However, your data subjects can still read the entire body text description by simply hovering over the ellipsis (three dots), as shown below.
> 
> ![step_4a.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8405815c-d9e1-98ef-f899-1aaf7dd75cc6.png)
> 
> ![step_4b.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e51dbc66-97dd-d477-69c1-0d2e40525caa.png)
  - Confirm button text
  - Cancel button text

![step_4c.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7fec92c1-a6f5-d215-4700-597e5f336ce2.png)
5. Complete the rest of double opt-in preference center configuration as explained in [Building a universal preference center](/v1/docs/building-a-universal-preference-center).
6. Review your double opt-in preference center, if it looks good then click **Publish**. If not, go back and make necessary changes.
7. On the Preference Center Dashboard page, find the entry for the new preference center and from the URL column, click **Copy** to copy the published link to the clipboard for later use. This is the link that you publish on your website for anyone who wants to configure their consent preferences.

![Dashboard displaying preference centers with published and draft statuses highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/double_optin_3.png)
8. Work with your website team to publish the link to the preference center on your website.

The final layout of your preference center is based on two columns. The first column represents the processing purposes along with mapped processing purpose category labels, and the second one represents consent purposes, as shown below.

![Pref-center-labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b77e7b66-b092-560c-96b2-27a0ffacdd7b.png)

Securiti lets you add custom translations for the texts of your double opt-in preference center. From the Preference Center Text Options section, enable the **Provide Translation Mapping** toggle and from the **Select Language** menu, select a language for which you want to add your custom translation, as shown below.

![step8_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1566a27d-2589-33d1-e7d9-77e0cc4d6a87.png)

![step8_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bc205d5d-1222-b866-4f56-6ea3a3d3c7ba.png)

### User journey and state diagram

The following state machine diagram explains the flow of data subject actions that they might take when interacting with the double opt-in preference center.

![Double_Opt-in_UJD__1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1726521e-c498-f2f2-649d-45ab57a6abe2.png)

The following table explains the flow of consent between two same or different consent states when data subjects interact with the double opt-in preference center.

| From state | To state | Description |
| --- | --- | --- |
| No Consent | Pending | When the data subject confirms their choice on the preference center for the first time. |
| Decline | When the data subject gives no consent or when they provide consent either as pending, and then change their mind and declines their given consent on the preference center. |
| Decline | Pending | When the data subject confirms their choice on the preference center. |
| Decline | When the data subject gives no consent or when they provide consent either as pending, and then change their mind and declines their given consent on the preference center. |
| Withdrawn | Pending | When the data subject confirms their choice on the preference center. |
| Decline | When the data subject declines their previously given consent on the preference center. |
| Pending | Granted | When the data subject confirms their choice on the confirmation popup. |
| Decline | When the data subject declines or changes their decision and revokes given consent. |
| Pending | When the data subject does not confirm their previous choices on the confirmation popup or declines their previous given consent, and then chooses to confirm again on the same instance. |
| Granted | Withdrawn | When the data subject opts out from the consent purposes which they granted on their previous interaction with the preference center. |

The following user journey explains the workflow of data subject's interaction with the double opt-in preference center.

![UCM_double_opt-in-R.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-00dbd9ee-fbb9-3e79-02ec-cc809dc1f631.png)

## Related

- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Customizing your universal preference center](/customizing-your-preference-center.md)
