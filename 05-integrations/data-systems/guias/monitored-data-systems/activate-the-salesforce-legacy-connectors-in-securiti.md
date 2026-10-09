---
title: "Activate the Salesforce (Legacy) connectors in Securiti"
slug: "activate-the-salesforce-legacy-connectors-in-securiti"
updated: 2026-03-10T05:49:35Z
published: 2026-03-10T05:49:35Z
canonical: "helpcenter.securiti.ai/activate-the-salesforce-legacy-connectors-in-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Activate the Salesforce (Legacy) connectors in Securiti

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
  - If you have not yet created any Data system Instance for Salesforce (Legacy), click **Create Instance** for it.
  - If you already have at least one Data system Instance for Salesforce (Legacy), near the upper right corner of the Instance, click **+** to create a new Instance.
2. Near the top of the page, click the **Basic Information** tab and apply the following settings as shown below:

| **Setting** | **Description** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the application name you entered when configuring the application in Salesforce. | Salesforce data Instance |
| Instance Location | Select your preferred Hosting Location and configure the Service provider settings. For more information, see [this section](/v1/docs/activate-the-salesforce-legacy-connectors-in-securiti#hosting-location-for-data-system-instance). Provide Country, State/Region, and City information. | Hosting location: SaaS Country: Australia |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | john.doe@securiti.ai |
3. Click **Create Instance & Continue**.
4. On the **Connector** tab, apply the following settings:

| **Setting** | **Description** |
| --- | --- |
| Connect with Pod | From the menu, select the Pod you configured earlier. |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Use Domain ID | Enable the toggle to use Domain ID as the input value. |
| Instance/Domain id | Enter the Instance ID or Domain ID you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The Instance/domain ID uses a string value. See an example below. *foundry-123* |
| (Optional) Use Keyring | To use Credentials in a Keyring, enable the toggle and then choose the Keyring type and add choose the Keyring you created earlier. See the following resources for more information. - [Using keyrings](/v1/docs/using-keyrings) - [Configuring credential vaults](/v1/docs/configuring-credential-vaults) - [(Optional) Configure the Hashicorp OAuth token for Salesforce (Legacy)](/v1/docs/optional-configure-the-hashicorp-oauth-token-for-salesforce-legacy) > [!WARNING] > **Important** > > For connectors using HashiCorp's OAuth plugin, Securiti dynamically retrieves the Credentials. For multiple accounts requiring different credential paths, you must configure separate keyrings. > > Keyrings can be linked to connectors in the following ways: > > - Multiple connectors can share the same Keyring. > - A Connector can only have one Keyring linked at a time, which can be updated during the Reconfiguration process. |
| Consumer Key | If you are not using a Keyring, enter the Consumer Key you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The consumer key is the public identifier for the Connector and uses an alphanumeric string value. See an example below. *3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpmiB* |
| Consumer Secret | If you are not using a Keyring, enter the Consumer Secret you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The consumer secret is the confidential key for the Authentication and uses an alphanumeric string value. See an example below. *5678901234567890123* |
| (Optional) Store Sample file on PCS | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Authenticate & Activate Connector.**

Securiti redirects you to Salesforce to authenticate the connecting application's Credentials you entered into the Connector tab.
6. Click **Allow**. ![SF_ConnectAuth_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25551145-581b-5a1d-8776-25c67471755f.png)

Salesforce redirects you back to the Connector tab. Securiti activates the Connector.
7. Configure the following on the **Permissions** tab under the **DSR Scan** section:

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enable this option to include the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For structured data system instances, Securiti creates subtasks in the DSR workbench. If no data is found during the data search, the subtasks are automatically deleted. |
| Allow Multi Column Join DSR | Enable this to combine data from multiple tables based on the values in more than one column. It enables AND condition in the DSR joins. |
| Require indices on primary identifier columns | Enable this if you require an index to exist on primary identifier columns, such as SSN or Email address, for any DSR to improve the speed of data retrieval operations. Enabling this option makes the DSR run more efficiently. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |
8. Proceed to [Configure discovery scans in Salesforce (Legacy)](/v1/docs/configure-discovery-scans-in-salesforce-legacy).
