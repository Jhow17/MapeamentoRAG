---
title: "Connect Salesforce Chatter connector with Securiti"
slug: "connecting-salesforce-chatter-connector-with-securiti"
updated: 2026-07-31T09:54:08Z
published: 2026-07-31T09:54:08Z
canonical: "helpcenter.securiti.ai/connecting-salesforce-chatter-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect Salesforce Chatter connector with Securiti

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
  - If you have not yet created any Data system instances for Salesforce Chatter, click **Create Instance** for it.
  - If you already have at least one Data system Instance for Salesforce Chatter, near the upper right corner of the Instance, click **+** to create a new Instance.
2. Near the top of the page, click the **Basic Information** tab and apply the following settings:

| **Setting** | **Description** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend that you use the application name you entered when configuring the application in Salesforce Chatter. | SF Chatter - Data |
| Instance Location | Select your preferred Hosting Location and configure the Service provider settings. For more information, see [this section](/v1/docs/activate-the-salesforce-chatter-connector-in-securiti#hosting-location-for-data-system-instance). Provide Country, State/Region, and City information | Hosting location: SaaS Country: Australia |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | John.doe@securiti.ai |
3. Click **Create Instance > Continue**.
4. Near the top of the page, click the **Connector** tab.
5. Enter the following information that you recorded in [Acquire authentication credentials in Salesforce Chatter](/latest/docs/acquire-authentication-credentials-in-salesforce-chatter) as shown below.

| **Settings** | **Description** |
| --- | --- |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Use Domain id | Toggle the *Use Domain id* button to use Domain ID as the input value |
| Instance/Domain id | Enter the Instance ID or Domain ID you acquired in [Acquire authentication credentials in Salesforce Chatter](/latest/docs/acquire-authentication-credentials-in-salesforce-chatter) |
| Consumer Key | Enter the Consumer Key you acquired in [Acquire authentication credentials in Salesforce Chatter](/latest/docs/acquire-authentication-credentials-in-salesforce-chatter). The Consumer Key uses a string value. See the example below. *8a7b3c9d-12e4-567f-89ab-0123456789cd* |
| Consumer Secret | Enter the Consumer Secret you acquired in [Acquire authentication credentials in Salesforce Chatter](/latest/docs/acquire-authentication-credentials-in-salesforce-chatter). The Consumer Secret uses a string value. See the example below. *n3v3rU53th1s_Ke3p1tS3cur3!* |
6. For Securiti Cloud Only. Configure the following on the **Permissions** tab under the **Breach** section:

Mark the **Breach Analysis** checkbox to initiate enhanced analysis for any reported incident for your Data system and get an automated report for Remediation.
7. Click **Authenticate & Activate Connector**.

Securiti redirects you to Salesforce to authenticate the connecting application's Credentials you entered into the Connector tab.
8. Click **Allow**.

![SF_ConnectAuth_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25551145-581b-5a1d-8776-25c67471755f(2).png)

Salesforce redirects you back to Securiti.
9. Securiti activates the Connector.

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
