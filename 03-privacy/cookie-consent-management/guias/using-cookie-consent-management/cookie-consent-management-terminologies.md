---
title: "Cookie Consent Management terminologies"
slug: "cookie-consent-management-terminologies"
status: "update"
updated: 2026-09-23T13:49:24Z
published: 2026-09-23T13:49:24Z
canonical: "helpcenter.securiti.ai/cookie-consent-management-terminologies"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Cookie Consent Management terminologies

This help article defines the key terms that Securiti uses in the Cookie Consent Management module. It explains how Securiti classifies cookies, how it groups them into the out-of-the-box (OOTB) cookie categories, and how it enforces consent through initiators.

In brief:

- Securiti treats every cookie as either **known** or **unknown**.
- Every known cookie is either **Essential** or **Non-Essential**.
- **Unclassified** cookies are one type of **Non-Essential** cookies. Securiti places them in the **Unclassified** cookie category until you assign them to a specific cookie category.
- Securiti enforces consent by blocking **initiators**, not by blocking cookies.

Use the following table to understand key terms and how Securiti applies them in Cookie Consent Management:

| Term | Description | Additional details |
| --- | --- | --- |
| Cookie category | A group of similar cookies, such as **Analytics & Customization**, **Advertising**, or **Essential**. Cookie categories determine how consent preferences apply to cookies on a domain. | The cookie banner and preference center are organized by cookie category. A cookie category also determines whether cookies in that category are treated as **Essential** or **Non-Essential**. |
| Always Active | A cookie category setting that prevents data subjects from turning off the category because the cookies in it are required for the website to function. | Every cookie in an **Always Active** cookie category is treated as an **Essential** cookie. |
| Known cookies | Cookies that Securiti has a record of because Securiti found them during a cookie scan or because a user added them manually to the domain record. | You can view and manage known cookies in Securiti. Every known cookie is either **Essential** or **Non-Essential**, depending on its cookie category. |
| Unknown cookies | Cookies that Securiti detects on the live website but does not have a matching record for. Securiti has not found these cookies in a scan and you have not added them manually. | Unknown cookies do not belong to any cookie category, and are not present in the cookie preference center, so data subjects cannot accept or reject them. Securiti does not block unknown cookies directly. When you enable the **Enable Auto Blocking Unknown Initiators** toggle, Securiti blocks the unknown initiators that would would carry those cookies. To bring an unknown cookie under consent control, rescan the domain or add the cookie to the domain record, then assign it to a cookie category. |
| Essential cookies | Cookies that belong to a cookie category marked **Always Active**. These cookies are required for core website functionality. | Data subjects cannot reject Essential cookies. Some organizations also call these cookies **Strictly Necessary** cookies. |
| Non-essential cookies | Cookies that belong to a cookie category that is not marked **Always Active**. | Data subjects can accept or reject Non-Essential cookies through the cookie banner or preference center, depending on the configured consent experience. Unclassified cookies are one type of Non-Essential cookie. |
| Classified cookies | Known cookies that have been placed into a cookie category. | Every classified cookie is either **Essential** or **Non-Essential**, depending on its cookie category. A cookie that has not been placed into a cookie category remains unclassified. |
| Unclassified cookies | Known cookies that Securiti found during a scan or that you added manually, but that have not yet been assigned to a specific cookie category, such as **Advertising**, **Analytics & Customization**, or **Essential**. | **Unclassified** cookies are one type of **Non-Essential** cookie. **Unclassified** is a standard cookie category. It appears in the preference center alongside cookie categories such as **Advertising** and **Analytics & Customization**, and data subjects can accept or reject it. Assign each unclassified cookie to a specific cookie category. Securiti keeps your assignment for future scans of the same domain. A rescan on its own does not resolve unclassified cookies because the scanner finds them again and marks them **Unclassified** again. |
| Initiator | An HTML resource that can set cookies. An initiator is a `SCRIPT`, `IMG`, `IFRAME`, or `EMBED` element, and Securiti identifies it by its source URL. | Securiti associates each initiator with one or more cookie categories. The cookie scanner creates this association automatically, or a Domain Admin creates it manually. The auto-blocking script acts on initiators, not on cookies. Not every cookie has an initiator. A cookie that a server sets in an HTTP response header, for example, has none. |
| Unknown initiator | An initiator that Securiti has no record of. The cookie scanner did not find it during a scan, and no one added it to the domain manually. | An unknown initiator belongs to no cookie category, so no consent choice applies to it. Only the **Enable Auto-blocking Unknown Initiators** toggle blocks it. To bring it under consent control, rescan the domain or add it manually, then assign it to a cookie category. |
| Unclassified initiator | A known initiator that Securiti found during a scan, or that a Domain Admin added manually, that no one has assigned to a specific cookie category. | An unclassified initiator sits in the **Unclassified** cookie category, so the data subject’s choice on that cookie category controls it. The **Enable Auto-blocking Unknown Initiators** toggle does not apply to it. Assign the initiator to a cookie category to resolve it. |
| Auto-blocking script | The Securiti JavaScript that blocks initiators. It must be the first script in the `&lt;head&gt;` tag of your webpage. | The auto-blocking script watches `SCRIPT`, `IMG`, `IFRAME`, and `EMBED` elements. It does not read cookies and it does not delete them. When it blocks an initiator, the cookies that the initiator would have set are never set. If the initiator already set cookies in the web browser before Securiti blocked it, those cookies stay in the web browser, but they become ineffective because the initiator no longer runs. To delete those cookies, you must use a custom script on your website. |

