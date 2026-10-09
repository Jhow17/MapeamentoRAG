---
title: "Activate the Salesforce (Securiti Cloud) connectors in Securiti"
slug: "activate-the-salesforce-securiti-cloud-connectors-in-securiti"
updated: 2025-12-07T20:00:57Z
published: 2025-12-07T20:00:57Z
canonical: "helpcenter.securiti.ai/activate-the-salesforce-securiti-cloud-connectors-in-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Activate the Salesforce (Securiti Cloud) connectors in Securiti

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
  - If you have not yet created any Data system Instance Salesforce (Securiti Cloud), click **Create Instance** for it.
  - If you already have at least one Data system Instance for Salesforce (Securiti Cloud), near the upper right corner of the Instance, click **+** to create a new Instance.
2. Near the top of the page, click the **Basic Information** tab and apply the following settings as shown below:

| **Setting** | **Description** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the application name you entered when configuring the application in Salesforce. | Salesforce data Instance |
| Instance Location | Select your preferred Hosting Location and configure the Service provider settings. For more information, see [this section](/v1/docs/activate-the-salesforce-securiti-cloud-connectors-in-securiti#hosting-location-for-data-system-instance). Provide Country, State/Region, and City information. | Hosting location: SaaS Country: Australia |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | john.doe@securiti.ai |
3. Click **Create Instance & Continue**.
4. On the **Connector** tab, apply the following settings:

| **Setting** | **Description** |
| --- | --- |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Use Domain ID | Enable the toggle to use Domain ID as the input value. |
| Instance/Domain id | Enter the Instance ID or Domain ID you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The Instance/domain ID uses a string value. See an example below. *foundry-123* |
| Consumer Key | If you are not using a Keyring, enter the Consumer Key you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The consumer key is the public identifier for the Connector and uses an alphanumeric string value. See an example below. *3MVG9lKcPoNINVBIPJjdw1J9LLM82Hn_9Z1Y39uUexTInpH6rP6ConZah1WmmzPfWvP9CqFJ86G32Wo3mpfiB* |
| Consumer Secret | If you are not using a Keyring, enter the Consumer Secret you recorded earlier in [Register a connecting app in Salesforce](/v1/docs/register-a-connecting-app-in-salesforce). The consumer secret is the confidential key for the Authentication and uses an alphanumeric string value. See an example below. *5678901234567890123* |
5. Click **Authenticate & Activate Connector.**

Securiti redirects you to Salesforce to authenticate the connecting application's Credentials you entered into the Connector tab.
6. Click **Allow**.

![SF_ConnectAuth_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25551145-581b-5a1d-8776-25c67471755f(1).png)

Salesforce redirects you back to the Connector tab. Securiti activates the Connector.

> [!WARNING]
> **Important**
> 
> Securiti sends email notifications to Connector owners when critical access-related issues occur during a metadata or Discovery scan.
> 
> These notifications are triggered by Authentication and authorization issues such as:
> 
> - An expired or invalid access or refresh Token
> - An invalid Connector Configuration
> - Other Authentication grant errors for example, invalid_grant
7. Configure the following on the **Permissions** tab under the **Privacy Platform Integration** section:
  - **Enable Privacy Platform Integration**: Enable the toggle to include the Data system Instance for Integration in the Privacy **Platform Integrations**. For more information, see [Using the Privacy Platform Integrations](/v1/docs/configuring-salesforce-integration-in-securiti).

> [!NOTE]
> **Important**
> 
> **Privacy Integrations Framework** is available by subscription only. Contact [support@securiti.ai](http://support@securiti.ai) to enable it for your tenant.

Once the toggle is enabled, Scoping Metadata Sync starts for the Data system Instance. After the sync completes, the Data system Instance can be used in the Privacy **Platform Integrations**.

> [!NOTE]
> **Note**
> 
> - Once enabled, the **Enable Privacy Platform Integration** toggle cannot be disabled.
> - Scoping Metadata Sync runs every 7 days after completion. Additionally, it runs every 15 minutes to detect any new Data system instances.
> - Securiti does not let you deactivate and purge a Data system Instance that is used in Privacy **Platform Integrations**
8. Configure the following on the **Permissions** tab under the **DSR Scan** section:

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enable this option to include the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For structured data system instances, Securiti creates subtasks in the DSR workbench. If no data is found during the data search, the subtasks are automatically deleted. |
| Allow Multi Column Join DSR | Enable this to combine data from multiple tables based on the values in more than one column. It enables AND condition in the DSR joins. |
| Require indices on primary identifier columns | Enable this if you require an index to exist on primary identifier columns, such as SSN or Email address, for any DSR to improve the speed of data retrieval operations. Enabling this option makes the DSR run more efficiently. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |
9. Configure the following on the **Permissions** tab under the **Security Posture scan settings** section, and click **Run a scan now**.

> [!NOTE]
> Note
> 
> You cannot cancel a running Security Posture scan, it must complete its current scanning because the platform does not support in-flight termination. However, you can disable posture scanning by clearing Enable Security Posture Scan checkbox to prevent any future or scheduled runs from starting.

| Parameter | Description |
| --- | --- |
| Enable Security Posture Management | Enabling this option runs one-time or periodic posture scans as per your schedule settings. After marking the checkbox, set the **Period** and **Exclusion Time** in the fields below. Running posture scans on the Data system checks for any policy violations and performs automated Remediation of misconfigurations. > [!NOTE] > **Note** > > By default, **Auto Scan** option is selected. |
| Select Mode (Monitor Only) | The Select mode lets you monitor the misconfigurations associated with your SaaS Cloud account. For SaaS applications ‘Monitor Only’ is available for now. This option is enabled by default if the **Enable Security Posture Management** checkbox is marked. |
| Auto Scan | This option lets you schedule automatic posture scans to discover your data systems and their security posture. |
| Period | Set the Period for your scan frequency. The scan period can be hourly, weekly, or monthly. |
| (Optional) Exclusion Time | Set the time range in which you need to avoid running posture scans such as maintenance. |
10. Proceed to [Initiate Salesforce data scanning](/v1/docs/initiate-salesforce-data-scanning).

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
