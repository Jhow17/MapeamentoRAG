---
title: "Unknown initiators"
slug: "unknown-initiators"
updated: 2026-09-23T14:20:44Z
published: 2026-09-23T14:20:44Z
canonical: "helpcenter.securiti.ai/unknown-initiators"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Unknown initiators

An initiator is an HTML resource that sets cookies. It is a `SCRIPT`, `IMG`, `IFRAME`, or `EMBED` element, and Securiti identifies it by its source URL. Initiators help you understand which resource set a cookie and when it was set.

An initiator is unknown when Securiti has no record of it. The cookie scanner never found it during a scan, and no one added it to the domain manually via the Cookie & Tracker Library. An unknown initiator belongs to no cookie category, so no consent choice applies to it.

Securiti treats an initiator as unknown when one of the following is true:

- The cookie scanner did not find it during the domain scan.
- Someone added it to your website after the scan finished.
- It appears in the cookie scan report, but you have not deployed the cookie configuration, so the change is still in draft.
- It does not belong to the domain that you scanned in Securiti.

The `data-skip-blocking` attribute is separate from this list. Securiti never blocks an initiator that carries this attribute, whether Securiti knows the initiator or not.

## What unknown initiator blocking does not do

The **Enable Auto-blocking Unknown Initiators** toggle applies only to unknown initiators. This toggle does not:

- Block unclassified initiators or known initiators in other cookie categories. Unclassified initiators are known to Securiti and belong to the Unclassified cookie category, so Securiti applies the data subject’s consent preference for that cookie category. For known initiators, the **Enable Auto-blocking** toggle handles blocking based on the data subject’s cookie category choice.
- Block known initiators in any other cookie category. The **Enable Auto-blocking** toggle controls those initiators.
- Evaluate consent. An unknown initiator belongs to no cookie category, so there is no consent preference to evaluate.
- Check whether a resource sets cookies. It blocks every unknown `SCRIPT`, `IMG`, `IFRAME`, and `EMBED` resource that Securiti has no record of.

By default, Securiti does not block unknown initiators. To block unknown initiators from running on your domain, enable the **Enable Auto-blocking Unknown Initiators** toggle from the **Consent Code** tab, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Enable Auto-blocking Unknown initiators.png)

## Cookie initiation methods

Cookies are initiated in many ways. You can review the initiation method to understand how a cookie was set. Common initiation methods include:

- Application Code (APP)
- HTTP Response Header (HTTP)
- Unknown

## When to block unknown initiators

Enable the **Enable Auto-blocking Unknown Initiators** toggle when:

- An unknown initiator might set cookies that you do not want on your domain.
- You want to protect your domain against tracking technologies that you have not identified yet.
- You want greater control over tracking technologies and unknown cookies.
- You want to review which unknown initiators Securiti blocks.

To review blocked unknown initiators, see [Auto blocking script debug methods](/latest/docs/auto-blocking-script-debug-methods).

## When not to block unknown initiators

Do not enable the **Enable Auto-blocking Unknown Initiators** toggle when:

- You want to observe which tracking technologies set cookies on your domain before you block anything.
- Your website depends on an initiator that Securiti has not scanned, and blocking it breaks the webpage or affects performance.
- The initiator path changes on every page load and shares no common pattern, so you cannot add it with a regular expression.

> [!NOTE]
> Note
> 
> If a resource is legitimate but Securiti has no record of it, you do not have to leave this toggle off. Add its initiator path to a cookie category in the **Categorize Initiator** section, such as the **Essential** cookie category, and Securiti lets it run.

## Bring unknown initiators under consent control

Blocking an unknown initiator is a temporary safeguard. To bring the initiator under consent control, resolve it instead.

1. Rescan the domain so that the cookie scanner finds the initiator, or add the initiator to the domain record manually.
2. Assign the initiator to a cookie category.
3. Redeploy the domain.

> [!NOTE]
> Note
> 
> A rescan resolves unknown initiators. It does not resolve unclassified initiators. The scanner finds an unclassified initiator again and marks it **Unclassified** again because what is missing is a decision about which cookie category it belongs to.

## Reviewing dropped cookies and initiators via developer tools

You can use developer tools to review cookies already set in the web browser and initiators that Securiti blocks on your domain.

### Review consent changes in real time

To view cookie category-level consent preference changes in real time on your website:

1. Configure and deploy a cookie banner and preference center on your domain.
2. Navigate to your domain, and open developer tools.
3. Switch to the **Console** tab.
4. Interact with the cookie banner and preference center. For instance, accept or decline a cookie category, and then submit your consent preference.
5. Review the cookie category-level changes in real time as you interact with the cookie categories, as shown below.

![Screenshot_2023-10-24_at_12_42_11_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b53f99c1-0c9f-c4a0-c0ba-f9d81e52757e.png)

### Review cookies already set in the web browser

To view cookies that are already set in the web browser:

1. Navigate to your domain, and open developer tools.
2. Switch to the **Application** tab.
3. From the left navigation panel, select **Storage > Cookies**, and then select a cookie, as shown below.

![Screenshot_2023-10-24_at_12_39_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-074daf46-d4c5-8d09-8b0d-ea99160529a9.png)
4. In the filter search box, enter the cookie name, or review the **Name** column to find the cookie, as shown below.

![Screenshot_2023-10-24_at_12_39_40_PM_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea342db0-2e86-829f-89db-a73200741b74.png)
5. You can use the **Domain** column to search for a cookie, as shown below. ![Screenshot_2023-10-24_at_12_39_59_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c69ebf87-5a93-ab8a-65fa-0db1cfc8cf95.png)

## Related

- [Cookie Consent Management terminologies](/cookie-consent-management-terminologies.md)
- [Resolving cookie categorization conflicts in auto-blocking](/resolving-cookie-categorization-conflicts-in-auto-blocking.md)
