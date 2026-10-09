---
title: "Connect MoEngage connector with Securiti"
slug: "connecting-the-moengage-connector-in-securiti"
updated: 2026-07-31T06:31:02Z
published: 2026-07-31T06:31:02Z
canonical: "helpcenter.securiti.ai/connecting-the-moengage-connector-in-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect MoEngage connector with Securiti

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

1. Do one of the following:
  - If you have not created instances for MoEngage, Click **Create Instance**.
  - If you already have created a Data system Instance for MoEngage, click **+** in the upper right corner to create a new Instance.
2. Near the top of the page, click the **Basic Information** tab and apply the following settings:

| Parameter | Description | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the name that you entered when configuring the application in Moengage. | Moengage - Demo |
| Instance Location | Select **SaaS** as your preferred Hosting Location. Provide Country, State/Region, and City information. | Hosting Location: SaaS Country: United States of America State/Region: Alabama |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | john.doe@securiti.ai |
3. Click **Create Instance and Continue**.
4. Configure the following on the **Permissions** tab under the DSR Scan section:

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |
5. Near the top of the page, click the **Connector** tab.
6. Apply the following settings you recorded earlier in [Acquire API credentials in MoEngage](/latest/docs/acquire-api-credentials-in-moengage):

| **Parameter** | **Description** |
| --- | --- |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| **App ID** | Enter the App ID |
| **User Name** | Enter the Data API ID as the user name. The username uses a string parameter. See example below: *John Smith 04* |
| **Password** | Enter the Data API Key. The password uses a string parameter. See example below: *MyMarketingApp2023* |
7. Click **Authenticate & Activate Connector**.

Securiti activates the Connector.
