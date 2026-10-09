---
title: "Automatically blocking scripts from dropping cookies"
slug: "automatically-blocking-scripts-from-dropping-cookies"
status: "update"
updated: 2026-09-23T13:56:51Z
published: 2026-09-23T13:57:45Z
canonical: "helpcenter.securiti.ai/automatically-blocking-scripts-from-dropping-cookies"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Automatically blocking scripts from dropping cookies

**Scenario**

As a Data Privacy Officer, you need to block non-essential cookies until data subjects’ consent preferences are recorded. For instance, when you deploy a new cookie banner, manually identifying and blocking each script can take time and increase the risk of missed trackers. With Securiti’s Cookie Consent Management module, you can enable Auto-blocking to enforce consent choices for known initiators and optionally block unknown initiators that Securiti has no record of. This helps you apply consent behavior consistently across your website.

You can automatically block the initiators that set cookies, image beacons, local storage items, and session storage items when a data subject opts out of a cookie category.

Securiti blocks at the initiator level. An initiator is an HTML resource that sets cookies, such as a `SCRIPT`, `IMG`, `IFRAME`, or `EMBED` element. The auto-blocking script does not read cookies and it does not delete them. It matches each initiator against the cookie categories you mapped it to, and blocks the initiator when a data subject declines that cookie category. The cookies that the initiator would have set are then never set.

> [!NOTE]
> **Note**
> 
> Auto-blocking treats initiator URLs with and without the `www` prefix as equivalent. If an initiator is allowed or blocked, the same action applies to both forms of the URL, regardless of whether the `www` prefix is present.

## How auto-blocking decides what to block

Auto-blocking runs in three steps.

1. A data subject accepts or declines a cookie category in the cookie banner or preference center. Data subjects choose cookie categories. They do not choose individual initiators.
2. Securiti finds the initiators mapped to that cookie category. The cookie scanner creates this mapping during a scan, or you create it manually in the **Categorize Initiator** section.
3. The auto-blocking script blocks those initiators. The cookies that they would have set are never set.

> [!NOTE]
> Note
> 
> The auto-blocking script does not remove cookies that a page already set. Under the Opt-out and Notice Only compliance types, initiators run on the first page load, so their cookies are set at that moment. When a data subject later declines the cookie category, Securiti blocks the initiator on subsequent page loads, but the cookies already in the web browser stay there.Your content goes here

The auto-blocking behavior is determined by the compliance type you configure on the **Customize Banner and Preference Center > Configuration & Mapping** subtab.

Use the following table to understand auto-blocking behavior for each compliance type:

| Compliance type | Auto-blocking script behavior |
| --- | --- |
| **Notice Only** | Securiti lets all initiators run on the initial page load. If a data subject later updates consent preferences for a cookie category, Securiti records the consent behavior and honors the updated preference from the next page load. Cookies that were already set stay in the web browser. |
| **Opt-out** | Securiti treats the data subject as opted in until they opt out. Initiators for non-essential cookie categories run until the data subject declines the related cookie category. After the data subject opts out, Securiti blocks the related initiators on subsequent page loads. Cookies that were already set stay in the web browser, but the blocked third-party initiators can no longer send them back to third-party servers. |
| **Opt-in** | Securiti withholds initiators for non-essential cookie categories on the initial page load. The initiators run only after the data subject gives consent to the related cookie category. |
| **Hybrid** | Auto-blocking follows the consent state you configure for each cookie category. A cookie category set to **Declined** behaves as it does under Opt-in. A cookie category set to **Granted** behaves as it does under Opt-out. A cookie category marked **Always Active** behaves as Essential. |

> [!NOTE]
> **Note**
> 
> - Scripts that set Essential cookies are always allowed to run.
> - When data subjects use web browser extensions that modify the behavior of their web browsers, Securiti’s SDK and auto-blocking script are subject to the behavior imposed by those extensions. Interference from such extensions can prevent Securiti scripts from working as expected.

## Why there are two auto-blocking toggles

