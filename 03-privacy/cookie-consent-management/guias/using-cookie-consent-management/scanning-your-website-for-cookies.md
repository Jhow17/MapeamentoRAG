---
title: "Scanning your website for cookies"
slug: "scanning-your-website-for-cookies"
status: "update"
updated: 2026-09-21T15:20:34Z
published: 2026-09-21T15:20:34Z
canonical: "helpcenter.securiti.ai/scanning-your-website-for-cookies"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Scanning your website for cookies

**Scenario**

As a Data Privacy Officer, you need to ensure that your website complies with data privacy laws requiring cookie consent. For instance, when regulators request proof of consent collection, relying on manually tracked logs and opt-outs can be time-consuming and error-prone. With Securiti’s Cookie Consent Management module, you automatically scan your website, display a compliant cookie banner, and reliably capture cookie consent, even during network issues. You gain consistent, verifiable compliance with less operational effort.

You scan your domains to see what cookies they drop on the web browsers of your data subjects. You start by adding domains, organizing them into domain groups, and then scanning each domain to see what cookies it drops.

The cookie scanner uses advanced logic to detect cookies and trackers across modern web browsers while aligning with current privacy requirements. It traces initiator paths for cookies, image beacons, local storage, and session storage items to improve tracker visibility and help identify how websites initiate tracking elements.

It also detects the following request types, extending detection beyond image tag-based beacons and standard tracker domain requests:

- `navigator.sendBeacon()` calls
- `Fetch` and `XHR` requests to known tracker domains
- Chained tracker requests

This approach helps maintain more accurate and consistent detection across your domains while enabling future improvements to detection capabilities.

> [!NOTE]
> **Tip**
> 
> If Securiti's cookie scanner misses some cookies during a domain scan, you can manually add them to your domain’s cookie banner and preference center using the [Cookie and Tracker Library](/v1/docs/using-the-cookie-and-tracker-library) functionality instead of submitting a support request or escalation.

1. If your firewalls or WAFs are configured to block the entire AWS or Azure address ranges, allow-list the IPs listed in [Configuring cookie scanner allow-listing](/v1/docs/configuring-cookie-scanner-allow-listing) to permit scanning by the Securiti cookie scanner.
2. If your website is configured to challenge with Captchas to eliminate or suppress bot traffic, allow-list the IPs listed in [Configuring cookie scanner allow-listing](/v1/docs/configuring-cookie-scanner-allow-listing) to suppress the Captcha and permit scanning by the Securiti cookie scanner.
3. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
4. To add a new domain, near the upper right corner of the page, click **+ New Domain**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/New-Domain-V2.png)
5. In the **Domain Group** box, choose an existing domain group from the menu, or type the name of a new domain group you want to create. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Domain-Group.png)
6. In the **Domain** box, type a valid and reachable domain. For instance, if your domain is accessible as `www.securiti.ai`, but not as `securiti.ai`, it's necessary to add the domain with the `www` prefix as `www.securiti.ai`.

> [!NOTE]
> **Note**
> 
> You can also add and scan domain URLs with **double hyphens** and **underscores**, such as `https://atlas--fodevs.sandbox.my.site.com` or `https://atlas--fodevs.sand_box.my_site.com`, ensuring compatibility with environments like Salesforce that use this format for test domains.

Securiti's cookie scanner automatically adds the protocol to the domain you input. For instance, if you enter the domain `securiti.ai`, the scanner first attempts to scan it with `https://` protocol like `https://securiti.ai`. If the entered domain is accurate but unreachable, the scanner then tries scanning with `http://` protocol like `http://securiti.ai`.
7. In the **Labels** field, create new appropriate and meaningful labels, as shown below. They let you tag domains with identifiers like team ownership, environment, or region. Labels help you group similar domains, filter them faster, and quickly find the right ones, especially when managing consent across a large and growing list of domains.

> [!NOTE]
> Note
> 
> Securiti lets you add as many labels as you want. However, avoid overusing them to prevent clutter and maintain a clean, manageable domain view. Use labels strategically for meaningful grouping.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Labels.png)
8. In the Owners area, add additional Securiti users as co-owners of the domain.
9. (Optional) Mark the **Send notification to all owners when changes to cookies are detected** checkbox to notify domain owners whenever Securiti detects any changes in the cookies associated with the domain.
10. Once done, click **Create Website Domain Object & Continue**.

