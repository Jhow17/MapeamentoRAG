---
title: "Integrating Securiti with Google Tag Manager"
slug: "integrating-securiti-with-google-tag-manager"
updated: 2026-08-05T17:43:04Z
published: 2026-08-05T17:43:04Z
canonical: "helpcenter.securiti.ai/integrating-securiti-with-google-tag-manager"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating Securiti with Google Tag Manager

**Scenario**

As a Data Privacy Officer, you use Google Tag Manager to load third-party scripts on your website. For instance, a marketing tag could fire before a data subject provides consent, potentially leading to compliance violations. Without proper gating, tags may run before consent is captured. With Securiti’s Cookie Consent Management module integration with Google Tag Manager, you can control tag firing based on consent signals. This helps prevent unauthorized tracking and maintain compliance without overhauling your GTM setup.

You can use the Google Tag Management system to honor cookie preferences submitted through the Securiti cookie consent management features. If your website uses Google Tag Manager (GTM) to deploy third party libraries, it must prevent them from triggering until website visitors have given their consent to the use of cookies. You can connect your Google Tag Management System to our Cookie Consent Manager to control the blocking or firing of tags.

> [!NOTE]
> **Note**
> 
> For cookie categories for which you have disabled Opt-out, by default Google Tag Manager drops those cookies without waiting for any triggers.

## Scan your website and classify cookies

First, scan your website for cookies as described in [Scanning your website for cookies](/v1/docs/scanning-your-website-for-cookies). Then categorize them as described in [Categorizing your website cookies](/v1/docs/categorizing-your-website-cookies).

## Build a website banner

Build a website banner and embed its code on your website as described in [Customizing your cookie banner and preference center](/v1/docs/customizing-your-cookie-banner-and-preference-center).

## Create a cookie accepted variable

1. Start Google Tag Manager.
2. Near the left edge of the page, click **Variables**.
3. In the User-Defined Variables area, click **New**.
4. Near the upper left corner of the Variable Configuration box, edit the variable name so it reads **cookieAccepted**.

![cookieAccepted_variable.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dfce6ae8-feb8-3fe5-33db-04d5f70369b6.png)
5. Near the upper right corner of the Variable Configuration box, click **Edit** (pencil icon).
6. Click **Data Layer Variable**.
7. In the Data Layer Variable Name box, type the name **cookieAccepted**.
8. Near the upper right corner of the page, click **Save**.
9. On the Variables page, confirm that there is a new data layer variable called "cookieAccepted." ![cookieAccepted_in_UDV_list.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-698ec214-1d71-bdb2-cb7d-7469e064089c.png)

## Create a watcher tag and trigger

1. Near the left edge of the page, click **Tags**.
2. Near the upper right corner of the Tags box, click **New**.
3. Near the upper left corner of the Tag Configuration area edit the variable name so it reads **Watcher**.
4. Near the upper right corner of the Tag Configuration area, click **Edit** (pencil icon).
5. On the Choose tag type panel, scroll down to the Custom area and choose **Custom HTML**.
6. In the HTML area, paste the following code snippet:

```javascript
<script>
 window.addEventListener('message', function(ev) {
   if(ev.data.message === 'consent_given') {
     console.log(ev.data.consentStatuses);
     ev.data.consentStatuses && Object.keys(ev.data.consentStatuses).forEach(function(category) {
        if(ev.data.consentStatuses[category]) {
          dataLayer.push({
            'event': 'userPrefUpdate',
            'cookieAccepted': category
          })
        }
     })
   }
 })
</script>
```
7. Near the upper right corner of the Triggering area, click **Edit** (pencil icon).
8. Near the upper right corner of the Choose a Trigger panel, click **+**.
9. Near the upper left corner of the panel, edit the trigger name so it reads **Watcher Trigger**.
10. Near the upper right corner of the Trigger Configuration area, click **Edit** (pencil icon).
11. On the Choose trigger type panel, choose **DOM Ready**.

![watcher_tag.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d3862bba-5fe5-d095-e02a-045726805884.png)
12. Near the upper right corner of the trigger panel, click **Save**.
13. Near the upper right corner of the tag panel, click **Save**.

## Create cookie category triggers

> [!WARNING]
> Important
> 
> The cookie categories configured in Securiti are used to display cookie categories to data subjects in the preference center and to capture their consent preferences.
> 
> 
> 
> When integrating with Google Tag Manager (GTM), you must configure and associate tags with the appropriate consent categories within GTM. Securiti does not automatically categorize, load, or block cookies in GTM.
> 
> 
> 
> Based on the data subject’s consent choices, Securiti sends consent events indicating which categories have been accepted or declined. GTM can use these events to determine whether to load or block the corresponding tags and cookies.

For each of the following cookie categories, you create a trigger:

- Essential
- Performance & Functionality
- Analytics & Customization
- Advertising
- Social Networking

