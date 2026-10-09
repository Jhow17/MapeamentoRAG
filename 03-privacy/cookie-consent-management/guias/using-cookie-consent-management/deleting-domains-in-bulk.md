---
title: "Deleting domains in bulk"
slug: "deleting-domains-in-bulk"
updated: 2026-09-03T06:55:52Z
published: 2026-09-03T06:55:52Z
canonical: "helpcenter.securiti.ai/deleting-domains-in-bulk"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Deleting domains in bulk

Securiti lets you delete the domains present in your Securiti tenant in bulk. As a dynamic solution, this is a swift operation. All selected domains are instantly deleted from the module. We also maintain audit logs for this feature.

> [!WARNING]
> **Important**
> 
> - The following admin roles in your Securiti tenant can delete domains in bulk:
>   - Super Admin
>   - Organization Admin
> - Securiti considers all domains present in your Securiti tenant applicable for the bulk delete operation, except the domain(s) associated with the Privacy Center(s).
> - After deleting the domains from Securiti, ensure to remove the **deployment code** snippet from your domain’s code. Failing to do so may result in 404 console errors related to CDN files of deleted domains when inspecting the console tab from the inspect mode. However, these console errors **do not impact** the behavior of your domain in any way.

## Procedure

To delete the domains in bulk:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Mark the checkboxes next to the domains you want to delete in bulk, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_0(4).png)
3. You can also filter out domains to delete in bulk, and select them to delete. On the Cookie Consent Domains page, from the **Domains** table, select a domain either by scrolling down to it or by filtering it by its **name** or **group name** as explained in [Filtering the domain list](/v1/docs/scanning-your-website-for-cookies).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/delete_bulk_1.png)
4. (Optional) To select multiple domains at once, from the upper left corner of the domain list headers, mark the checkbox next to the Domain/Subdomain column header, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_2(3).png)

> [!NOTE]
> Note
> 
> The **Cookie Consent Domains** page initially displays 10 domains, with pagination set at 10 domains per page. To change the number of displayed domains per page, from the bottom left corner of the page, click the menu next to **Showing**. You can choose to view 10, 25, or 50 domains per page.

Securiti displays the number of currently selected domains above the domain list, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bulk_report_u1(2).png)
  1. Click **Select all across all pages** to select all domains across the entire pagination. For instance, if you are viewing 10 domains per page and have 100 domains spread across 10 pages, this option selects all 100 domains at once.
  2. Click **Select all on this page** to select all domains currently visible on the page. For instance, if you are viewing 10 domains per page and have 100 domains across 10 pages, this option selects only the 10 domains on the current page.
  3. Click **Select none** to not select any domain.
5. From the action toolbar above the domain list, click **Delete Domains**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/delete_bulk_2.png)
6. On the **Delete Domains** confirmation popup, type **bulk_delete** as confirmation text in the text field, and click **Delete**, as shown below.

![CCD-BulkDelete-7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84f12b87-4591-613c-13f1-122ec6e1c17c.png)

After the successful deletion of domains in bulk, Securiti shows you a confirmation message near the upper right corner of the **Cookie Consent Domains** page.
