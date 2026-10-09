---
title: "Configure Data Inventory Sync for Confluence Cloud"
slug: "configure-data-inventory-sync-for-confluence-cloud"
updated: 2026-08-31T08:47:14Z
published: 2026-08-31T08:47:14Z
canonical: "helpcenter.securiti.ai/configure-data-inventory-sync-for-confluence-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure Data Inventory Sync for Confluence Cloud

Securiti supports data inventory sync and entitlement scanning for Confluence Cloud (self-hosted) data system connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/v1/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure data inventory sync and entitlement scanning for your data system instance, after the connector activation. Prior to the connector activation process, fulfill any required prerequisites as highlighted in the [section below](/v1/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

### Prerequisites for running Data Inventory Sync for Confluence Cloud

#### Permissions required for Confluence Cloud Data Inventory Sync

You must configure the required permissions in [Acquire authentication credentials in Confluence Cloud](/v1/docs/acquire-authentication-credentials-in-confluence-cloud) for running Data Inventory sync on Confluence Cloud data system instance.

In the **Granular scopes** section, add the below permissions:

- **read:content-details:confluence**: This permission lets Securiti read detailed content information within Confluence.
- **read:permission:confluence**: This permission lets Securiti read permission settings which are important for understanding who has access to specific content and which entitlements are associated with the content.

Add the following permissions in the **Classic scopes** section:

- **read:confluence-groups**: This permission lets Securiti read group details within Confluence.
- **read:confluence-content.permission**: This permission lets Securiti read the permission settings for specific content in Confluence. It is used to determine which users or groups have permissions to view, edit, or manage specific pages or spaces, which is essential for entitlement scanning.

#### Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti pod and the Confluence Cloud APIs to successfully run the Data Inventory Sync.

Following are the Base URLs for the Confluence Cloud APIs

- **Default URL:** "https://api.atlassian.com/ex/jira"
- **Atlassian URL:** "https://api.atlassian.com"
- **Site_URL:** "https://{{site_name}}.atlassian.net"

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://api.atlassian.com/ex/jira/_edge/tenant_info | Get configured site id |
| 2 | GET | https://api.atlassian.com/ex/jira/oauth/Token/accessible-resources | Get accessible sites |
| 3 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/search | Get all project issues |
| 4 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/search | Get issues |
| 5 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/attachment/content/$attachment_id | Download attachment |
| 6 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/issue/{{issue_id}} | Get an issue |
| 7 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/issue/{{issue_id}}/comment | Get comments of an issue |
| 8 | GET | https://api.atlassian.com/ex/jira/{{site_id}}/rest/api/2/project/search | List projects |
| 9 | GET | https://api.atlassian.com/ex/jirarest/api/2/users/search | Get all users |
| 10 | GET | https://api.atlassian.com/ex/jira/rest/api/2/permissions/check | Get permissions |

### Configure Data Inventory Sync for Confluence Cloud

After activating the Confluence Cloud connector, wait until the discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and entitlement scan for Confluence Cloud.

1. In the **Inventory** tab, under the **Data Inventory Sync**, configure the following settings:

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Enable Data Inventory Sync | Enable the toggle to sync the metadata for your data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: All sites and their spaces - Data inventory: All Pages, Blogposts, Attachments and all comments for pages and blogposts |
| Run Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines | View permissions on Confluence spaces and files used to restrict prompt responses in our Gencore AI product. |
2. (Optional) In the **Data Inventory Sync and Gencore Entitlements Scope** section on the same **Inventory** tab, select the collections of data resources to be included in your inventory.

You can select the following scopes:
  - Sites
  - Spaces
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory and Entitlement scans:

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.

For more information on Scan statistics, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

For more information on viewing Confluence Cloud metadata in graph, proceed to [Viewing Confluence Cloud metadata in Securiti](/latest/docs/viewing-confluence-cloud-metadata-in-securiti).
