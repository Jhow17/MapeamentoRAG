---
title: "Editing the domain configurations in bulk"
slug: "editing-the-domain-configurations-in-bulk"
updated: 2026-09-03T07:00:32Z
published: 2026-09-03T07:00:32Z
canonical: "helpcenter.securiti.ai/editing-the-domain-configurations-in-bulk"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Editing the domain configurations in bulk

Securiti’s Bulk Edit Domain Configurations functionality helps you apply consistent cookie settings to multiple domains at once. It gives you a streamlined way to update key configurations such as deployment model, monthly scan, ADA compliance, and top-level domain consent at once.

Bulk editing not only saves time but also helps reduce configuration errors, improve consistency, and support faster deployment across your domain list. You can also use this functionality to apply meaningful labels to domains in bulk, making it easier to organize and filter domains across business units, regions, or environments.

Use the following table to understand the operational value of this functionality offers:

| Offering | Description |
| --- | --- |
| Configuration consistency across domains | With bulk updates, customers can apply identical configurations, such as enabling ADA compliance or standardizing deployment models across hundreds of domains, which minimizes configuration drift and ensures a uniform privacy experience for data subjects. |
| Error reduction and change accuracy | Manually editing each domain increases the likelihood of a misconfiguration. Bulk edits reduce this risk by letting customers apply exact settings across selected domains in a single action. |
| Governance and audit readiness | By centralizing configuration changes and allowing downloadable deployment-ready files, this feature supports better documentation, tracking, and audit preparedness for compliance teams. |
| Faster deployment at scale | You can deploy updated configurations faster across a large domain list, helping you stay compliant when introducing new standards or updating cookie banner behavior. |
| Labeling and organizational efficiency | The ability to apply labels in bulk helps large organizations and businesses organize and track domains by team, brand, region, or environment which is useful for internal reporting and operations. |

## Key considerations

- Securiti only publishes domains with active drafts. Domains already in a published state remain unchanged.
- If you bulk-update deployment models from manual to automatic SDK, all selected domains start receiving the latest SDK and CSS updates from Securiti.
- Each test and production code file is tailored to the corresponding domain to ensure precise deployment.

## Procedure

To edit the domain configurations in bulk:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent > Domains**.
2. Mark the checkboxes next to the domains whose configurations you want to edit in bulk, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select-Domains.png)
3. (Optional) If you want to select multiple domains at once, from the upper left corner of the domain list headers, mark the checkbox next to the **Domain/Subdomain** column header, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select-Multiple-Domains.png)

> [!NOTE]
> Note
> 
> The **Cookie Consent Domains** page initially loads and displays 10 domains, with pagination set at 10 domains per page. To change the number of displayed domains per page, from the bottom left corner of the page, click the menu next to the **Showing**. You can choose from 10, 25 and 50 domains per page.

Securiti displays the number of currently selected domains above the domain list, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Displays-Selected-Domains.png)
  1. Click **Select all across all pages** to select all domains across the entire pagination. For instance, if you are viewing 10 domains per page and have 100 domains spread across 10 pages, this option selects all 100 domains at once.
  2. Click **Select all on this page** to select all domains currently visible on the page. For instance, if you are viewing 10 domains per page and have 100 domains across 10 pages, this option selects only the 10 domains on the current page.
  3. Click **Select none** to not select any domain or unselect any previously selected domains.
4. From the action toolbar above the domain list, click **Edit Configurations**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select-Edit-Configuration.png)
5. On the **Bulk Edit Configurations** popup, click **Update** next to each configuration, as shown below. Depending on the configuration, you might need to select a radio button, type a value, or choose an option from a dropdown menu. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Edit-Configurations-Popup.png) You can update the following configurations in bulk:

| Configuration | Description |
| --- | --- |
| Deployment model | Switch between automatic or manual SDK deployment. |
| Monthly scan | Enable or disable automatic monthly scans. |
| Strict CSP | Enforce or relax strict content security policy. |
| ADA compliance | Enable or disable compliance with the Americans with Disabilities Act. |
| Top-level domain consent | Apply consent at the top-level domain for coverage across subdomains. |
| Auto-blocking | Enable or disable automatic blocking of non-essential scripts. |
| Labels | Add new or override existing domain labels for easier grouping, filtering, and management. |
6. (Optional) If you want to add more domains, from the **Search Domains** menu, select the names of the domains or type their URLs, and press enter, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add-Domains-From-Popup.png)

Securiti displays all the currently selected domains below the Search Domains menu.
7. From the bottom of the popup, click **Update** to save all the selected configurations, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Edit-Configurations-Popup-Update.png)
8. From the **Configuration Updated** popup, click **Download Test & Production Code Files** to download a `.zip` file containing test and production code files for all selected domains and receive a copy via email, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download-Code-Files-Zip.png) ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Email.png)

> [!NOTE]
> Note
> 
> You must use the test code in your QA or staging environment to conduct thorough tests.

On the **Configuration Updated** popup, Securiti shows you the number of domains you selected for bulk configurations and the number of configurations you updated for those domains, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Configuration-Updated-Popup.png)
9. From the bottom of the popup, click **Proceed to Deploy Updates** to apply the updated configurations across the selected domains, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Configuration-Updated-Deploy-Updates.png)
10. On the **Confirm Deployment Details** popup, in the **Change Note** text field, enter your summary of the changes, and mark all the checkboxes next to the terms listed below **Please acknowledge**. Then, from the bottom of the popup click **Deploy**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Confirm-Deployment-Details-Popup.png) Once the bulk domain configuration operation initiates successfully, Securiti shows you a success message near the upper right corner of the page.
