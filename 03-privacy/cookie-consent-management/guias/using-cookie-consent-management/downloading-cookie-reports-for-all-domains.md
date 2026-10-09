---
title: "Downloading cookie reports for all domains"
slug: "downloading-cookie-reports-for-all-domains"
updated: 2026-09-03T07:02:15Z
published: 2026-09-03T07:02:15Z
canonical: "helpcenter.securiti.ai/downloading-cookie-reports-for-all-domains"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Downloading cookie reports for all domains

Securiti lets you download the cookie reports for all the domains existing in your Securiti tenant for holistic cross-domain reporting. The cookie reports are not directly downloaded in your local machine. You receive an email containing the download link for the cookie reports instead.

> [!WARNING]
> **Important**
> 
> - You can only download the cookie reports for your domains that are **successfully scanned**, **published** and **contain cookies**. Cookie reports are not downloaded for domains that do not fulfill the aforementioned criteria.
> - Only the following roles in your Securiti tenant can download the cookie reports:
>   - Super Admin
>   - Organization Admin
>   - Operator
> - The following roles in your Securiti tenant only have **READ** permissions for this functionality:
>   - DPO
>   - User

## Procedure

To download the cookie reports for your domains:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Mark the checkboxes next to the name of the domains for which you want to download the cookie reports, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_0(1).png)
3. Alternatively, to select all domains at once, mark the checkbox next to the **Domain/Subdomain** column header in the upper-left corner of the domain list. Then click **Select all across all pages**, to select all domains across the entire pagination, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/domain_list_3.png)

> [!NOTE]
> Note
> 
> The **Cookie Consent Domains** page initially displays 10 domains, with pagination set at 10 domains per page. To change the number of displayed domains per page, from the bottom left corner of the page, click the menu next to **Showing**. You can choose to view 10, 25, or 50 domains per page.

Securiti displays the number of currently selected domains above the domain list, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/domain_list_4(1).png)
4. From the action toolbar above the domain list, click **Generate Cookie Reports**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bulk_report_u2.png)
5. On the **Generate Cookie Report** popup, from the **Export** **using** menu, select the report format in which you want to download your cookie report.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cookie_report_4.png)

> [!NOTE]
> Note
> 
> Securiti lets you choose between `Excel`, `JSON` and `CSV` file formats currently. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cookie_report_5.png)
6. Mark the **Combined report** radio button if you want to download a single cookie report for all selected domains.
7. Mark the **Separate report for each domain** radio button if you want to download a separate report against the selected domains.
8. Once done, click **Generate** and Securiti sends you an email containing the download link. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/cookie_report_6.png)
9. Open your email associated with your Securiti tenant and download the cookie report by clicking the **Download File** button, as shown below. Based upon your choice, Securiti downloads a `ZIP` file containing a combined cookie report or separate cookie reports in your local machine.

![Screenshot_2023-09-07_at_3_03_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0de5cf5-1c7b-7aef-852f-0ef85d0b17f3.png)

> [!NOTE]
> **Note**
> 
> The download link remains valid for **seven days**.
