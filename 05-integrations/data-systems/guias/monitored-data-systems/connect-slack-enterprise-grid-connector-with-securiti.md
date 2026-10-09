---
title: "Connect Slack Enterprise Grid connector with Securiti"
slug: "connect-slack-enterprise-grid-connector-with-securiti"
updated: 2025-12-09T14:03:57Z
published: 2025-12-09T14:03:57Z
canonical: "helpcenter.securiti.ai/connect-slack-enterprise-grid-connector-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect Slack Enterprise Grid connector with Securiti

> [!CAUTION]
> Warning
> 
> Slack Enterprise Grid is currently unavailable due to Slack platform prerequisites required for integration.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Settings**.
4. From the **System Settings** menu, choose **Integrations** > **Data Systems** > **Monitored**.

1. In the data systems list, find the Slack tile and click **Create Instance**.
2. On the **Basic Information** tab, apply the following settings:

| **Setting** | **Description** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend that you use the application name you entered when configuring the application in Slack | Slack Enterprise Grid - Data |
| Instance Location | Select **SaaS** as the Hosting Location. Provide Country, State/Region, and City information. | Hosting location: SaaS Country: Australia |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. Mark the **Send notifications to all owners** checkbox to notify all the owners of the Instance. | john.doe@securiti.ai |
3. Click **Create Instance & Continue**.
4. Configure the following on the **Permissions** tab under the **DSR Scan** section:

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |
5. Near the top of the page, click the **Connector** tab.
6. Apply the following settings that you acquired in [Create and configure the connecting app in Slack Enterprise Grid](/v1/docs/create-and-configure-the-connecting-app-in-slack-enterprise-grid)

| **Setting** | **Description** |
| --- | --- |
| Connect with Pod | Select the Pod you configured earlier. |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Client ID | Enter the Client ID you recorded in step 5 of [Create and configure the connecting app in Slack Enterprise Grid](/v1/docs/create-and-configure-the-connecting-app-in-slack-enterprise-grid). The Client ID uses a string value. See the example below. *1234567891011.1008004440404* |
| Client Secret | Enter the Client Secret you recorded in step 5 of [Create and configure the connecting app in Slack Enterprise Grid](/v1/docs/create-and-configure-the-connecting-app-in-slack-enterprise-grid). The Client Secret uses a string value. See the example below. *n3v3rU53th1s_Ke3p1tS3cur3!* |
7. Click **Authenticate & Activate Connector**.

Securiti redirects you to the app's Authentication page in Slack and sign into your workspace.
8. Configure **Data Inventory Sync** for your Connector to enable Data Inventory and Entitlement scanning for your files. See [Configuring Data Inventory Sync for Slack Enterprise Grid](/docs/configuring-data-inventory-sync-for-slack-enterprise-grid), for more information.

See [Data Inventory Sync for self-hosted connectors](/v1/docs/data-inventory-sync-for-self-hosted-connectors), for more information.
9. Proceed to [Configure discovery scans in Slack Enterprise Grid](/v1/docs/configure-discovery-scans-in-slack-enterprise-grid).