1. In Google Tag Manager, near the left edge of the page choose **Triggers**.
2. Near the upper right corner of the Triggers list, click **New**.
3. Near the upper left corner of the trigger panel, edit the trigger name so it reads **<cookie category name>** **Trigger**, for instance "Advertising Trigger".
4. Near the upper right corner of the Trigger Configuration area, click **Edit** (pencil icon).
5. On the Choose trigger type panel, scroll down to the **Other** area and click **Custom Event**.
6. In the Event Name box, type `userPrefUpdate`.
7. Mark the checkbox for **Use regex matching**.
8. Mark the radio button for **Some Custom Events**.
9. Near the bottom of the panel, configure the event so that it is:

| cookieAccepted | matches RegEx (ignore case) | `&lt;cookie_category&gt;` |
| --- | --- | --- |

Where `&lt;cookie_category&gt;` matches one of the available categories verbatim.

![Advertising_cookie_trigger.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-880db958-5301-eb16-3918-b5bef8bfe6d8.png)
10. Near the upper right corner of the trigger configuration panel, click **Save**.
11. Repeat the procedure for each of the remaining cookie categories.

## Add category triggers to your existing cookie tags

For each of the existing tags that control your cookies, add the category triggers so that they drop cookies only when the watcher receives the `userPrefUpdate` object from Securiti:

1. In Google Tag Manager, near the left edge of the page choose **Tags**.
2. From the tags list, choose a tag that manages a category of cookies, for instance Advertising.

> [!WARNING]
> **Important**
> 
> You must explicitly mention the name of cookie category in the tag for the Google Tag Manager **Watcher** to commission triggers based on the data subject's actions such as accept, decline, withdraw or modify consent.
> 
> ![Screenshot_2023-09-04_at_4_07_51_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fdf1c87d-a792-cd9e-d2e3-9f090e604399.png)
3. On the panel for the tag, near the upper right corner of the Triggering area click **Edit**.
4. On the Choose a Trigger panel, choose the corresponding tag you created in the procedure [Create cookie category triggers](/v1/docs/integrating-securiti-with-google-tag-manager).

![Add_tag_to_trigger.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0de1dbb9-5e5a-1108-37f2-8fae04b28911.png)
5. On the tab panel, click **Save**.
6. Repeat the procedure for the remaining cookie categories.

## GTM behavior with non-essential cookie categories

Securiti provides trigger messages to the Google Tag Manager (GTM) with the latest consent information for both **Opt-in** and **Opt-out** compliance types. Whenever your data subjects revisit your website and interact with the cookie consent preferences banner such as grant, decline or withdraw their consents, we provide the new trigger messages to the GTM based on their latest interactions.

- For Opt-in compliance type:
  - On page load, for the essential (non opted-out) categories, Securiti provides the trigger message to the GTM as **true**.
  - We provide the information about non-essential categories to the GTM only after the data subjects provide their consent.
- For Opt-out compliance type:
  - On page load, if all cookie categories are allowed, Securiti provides the trigger message for all cookie categories to the GTM as **true**.
  - Once the data subjects change their consent, Securiti provides the information only for the non-essential cookie categories to the GTM.
- For implicit consent type:
  - Securiti provides the trigger messages for both essential and non-essential categories and provides this information to the GTM.

## GTM behavior with different compliance types

The following table explains the behavior of Google Tag Manager with different compliance types such as Opt-in, Opt-out, and implicit consent:

| Compliance Type | GTM Behavior |
| --- | --- |
| Opt-in | In Opt-in compliance type cookie banners, only essential cookie categories are **true** and all other cookie categories are false. On the very first page load, Securiti only triggers the **essential** cookie categories and passes information to the data layer variable, which then triggers the essential trigger configured by you. After this when your data subject visits your website, interacts with your deployed cookie banner, and gives consent to any **non-essential** cookie category such as **Advertising**, Securiti sends a consolidated trigger message containing essential cookie categories as FALSE because essential cookie categories were triggered previously as TRUE. The essential cookie categories are required to perform the website's basic functionality, and they are important to load the website properly. That is why Securiti performs two triggers for Opt-in compliance type cookie banners. Securiti triggers essential cookie categories as TRUE because this is a helpful approach if you want to inject dynamic scripts (which are mandatory to perform the function of a website) into your website using GTM. |
| Implicit consent for Opt-in | Same behavior as Opt-in compliance type. |
| Opt-out | In Opt-out compliance type cookie banners, all essential and non-essential cookie categories are always TRUE on the first page load when the data subject visits the website. From the second visit onwards, if the data subject provides any consent, Securiti honors that consent and passes the same information to the GTM. If the data subject changes their consent on any of their visits, at any point in time, Securiti sends out a consolidated consent to the GTM. |
| Implicit consent for Opt-out | Same behavior as Opt-out compliance type. |
| Common behavior of implicit consent with Opt-in and Opt-out | When you enable implicit consent from the module, Securiti takes the consent of your data subjects and records it in its database as is. This same information is then passed to the GTM. Securiti honors the consent values for Opt-in and Opt-out compliance types: - In the case of **Opt-in** compliance type, all **essential** cookie categories are **TRUE** and **non-essential** cookie categories are **FALSE**. - In the case of **Opt-out** compliance type, all **essential** and **non-essential** cookie categories are **TRUE**. If the data subject does not give any consent on their first visit, we take the implicit consent and store it in our database. If the data subject gives their consent on the next visit, Securiti honors it and stores this consent into the database. |

