---
title: "Resolving cookie categorization conflicts in auto-blocking"
slug: "resolving-cookie-categorization-conflicts-in-auto-blocking"
updated: 2026-04-06T15:58:58Z
published: 2026-04-06T15:58:58Z
canonical: "helpcenter.securiti.ai/resolving-cookie-categorization-conflicts-in-auto-blocking"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Resolving cookie categorization conflicts in auto-blocking

**Scenario**

As a Data Compliance Officer, you need to ensure that each cookie is blocked or allowed according to its category. For instance, some scripts may drop both essential and non-essential cookies, creating conflicts in how they should be treated before consent. Without proper checks, these conflicts can lead to misconfiguration and compliance risks. With Securiti such conflicts are flagged during draft or published reviews, allowing you to resolve them before deployment. This helps you avoid misconfigurations and protect the rights of your data subjects more accurately.

You can use Securiti's enhanced auto-blocking functionality to resolve cookie categorization conflicts that occur when an initiator script drops several cookies that span multiple cookie categories. This functionality brings the cookie categorization conflicts to the surface for you, and lets you resolve these conflicts before deploying changes to the cookie banner and preference center of your domain.

> [!NOTE]
> **Note**
> 
> Autoblocking treats initiator URLs with and without the `www` prefix as equivalent. If an initiator is allowed or blocked, the same action applies to both forms of the URL, regardless of whether the `www` prefix is present.

When categorizing cookies, if an initiator script drops cookies into both **Essential** and **Non-Essential** cookie categories, a banner informs you of this conflict, as shown below.

![Resolving_conflicts_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba9ec9e4-fc18-0ede-3423-a924d6e96397.png)

Securiti shows these conflicts based on the **latest draft** or **published version** of your cookie configuration, ensuring you're always informed of the most current issues.

If you have a draft containing cookie configuration changes with conflicts, Securiti shows the cookie categorization conflicts of this draft because it takes precedence over the published version. If no draft exists and all changes are published, but conflicts are present, then Securiti displays the conflicts from the published version.

> [!NOTE]
> **Note**
> 
> You must have auto-blocking enabled for your Securiti tenant to use this functionality.

To resolve cookie categorization conflicts:

1. In Securiti, open Cookie Consent Management, and choose **Cookie Consent > Domains**.
2. On the Cookie Consent Domains page, click the card for the domain for which you want to resolve cookie categorization conflicts.
3. Click the **Categorize Cookies** tab.
4. Below the Categorize Cookies tab, from the right side of the yellow banner, click **View & Edit Initiators List**, as shown below.

![Resolving_conflicts_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba9ec9e4-fc18-0ede-3423-a924d6e96397.png)
5. On the **Initiators List** page, from the left side you can view the list of all initiators that drop cookies in your domain, as shown below.

![Initiators-List.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-60dd10a3-6cf6-3f79-c279-749ad7689972.png)

From the initiator list on the left side, from the upper right corner, enable the **Conflicts Only** toggle to view the initiators with the conflicts, as shown below.

![Filtered-Initiators-List.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ea0f9d3b-403e-7175-7eaf-6e659a18f10f.png)
6. First, click the initiator whose conflicts you wish to resolve. Then, expand the cookie categories highlighted in red to view the conflicting cookies, For instance, see the following screenshot where cookies from the selected initiator are categorized as both **Essential** and **Non-Essential**.

![Expanded-conflicting-cookie-categories.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-376bf9a0-01ec-d3ff-bfb1-b32c0fb6446b.png)
7. To resolve conflicts for cookies that fall into multiple categories but are dropped by a single initiator, mark the checkbox next to each cookie to reclassify it as either **Essential** or **Non-Essential**.
8. On the **Cookie Selected** banner near the bottom of the page, from the right side click **Reassign Category**, as shown below.

![Selected-cookies.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1345137-5592-a17d-503b-f16e96df9efe.png)
9. On the **Reassign Category** popup, from the **Select Destination Cookie Category** menu, select the cookie category in which you want to classify the selected cookie to resolve the categorization conflicts, as shown below.

In the following screenshot, we are reassigning conflicting cookies from the **Essential** cookie category to the **Analytics** (Non-Essential) cookie category.

![Reassign-menu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-606b00dd-a142-3ec6-7fb0-3454b41150d4.png)
10. On the **Reassign Category** popup, click **Reassign** to save this change, as shown below.

![Reassign-category-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85401f5a-569d-df58-036f-819cb570921e.png)
11. Do this for other initiators that are dropping cookies in both **Essential** and **Non-Essential** cookie categories and causing conflicts.
12. Once done, on the Initiators List page, from the upper right corner, click **+ Apply** to save your changes.
13. On the Cookie Configuration page, from the upper right corner, click **Deploy**, as shown below.

![Resolving_conflicts_9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d6f0e7b-07c5-2b9f-bb0d-db86ca09c113.png)
14. Follow the procedure on the on **Publish Code** popup, and near the bottom of the popup, click **Publish** to publish all these accurate cookie changes to your domain.

### Filtering the Initiators List

On the Initiators List page, you can use the horizontal filter bar above the initiators data table, to actively filter specific trackers and cookies by various types, as shown below.

![Filter-bar.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9bf55098-4de6-2e83-b7bd-180266ffbc92.png)

Use the following table to understand the filter options and and their effects:

| Filter | Description |
| --- | --- |
| Service Name | Lets you filter cookies and trackers by their service name. For instance, you can filter cookies and trackers that are dropped by the same service such as LinkedIn or Google. |
| Cookie Category | Lets you to filter for specific cookies and trackers within their respective categories. For instance, you can select the **Analytics** cookie category, and the filter returns all conflicting cookies belonging to this cookie category. > [!NOTE] > **Note** > > The filter only displays cookie categories that contain conflicting cookies dropped by the selected initiator. |
| Tracker Domain | Lets you filter cookies and trackers based on their point of origin. For instance, you can filter cookies and trackers based on the domains where they were detected by the cookie scanner |
| Tracker Type | Lets you filter cookies and trackers based on the following types: - Beacon - Cookie - Local storage item - Session storage item |
| First/Third Party Type | Lets you filter cookies and trackers based on their party type. For instance, you can filter out cookies and trackers between first-party and third-party types. |

To apply these filters:

1. Click the initiator whose conflicts you wish to resolve.
2. Click the filter type that you want to apply. For instance, if you want to filter cookies and trackers based on their party type, click **First/Third Party**.
3. From the menu, select a value, as shown below. Securiti instantly filters cookies and trackers associated with the selected value.

![Example-filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0cfd02e-d5a7-c26a-6b25-736e9645dc51.png)

Securiti lets you select all filters depending on your search need, as shown below.

![All-filters-selected.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59e8df1f-ef37-d70b-f538-ce1753310d67.png)

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

Initiator (in the context of web requests) is an entity that triggers a request for a resource such as a web page, an image, or a script to be loaded from a server. Initiators help in tracking and data collection because they can be associated with third-party domains that set tracking cookies or collect data.

A web beacon is a small, usually transparent image embedded on a website or email that tracks the behavior of data subjects.

Local storage item stores the data in a persistent manner until the user manually clears the browser cache or until the web application clears the data.

Session storage item stores the data in a persistent manner only until the window or tab is closed.

## Related

- [Automatically blocking scripts from dropping cookies](/automatically-blocking-scripts-from-dropping-cookies.md)
- [Unknown initiators](/unknown-initiators.md)
