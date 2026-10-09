---
title: "Using Cross-Domain Consent Groups to sync consent across domains"
slug: "using-cross-domain-consent-groups-to-sync-consent-across-domains"
updated: 2026-09-16T09:16:21Z
published: 2026-09-16T09:17:45Z
canonical: "helpcenter.securiti.ai/using-cross-domain-consent-groups-to-sync-consent-across-domains"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using Cross-Domain Consent Groups to sync consent across domains

**Scenario**

As a Data Privacy Officer, you need to provide a consistent consent experience across multiple domains that share the same consent requirements. For instance, when a data subject provides consent on one domain and then visits another domain in the same group, they should not see a repeated cookie banner if the same consent preferences already apply. With Cross-Domain Consent Groups, you group eligible domains, share consent preferences across those domains, and help data subjects maintain consistent privacy choices across their browsing journey.

Cross-Domain Consent Groups let you share and apply a data subject's consent preferences across multiple domains and subdomains that you manage in Securiti. Instead of managing consent settings individually for each domain, you can group your domains together so that a data subject's consent preference on one domain applies automatically across all other eligible domains in the group. When a known data subject provides consent on one domain, Securiti maps each domain's cookie categories to its standard cookie categories to determine which consent preferences can be shared, ensuring a consistent consent experience for data subjects across all your web properties.

> [!WARNING]
> **Important**
> 
> Cross-Domain Consent Groups synchronize consent only for domains that belong to the same configured Cross-Domain Consent Group. For instance, if a data subject provides consent through the cookie banner or preference center while accessing one of these domains from a mobile web browser on an Android or iOS device, that consent is synchronized across all other domains in the same Cross-Domain Consent Group. This behavior does not apply to native mobile applications.

Securiti uses a unique subject identifier to link a data subject's consent records across domains and web browser sessions. If a domain introduces new purposes, uses different category mappings, or has no existing consent record for the data subject, Securiti may show the cookie banner again to collect or update consent.

## How cross-domain consent works

When Securiti identifies a known data subject, it links their consent preferences to a unique subject identifier and applies the relevant consent state across every domain in the same Cross-Domain Consent Group. This keeps consent preferences consistent across websites and web browser sessions.

If a domain introduces new purposes, uses different cookie category mappings, or has no existing consent record for the data subject, Securiti might show the cookie banner again to collect or update consent.

Securiti also honors Global Privacy Control (GPC) across the group. If a data subject enables GPC in their web browser on any domain in the group, Securiti treats the resulting Opt-out as the most restrictive consent state. Securiti then applies that Opt-out across all cookie categories mapped to GPC in the group, unless the data subject explicitly updates a category afterward.

> [!WARNING]
> **Important**
> 
> Securiti currently supports consent sharing only between domains with the same GPC configuration. To ensure consistent consent synchronization, include only GPC-enabled domains together or only non-GPC-enabled domains within the same Cross-Domain Consent Group. For instance, if domain A, domain B, and domain C have GPC enabled, group them together. If domain D and domain E do not have GPC enabled, create a separate Cross-Domain Consent Group for those domains. Do not mix GPC-enabled and non-GPC-enabled domains within the same group.

## Key considerations

Review the following considerations before creating a Cross-Domain Consent Group:

| Consideration | Description |
| --- | --- |
| Domain eligibility | You can add only eligible domains to a Cross-Domain Consent Group. A domain is eligible if it meets all of the following conditions: - It has a successful scan. - You've deployed it at least once. - It doesn't use an IAB consent framework configuration. - It isn't already part of another Cross-Domain Consent Group. |
| IAB consent frameworks | Cross-Domain Consent Groups don't support domains configured with IAB consent frameworks in the current version. |
| Category mapping responsibility | You're responsible for mapping domain-level cookie categories to the correct standard categories. Incorrect mapping can result in inaccurate consent behavior and compliance risk. |
| Consent synchronization delay | When a data subject accesses an authenticated experience from a different web browser for the first time, consent preferences may take up to 30 minutes to synchronize. For instance, if a data subject provides consent using Google Chrome and later signs in using Mozilla Firefox, the initial synchronization process reconciles consent records across web browsers to identify the data subject's most recent consent preferences. This delay only applies during the first login from the new web browser. After the initial reconciliation is complete, future consent updates synchronize normally across supported web browsers. |
| GPC handling | Securiti treats an active GPC signal as the most restrictive consent state and shares the resulting Opt-out across all mapped cookie categories in the group, unless the data subject later updates a category explicitly. |
| Implementation requirement | You must add the Cross-Domain Consent Group code snippet before the Cookie Consent SDK script so Securiti can recognize the known data subject and sync consent correctly. |
| Cookie banner and preference center content | Configure your cookie banner and preference center to clearly communicate that consent applies across multiple domains or devices. |

