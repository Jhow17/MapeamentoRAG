---
title: "Synchronizing assets from ServiceNow"
slug: "synchronizing-assets-from-servicenow"
updated: 2026-04-24T10:56:52Z
published: 2026-04-24T10:57:02Z
canonical: "helpcenter.securiti.ai/synchronizing-assets-from-servicenow"
stale: true
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Synchronizing assets from ServiceNow

> [!WARNING]
> **Important**
> 
> We assume you have the System Administrator role for your connector instance before configuring the asset sync via ServiceNow.

You can synchronize Securiti with a ServiceNow instance to import assets from ServiceNow into the catalog in the [**Data Mapping Automation**](/v1/docs/using-data-mapping-automation) module. Once, asset synchronization is complete, you can view assets in **Data Mapping Automation > Catalog > Assets**.

Once we have activated this feature for your account, use this procedure to configure asset sync from ServiceNow:

1. In Securiti open **Settings > Data Systems**, or from the System Settings page, select **Data Systems > Data Systems (Monitored)**.
2. Under “Integrations”, click **CMDB Systems**.

![Overview of CMDB systems showing active and inactive connectors with their statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Navigation_path.png)

In the upper right corner of the page, click **Add CMDB Systems**.
3. Choose the card for “ServiceNow” to create a new instance.

![Interface for adding a CMDB system with options for Okta and ServiceNow.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add_new_CMDB_data_system.png)

> [!NOTE]
> Note
> 
> The updated flow to access CMDB data systems is not available to all accounts; contact your Securiti representative for details and to activate this feature for your Securiti account.
4. Configure the connector as described in [Configuring the ServiceNow connector](/v1/docs/servicenow-connectors), with one exception: In ServiceNow, use one of the following Redirect URLs:

| Cloud | URL |
| --- | --- |
| US | `https://app.securiti.ai/static/activateAssetDatabase.html` |
| US1 | `https://app1.securiti.ai/static/activateAssetDatabase.html` |
| Canada | `https://app3.securiti.ai/static/activateAssetDatabase.html` |
| EU | `https://app.eu.securiti.ai/static/activateAssetDatabase.html` |
| Indonesia | `https://app2.securiti.ai/static/activateAssetDatabase.html` |
| Australia | `https://app4.securiti.ai/static/activateAssetDatabase.html` |
| UAE | `https://app5.securiti.ai/static/activateAssetDatabase.html` |
| Sovereign deployment | `https://&lt;sovereign_deployment_portal_host&gt;/static/activateAssetDatabase.html` |

![Screenshot_2022-11-07_at_12_30_54_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e9d26590-68a3-0532-ef42-0c3b3ea175f8.png)

![ServiceNow system settings interface showing instance setup and owner information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ServiceNow_instance.png)
5. After configuring the connector, wait for its status to change to "Scan Complete." This may take up to 20 minutes.
6. (Optional) Click the **Scheduling** tab and use the tools there to schedule periodic re-scans. Click **Add Exclusion** to create one or more exclusion periods during which Securiti does not perform re-scans.
7. When you are done, click **Save** to save your settings.
8. On the Connector Setup tab click **Initiate Data Scan** to start the synchronization. Securiti imports the assets from ServiceNow using the new ServiceNow catalog definitions template.
