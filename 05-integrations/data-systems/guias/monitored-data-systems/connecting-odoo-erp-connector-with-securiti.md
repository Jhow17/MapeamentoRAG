---
title: "Connect Odoo ERP connector with Securiti"
slug: "connecting-odoo-erp-connector-with-securiti"
updated: 2026-07-31T07:05:59Z
published: 2026-07-31T07:05:59Z
canonical: "helpcenter.securiti.ai/connecting-odoo-erp-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect Odoo ERP connector with Securiti

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
  - If you have not yet created any Data system instances for Odoo ERP, click **Create Instance** for it.
  - If you already have at least one Data system Instance for Odoo ERP, near the upper right corner of the Instance, click **+** to create a new Instance.
2. Near the top of the page, click the **Basic Information** tab and apply the following settings:

| Parameter | Description | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the application name you entered when configuring the application in Odoo. | Odoo - Data |
| Instance Location | Select your preferred Hosting Location and configure the Service provider settings. Toggle on the Managed option to indicate the "Native" status of the Data system. Provide Country, State/Region, and City information. | Hosting location: Private Cloud Country: United States of America State/Region: Alabama |
| Owner | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | john.doe@securiti.ai |
3. Click **Create Instance & Continue**.
4. On the **Permissions** tab, in the **DSR Scan** area, apply these settings to suit.

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | To include the respective data system in processing the DSR request, enable this option. > [!WARNING] > **Important** > > For structured data system instances, Securiti creates subtasks in the DSR workbench. If no data is found during the data search, the subtasks are automatically deleted. |
| Allow Multi Column Join DSR | Enable this to combine data from multiple tables based on the values in more than one column. It enables AND condition in the DSR joins. |
| Require indices on primary identifier columns | Enable this if you require an index to exist on primary identifier columns such as SSN or Email address, for any DSR to improve the speed of data retrieval operations. Enabling this option makes the DSR run more efficiently. |
| Require database indexes for SQL table joins | Enable this option to limit the joins in the generated SQL queries to only tables that have indexes on joined columns. |
| Maximum depth for SQL table relations | This is the maximum depth to which relations between tables will be considered for JOIN clauses in the SQL queries generated for DSR automation. Lowering the depth speeds up automation and eases the load on the database server. Configure this value to suit. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfill DSR requests. |
| Limit Guest access to specific DSR types | Enable this toggle to assign only specific DSR types to the collaborators. |
5. On the **Connector** tab, enter the values you recorded in [Grant permissions and obtain credentials in Odoo ERP](/latest/docs/grant-permissions-and-obtain-credentials-in-odoo-erp) for these parameters:

| Parameter | Description |
| --- | --- |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| User | Enter the login username for your Database you recorded in [Grant permissions and obtain credentials in Odoo ERP](/latest/docs/grant-permissions-and-obtain-credentials-in-odoo-erp) |
| Password | Enter the login password for your Database you recorded in [Grant permissions and obtain credentials in Odoo ERP](/latest/docs/grant-permissions-and-obtain-credentials-in-odoo-erp) |
| Instance ID | Enter your Instance ID, which you recorded from the Odoo ERP Dashboard in [Grant permissions and obtain credentials in Odoo ERP](/latest/docs/grant-permissions-and-obtain-credentials-in-odoo-erp). The Instance ID uses a string value. The value in the URL before *odoo.com* is the Instance ID. See example below. *securiti-admin* |
6. Click **Authenticate & Activate Connector**.

Securiti activates the Connector.
7. Proceed to [Initiate Odoo ERP learning](/latest/docs/initiate-odoo-erp-learning).

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