The two toggles are not two strengths of the same setting. They follow different decision paths and use different inputs.

Use the following table to understand the difference between the two toggles:

| **Toggle** | **What it blocks** | **What it uses to decide** |
| --- | --- | --- |
| **Enable Auto-blocking** toggle | Known initiators whose cookie category a data subject declined or by default non essential cookies are declined. | The data subject’s consent for each cookie category. Securiti never blocks initiators in an Essential or Always Active cookie category. |
| **Enable Auto-blocking Unknown Initiators** toggle | Any initiator that Securiti has no record of. | Nothing from the data subject. An unknown initiator belongs to no cookie category, so there is no consent to apply. This toggle applies a blanket block. |

To summarize:

- **Enable Auto-blocking** toggle enforces what the data subject decides and what default cookie banner compliance type is.
- **Enable Auto-blocking Unknown Initiators** blocks an initiator because it has no cookie category at all.

> [!WARNING]
> Important
> 
> The **Enable Auto-blocking Unknown Initiators** toggle blocks every unknown `SCRIPT`, `IMG`, `IFRAME`, and `EMBED` resource that Securiti has no record of, whether or not that resource sets cookies. Test it in a QA or staging environment before you enable it in production because it can block resources that your website needs. This toggle does not apply to unclassified initiators.
> 
> 
> 
> Unclassified initiators are known to Securiti and belong to the Unclassified cookie category, so the data subject’s consent preference for that cookie category controls them.

For more information, see Unknown initiators.

## How unclassified cookies behave under each compliance type

**Unclassified** is a standard cookie category. It is not **Always Active**, so it behaves the same way as any other non-essential cookie category, such as **Advertising** or **Analytics & Customization**. It appears in the preference center, and data subjects can accept or reject it.

Use the following table to understand how the **Unclassified** cookie category behaves under each compliance type:

| Compliance type | Behavior of the Unclassified cookie category |
| --- | --- |
| Notice Only | All initiators run on the first page load, including initiators in the **Unclassified** cookie category. Securiti records any later change and honors it from the next page load. |
| Opt-out | Securiti treats the data subject as opted in, so initiators in the **Unclassified** cookie category run on the first page load and set their cookies. When the data subject declines the **Unclassified** cookie category, Securiti blocks those initiators on subsequent page loads. The cookies that are already in the web browser stay there. |
| Opt-in | Securiti withholds initiators in the **Unclassified** cookie category on the first page load. They run only after the data subject accepts the **Unclassified** cookie category. |
| Hybrid | The **Unclassified** cookie category follows the consent state you configure for it. A cookie category set to **Declined** behaves as it does under Opt-in. A cookie category set to **Granted** behaves as it does under Opt-out. |

> [!WARNING]
> Important
> 
> Assign unclassified cookies to a specific cookie category. Until you do, data subjects see them in the preference center as **Unclassified**, and under the Opt-out compliance type, Securiti enables them by default. Assigning a cookie also improves future scans because Securiti keeps your assignment for later scans of the same domain.

## What auto-blocking does not block

Securiti’s auto-blocking script blocks initiators associated with tracking elements detected during cookie scans, including **cookies**, **image beacons**, **local storage items**, and **session storage items**. When Securiti detects `navigator.sendBeacon()` calls, `Fetch` and `XHR` requests to known tracker domains, or chained tracker requests, it traces these requests back to their initiating script. It then blocks at the script level, preventing the associated beacons from firing.

However, auto-blocking does not block scripts or network calls that Securiti does not associate with detected tracking elements. You must ensure that your website does not run scripts or network calls that drop tracking elements after data subjects decline consent.

This feature does not block the following:

- Initiators in a cookie category marked **Always Active**, such as **Essential**.
- Initiators in a cookie category for which you disabled Opt-out.
- Cookies that a script sets inline in the page HTML.
- Cookies that a server sets in an HTTP response header because these cookies have no initiator.
- Initiators that Securiti did not detect during a scan, unless you enable the **Enable Auto-blocking Unknown Initiators** toggle.
- Initiators that carry the `data-skip-blocking` attribute.

