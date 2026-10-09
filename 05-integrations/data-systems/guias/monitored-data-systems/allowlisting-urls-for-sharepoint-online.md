---
title: "Allowlisting URLs for SharePoint Online"
slug: "allowlisting-urls-for-sharepoint-online"
updated: 2026-06-23T06:00:55Z
published: 2026-06-23T06:00:55Z
canonical: "helpcenter.securiti.ai/allowlisting-urls-for-sharepoint-online"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Allowlisting URLs for SharePoint Online

This topic cover the list of allowlisting URLs for SharePoint Online Connector.

#### Allowlisting APIs for Data Inventory Sync with Self-hosted connector

You must allowlist the following APIs to successfully run the Data Inventory Sync for SharePoint Online (Self-hosted) Connector.

Default URL is `https://graph.microsoft.com/`

Default SharePoint site URL is `https://{tenant}.sharepoint.com/`

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://graph.microsoft.com/v1.0/sites/$collection/sites | Get all sites for collection |
| 2 | GET | https://graph.microsoft.com/v1.0/sites/$site_id/drives | Get all site drives |
| 3 | GET | https://graph.microsoft.com/v1.0/sites | Get all sites |
| 4 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id/root/delta | Get SharePoint drive delta |
| 5 | GET | https://graph.microsoft.com/v1.0/sites/$site_id | Get site meta |
| 6 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id | Get drive meta |
| 7 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id/root:/$folder_encoded_path:/children | Get configured folders data |
| 8 | GET | https://graph.microsoft.com/v1.0/drives/$drive_id/items/$item_id/children | Get folder content per drive |
| 9 | GET | https://{tenant}.sharepoint.com/_api/Web/SiteGroups | Get site groups |
| 10 | GET | https://{tenant}.sharepoint.com/_api/HubSites | List Hubsites |
| 11 | GET | https://{tenant}.sharepoint.com/_api/search/query | List Hub Linked Sites |
| 12 | GET | https://{tenant}.sharepoint.com/_api/SPO.Tenant/sites('$site_id') | Get Site Properties |

#### Allowlisting URLs for Discovery Scan with Self-hosted connector

Securiti requires the following URLs to be allowlisted on the customer's firewall for the Microsoft 365 SharePoint Online (Self-hosted) Connector for Sensitive data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:

- *https://graph.microsoft.com*
- *https://login.microsoftonline.com*

Additionally, you must allowlist either of the following URLs:

- **.sharepoint.com*

OR
- Both of the following:
  - *https://{{****<customer_tenant_name>****}}.sharepoint.com*
  - *https://{{****<customer_tenant_name>****}}-my.sharepoint.com*

To obtain the tenant's name for the allowlisted URL, perform the following steps.

1. See **Record Obtain Tenant Name and Domain step** in the [Obtain credentials for SharePoint Online Selective Site(s) Access](/latest/docs/obtain-credentials-for-sharepoint-online-selective-sites-access) or [Obtain credentials for SharePoint Online (Self-hosted)](/latest/docs/grant-access-and-obtain-credentials-in-sharepoint-online-self-hosted) to obtain the Tenant's name.
2. Replace the <customer_tenant_name> with the Tenant Name in the above URL.
