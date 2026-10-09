---
title: "(Optional) Acquire Quarantine Policy parameters in SharePoint Online"
slug: "optional-acquire-quarantine-policy-parameters-in-sharepoint-online"
updated: 2026-06-23T05:56:31Z
published: 2026-06-23T05:56:31Z
canonical: "helpcenter.securiti.ai/optional-acquire-quarantine-policy-parameters-in-sharepoint-online"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Acquire Quarantine Policy parameters in SharePoint Online

You can configure the quarantine policy when activating the SharePoint Online Self-hosted Connector in Securiti.

> [!WARNING]
> **Important**
> 
> Before proceeding, ensure you are the admin with this privilege:
> 
> - Sites.ReadWrite.All

The Quarantine Policy uses the Site URL and Library Name as Activation parameters:

> [!NOTE]
> **Note**
> 
> - Files belonging to system libraries will be excluded from the File Quarantine process.
> - Securiti checks multiple SharePoint sites when running quarantine diagnostics. If an individual site is inaccessible or misconfigured, the diagnostic continues checking other available sites before returning a result. A quarantine permission failure for one site does not indicate a failure across your entire SharePoint tenant. For more information, see [Using Auto-diagnostic reports for connectors](/latest/docs/auto-diagnostic-reports-in-data-system-connectors).

1. On the Microsoft 365 dashboard, from the **All Apps** sidebar view, select **SharePoint**.

![all_apps.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fca1b0e-a926-8661-17d5-dc4fe37c92ed.png)
2. At the top of the page, in the search bar, enter the site name. You can filter the results by clicking the **Sites** tab.

![search_bar.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99cfef7d-478b-8a26-5978-53101551105e.png)

![sites_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a919dfe7-66a6-daa6-2f80-ee7b1d370ee7.png)
3. Record the URL of the site you want from the search results.

![record_site_url.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-40f63d3b-4ffa-35b9-4e3f-86762f2a6c48.png)
4. (Optional) You can also record the URL by clicking on your site's home icon and copying the URL in the address bar.

![site_url_in_address_bar.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86985117-a421-1db6-f9c3-771d22b2ea8a.png)

Proceed to [Connecting Microsoft 365 SharePoint Online (Self-hosted) with Securiti](/latest/docs/new-ui-connecting-microsoft-365-sharepoint-online-self-hosted-with-securiti).
