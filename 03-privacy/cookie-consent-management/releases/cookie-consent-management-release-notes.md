---
title: "Cookie Consent Management release notes"
slug: "cookie-consent-management-release-notes"
updated: 2026-09-22T08:07:36Z
published: 2026-09-22T08:07:36Z
canonical: "helpcenter.securiti.ai/cookie-consent-management-release-notes"
area: privacy
modulo: cookie-consent-management
tipo: release
data_captura: 2026-10-08
---

# Cookie Consent Management release notes

## 1.151

### Release updates - September 2026

#### Debugging Cookie Consent SDK and auto-blocking deployment issues with the web browser extension

Securiti has introduced the [Cookie Consent Browser Assistant](https://chrome.google.com/webstore/detail/bahgegefjapkefhdhafefpmkffbccgih), a web browser extension that lets you inspect, validate, and debug the Cookie Consent SDK and auto-blocking SDK on any live webpage of your domain. You can download the extension from the Help Center article and use it to quickly diagnose consent deployment issues, validate cookie banner behavior, and confirm that consent signals and auto-blocking controls work as expected.

Use the following table to understand the capabilities of the Cookie Consent Browser Assistant:

| Capability | Description |
| --- | --- |
| Health check badge | Adds a toolbar badge that gives an at-a-glance view of the cookie consent implementation status. |
| Inspection panel | Shows live consent state, blocked resources, and compliance signals such as Global Privacy Control (GPC), Google Consent Mode (GCM), IAB Transparency and Consent Framework (IAB TCF), and Global Privacy Platform (GPP). |
| Real-time event timeline | Displays consent-related events as they occur on the webpage. |
| Banner action testing | Lets you trigger cookie banner actions such as accept, reject, and open the cookie preference center directly from the webpage without writing code. |
| Issue diagnostics | Helps identify unknown trackers, configuration mismatches, auto-blocking order issues, and cookie banner behavior differences across geolocations. |
| Additional diagnostics | Supports cookie audits, configuration drift detection, and AI-assisted diagnostic prompts to help investigate consent implementation issues more efficiently. |

> [!NOTE]
> Note
> 
> Cookie Consent Assistant supports Chromium-based web browsers, including **Google Chrome**, **Microsoft Edge**, and **Mozilla Firefox**.

For more information, see [Debugging Cookie Consent SDK and auto-blocking deployment issues](/latest/docs/debugging-cookie-consent-sdk-and-auto-blocking-deployment-issues).

#### Introducing a comprehensive module-level audit log for cookie consent activity

Securiti has introduced a comprehensive audit log in its Cookie Consent Management module to help you review cookie consent-related activity from one centralized view. This update gives you more granular, module-specific visibility into actions and changes associated with domains in an organization within your Securiti tenant.

> [!NOTE]
> Note
> 
> The platform-level audit log remains available. However, we recommend using the module-level audit log because it provides more detailed information.

Use the following table to understand the key audit log capabilities:

| Capability | Description |
| --- | --- |
| Message-based search | Lets you search audit records by message text to find relevant activity more quickly. |
| Filtered audit review | Lets you filter audit records using available audit properties, including domain-related filters for records that include domain information. > [!WARNING] > Important > > Domain URL filtering works for audit records created in the current Securiti release 1.151 (which started to go live the week of September 21, 2026) and later. Older audit records remain visible, but some historical records may not include the domain information required for domain-based filtering. |
| Active and deleted domain coverage | Includes audit records for domains that currently exist in the tenant and domains that existed previously. |
| Cookie & Tracker Library audit consolidation | Merges the Cookie & Tracker Library audit log with the comprehensive module-level audit log. When you access the audit log from Cookie & Tracker Library, Securiti opens the comprehensive audit log with the **Cookie & Tracker Library** filter pre-applied. |
| `CSV` export | Lets you export audit log data in `CSV` format. Exports honor the filters applied to the audit log view. > [!WARNING] > Important > > - All Securiti user roles can view the comprehensive audit log, but export permissions are limited to the following roles: > - Super Admin > - Organization Admin > - Module Owner > - When exporting a large number of audit records, you must keep the audit log page open while Securiti prepares the `CSV` file. Larger exports might take longer to generate. |

For more information, see [Using the Cookie Consent Management Audit Log](/latest/docs/using-the-cookie-consent-management-audit-log).

#### New system cookie banner templates

Securiti now offers four additional ready-to-use system cookie banner templates in the **Banner Templates Gallery**. These new cookie banner templates help you easily meet legal requirements in **Alabama**, **Louisiana**, **Oklahoma**, and **Vermont**. You can now apply these system cookie banner templates to your domains to help comply with:

- Alabama Personal Data Protection Act (APDPA)
- Louisiana Data Privacy Act (LDPA)
- Oklahoma Consumer Data Privacy Act (OCDPA)
- Vermont Data Privacy and Online Surveillance Act (VDPOSA)

For more information, see [System banner templates for countries and states](/latest/docs/using-the-banner-templates-gallery#system-banner-templates-for-countries-and-states).

#### Accessing Securiti’s offline plugin directly from the Chrome Web Store

Securiti now lets you install the [Offline Cookie Scanner](https://chrome.google.com/webstore/detail/kgleeojgabnjeebilliignebkdeajibe) web browser extension directly from the Chrome Web Store instead of downloading it in a `ZIP` file from the Cookie Consent Management’s Help Center. This simplifies installation, improves extension security, and supports web browser environments that restrict manually installed extensions.

Securiti has also addressed security vulnerabilities in the Offline Cookie Scanner plugin, further improving its security and reliability.

For more information, see [Using the offline cookie scanner plugin](/latest/docs/using-the-offline-cookie-scanner-plugin).

---

## 1.150

### Release updates - August 2026

No updates

---

## 1.149

### Release updates - August 2026

#### Visualizing cookie consent compliance risks with Compliance Metrics

Securiti has introduced a **Compliance Metrics** dashboard in its Cookie Consent Management module. This is an extension of the [Compliance Dashboard](/latest/docs/cookie-consent-management-release-notes#detecting-and-remediating-cookie-compliance-risks-with-the-consent-agent) introduced in the previous Securiti release 1.148. It helps you gain deeper visibility into cookie compliance performance, risk distribution, failed tests, and remediation progress across scanned domains.

> [!NOTE]
> Note
> 
> If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether the [Compliance Dashboard](/latest/docs/cookie-consent-management-release-notes#detecting-and-remediating-cookie-compliance-risks-with-the-consent-agent) is included in your plan and whether your tenant meets the eligibility requirements for its activation. Access to the Compliance Metrics dashboard is included with the Compliance Dashboard.

The **Metrics** tab turns compliance scan data into visual widgets that help you identify domains that need attention, understand recurring compliance gaps, and track manual and auto-remediation progress from one place, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Metrics-RN.png)

> [!WARNING]
> Important
> 
> Securiti includes only domains registered in your tenant when calculating **Metrics** tab data. If Securiti scans a domain that is not registered in the tenant, the domain may still appear on the **Compliance Dashboard**, but Securiti excludes it from the **Compliance Metrics** calculations.
> 
> Securiti also excludes failed and in-progress compliance scans from compliance score calculations. By default, the metrics include all jurisdictions covered by completed compliance scans. For domains scanned across multiple jurisdictions, Securiti uses the average jurisdiction score for the overall compliance score and the lowest jurisdiction score to identify critical risk.

Use the following table to understand the widgets available in the **Metrics** tab:

| Widget | Description |
| --- | --- |
| Overall Compliance Score | Shows the overall compliance score across scanned domains. Securiti calculates this score by averaging successful individual domain compliance scans and excludes failed or in-progress scans. |
| Historical Compliance Scores | Shows how the overall compliance score changes over time across scanned domains. |
| Compliance Overview | Provides a consolidated view of critical risk domains, failed tests, and successful remediation rate. |
| Portfolio Risk Distribution | Shows the distribution of domains by compliance posture, including **Non-Compliant**, **Partially Compliant**, **Mostly Compliant**, and **Compliant**. |
| Test Distribution by Status | Shows compliance test results by status, including **Passed**, **Failed**, **Remediated**, **User-Accepted Risk**, **User-Excluded Risk**, and **Not Applicable**. |
| Failed Test Distribution | Shows which compliance test types fail most frequently across scanned domains. |
| Failed Test Distribution by Severity | Shows failed compliance tests by severity, including **Very High**, **High**, **Medium**, **Low**, and **Very Low**. |
| Aging Buckets - Risks | Shows how long unresolved compliance risks have remained open. |
| Remediation Distribution | Shows remediation tasks by status and remediation type, including pending and completed tasks across manual remediation and auto-remediation. |
| Top Pending Remediations by Assignee | Shows assignees with the highest number of pending remediation tasks. |
| Domains at Risk | Shows domains with compliance issues, including compliance score, failed tests, and most recent compliance scan date. |

These visual metrics help you assess the cookie compliance posture of your domains, prioritize remediation efforts, and track compliance improvements over time.

For more information, see [Using Compliance Metrics to monitor cookie compliance risks and remediations](/latest/docs/using-compliance-metrics-to-monitor-cookie-compliance-risks-and-remediations).

#### Enhanced beacon and tracker request detection in domain scans

Securiti has enhanced the cookie scanner in its Cookie Consent Management module to detect additional beacon and network request types during scans, including `navigator.sendBeacon()` calls, `Fetch` and `XHR` requests to known tracker domains.

This enhancement expands detection beyond image tag-based beacons and standard tracker domain requests, helping you identify tracking activity that standard cookie detection may not capture. When Auto-Blocking SDK applies, Securiti traces these requests back to the initiating script and blocks the script-level source of the tracking activity, preventing associated beacons from firing.

> [!CAUTION]
> Caution
> 
> Newly detected beacons might initially appear as unclassified trackers if Securiti cannot automatically categorize them. Review and categorize these trackers to maintain accurate tracker classifications.

For more information, see [Scanning your website for cookies](/latest/docs/scanning-your-website-for-cookies).

#### Resolved issue

- Fixed an issue where the platform audit log did not record updates to a domain’s auto-blocking custom initiators. With this fix, the audit log captures Securiti user details, event time, and before-and-after values when you add, edit, or clear custom initiators, so you can verify who made the update, when it occurred, and what changed (PRIV-249818).

---

## 1.148

### Release updates - July 2026

#### Detecting and remediating cookie compliance risks with the Consent Agent

Securiti has introduced the **Compliance Dashboard** in its Cookie Consent Management module. The Consent Agent performs compliance scans on your domains, and the Compliance Dashboard displays the results in a visual format, giving your privacy, compliance, and marketing teams a centralized place to review identified risks and manage remediation activity.

This dashboard extends the existing **Build with Consent Agent** capability, which previously let you scan domains for cookies and now also supports:

- Compliance scans that check domain adherence to regional laws
- Cookie banner requirements
- Consent regime standards

It gives you visibility into compliance scores, test outcomes, risk severity, and remediation guidance for each domain, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Compliance-Dashboard-RN(1).png)

> [!NOTE]
> Note
> 
> If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.

To populate the dashboard, you can first use **Build with Consent Agent** to request compliance scans for your domain(s). After the scans complete, the dashboard displays the latest successful scan results for each domain.

> [!CAUTION]
> Caution
> 
> Consent Agent provides compliance insights for informational purposes only and does not constitute legal advice.
> 
> Securiti does not accept liability for any decision you make based on these insights.

Use the following table to understand the main compliance dashboard capabilities:

| Capability | Description |
| --- | --- |
| Latest scan visibility | Displays the latest successful compliance scan for each domain, including compliance score and test outcome summary. > [!WARNING] > Important > > Domains without completed compliance scans do not show dashboard data until a scan runs successfully. |
| Test outcome review | Shows test outcomes such as **Passed**, **Failed**, **Not Applicable**, **User Accepted Risk**, and **User Excluded Risk**. |
| Test detail view | Lets you expand individual test results to view severity, confidence score, risk category, test owner, remediator, evidence, and remediation steps. |
| Manual and automatic remediation | Lets you assign or reassign remediators for failed tests and use Consent Agent to apply automated remediation for eligible compliance findings. |
| Remediation tracking | Helps you track remediation ownership, actions, and unresolved risks from the dashboard. |
| Excluded tests review | Provides an **Excluded Tests** view so you can review tests excluded from compliance evaluation. |

For more information, see [Using the Compliance Dashboard to remediate cookie compliance risks](/latest/docs/using-the-compliance-dashboard-to-remediate-cookie-compliance-risks).

#### Sharing consent across eligible domains with Cross-Domain Consent Groups

Securiti has introduced Cross-Domain Consent Groups (CDCG) in its Cookie Consent Management module to help you share consent preferences across related websites that use the same cookie purposes, categories, and settings, as shown below. You can group eligible domains and use Standard Cookie Categories to align domain-level cookie categories for consent sharing across the group.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Cross-Domain-Consent-Groups-RN.png)

> [!NOTE]
> Note
> 
> If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.

Instead of configuring consent settings individually for each domain, you can group domains together so that a data subject's consent preferences on one domain applies automatically across all other domains in the group. This is particularly useful for organizations that operate multiple regional or brand-specific websites under a shared consent framework. By centralizing consent management at the group level, you reduce manual configuration effort, minimize the risk of inconsistent consent states, and ensure a uniform consent experience for data subjects across all your web properties.

> [!WARNING]
> Important
> 
> You can add only eligible domains to a Cross-Domain Consent Group. A domain is eligible if it meets all of the following conditions:
> 
> - It has a successful scan.
> - You've deployed it at least once.
> - It doesn't use an IAB consent framework configuration.
> - It isn't already part of another Cross-Domain Consent Group.

After the domains go live, when a data subject gives consent on one website, Securiti applies that consent to the matching cookie category on the other websites in the Cross-Domain Consent Group, if the domain configuration and web browser settings support it. If consent purposes differ, Securiti shows the cookie banner so the data subject can provide or update consent for the applicable purposes.

Use the following table to understand the main capabilities available for CDCG:

| Capability | Description |
| --- | --- |
| Standard Cookie Categories | Helps standardize cookie categories and map them to domain-level cookie categories so Securiti can unify consent behavior across domains in the Cross-Domain Consent Group, as shown below. |
| Consent Recording Mode | Lets you choose how Securiti records consent when a data subject interacts across multiple domains or web browser sessions. The Consent Recording Mode includes the following options for determining which consent preference Securiti records across domains and web browser sessions: \| Conflict resolution policy \| Description \| \| --- \| --- \| \| Use Latest Consent \| Records the data subject's most recent consent preference as the final consent across domains and web browser sessions. \| \| Use Consent After Login \| Applies consent after the data subject logs in, linking it to their known profile. Consent recorded by an unknown data subject is overridden once they log in and provide consent. \| |
| Conflict resolution policy | Description |
| Use Latest Consent | Records the data subject's most recent consent preference as the final consent across domains and web browser sessions. |
| Use Consent After Login | Applies consent after the data subject logs in, linking it to their known profile. Consent recorded by an unknown data subject is overridden once they log in and provide consent. |
| Anonymous-to-authenticated user linking | Links an anonymous web browser ID to a known data subject ID after login so consent remains consistent across domains and web browser sessions. |
| GPC-based consent sharing | Shares Global Privacy Control (GPC) consent preferences that Securiti honors across domains in the group, unless the data subject explicitly updates their preferences. |
| Group-level actions | Lets you scan domains, generate cookie reports for domains with completed scans, export the domain list, and edit domain configurations from the consent group. |

Use the following table that outlines how CDCG handles consent sharing across domains based on your configuration.

| Mode | Behavior |
| --- | --- |
| Implicit Consent | Consent preferences from the source domain copy over without showing a cookie banner on the destination domain. |
| GPC | When Securiti detects GPC on a domain, opted-out preferences apply to all domains in the group that share the same cookie categories and GPC mappings. |

For more information, see [Using Cross-Domain Consent Groups to sync consent across domains](/latest/docs/using-cross-domain-consent-groups-to-sync-consent-across-domains).

#### Increased bulk edit capacity in the Cookie & Tracker Library

Securiti has increased the bulk edit limit in the **Cookie & Tracker Library** from **50 to 100 trackers**. You can now bulk edit fields for up to 100 selected trackers at a time. This helps you manage larger tracker sets across domains with less manual effort. Before applying the changes, Securiti shows a confirmation message so you can review the selected fields and new values (FR-5410).

For more information, see [Using the Cookie and Tracker Library](/latest/docs/using-the-cookie-and-tracker-library).

#### Standardizing verbiage for OOTB cookie banner templates

Securiti has standardized the cookie banner content and legal verbiage across the following out-of-the-box (OOTB) cookie banner templates for consistency:

> [!WARNING]
> Important
> 
> This is a verbiage update only with no functionality changes. Securiti's Data Privacy Legal Analyst team standardized the wording across cookie banner templates for consistency, not in response to a change in regulatory requirements.

- Alberta
- Argentina
- Australia
- Brazil
- British Columbia
- Chile
- China
- Colombia
- Connecticut
- Delaware
- EU
- France
- Indonesia
- Iowa
- Ireland
- Italy
- Japan
- Latvia
- Luxembourg
- Malaysia
- Montana
- Nebraska
- Netherlands
- New Hampshire
- New Jersey
- New Zealand
- Oregon
- Philippines
- Quebec
- South Korea
- Spain
- Standard Opt-in
- Standard Opt-out
- Taiwan
- Texas
- UK
- Utah
- Virginia

For more information, see [Using the Banner Templates Gallery](/latest/docs/using-the-banner-templates-gallery).

#### Improved cookie banner styling compatibility with AEM

Securiti has improved cookie banner styling behavior to reduce conflicts with website CSS, including websites that use component-based styling frameworks such as Adobe Experience Manager (AEM). Securiti now applies cookie banner styles through an additional parent wrapper class, helping ensure that banner styles apply only to the intended banner elements.

This update improves styling reliability for existing and new cookie banner configurations while preserving existing banner behavior. Securiti has also removed legacy style rules that could interfere with updated styling behavior.

---

## 1.147

### Release updates - June 2026

#### Capturing GTM-managed cookies and trackers during scans

Securiti has enhanced the cookie scanner to improve cookie and tracker detection for websites that use Google Tag Manager (GTM). Before starting a domain scan or compliance scan, the cookie scanner now sends a scanner-specific `securiti_scanning` event to the GTM data layer so configured tags can run during scanning.

This update helps the scanner detect tracking technologies that load only after specific GTM conditions or triggers occur. For instance, some marketing tags may drop cookies only after a GTM trigger runs. The cookie scanner can now send the `securiti_scanning` event to help those configured tags load, letting the scanner capture the associated cookies and trackers (FR-5459).

> [!NOTE]
> Note
> 
> For GTM implementations, you can associate the Securiti’s `securiti_scanning` event with relevant GTM tags to improve visibility into GTM-managed tracking technologies and maintain a more complete cookie inventory.

For more information, see [Configuring GTM to load tracking scripts during domain scans](/latest/docs/configuring-gtm-to-load-tracking-scripts-during-domain-scans).

The Global Privacy Control (GPC) is a browser-based global opt-out tool that lets the Internet users signal their opt-out consent settings to websites, advertisers, and publishers on the world wide web. Some global privacy laws, such as the CPRA, require covered entities to mandatorily detect and honor users’ GPC signal. The Cookie Consent Management module lets you configure cookie banners and preference centers with GPC to ensure detection of the GPC signals on the web browsers of your data subjects to honor their opt-out cookie preferences

Google Consent Mode (GCM) is a functionality that allows website owners to adjust how their Google services behave based on the consent preferences of their data subjects. When a data subject opts in or out of cookies for advertising or analytics, Consent Mode dynamically adapts, ensuring that Google's tools comply with the data subject's choices. Essentially, it enables websites to respect user consent for cookies while still providing valuable data insights and advertising capabilities in a privacy-focused manner

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.

The Transparency and Consent Framework (TCF) is a voluntary consent standardization protocol tool developed by the IAB Europe. It facilitates publishers, vendors, and consent management platforms (CMPs) to comply with certain provisions of the ePrivacy Directive and the GDPR.

The Global Privacy Platform (GPP) is a protocol designed by the Interactive Advertising Bureau (IAB) Tech Lab to streamline and standardize the transmission of consumer consent choice signals from websites and applications to IAB enrolled providers. The framework enables user consent signals to be communicated throughout the digital ad supply chain

The Alabama Personal Data Protection Act (APDPA) applies to persons that conduct business operating in or targeting Alabama that meet one of two thresholds:

(i) processing personal data of more than 25,000 consumers, excluding the processing of payment data; or

(ii) deriving 25%+ of gross revenue from data sales.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Alabama and apply it to your domains.

Louisiana Data Privacy Act (LDPA) applies to any entity or a person doing business in the state that meets one of three operational thresholds:

(i) exceeding $25 million in gross annual revenue, commercially handling the personal data of at least 75,000 consumers, households or devices annually; or

(ii) generating 50% or more of its yearly revenue directly from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Louisiana and apply it to your domains.

The Oklahoma Consumer Data Privacy Act (OCDPA) applies to controllers or processors that conduct business in Oklahoma, or produce products/services targeted to its residents, and meet either of the following thresholds:

(i) Control or process the personal data of at least 100,000 consumers, or

(ii) Control or process the personal data of at least 25,000 consumers AND derive over 50% of gross revenue from the sale of personal data.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Oklahoma and apply it to your domains.

The Vermont Data Privacy and Online Surveillance Act (VDPOSA) applies to persons or entities that conduct business in Vermont, or produce products or services targeted to Vermont residents, and met the following thresholds during the preceding calendar year:

(i) processed the personal data of at least 35,000 consumers and sensitive data of at least 3,000 consumers, excluding the processing of payment data; or

(ii) offered for sale the personal data of at least 3,000 consumers.

From Securiti’s **Banner Templates Gallery**, you can import a ready-to-use system banner template designed specifically for Vermont and apply it to your domains.