> [!NOTE]
> **Note**
> 
> - Embed the auto-blocking script directly in the `&lt;head&gt;` tag. Do not implement it inside a Tag Management System. The auto-blocking script must load before all other tags.
> - If your domain uses a plugin that optimizes page performance by lazy loading scripts, such as the Rocket plugin for WordPress, exclude the auto-blocking script from lazy loading.
> - If a page has a script that sets non-essential cookies and you want to skip blocking the cookies it sets, add the `data-skip-blocking` attribute to that script element. The auto-blocking logic ignores these tags.
> 
> ```javascript
> <script src="https://example.com/examplescript.js" data-skip-blocking></script>
> ```
> - To manage or restrict local and session storage items that Securiti does not detect or associate with initiators, implement controls within your website code or tag management setup.

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. On the **Cookie Consent Domains** page, click the domain where you want to implement auto-blocking.
3. Near the upper right corner of the page, click **Edit**, then click the **Consent Code** tab.
4. Scroll to the bottom of the page and enable the **Enable Auto-blocking** toggle. To also block initiators that Securiti has no record of, enable the **Enable Auto-blocking Unknown Initiators** toggle, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(90).png)
5. Copy the auto-blocking code and paste it into the code for your page so that it is the first script in the `&lt;head&gt;` of the page.

> [!WARNING]
> **Important**
> 
> Copy the auto-blocking testing code into your QA or staging environment and test it there before you deploy auto-blocking to production.

The script must be the first script in the `&lt;head&gt;` tag so that it can monitor page loading and block cookie-setting scripts and frames before they run.

> [!NOTE]
> **Note**
> 
> Do not add the `async` attribute to the auto-blocking script. The script must run synchronously. Adding the `async` attribute lets the rest of the page continue loading while the auto-blocking script runs, which can prevent auto-blocking from working as intended.

1. Add an initiator path to a cookie category through the **Categorize Initiator** section, as shown below. This lets you assign an initiator URL to the cookie category that should control it. ![Screenshot_2023-09-11_at_12_50_42_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60c4f94a-9c2b-1326-af29-91a93a3d8cd2.png)

![Screenshot_2023-09-11_at_12_51_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e91e5ab-aa27-05ff-3b16-60193293a76b.png)

For instance, Google Tag Manager usually carries initiators in the **Advertising** or **Analytics & Customization** cookie category. If your website needs Google Tag Manager to run without interruption, assign its initiator to the **Essential** cookie category. Securiti then lets it run on every page load, regardless of the data subject’s consent preference for **Advertising** or **Analytics & Customization**.

> [!NOTE]
> **Note**
> 
> Adding initiator paths to cookie categories lets Securiti apply category-based Auto-Blocking to those initiators.
> 
> - Click **+ Add Initiator Path**, and select the cookie category for the initiator path.
> - Add the URL in the **Initiator URL** field, and from the upper right corner of the **Cookie Configuration** page, click **Save** to save your changes.
> - Click **Deploy** to deploy the change to your domain.
2. Redeploy the domain.

## When one initiator serves several cookie categories

A single initiator can set cookies that belong to more than one cookie category. Securiti blocks or lets the whole initiator run, so it cannot block part of what that initiator does.

If a data subject declines one of those cookie categories, Securiti blocks the initiator. The cookies that would have belonged to the cookie categories the data subject accepted are then not set either.

To find these cases, open the domain and review the **Initiator Conflicts** screen. Reassign the initiator, or split the resource, so that each initiator serves one cookie category.

## Related

- [Categorizing your website cookies](/categorizing-your-website-cookies.md)
- [Unknown initiators](/unknown-initiators.md)
- [Cookie Consent Management terminologies](/cookie-consent-management-terminologies.md)
- [Resolving cookie categorization conflicts in auto-blocking](/resolving-cookie-categorization-conflicts-in-auto-blocking.md)