> [!NOTE]
> Note
> 
> **Unclassified** cookies and **Unknown** cookies are different, although they can seem similar. Here are the main differences:
> 
> - An **Unclassified** cookie is already known to Securiti either because Securiti detected it during a scan, or because you added it manually. Securiti places it in the **Unclassified** cookie category until you assign it to a another cookie category, such as **Advertising**, **Analytics & Customization**, or **Essential**.
> - An **Unknown** cookie is not known to Securiti at all. No scan found it and no one added it manually via Cookie & Tracker Library.
> 
> The same distinction applies to initiators. An unclassified initiator is known to Securiti and sits in the **Unclassified** cookie category. An unknown initiator is not known to Securiti and belongs to no cookie category.

For more information, see [Understanding how Securiti categorizes cookies and trackers](/latest/docs/understanding-how-securiti-categorizes-cookies-and-trackers).

## How auto-blocking works

Securiti enforces cookie consent through the auto-blocking script. The script runs on your website and decides which resources load.

The auto-blocking script monitors the following element types:

- `SCRIPT`
- `IMG`
- `IFRAME`
- `EMBED`

The script identifies each element by its source URL and matches that URL against the initiators that Securiti holds for your domain. It does not read cookies and it does not delete them. When it blocks an initiator, the cookies that the initiator would have set are never set. Stopping a cookie is the result of blocking an initiator, not the method.

### Consent applies to cookie categories, not to individual initiators

Data subjects accept or decline cookie categories in the cookie banner and preference center. They do not accept or decline a single initiator.

Securiti associates every initiator with one or more cookie categories. The cookie scanner creates the association during a scan, or a domain admin creates it in the **Categorize Initiator** section.

Auto-blocking then works as follows:

1. A data subject declines a cookie category.
2. Securiti finds the initiators associated with that cookie category.
3. The auto-blocking script blocks those initiators.
4. The cookies that those initiators would have set are never set.

> [!WARNING]
> Important
> 
> Securiti never blocks the initiators in a cookie category marked **Always Active**, such as **Essential**. Data subjects cannot decline those cookie categories.

## Unknown initiators and unclassified initiators

Unknown initiators and unclassified initiators describe different situations. Securiti handles them through different auto-blocking paths.

Use the following table to understand the difference between unknown initiators and unclassified initiators:

| Attribute | Unknown initiator | Unclassified initiator |
| --- | --- | --- |
| Securiti record | Securiti has no record of the initiator. The scanner did not find it, and you did not add it manually. | Securiti has a record of the initiator because the scanner found it or you added it manually. |
| Category | No category exists for the initiator, so Securiti has no consent category to evaluate. | The initiator is known but has not been assigned to the correct cookie category. |
| Preference center visibility | The data subject cannot see or consent to the initiator because it has no category. | The data subject can see and control the related category if it appears in the preference center. |
| Consent control | Data subject consent cannot control the initiator because there is no category mapping. | Data subject consent can control the initiator once it is mapped to a category. |
| Blocking behavior | Securiti blocks it only when **Enable Auto-blocking for Unknown Initiators** toggle is enabled. | Securiti blocks it through normal category-based consent enforcement when the related category is denied. |
| Resolution | Rescan the domain so Securiti can discover the initiator, or add the initiator manually. Then assign it to the appropriate category. | Assign the initiator to the appropriate cookie category. A rescan does not resolve the missing category decision. |