## Procedure

To create and configure a Cross-Domain Consent Group:

1. In Securiti, open **Cookie Consent Management**, and choose **Explorers > Cross-Domain Consent Groups**.
2. Near the upper right corner, click **+ New Group**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-New-Group.png)
3. In **Cross-Domain Consent Group Name**, enter a name for the group.
4. Click **Create & Configure**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New-Cross-Domain-Consent-Group-Popup.png) Securiti creates the group and opens the **Group Configuration** tab.
5. In the **Consent Group Details** section, from the **Select Domains** menu choose the domains you want to include in the group.

> [!WARNING]
> **Important**
> 
> You can add only eligible domains to a Cross-Domain Consent Group. A domain is eligible if it meets all of the following conditions:
> 
> - It has a successful scan.
> - You've deployed it at least once.
> - It doesn't use an IAB consent framework configuration.
> - It isn't already part of another Cross-Domain Consent Group.
6. (Optional) To show custom cookie banner text, mark the **Show additional text in cookie banner** checkbox, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Show-Additional-Text-In-Cookie-Banner-checkbox.png)
  1. In the **Banner Text** text area, enter the additional message that should appear with the cookie banner.
7. (Optional) Mark the **Show grouped domains in the preference center** checkbox to control whether grouped domains appear in the preference center, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Show-Grouped-Domains-in-Preference-Center-checkbox.png)
  1. In the **Group Title** text field, enter the title that should appear in the preference center.
  2. In the **Group Description** text area, enter the description that should appear in the preference center.
8. From near the upper right corner, click **Save**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Save-Group-Configuration.png.png)
9. In the left panel, from the **Consent** section, select **Consent Options**.
10. Under **Consent Recording Mode**, select how you want Securiti to record consent when a data subject interacts across multiple domains or web browser sessions:

| Consent Recording Mode | Description |
| --- | --- |
| Use Latest Consent | Records the data subject's most recent consent preference as the final consent across domains and web browser sessions. |
| Use Consent After Login | Applies consent after the data subject logs in, linking it to their known profile. Consent recorded by an unknown data subject is overridden once they log in and provide consent. |
11. From near the upper right corner, click **Save**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Consent-Options-Save.png)
12. In the left panel, from the **Categories** section, select **Category Mapping**.
13. To view the category mapping of a domain, select it from the **Domains** list.
14. For each **Domain-level Category**, select the corresponding **Standard Category** from the menu, as shown below.

> [!CAUTION]
> **Caution**
> 
> You are responsible for ensuring that domain-level cookie categories are mapped to the correct standard categories. Incorrect mapping directly affects consent behavior across all domains in the group and may result in non-compliance. For instance, if you map a Social Media or Marketing category from your domain to the Essential standard category in CDCG, cookies under that category are treated as strictly necessary and are automatically consented to without giving the data subject a choice. This means non-essential cookies may be activated without valid consent, exposing your organization to compliance risk.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Category-Mapping-Menu.png)
15. Near the bottom right, click **Apply**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Apply-Category-Mapping.png)
16. In the left panel, from the **Actions** section, select **Group Actions**.
17. Select one of the following actions:

| Action | Description |
| --- | --- |
| Scan Domains | Scans all domains in the Cross-Domain Consent Group to detect cookies and trackers. |
| Generate Cookie Reports | Generates reports for domains with completed scans. Securiti excludes domains with failed scans. |
| Export Domain List | Downloads the domain list as a `CSV` file from Key Vault. |
| Edit Domain Configurations | Updates settings for domains in the Cross-Domain Consent Group. |
18. In the left panel, from the **Deploy & Implement** section, select **Deploy Configurations**.
19. To preview and validate your changes before going live, click **Deploy Test Version**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deploy-Test-Version-button.png)
20. After reviewing the changes, to publish your configuration live to your production environment across all domains in the group, click **Deploy Production Version**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Deploy-Production-Version-button.png)
21. In the left panel, from the **Deploy & Implement** section, select **Implementation**.
22. Expand the **Pass Subject Identity to the SDK** and Single-Page Application **(SPA) Integration** accordions to complete your implementation, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Implementation-Expand-Accordions.png)

