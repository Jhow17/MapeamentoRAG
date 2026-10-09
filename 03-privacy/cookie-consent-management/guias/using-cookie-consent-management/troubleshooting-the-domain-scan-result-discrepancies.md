---
title: "Troubleshooting the domain scan result discrepancies"
slug: "troubleshooting-the-domain-scan-result-discrepancies"
updated: 2026-09-28T09:00:38Z
published: 2026-09-28T09:00:38Z
canonical: "helpcenter.securiti.ai/troubleshooting-the-domain-scan-result-discrepancies"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Troubleshooting the domain scan result discrepancies

This troubleshooting guide provides detailed instructions to effectively address and rectify challenges that may arise during domain scans. Whether you encounter discrepancies in **cookie detection**, **connectivity issues**, or **unexpected scan behaviors**, this guide provides instructions to effectively address and rectify these challenges.

Use the following table to quickly identify relevant details and guidance tailored to your specific needs:

| Aspect | Description |
| --- | --- |
| Intended Audience | This troubleshooting guide is specifically designed to assist internal stakeholders at Securiti, including the **Customer Success**, **Professional Services**, **Sales**, and **Quality Assurance** (QA) teams, in diagnosing and resolving issues that may arise during domain scans. |
| Preparation | Before you begin troubleshooting, you must ensure you have the necessary access to the tools and information mentioned throughout this guide, including developer tools, EFK logs, and the appropriate environment settings for your domain scans. |

> [!WARNING]
> **Important**
> 
> If the following steps do not resolve the issue, you can submit a detailed ticket to the development team for further analysis and assistance. You must attach any relevant error details, screenshots, and EFK logs to the ticket.

Use the following troubleshooting cases to diagnose issues encountered during domain scans before responding to customer queries:

### Case 1: Cookie scanner found cookies which are not present on the domain

The domain scan may occasionally detect more cookies than are visible in the developer tools of the web browser. This discrepancy is expected and requires further analysis to ascertain whether it reflects an actual issue with the scanner.

To further investigate the issue:

1. Determine your operational environment and access the region-specific domain using direct access, either directly or via a VPN service. For instance:

| Region | Cloud URL |
| --- | --- |
| U.S. | `app.securiti.ai` |
| EU | `app.eu.securiti.ai` |
| Indonesia (Jakarta) | `app2.securiti.ai` |
| Canada (Montreal) | `app3.securiti.ai` |
| Australia (Sydney) | `app4.securiti.ai` |
| United Arab Emirates (UAE) | `app5.securiti.ai` |
| India (Mumbai) | `app6.securiti.ai` |
| Kingdom of Saudi Arabia (KSA) | `app7.securiti.ai` |
| State of Qatar | `app8.securiti.ai` |
2. Perform a fresh domain scan to check if the cookies are consistently detected. You must take into consideration that some domains with dynamic behavior may drop cookies differently across various times.
3. Check the `FoundOnUrl` of the cookie:
  1. **Access the URL:** Visit the URL indicated in the `FoundOnUrl` field, using a VPN corresponding to the respective country if applicable.
  2. **Open Developer Tools:** Navigate to the **Application** tab to inspect the domain’s data storage.
    1. **Inspect Storage:** Verify if the cookie is present in cookies, local storage, or session storage.
    2. **Browser Verification:** Using a **Chromium** browser, check the address bar by clicking the **View site information** icon and selecting **Cookies in use** to see if the cookie is listed.
    3. **Refresh and Interact:** Refresh the webpage, then scroll and hover over interactive elements like maps or videos to trigger any additional cookies and check again.
    4. **Network Analysis:** Review the network call response headers for **Set-Cookie** entries, which indicate cookies being set in the web browser.
    5. **Adjust Cookie Settings:** If your web browser blocks third-party cookies, adjust the settings to allow them, then refresh the webpage and verify the changes.
4. For image beacons, inspect the HTML content for **image src attributes** and network calls for image requests that carry cookies.

### Case 2: Cookie scanner not finding certain cookies which are present on the domain

- Conduct domain scans in both EU and U.S. production cloud environments to confirm if the cookie scanner is detecting the cookies as expected.
- If a cookie is only present on a specific subpage, verify using EFK logs whether the scanner scanned that page.
- When analyzing with browser developer tools, ensure you visit the domain in a fresh browser session to prevent cookie sharing across tabs.