## Key points to consider for data layer variables used in GTM configuration

- Data layer data layer is a JavaScript object that you can use to pass information from your website to your Google Tag Manager container. You can then use this information to populate variables and activate triggers in your GTM tag configurations.

> [!NOTE]
> **Note**
> 
> The data layer variable always contains the latest information you pass from your website to your GTM container.
- Securiti passes the data subject’s consent given to the cookie categories present on the cookie banner. In that consent we push the cookie category name that contains consent data of the data subject.
- Once all triggers fire, the data layer variable contains the cookie category name which was last consented by the data subject.
- The data layer variable contains only the most recent cookie category name passed to it. For instance, if the data subject gives consent to the **Advertising** cookie category before submitting their consent on the cookie banner, the data layer variable will contain the name of this cookie category.

## FAQs

****How to receive consolidated data subject consent in a single variable?****

You can get the consolidated data subject consent from Securiti’s code which is configured in the GTM Watcher. Copy it and you must store this value into one of your data layer variables for further usage.

If essential cookie category is false or not available, make sure to set the essential cookie category as true always. For unique use cases, reach out to [support@securiti.ai](mailto:support@securiti.ai).

****Can I create a cookie category trigger with a custom name?****

Yes, you can and you must use the same custom cookie category name in the management portal configuration before using that in GTM.

****Why does send essential as false on the second trigger in the GTM?****

It happens when the cookie banner compliance type is Opt-in, and the data subject visits your website for the first time, and consents to any of the non-essential cookie categories from the cookie banner. Securiti sends the essential as false on the second trigger to avoid the duplicate trigger of the same cookie category.

Securiti considers the essential cookie category as mandatory on the first page load, and deems it necessary for the essential cookie category to perform basic functionality on your website on the first page load.

****Can I configure the deployment code (consent SDK) in the** `&lt;body&gt;` **tag instead of the** `&lt;head&gt;` **tag?****

Securiti's recommended best practice is to place the deployment code at the beginning of the `&lt;head&gt;` tag. This ensures that our SDK loads first, minimizing any potential delays in rendering cookie consent banners on domains.

****Why is it preferable to place the deployment code in the** `&lt;head&gt;` **tag?****

Scripts from the `&lt;head&gt;` tag always load before those from the `&lt;body&gt;` tag, and aims to load its SDK first to avoid any possible delays or unknown side effects, such as delayed rendering of cookie consent banners on your domains.

****Can I still use GTM to deploy the SDK code in the** `&lt;body&gt;` **tag?****

While deploying the deployment code (Cookie Consent SDK) in the `&lt;body&gt;` tag using GTM may work in specific cases, success isn't guaranteed due to variations in GTM configurations. You can use this approach if it works for you, but Securiti strongly recommends that you thoroughly test your cookie banner and preference center configurations in your QA or staging environments to ensure they render as expected.

****If I update cookie category names in Securiti, do they automatically update in Google Tag Manager (GTM)?****

No. If you change a cookie category name in Securiti, you must **manually** update the cookie category mapping in GTM.

For instance, if you rename the "Essential" cookie category in the cookie configuration of your domain in Securiti to "Strictly Necessary," you must also update the "Essential" cookie category trigger in GTM. Update it to "Strictly Necessary" to align with the cookie categories sent to GTM from Securiti.

Under an Opt-in cookie banner compliance type, cookies are not set on the data subject's device until they have explicitly given permission. This means that, except for strictly necessary cookies (which are essential for the basic functioning of the website), no cookies are loaded until the data subject actively consents to them. This approach is particularly common in regions like the European Union, where regulations such as the General Data Protection Regulation (GDPR) require explicit consent for the storage or access of information on a user's device.

The Opt-out cookie banner compliance type assumes consent for cookies from the outset. Here, cookies might be set on the data subject's device when they first visit your domain, but the data subject has the option to withdraw their consent and opt out of cookie usage. This model is less strict than Opt-in and is often seen in jurisdictions with less stringent privacy laws. Data subjects, website visitors, and data subjects must be given a clear and straightforward way to decline cookies, usually through the cookie preference center or settings panel.

## Related

- [Using a Securiti cookie consent banner on a Wix website](/using-a-securiti-cookie-consent-banner-on-a-wix-website.md)
- [Using a Securiti cookie consent banner on a WordPress website](/using-a-securiti-cookie-consent-banner-on-a-wordpress-website.md)
- [Using the advanced event-driven methods](/using-the-advanced-event-driven-methods.md)
