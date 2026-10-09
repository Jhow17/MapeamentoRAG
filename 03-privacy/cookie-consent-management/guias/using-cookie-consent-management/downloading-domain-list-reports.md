---
title: "Downloading domain list reports"
slug: "downloading-domain-list-reports"
updated: 2026-09-03T06:57:52Z
published: 2026-09-03T06:57:52Z
canonical: "helpcenter.securiti.ai/downloading-domain-list-reports"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Downloading domain list reports

Securiti lets you download the domain list reports for all the domains existing in your Securiti tenant. You can see information of different configurations applied on your domain from the exported domain list reports, and also use this information by importing it in your internal systems.

The domain list reports are not directly downloaded in your local machine. You receive an email containing the download link for the domain list reports instead. Your downloaded domain list report includes the following attributes for the domain(s) you selected when generating the domain list report:

| Attribute | Description |
| --- | --- |
| Domain URL | URL of the scanned domain(s). |
| Domain ID | ID of the scanned domain(s). |
| Domain UUID | Unique ID of the scanned domain(s). |
| Domain owner | Name of the owner who scanned the domain. |
| Domain group name | The name of the group which the domain belongs to. |
| Subdomains | Subdomain(s) that were found on your primary domain during the domain scan. |
| Last scanned date | The date when the domain was last scanned either by you or automatically. |
| Scan status | Domain scan status such as successful, failed, or incomplete. |
| Draft cookies count | Total count of cookies present in the draft mode of your cookie configuration. |
| Published cookies count | Total count of published cookies on your domain. |
| IAB GDPR policy version | The current version of the IAB or U.S National consent framework configured cookie banner and preference center. |
| Active version | The current version (active) of the domain. |
| Deployment type | 1,2 and 3 numbers represent automatic, manual, and legacy SDK deployment options respectively. For instance, if your domain is using automatic SDK deployment, you see 1 in the **deployment type** column of your domain list report. |
| Auto scan enabled | Auto scan status such as true or false. |

> [!WARNING]
> **Important**
> 
> - The following roles in your Securiti tenant have the access to download the domain list reports:
>   - Super Admin
>   - Organization Admin
>   - Operator
>   - DPO
>   - User
> - Securiti does not let the **Freemium** tier tenants download the domain list reports.

## Procedure

To deploy changes of your domains in bulk:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Mark the checkbox next to the name of the domains for which you want to download the domain list reports, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_0(2).png)
3. Alternatively, to select all domains at once, mark the checkbox next to the **Domain/Subdomain** column header in the upper-left corner of the domain list. Then click **Select all across all pages**, to select all domains across the entire pagination, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/domain_list_3(1).png)

> [!NOTE]
> Note
> 
> The **Cookie Consent Domains** page initially displays 10 domains, with pagination set at 10 domains per page. To change the number of displayed domains per page, from the bottom left corner of the page, click the menu next to **Showing**. You can choose to view 10, 25, or 50 domains per page.

Securiti displays the number of currently selected domains above the domain list, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/domain_list_4(2).png)
4. From the action toolbar above the domain list, click **Export Domain List**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/domain_list_1.png)
5. On the **Generate Domain List Export** popup, from the **Export using** menu, select one of the following report formats in which you want to download your domain list report, as shown below:
  - `Excel`
  - `JSON`
  - `CSS`

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/domain_list_2(1).png)

1. Once done, click **Generate** and Securiti sends you an email containing the download link.
2. Open your email associated with your Securiti tenant and download the domain list report by clicking the **Download File** button, as shown below. Securiti downloads a `ZIP` file containing the domain list reports in your local machine.

![Screenshot_2023-11-01_at_10_26_47_AM_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70d0c5cf-a052-b243-9228-e0fac716c897.png)

> [!NOTE]
> Note
> 
> The download link remains valid for **seven days**.

The Interactive Advertising Bureau (IAB) is a trade association representing advertising businesses. It develops industry standards, conducts research, and provides legal support for the online advertising industry. Cookie Consent Management module lets you configure your cookie banners and preference centers with two IAB privacy consent frameworks: the **EU TCF v2.2** and the **MSPA U.S. National**.
