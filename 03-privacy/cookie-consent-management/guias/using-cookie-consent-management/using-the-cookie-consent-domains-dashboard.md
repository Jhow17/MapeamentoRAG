---
title: "Using the Cookie Consent Domains dashboard"
slug: "using-the-cookie-consent-domains-dashboard"
updated: 2026-09-03T06:39:42Z
published: 2026-09-03T06:39:42Z
canonical: "helpcenter.securiti.ai/using-the-cookie-consent-domains-dashboard"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Cookie Consent Domains dashboard

**Scenario**

As a Data Protection Officer, you must manage multiple websites across departments. For instance, when a new domain is launched, you need to quickly assign responsibility to ensure privacy requirements are addressed from the start. Without a central system to track ownership and privacy responsibilities, things can quickly become chaotic. With Securiti’s Cookie Consent Management module, you can add domains and assign owners directly. This helps ensure each website meets regulatory requirements from the outset by establishing clear ownership.

The **Domains** page in **Cookie Consent Management** lets you view, filter, organize, and manage the domains configured for cookie scanning and consent deployment. You can use this page to review domain status, scan results, active versions, ownership, consent framework settings, and potential compliance risks from one central location.

Use the following table to understand the key capabilities available on the Domains page:

| Capability | Description |
| --- | --- |
| Top-level filter | Lets you create advanced filter queries by combining domain properties, such as domain group, scan status, labels, compliance risk, consent framework settings, and deployment type. |
| Saved views | Lets you save frequently used filter combinations for quick access. |
| Refresh Dashboard | Reloads the domain data and updates the grid with the latest available information. |
| Search | Lets you search for domains, subdomains, or domain groups. |
| Domain metrics | Shows summary counts for domains, such as total domains, published domains, draft domains, and IAB-enabled domains. |
| Bulk actions | Lets you perform actions on one or more selected domains, such as scanning, generating reports, deploying domains, reassigning domain groups, exporting the domain list, editing configurations, or deleting domains. |
| Column selector | Lets you choose which columns appear in the domains grid. |
| Domain metadata | Lets you expand a domain row to view additional details, such as scan, deployment, and cookie banner information. |

## Using the top-level filter

The top-level filter lets you combine different domain properties and narrow the domain list based on your selected criteria. You can filter domains by attributes such as domain group, scan status, labels, compliance risk, consent framework settings, and deployment type.

To use top-level filter:

1. From the upper left corner of the **Domains** page, click **+**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Domains-Filter-button.png)

> [!WARNING]
> Important
> 
> A warning icon next to a domain in the **Domain/Subdomain** column indicates potential compliance issues detected for that domain, as shown below.
> 
> 
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Risk(2).png)
> 
> 
> 
> For more information on reviewing and remediating flagged domains, see [Using the Compliance Dashboard to remediate cookie compliance risks](/latest/docs/using-compliance-metrics-to-monitor-cookie-compliance-risks-and-remediations).
2. From the filters panel, select a property and define the filter condition, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Domains-Filters-Panel.png) Use the following table to understand the available top-level filter properties:

