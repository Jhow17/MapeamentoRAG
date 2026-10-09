---
title: "Deploying domains in bulk"
slug: "deploying-domains-in-bulk"
updated: 2026-09-03T06:54:33Z
published: 2026-09-03T06:54:33Z
canonical: "helpcenter.securiti.ai/deploying-domains-in-bulk"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Deploying domains in bulk

Securiti lets you deploy changes made to the cookie configuration of multiple domains present in your Securiti tenant all at once in bulk. We also maintain audit logs for this functionality.

You can modify the cookie configurations of multiple domains individually without needing to deploy each change separately. Once you've completed the modifications, deploy them all at once using the bulk deploy operation. This functionality offers:

| Offering | Description |
| --- | --- |
| Time Efficiency | You can make changes to multiple domains without the need for individual deployments, saving time compared to deploying each change separately. |
| Simplified Management | Managing modifications across multiple domains becomes more straightforward as you can handle them collectively rather than individually. |
| Reduced Risk of Errors | With bulk domain deployment, there is a lower chance of oversight or error during the deployment process, enhancing overall reliability. |
| Streamlined Workflow | The functionality promotes a smoother workflow by letting you complete all modifications before deploying them in a single operation, eliminating the need for multiple deployment steps. |
| Improved Productivity | You can focus more on making necessary changes rather than managing deployment logistics, thereby boosting productivity. |

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.

## Key considerations

You must consider the following points when deploying domains in bulk:

- The completion time of bulk domain deployment operation depends on the number of domains included in the deployment operation.
- Securiti lets you deploy a maximum of **50 domains** in bulk at a time.
- Domains pinned to a specific manual SDK deployment option are automatically updated to the most recent Securiti release version at the time of deployment.

## Procedure

To deploy changes of your domains in bulk:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Mark the checkboxes next to the domains you want to deploy in bulk, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_0(2).png)
3. (Optional) To select multiple domains at once, from the upper left corner of the domain list headers, mark the checkbox next to the Domain/Subdomain column header, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scanning_bulk_2(4).png)

> [!NOTE]
> Note
> 
> The **Cookie Consent Domains** page initially displays 10 domains, with pagination set at 10 domains per page. To change the number of displayed domains per page, from the bottom left corner of the page, click the menu next to **Showing**. You can choose to view 10, 25, or 50 domains per page.

Securiti displays the number of currently selected domains above the domain list, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/bulk_report_u1(3).png)
  1. Click **Select all across all pages** to select all domains across the entire pagination. For instance, if you are viewing 10 domains per page and have 100 domains spread across 10 pages, this option selects all 100 domains at once.
  2. Click **Select all on this page** to select all domains currently visible on the page. For instance, if you are viewing 10 domains per page and have 100 domains across 10 pages, this option selects only the 10 domains on the current page.
  3. Click **Select none** to not select any domain.
4. From the action toolbar above the domain list, click **Deploy**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deploy_bulk_1.png)

> [!WARNING]
> Important
> 
> Securiti lets you select all domains present in your Securiti tenant for the bulk domain deployment operation, except:
> 
> - Domains that are in the **Scan Requested** state. These are domains on which you have already initiated (requested) the scan.
> - Domains that are in the **Scan In Progress** state. These are domains on which scans are already running.
> - Newly created domains that are not scanned yet. Such domains have nothing in the draft version.
> - Newly created domains on which you initiated the scan, but the scan failed.
> - Domains (new or existing) with nothing in the draft state.
> 
> The domains with the aforementioned statuses are not eligible for the bulk domain deployment operation.
5. On the **Confirm Deployment Details** popup, in the **Change Note** text field, enter your summary of the changes, mark the checkboxes next to the terms listed below **Please acknowledge**, and click **Deploy**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/deploy_bulk_2.png)

Once the bulk domain deployment operation initiates successfully, Securiti shows you a success message near the upper right corner of the page.
