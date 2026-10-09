---
title: "Connect Salesforce Commerce Cloud connector with Securiti"
slug: "connecting-salesforce-commerce-cloud-connector-with-securiti"
updated: 2026-07-31T10:29:04Z
published: 2026-07-31T10:29:04Z
canonical: "helpcenter.securiti.ai/connecting-salesforce-commerce-cloud-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect Salesforce Commerce Cloud connector with Securiti

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
  - If you have not yet created any Data system instances for Salesforce Commerce Cloud, click **Create Instance** for it.
  - If you already have at least one Data system Instance for Salesforce Commerce Cloud, near the upper right corner of the Instance, click **+** to create a new Instance.
2. On the **Basic Information** tab, apply the following Instance settings:

| **Setting** | **Description** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the application name you entered when configuring the application in Salesforce Commerce Cloud. | SFCommerce - Data |
| Instance Location | Select your preferred Hosting Location and configure the Service provider settings. Provide Country, State/Region, and City information. | Hosting location: SaaS Country: Australia |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | john.doe@securiti.ai |
3. Under Owners, choose the owner. By default, you’re the owner.
4. (Optional) Check the Identify Data element Type(s) area for the listed Data element types.
5. Configure the following on the **Permissions** tab under the **DSR Scan** section:

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |
6. On the Connector tab, apply the following settings:

| Setting | Description |
| --- | --- |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Authentication Type | Select **Basic** Authentication type from the menu. |
| Site ID | Enter the site ID you recorded in [Grant permissions and obtain credentials in Salesforce Commerce Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-salesforce-commerce-cloud) for Salesforce Commerce Cloud. The site ID uses a string value. See example below. *app_finuser_fu* |
| Consumer Key | Enter the Consumer Key you recorded in [Grant permissions and obtain credentials in Salesforce Commerce Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-salesforce-commerce-cloud) for Salesforce Commerce Cloud. The consumer key is the public identifier for the Connector and uses an alphanumeric string value. See the example below. *3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpH6rP6ConZah1WmmzPfWvP9CqFJ86G32Wo3mpfiB* |
| Consumer Secret | Enter the Consumer Secret you recorded in [Grant permissions and obtain credentials in Salesforce Commerce Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-salesforce-commerce-cloud) for Salesforce Commerce Cloud. The consumer secret is the public identifier for the Connector and uses an alphanumeric string value. See the example below. *5678901234567890123* |
| Base URL | Enter the base URL you constructed in [Grant permissions and obtain credentials in Salesforce Commerce Cloud](/latest/docs/grant-permissions-and-obtain-credentials-in-salesforce-commerce-cloud) for Salesforce Commerce Cloud. See example below. *https://development-ap01-finusert.abcware.net* |
7. Click **Authenticate & Activate Connector**.

Securiti activates the Connector.

#### Hosting location for data system instance

When creating an Instance for your Data system, you can select your preferred Hosting location in the **Instance location** section of the **Basic information** tab of the Connector you want to configure.

Securiti supports IaaS, SaaS, or Private Cloud as Hosting options for your Data system Instance.

For IaaS, Securiti supports the following service providers.

- AWS
- GCP
- OCI
- AZURE

Select your Service provider and configure additional fields or options based on your Connector prerequisites (where applicable) as described below.

| Service provider | Parameter | Description |
| --- | --- | --- |
| AWS | - Account ID - Region - Managed toggle | - Log in to your AWS Management Console, and your Account ID can be found in the upper right corner of the dashboard. e.g., *123456789012* - Specify the AWS region where you want to host your Securiti Instance, from the menu. e.g., *canadacentral* - Turn on the managed toggle option for controlled or native assets. |
| GCP | - Project ID - Region - Managed toggle | - Log in to your Google Cloud Console, select your project, and the Project ID can be found on the project dashboard. Eg, *my-project-123456* - Specify the GCP region where you want to host your Securiti Instance, from the menu. e.g., *asiaeast1* - Turn on the managed toggle option for controlled or native assets. |
| OCI | - Tenancy ID - Account ID - Region - Managed toggle | - Log in to your OCI Console, navigate to your tenancy details, and the Tenancy ID can be found in the tenancy information. e.g., *ocid1.tenancy.oc1..aaaaaaaa…* - Similar to the Tenancy ID, the Account ID can be found in the tenancy information. e.g., *ocid1.oc1..aaaaaaaa...* - Specify the OCI region where you want to host your Securiti Instance, from the menu. e.g., *ca-montreal-1* - Turn on the managed toggle option for controlled or native assets. |
| AZURE | - Account ID - Region - Managed toggle | - Log in to your Azure portal, and your Account ID can be found in the upper right corner of the dashboard. e.g., *12345678-90ab-cdef-1234-567890abcdef* - Specify the AZURE region where you want to host your Securiti Instance, from the menu. Eg, *canadacentral* - Turn on the managed toggle option for controlled or native assets. |