### Case 3: Domain scan results showing incorrect service name, category, or uncondensed cookies

> [!NOTE]
> **Note**
> 
> Contact Securiti’s **Knowledge Base** team for assistance with the issue.

### Case 4: Domain scan failed due to the domain not being reachable

- Check the EFK logs for issues such as all proxies being unable to reach the domain.
- Ensure the customer's domain is accessible online. If necessary, the customer may need to whitelist our IP addresses and initiate a rescan.

For more information on whitelisting the IP addresses, see [Configuring cookie scanner allow-listing](/v1/docs/configuring-cookie-scanner-allow-listing).

### Case 5: Domain scans running slowly or getting stuck

- You must first review the EFK logs to determine if multiple large domain scans are causing delays.
- If no such activity is observed in the EFK logs for domain scanner pods, you can escalate the issue by raising a priority ticket to the development team.

### Case 6: Domain scan failed due to exceeding 24 hours

- Use the domain scan doctor feature to terminate domain scans that exceed 24 hours.
- Reinitiate the domain scan to determine if the issue continues.

### Case 7: Unable to abort a running domain scan

- The abort scan functionality operates asynchronously and may be delayed depending on the current workload. If it takes longer than an hour, consider escalating the issue.

### Case 8: Domain scan stuck due to invalid domain

- An unresolved bug causes domain scans to get stuck when the domain does not exist, preventing the scan status from updating until the issue is addressed.

### Case 9: Understanding the differences between online and offline domain scan results

When evaluating the domain scan results, it is crucial to recognize that offline scanning inherently relies on manual navigation, which may not cover the entire domain as systematically as Securiti’s automated online domain scanner. The nature of offline scanning means it is often conducted in less controlled environments, where the web browser session might not be entirely fresh or isolated from other activities. This can lead to discrepancies as cookies from previously visited domains or open tabs might be picked up during the offline scan, further distinguishing it from the online method.

Moreover, the settings within the web browser itself can significantly impact the results of an offline domain scan. For instance, in Google Chrome, users have the option to disable third-party cookies. If this setting is enabled during an offline domain scan, it will prevent the collection of third-party cookies, thereby affecting the scan results. This highlights another layer of variability introduced by browser-specific settings that do not typically influence the controlled environment of an online domain scan. These factors underscore why offline and online scan results should not be directly compared without considering these contextual differences.

Use the following table to understand that differences between online and offline domain scan results are expected and these two should not be directly compared due to inherent differences in their methodologies.

| Aspect | Online Scan | Offline Scan |
| --- | --- | --- |
| Scope of Scanning | Comprehensive and crawls through a maximum of **1200** subpages. | Depends on manually visited pages; specific cookies may be missed. |
| Browser Session | Domain scan occurs in fresh browser sessions. | Fresh sessions are expected but not enforceable; may collect shared cookies. |
| Cookie Collection | Scanner collects third-party cookies by default. | If the web browser blocks third-party cookies, then cookies won't be collected. |
| Techniques Used | Uses multiple techniques like network proxies, response headers, etc. | Limited capabilities as the web browser plugin cannot fully control the web browser. |

Use the following table to determine when to use the offline cookie scanner.

| Scenario | Description |
| --- | --- |
| Limited Domain Accessibility | Use when the website is not exposed to the internet and the customer is not ready to whitelist our IP addresses. |
| Complex Login Mechanisms | Suitable for domains with login mechanisms not supported by the online scanner, such as **SSO** or **2FA**. |
| Selective Page Scanning | When the customer rejects online domain scan results or wishes to scan only a subset of pages. |
| Backup Solution | In situations where the online scanner does not work and the customer needs to proceed with domain and cookie configuration as a temporary solution. |

A small text file that is stored on a data subject's or website visitor's device (computer, smartphone, or tablet) by a domain (website). Cookies are used to collect information about the user's interactions with the website, such as preferences, login status, and browsing history. This information helps domains enhance user experience, perform analytics, and deliver personalized content and advertisements. Cookies can be categorized into various types, including Essential, Performance, Functionality, and targeting cookies, each serving different purposes in managing user consent and data privacy.

## Related

- [Scanning your website for cookies](/scanning-your-website-for-cookies.md)
- [Scanning domains in bulk](/scanning-domains-in-bulk.md)