Securiti creates the website domain object, and if appropriate, a new domain group. It then redirects you to the [Website Scan & Report](/v1/docs/scanning-your-website-for-cookies) tab.

## Website Scanning & Reporting

To use the tools on the **Website Scan & Report** tab to start scanning the domain for cookies:

> [!NOTE]
> **Note**
> 
> Alternatively, you can use the Securiti offline cookie scanner plugin. This Google Chrome web browser extension lets you scan websites and specific pages that might be behind complex authentication schemes and not amenable for scanning by the Securiti online scanner. For more information, see [Using the offline cookie scanner plugin](/latest/docs/using-the-offline-cookie-scanner-plugin).

1. Near the upper right corner of the page, click **Edit**.
2. To automatically scan all the URLs of the domain, from under Scan Options, select **Default Scanning**.
  1. (Optional) To scan specific pages instead of the entire domain, select **Sitemap Scanning**.

| Option | Description |
| --- | --- |
| Sitemap URL | Enter your sitemap URL in the **Sitemap URL or XML File** text field to scan only the pages listed in that sitemap. |
| Upload `XML` File | Click the **Upload XML File** button to upload a sitemap file from your computer. The file defines the specific pages to be scanned instead of scanning the entire domain. > [!NOTE] > Note > > - You can upload a sitemap `XML` file of up to **5 MB**. > - Securiti scans URLs from the sitemap based on the URL limit configured for your Securiti tenant. To request an increase in your domain scan limit, contact your **Customer Success Manage**r or **Account Representative**. |

> [!NOTE]
> Note
> 
> When you enable the Cookie & Tracker Library feature in your Securiti tenant, Securiti automatically adds all cookies and trackers detected during Sitemap Scanning to the library for easier management and review. For more information, see [Using the Cookie and Tracker Library](/v1/docs/using-the-cookie-and-tracker-library).
3. To scan multiple subdomains while scanning your base domain, mark the **Scan subdomains found on base domain** checkbox or manually add the URLs of subdomains in the **Additional subdomains (separated by commas)** text area, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Scan-Subdomains.png)

> [!NOTE]
> **Note**
> 
> - For instance, subdomains belonging to your base domain `www.securiti.ai` could be `app.securiti.ai`, `app.eu.securiti.ai`, `app2.securiti.ai`, etc.
> - Securiti lets you scan up to 300 subdomains, with a maximum of **2,500 pages** across all subdomains. Because some subdomains may contain more pages than others, this page limit applies to the entire scan collectively. To request an increase in your scan limit, contact your **Customer Success Manager** or **Account Representative**. The scanned subdomains automatically appear in the **Additional subdomains (separated by commas)** text field after the scan is completed.
> - The cookie scanner processes URLs beyond the predefined depth limit while keeping the total scanned URLs within the maximum threshold. It prioritizes unique URLs and excludes redundant ones, such as fragment URLs and analytical search parameters.
> 
> The scanning process, designed to improve cookie detection while maintaining efficiency, occurs in two phases:
>   - **Phase 1:** Scans URLs within the depth limit and stores excess URLs.
>   - **Phase 2:** If scan capacity allows, the stored URLs exceeding the depth limit are processed in priority order.
4. (Optional) To migrate scanned cookie data for the same domain across environments, use the options in the **Import & Export Scanned Cookie Data** section, as shown below: ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-Export-Scanned-Cookie-Data(1).png)
  1. Click **Import Cookie Scan Data** to upload scanned cookie data for the same domain from another environment.

> [!NOTE]
> Note
> 
> This upload option supports only `CSV` format.
  2. Click **Export Cookie Scan Data** to download the scanned cookie data.

> [!NOTE]
> Note
> 
> This option exports scanned cookie data only in `CSV` format. To download the scan results in additional formats, use the **Download Cookie Report** button. It provides the cookie report in `Excel`, `JSON`, and `CSV` formats, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download-Cookie-Report(2).png)
5. (Optional) To have Securiti repeat the scan from the domain creation date, mark the **Enable Auto-scan** checkbox, as shown below.
  1. To run the scan monthly from the domain’s creation date, select **Monthly Scan**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Monthly-Scan.png)
  2. To run the scan on a custom scan schedule, select **Custom Schedule** and configure the following settings:

| Setting | Description |
| --- | --- |
| Scan frequency | Select **Monthly** or **Twice Monthly** from the menu to define how often Securiti runs the scan, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Scan-Frequency(1).png) |
| Scan days | Use the date picker to select the specific day or days of the month when Securiti runs the scan, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Scan-Date-Picker.png) |
6. If the page is protected behind a login, mark the **Enable scan behind login** checkbox.
7. Now enter the login information in the **Login Details** and **HTML Attributes** sections, as shown below.

![Scan-Behind-Login-V2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-012797b3-b33e-2c50-d3ba-399b2e973bdc.png)

| Login Details |
| --- |
| Login Page | Add the URL of your login page that you want to scan. |
| Username | Enter your username. |
| Password | Enter your password. |
| 2-Step User Login Workflow (checkbox) | Mark this checkbox if your domain supports a two-step login workflow. For instance, if your domain first presents the data subjects and website visitors with a login screen to enter their **username**, and then advances to a second screen where they can enter their **password** before clicking the **submit** or **login** button. |

| HTML Attributes |
| --- |
| Input Selector for Username | Enter the inspect mode of your domain's login page and in the `&lt;form&gt;` tag section, find the value of the input selector for the **username**, and enter that value here, as shown below. ![Screenshot_2023-04-28_at_10_19_10_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ea05d74-ab5e-a6db-9c1a-7a66d961bba3.png) |
| Input Selector for Password | Enter the inspect mode of your domain's login page and in the `&lt;form&gt;` tag section, find the value of the input selector for the **password**, and enter that value here, as shown below. ![Screenshot_2023-04-28_at_10_25_35_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1471d3f9-0035-ec42-bd20-43d4d5802ea0.png) |
| Selector for Submit | Enter the inspect mode of your domain's login page and in the `&lt;form&gt;` tag section, find the value of the input selector for the **submit** button, and enter that value here. |
| Selector for Submit (Password Screen) | Enter the inspect mode of your domain's login page and in the `&lt;form&gt;` tag section, find the value of the input selector for the **submit** button that appears on the **password screen** (second screen if your domain supports a two-step login workflow), and enter that value here. |
8. Click **Reinitiate Website Scan**.

Securiti scans the domain for cookies and produces a report. When the scan completes, the **Scan Status** column on the Domains dashboard shows the status as **Scanned**, and Securiti displays a green **Scan complete** status in the **Website Scan & Report** tab.

When the scan completes, Securiti also emails each domain owner to let them know what cookies have been added or removed. This alert lets them know that they may need to update the cookie categorization as described in [Categorizing your website cookies](/v1/docs/categorizing-your-website-cookies).

> [!NOTE]
> **Note**
> 
> If the scan is marked as "Failed," it might mean that you must configure allow-listing as described in [Configuring cookie scanner allow-listing](/v1/docs/configuring-cookie-scanner-allow-listing).
9. After the scan completes, click the domain entry on the Cookie Consent table, then click the **Website Scan & Report** tab.
10. (Optional) Click **Download Cookie Report** to download the cookie report in the following file formats, as shown below.
  - `Excel`
  - `JSON`
  - `CSV`

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download-Cookie-Report(3).png)

> [!NOTE]
> Note
> 
> The cookie scan report includes details from Securiti’s consent simulation logic. Securiti captures the baseline cookie state before any consent interaction occurs. The cookie scan report also shows whether the cookie scanner simulated consent through SDK methods or by clicking the **Accept All** button, and identifies the Consent Management Platform (CMP) provider detected on the cookie banner. Supported CMP providers include:
> 
> - Securiti
> - OneTrust
> - CookieYes
> - UserCentrics
> - TrustArc
> 
> These details help you compare which cookies were present before consent with the cookies that loaded only after the data subject granted consent. You can also use this information to verify that cookie Auto-blocking releases the relevant cookies after consent is granted.
11. Proceed to [Categorizing your website cookies](/v1/docs/categorizing-your-website-cookies).

## Comparing cookie scan results

Securiti lets you compare cookie scan results across recent successful online scans for the same domain. With this capability, you can instantly see what changed between scans so you can detect new cookies, compliance risks, and vendor updates without manual auditing.

Use the following table to understand the value this capability provided you:

| Value | Description |
| --- | --- |
| Compliance-focused value | Helps you stay audit-ready and compliant with evolving privacy regulations. You can quickly identify newly introduced, removed, or reclassified cookies between scans so you can validate consent coverage, keep disclosures accurate, and maintain records that support GDPR, CPRA, and other audit requirements. |
| Efficiency and workflow value | Lets you reduce manual review and speed up validation after releases. You can instantly see differences between scans instead of comparing cookie lists manually, so you can focus only on what changed and review updates more efficiently across environments or deployments. |
| Risk-reduction value | Lets you catch privacy risks before they become compliance issues. You can detect newly added or uncategorized cookies, vendor changes, or unexpected trackers early and address them before they affect user consent, disclosures, or regulatory exposure. |
| Cross-team collaboration value | Helps you keep compliance, marketing, and engineering aligned on tracking changes. You can use scan comparisons to clearly see what changed, share findings across teams, and coordinate updates to consent configurations, disclosures, or implementations. |
| Data transparency and governance value | Maintains a clear history of how your tracking footprint evolves over time. You can compare past and current scans to understand trends, verify updates, and demonstrate governance and accountability when reviewing changes or preparing for audits. |

> [!WARNING]
> Important
> 
> Scan comparison is available only for scans that meet the following conditions:
> 
> - You can compare **any two successfully completed online scans** from the **five most recent domain scans**.
> - Scan comparison supports only **online scans completed after Securiti release 1.142 (week of February 9) or later**, including manually triggered scans and auto-scheduled scans using the Default or Sitemap strategy.
> - Scan comparison supports online scans only. It excludes offline scans and scans imported from `CSV` or other third-party tools.

To compare scan results in detail:

1. In the **Website Scan & Report** tab, click **View All Scans** to open the scan history list.
2. (Optional) Click the **metadata** icon next to a scan to view detailed scan information, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Metadata.png)
3. To select domains for comparison, from the **Scans** table, mark the checkboxes against any two scans.
4. Near the upper left and right below the search bar, click **Compare**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compare-Scans(1).png)
5. On the **Scan Over Scan Differences** page, select the appropriate analysis tab to review the scan differences.

> [!NOTE]
> Note
> 
> The selected scans appear side by side at the top of the page, with the latest scan on the left and the earlier scan on the right. Each scan entry displays its scan ID, timestamp, and total cookies detected.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Scan-ID.png)

Use the following table to understand the available analysis types:

| Analysis Type | Description |
| --- | --- |
| Tracker Analysis | Lets you compare tracker data across scans to instantly see what’s new, missing, or changed. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Tracker-Analysis.png) |
| URL Analysis | Lets you view the differences between the URLs scanned across different scans. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/URL-Analysis.png) |
| Category Analysis | Lets you view all the differences that occurred in cookie categories across different scans. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Category-Analysis.png) |
6. (Optional) Click the **+** icon above the analysis table to add filters. Use filters to narrow down and analyze scan differences:

| Filter | Description |
| --- | --- |
| Scan ID | Displays data from one of the two selected scans, allowing you to review values from each scan independently. |

In addition to these common filters, each analysis tab provides its own filters:
  1. Tracker Analysis filters

| Filter | Description |
| --- | --- |
| Changed | Filters categories based on whether they have **Changed** or remain **Unchanged** between the selected scans. > [!NOTE] > Note > > In the Tracker Analysis tab, use group by to organize results for easier review. Select **Group by None** to view an ungrouped list, or **Group by Service** to group trackers by their associated service, as shown below. > > ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Group-By.png) |
  2. URL Analysis filter

| Filter | Description |
| --- | --- |
| Changed | Filters URLs based on whether they differ between the two selected scans. Select **True** to view only changed URLs, or **False** to view unchanged ones. |
  3. Category Analysis filter

| Filter | Description |
| --- | --- |
| Category State | Filters categories based on whether they have **Changed** or remain **Unchanged** between the selected scans. |
7. (Optional) Use the search bar to quickly find a specific tracker, URL, or category, depending on the selected analysis tab.

> [!NOTE]
> Tip
> 
> The search bar always searches by the first column of the selected analysis tab. For instance, in the URL Analysis tab, the search bar lets you search by URL and the first column displays URLs. Similarly, in the Tracker Analysis and Category Analysis tabs, the search applies to the tracker name or category name shown in the first column.
8. (Optional) From the top right corner of the page, click **Download Report**. From the menu, mark the checkboxes for the analysis views you want to include in the report, then click Download, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download-Report.png)

You can download the scan comparison report as a `CSV` so you can analyze changes in detail, share them with stakeholders, and maintain a record of tracking differences between scans.

## Filtering the domain list

To filter out domains either by their domain name or group name:

1. In the search bar, type the domain name or group name, and press enter, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filter-By-Domain-Name-V2.png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Filter-by-Group-Name-V2.png)

## Deleting a domain from the domain list

Securiti lets you delete a particular domain from the domain list present on the **Domains** page.

> [!NOTE]
> **Important**
> 
> - The following admin roles in your Securiti tenant can delete a domain:
>   - Super Admin
>   - Organization Admin
>   - Module Owner
> - Securiti considers all domains present in your Securiti tenant applicable for the bulk delete operation, except the domain(s) associated with the Privacy Center(s).
> - After deleting the domains from Securiti , ensure to remove the **deployment code** snippet from your domain’s code. Failing to do so may result in 404 console errors related to CDN files of deleted domains when inspecting the console tab from the inspect mode. However, these console errors **do not impact** the behavior of your domain in any way.

1. On the **Domains** page, from the domains list, select a domain either by scrolling down to it or by filtering it by its **name** or **group name** as explained in [Filtering the domain list](/v1/docs/scanning-your-website-for-cookies).
2. From the right side of the domain, click **Options** (three dots), and select **Delete**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Delete-Domain-V2.png)

> [!NOTE]
> Note
> 
> Securiti does not let you delete domains that are linked to a privacy center.
3. On the **Delete Domain** popup, type **delete** in the text field as your confirmation message, and click **Delete**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Delete-Domain-Popup-V2.png)

After the successful deletion of domains in bulk, Securiti shows you a confirmation message near the upper right corner of the Cookie Consent Domains page.

## Domain scan types in Cookie Consent Management

Securiti supports multiple scan types to help you discover cookies and trackers across your domains in different scenarios. Depending on how you want to initiate a scan, automate it, or reuse existing scan data from an environment, you can choose from online, offline, or import-based scans, each with its own execution method and scanning strategy. The diagram below provides a high-level view of the available scan types and how they relate to each other.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CCM Scan Types-[Final] CCM Scan Types.drawio.png)

The following table explains the different types of domain scans available in the Cookie Consent Management module and how they are labeled on the scan listing page.

| Scan Category | Scan Mode | How the scan is initiated | Scan Strategy | What this means |
| --- | --- | --- | --- | --- |
| Online | Manual | You manually click **Initiate Domain Scan** after adding a domain | Default Strategy | Scans the entire domain automatically using Securiti’s standard crawling logic. |
| Online | Manual | You manually click **Initiate Domain Scan** | Sitemap Strategy | Scans only the URLs provided in the uploaded sitemap instead of crawling the entire domain. |
| Online | Automatic | Scan runs automatically based on the configured scan schedule (monthly, from domain creation date or selected dates) | Default Strategy | Automatically scans the entire domain on the scheduled dates without manual intervention. |
| Online | Automatic | Scan runs automatically based on the configured scan schedule | Sitemap Strategy | Automatically scans only the URLs defined in the sitemap on the scheduled dates. |
| Offline | Manual | You use the browser extension to record cookies while navigating the domain and then upload the generated `JSON` file | Not applicable | Cookies and trackers are captured based on the pages you manually visit during playback, rather than through automated crawling. |
| Import | Manual | You upload a `CSV` file generated by another CMP or scanning tool | Not applicable | Lets you import cookie and tracker data from third-party tools without scanning the domain directly in Securiti. |

### How this helps when viewing scan results

- **Online vs Offline** indicates whether the scan was performed directly by Securiti’s scanner or uploaded manually.
- **Manual vs Automatic** indicates whether the scan was triggered by a user action or by a scheduled configuration.
- **Default vs Sitemap Strategy** indicates whether the entire domain was scanned or only specific URLs from a sitemap.
- **Import** scans represent externally generated scan results uploaded into the platform.

This table helps you quickly understand and compare scan results, especially when using features like **Scan Over Scan** or **Scan Compare**, where multiple successful scans appear together.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

The California Privacy Rights Act (CPRA) amended the CCPA by adding additional consumer privacy rights and obligations for businesses. It also created the California Privacy Protection Agency (CPPA), tasked with enforcing the law and educating the public on their rights and obligations under the law.

## Related

- [Scanning domains in bulk](/scanning-domains-in-bulk.md)
- [Troubleshooting the domain scan result discrepancies](/troubleshooting-the-domain-scan-result-discrepancies.md)
- [Managing cookie policies](/managing-cookie-policies.md)