| Property | Description |
| --- | --- |
| Active Version | Filters domains by active published version. You can filter by a specific version, version range, or version comparison. |
| ADA Compliance | Filters domains based on whether ADA compliance is **Enabled** or **Disabled**. |
| Auto-blocking | Filters domains based on whether Auto-blocking is **Enabled** or **Disabled**. |
| Custom CSS | Filters domains based on whether custom CSS is **Enabled** or **Disabled**. |
| Deployment Type | Filters domains by deployment type, such as **Manual** or **Automatic**. |
| Domain Created | Filters domains by the date range in which they were created. Use **between** to select the start and end dates. |
| Domain Group | Filters domains by one or more domain groups. Use **is one of** to select domain groups from the provided list, or use the search option. |
| Cross-Domain Consent | Filters domains based on whether Cross-Domain Consent is **Enabled** or **Disabled**. |
| Cross-Domain Consent Group | Filters domains by one or more Cross-Domain Consent Groups. Use **is one of** to select groups from the provided list, or use the search option. |
| Domain Status | Filters domains by status, such as **Published** or **Draft**. |
| Domain/Subdomain | Filters domains by domain or subdomain name. Use **contains** and enter the required value. |
| Domain UUID | Filters domains by domain UUID. Use **is equal to** or **is not equal to** and enter the required UUID. |
| Domains at Risk | Filters domains based on whether Securiti detected potential compliance risks. Select **Yes** to view domains with potential compliance risks, or **No** to view domains without potential compliance risks. |
| GCM | Filters domains based on whether Google Consent Mode (GCM) is **Enabled** or **Disabled**. |
| GPC | Filters domains based on whether Global Privacy Control (GPC) is **Enabled** or **Disabled**. |
| IAB GDPR Policy | Filters domains based on whether the IAB GDPR policy is **Enabled** or **Disabled**. |
| Labels | Filters domains by labels. Use **contains** and enter the required label value. |
| Last Scanned | Filters domains by the last scanned date range. Use **between** to select the start and end dates. |
| Monthly Auto Scan | Filters domains based on whether monthly auto scan is **Enabled** or **Disabled**. |
| Owner Email | Filters domains by owner email. Use **is one of** to select one or more owners from the provided list, or use the search option. |
| Privacy Centers | Filters domains based on privacy center linkage status, such as **Unlinked**. |
| Scan Behind Login | Filters domains based on whether scan behind login is **Enabled** or **Disabled**. |
| Scan Status | Filters domains by scan status, including **Not Scanned**, **Scan Requested**, **Scanning**, **Scanned**, **Scan Failed**, **Scan Abort Requested**, or **Scan Aborted**. |
| Strict CSP | Filters domains based on whether Strict Content Security Policy (CSP) is **Enabled** or **Disabled**. |
| Top Level Domain Consent | Filters domains based on whether top-level domain consent is **Enabled** or **Disabled**. |
3. Once you set all required properties, click **Apply** at the bottom of the filters panel, as shown below. Securiti builds a query based on your selected properties and displays the filtered results. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Domains-Filter-Panel-Apply.png)
4. (Optional) To clear the top-level filter, click **Clear Search** from the upper right corner of the **Domains** page, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Clear-Search(1).png)

## Saving searched views

Securiti lets you save your built queries as **Saved Views** for later use. For instance, once you save a query, it gets saved as a Saved View with the filters you applied and the results that were filtered out. This ensures you can access commonly used searches from the Saved View section, instead of repeatedly searching for cookies and trackers with specific and occasionally used properties.

To save a built query as a saved view:

1. After filtering the domains from the top-level filter, from the upper right corner, click **Save View**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ccm_dash_save_view_1.png)
2. On the Save View side panel:
  1. Select the Group Name or click **Add New** to create a new group name. Type the group name, and press **Enter**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ccm_dash_save_view_2.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ccm_dash_save_view_3.png)
  2. Enter a name for the view that you want to save.
  3. Near the bottom of the side panel, click **Save View**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ccm_dash_save_view_4.png)

Once done, Securiti shows you a success message near the upper right side, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ccm_dash_save_view_5.png)
3. To view your saved view, from the upper right corner, click **Saved Views**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ccm_dash_save_view_6.png)

## Adding a new domain

To add a domain:

1. In Securiti, open Cookie Consent Management and choose **Cookie Consent > Domains**.
2. Near the upper right corner of the page, click **+ New Domain**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ccm_dash_add_domain_1.png)
3. Follow the procedure as explained in [Scanning your website for cookies](/latest/docs/scanning-your-website-for-cookies#website-scanning-reporting).

## Adding additional columns

To add more columns and display additional information about the domains:

1. In Securiti, open **Cookie Consent Management** and choose **Cookie Consent > Domains**.
2. Near the top right corner of the table, click **Column Selector,** as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/column_view_1.png)
3. In the popup, select the columns you want to view, then click **Apply**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/column_view_2.png)
4. To restore the default column view, click **Restore Defaults** in the column selector popup, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/column_view_3.png)

> [!NOTE]
> Note
> 
> Securiti adds a horizontal scrollbar automatically as the number of columns increases.

## Performing bulk actions

When you select two or more domains, the action toolbar appears just above the domain list and lets you perform bulk actions such as:

- [Scanning domains](/latest/docs/scanning-domains-in-bulk)
- [Generating cookie reports](/latest/docs/downloading-cookie-reports-for-all-domains)
- [Deploying domains](/latest/docs/deploying-domains-in-bulk)
- [Reassigning domain groups](/latest/docs/reassigning-domains-between-domain-groups)
- [Exporting domain list](/latest/docs/downloading-domain-list-reports)
- [Bulk editing domain configurations](/latest/docs/editing-the-domain-configurations-in-bulk)
- [Deleting domains](/latest/docs/deleting-domains-in-bulk)

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

## Related

- [Scanning your website for cookies](/scanning-your-website-for-cookies.md)
- [Scanning domains in bulk](/scanning-domains-in-bulk.md)
- [Editing the domain configurations in bulk](/editing-the-domain-configurations-in-bulk.md)
- [Configuring cookie consent experiences using Build with AI](/configuring-cookie-consent-experiences-using-build-with-ai.md)