## Auto-blocking toggles

Securiti uses separate toggles for category-based auto-blocking and unknown initiator blocking.

Use the following table to understand how each toggle works:

| Toggle | What it blocks |
| --- | --- |
| **Enable Auto-blocking** toggle | Blocks known initiators that belong to a cookie category the data subject denied. This toggle uses the data subject’s consent for each cookie category. |
| **Enable Auto-blocking Unknown Initiators** toggle | Blocks initiators that Securiti has no record of and cannot map to a cookie category. Since an unknown initiator belongs to no cookie category, there is no data subject consent to apply. > [!WARNING] > Important > > The **Enable Auto-blocking Unknown Initiators** toggle blocks every unknown `SCRIPT`, `IMG`, `IFRAME`, and `EMBED` resource that Securiti has no record of, whether or not that resource sets cookies. > > However, it does not apply to unclassified initiators. Unclassified initiators are known to Securiti and belong to the **Unclassified** cookie category, so the data subject’s consent preference for that cookie category controls them. |

For more information on how to configure these toggles, see Automatically blocking scripts from dropping cookies.

## How the Unclassified cookie category behaves

**Unclassified** is a standard cookie category. It is not **Always Active**, so it behaves the same way as any other non-essential cookie category, such as **Advertising**.

- It appears in the preference center, and data subjects can accept or reject it.
- Under the Opt-out compliance type, its initiators run until a data subject declines the cookie category.
- Under the Opt-in compliance type, its initiators run only after a data subject accepts the cookie category.
- The **Enable Auto-blocking Unknown Initiators** toggle does not apply to it because its initiators are known to Securiti.

Assign unclassified cookies to a specific cookie category. Until you do, data subjects see them in the preference center as **Unclassified**, and under the Opt-out compliance type, Securiti enables them by default. Securiti keeps your assignment for future scans of the same domain.

After a scan finds unclassified cookies, Securiti emails domain co-owners a **Review Scan Changes** notification that lists them, so that they can assign each one to a cookie category. Securiti also records unclassified cookie detections in the scan log.

For more information on the behavior of the **Unclassified** cookie category under each compliance type, see Automatically blocking scripts from dropping cookies.

## How auto-blocking handles existing cookies

The auto-blocking script prevents initiators from running. It does not remove cookies that a page already set.

Under the Opt-out and Notice Only compliance types, Securiti treats the data subject as opted in on the first page load, so initiators run and set their cookies at that moment. When the data subject declines the cookie category later:

- Securiti blocks those initiators on subsequent page loads, so they set no new cookies.
- The cookies already in the web browser stay there. Securiti does not delete them.

Under the Opt-out compliance type, blocking the initiator also renders the cookies that are already set ineffective because the third-party initiators that would send them back to third-party servers no longer run.

Under an Opt-out consent banner compliance type, the mobile app's SDKs are active by default. However, mobile app users can visit the consent preference center to withdraw their consent and Opt-out of optional SDK usage. This approach is less strict than Opt-in compliance type and is common in jurisdictions with less stringent privacy laws.

Under an Opt-in consent banner compliance type, the app's non-essential SDKs remain inactive until a mobile app user explicitly grants consent. Only strictly necessary SDKs (which are essential for basic functioning of the app) are active by default. This approach aligns with privacy regulations such as GDPR, which require explicit consent before accessing data or storing information on a mobile app user’s device.

## Related

- [Categorizing your website cookies](/categorizing-your-website-cookies.md)
- [Understanding how Securiti categorizes cookies and trackers](/understanding-how-securiti-categorizes-cookies-and-trackers.md)
- [Automatically blocking scripts from dropping cookies](/automatically-blocking-scripts-from-dropping-cookies.md)
- [Unknown initiators](/unknown-initiators.md)
