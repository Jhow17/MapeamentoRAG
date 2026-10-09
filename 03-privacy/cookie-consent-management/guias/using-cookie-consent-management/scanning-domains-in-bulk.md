---
title: "Scanning domains in bulk"
slug: "scanning-domains-in-bulk"
updated: 2026-09-03T06:56:23Z
published: 2026-09-03T06:56:23Z
canonical: "helpcenter.securiti.ai/scanning-domains-in-bulk"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Scanning domains in bulk

Securiti lets you scan the domains present in your Securiti tenant in bulk. As a dynamic solution, the completion time of bulk domain scan operation adapts to the number of domains included. We also maintain audit logs for this feature.

If you initiate an individual scan on your domain following the activation of the bulk scan, the scanner detects and processes your individual scan once the bulk scan is entirely finished. The completion of the individual scan may experience delays while waiting for the bulk scan operation to complete.

> [!NOTE]
> **Note**
> 
> If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.

## Procedure

To scan your domains in bulk:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Mark the checkboxes next to the domains you want to scan in bulk, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_0.png)
3. (Optional) To select multiple domains at once, from the upper left corner of the domain list headers, mark the checkbox next to the Domain/Subdomain column header, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_2.png)

> [!NOTE]
> Note
> 
> The **Consent Domains** page initially loads and displays 50 domains, with pagination set at 50 domains per page. To view all your domains at once, you must scroll down to the bottom of the page. For instance, if you have 150 domains, you must scroll down to load the next set of 50 domains, and then scroll down again to the bottom of the page to load the remaining 50 domains.

Securiti displays the number of currently selected domains above the domain list, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/domain_list_4.png)
  1. Click **Select all across all pages** to select all domains across the entire pagination. For instance, if you are viewing 10 domains per page and have 100 domains spread across 10 pages, this option selects all 100 domains at once.
  2. Click **Select all on this page** to select all domains currently visible on the page. For instance, if you are viewing 10 domains per page and have 100 domains across 10 pages, this option selects only the 10 domains on the current page.
  3. Click **Select none** to not select any domain.
4. From the action toolbar above the domain list, click **Scan Domains**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_1.png)

> [!WARNING]
> Important
> 
> Securiti lets you select all domains present in your Securiti tenant for the bulk domain scan operation, except:
> 
> - The domains that are in the **Scan Requested** state. These are domains on which you have already initiated (requested) the scan.
> - The domains that are in the **Scan In Progress** state. These are domains on which scan is already running.
> - The domains that are in the **Scan Abort Requested** state. These are domains on which you initiated the scan, and later aborted it, but the abort action was still in progress. The scanner takes some time for the abort scan action to complete.
> 
> The domains with the aforementioned statuses are not eligible for the bulk domain scan operation.
5. On the **Scan Multiple Domains** confirmation popup, click **Start Scanning**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_4.png)

Once the bulk domain scan operation initiates successfully, Securiti shows you a success message near the upper right corner of the page, and the **Cookie Consent Domains** page refreshes automatically right away. You see loader icons in the running state next to the domains on which bulk domain scan operation is successfully initiated.

> [!CAUTION]
> **Caution**
> 
> Securiti does not let you cancel the bulk domain scan operation once you initiate it, because it is an irreversible action.

## Related

- [Scanning your website for cookies](/scanning-your-website-for-cookies.md)
- [Troubleshooting the domain scan result discrepancies](/troubleshooting-the-domain-scan-result-discrepancies.md)