Add the code snippet to every domain in the Cross-Domain Consent Group so Securiti can link consent records to a known data subject across domains and web browser sessions.

Use the following table to determine which method applies to your domain setup:

| Method | When to use | Description |
| --- | --- | --- |
| Pass Subject Identity to the SDK | Standard multi-page sites | Passes the subject identifier to the SDK before it loads, using a `beforeLoad` callback. |
| Single-Page Application (SPA) Integration | Only if the standard method doesn't work in your application. It is required for SPAs where a full page reload can't happen after logging in. | Passes the subject identifier to the SDK after it has already loaded, using `SecuritiSDK.onReady`. |

## Deleting a Cross-Domain Consent Group

> [!WARNING]
> Important
> 
> Once you delete a Cross-Domain Consent Group, the cookie banner continues to appear on each domain that was part of the group, but Securiti no longer shares or synchronizes consent preferences across those domains. This action cannot be undone.

To delete a Cross-Domain Consent Group when you no longer need to share consent across its associated domains:

1. On the **Cross-Domain Consent Groups** page, in the **Groups** tab, from next to the consent group you want to delete, click **Options** (three dots).
2. From the **Options** menu, select **Delete Consent Group**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CDCG-Options-Menu.png)
3. On the **Delete Cross-Domain Consent Group** popup, review the warning message, and click **Yes, Delete**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CDCG-Yes-Delete.png)

## Filtering Cross-Domain Consent Groups

You can use filters on the **Cross-Domain Consent Groups** and **Standard Cookie Categories** pages to narrow down the consent groups and standard cookie categories based on specific attributes. Filters help you quickly find the records most relevant to your review, configuration, or troubleshooting needs.

To view the filters, click the **+** icon above the table, as shown below. The filters panel opens, showing a searchable list of available filter properties.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cross-Domain-Consent-Groups-filter.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Standard-Cookie-Categories-filter.png)

> [!NOTE]
> **Tip**
> 
> Securiti lets you apply multiple filters at the same time to further refine the results.

Use the following table to understand the filters available on the **Groups** tab:

| Filter | Description |
| --- | --- |
| Group Name | Filters Cross-Domain Consent Groups by group name. You can match group names that contain a specific value. |
| No. of Domains | Filters Cross-Domain Consent Groups based on the number of domains in the group. |
| Scan Status | Filters Cross-Domain Consent Groups by scan status. Available values include Not Scanned, Incomplete, and Complete. |
| Last Scanned | Filters Cross-Domain Consent Groups based on the last scan date. You can filter by dates that are equal to, not equal to, before, after, or between selected dates. |
| Consent Recording Mode | Filters Cross-Domain Consent Groups by consent recording mode. Available values include Use Latest Consent and Use Consent After Login. |
| Show Domains in Preference Center | Filters Cross-Domain Consent Groups based on whether Securiti shows grouped domains in the preference center. Available values include Enabled and Disabled. |

Use the following table to understand the filters available on the **Categories** tab:

| Filter | Description |
| --- | --- |
| Category Name | Filters standard cookie categories by category name. You can match category names that contain a specific value. |
| Category ID | Filters standard cookie categories by category ID. This is useful when you want to review a specific standard category. |
| State | Filters standard cookie categories by state, such as Active or Inactive. |

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

A Single-Page Application (SPA) is a web application that loads one web document and updates content dynamically as data subjects interact with it. It uses JavaScript to refresh only the required parts of the page, instead of loading a new page each time. This approach helps create faster, app-like web experiences.

## Related

- [Consent sharing scenarios in Cross-Domain Consent Groups](/consent-sharing-scenarios-in-cross-domain-consent-groups.md)
- [Understanding the Cross-Domain Consent Groups functionality visually](/understanding-the-cross-domain-consent-groups-functionality-visually.md)
