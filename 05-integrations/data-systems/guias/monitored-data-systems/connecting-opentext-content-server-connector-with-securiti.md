---
title: "Connect OpenText Content Server connector with Securiti"
slug: "connecting-opentext-content-server-connector-with-securiti"
updated: 2026-07-31T07:41:29Z
published: 2026-07-31T07:41:29Z
canonical: "helpcenter.securiti.ai/connecting-opentext-content-server-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect OpenText Content Server connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

> [!NOTE]
> **Note**
> 
> The OpenText Content Server only scans documents within Enterprise Workspace.

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Settings**.
4. From the **System Settings** menu, choose **Integrations** > **Data Systems** > **Monitored**.

1. Do one of the following:
  - If you have not yet created any Data system instances for OpenText Content Server, click **Create Instance** for it.
  - If you already have at least one Data system Instance for OpenText Content Server, near the upper right corner of the Instance, click **+** to create a new Instance.
2. Near the top of the page, click the **Basic Information** tab and apply the following settings:

| **Setting** | **Description** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the application name you entered when configuring the application in OpenText Content Server. | OT CS - Data |
| Instance Location | Select your preferred Hosting (location) Location and configure the Service provider settings (if they apply). Provide Country, State/Region, and City information. | Hosting (location) location: SaaS Country: Australia |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | John.doe@securiti.ai |
3. Click **Create Instance > Continue**.
4. Configure the following on the **Permissions** tab under the **DSR Scan** section:

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |
5. Near the top of the page, click the tab.
6. Enter the following information you recorded in [Grant permissions and obtain credentials in OpenText Content Server](/latest/docs/grant-permissions-and-obtain-credentials-in-opentext-content-server), as shown below.

| Setting | Description |
| --- | --- |
| Connect with Pod | Select the Pod you configured earlier. |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Content Server URL | Enter the login page URL of the app. The path may appear as follows. <*http(s)://hostname/abc/abc/app/...*> Your Content Server URL is **http(s)://hostname/abc/abc** just before the third slash ("/app" in the case of smart view), as seen in the example above. |
| Username | Enter the OpenText Content Server username you acquired in step 1 of [Grant permissions and obtain credentials in OpenText Content Server](/latest/docs/grant-permissions-and-obtain-credentials-in-opentext-content-server). See the example below. *John Doe* |
| Password | Enter the OpenText Content Server password acquired in step 1 of [Grant permissions and obtain credentials in OpenText Content Server](/latest/docs/grant-permissions-and-obtain-credentials-in-opentext-content-server). |
| (Optional) Allow Private IP | Enable if you want to use a Private IP or Hostname for Activation. |
7. Click **Authenticate & Activate** .

Securiti activates the .
  - After the connector activation, Scoping Metadata Sync collects user groups from the connected data system to define scopes for Discovery Scans.

> [!WARNING]
> Important
> 
> Securiti disables scoping metadata sync configuration options when authentication fails.
  - These syncs run automatically as well as manually after a connector is activated, allowing OpenText Server Groups to appear in Discovery Scans. For more details on automatic and manual syncs, see Scoping Metadata Syncs for connectors.
8. Proceed to [Configure discovery scans in OpenText Content Server](/latest/docs/configure-discovery-scans-in-opentext-content-server).

#### Hosting location for data system instance

When creating an Instance for your Data system, you can select your preferred Hosting (location) location in the **Instance location** section of the **Basic information** tab of the you want to configure.

Securiti supports IaaS, SaaS, or Private Cloud as Hosting (location) options for your Data system Instance.

For IaaS, Securiti supports the following service providers.

- AWS
- GCP
- OCI
- AZURE

Select your Service provider and configure additional fields or options based on your prerequisites (where applicable) as described below.

| Service provider | Parameter | Description |
| --- | --- | --- |
| AWS | - Account ID - Region - Managed toggle | - Log in to your AWS Management Console, and your Account ID can be found in the upper right corner of the dashboard. e.g., *123456789012* - Specify the AWS region where you want to host your Securiti Instance, from the menu. e.g., *canadacentral* - Turn on the managed toggle option for controlled or native assets. |
| GCP | - Project ID - Region - Managed toggle | - Log in to your Google Cloud Console, select your project, and the Project ID can be found on the project dashboard. Eg, *my-project-123456* - Specify the GCP region where you want to host your Securiti Instance, from the menu. e.g., *asiaeast1* - Turn on the managed toggle option for controlled or native assets. |
| OCI | - Tenancy ID - Account ID - Region - Managed toggle | - Log in to your OCI Console, navigate to your tenancy details, and the Tenancy ID can be found in the tenancy information. e.g., *ocid1.tenancy.oc1..aaaaaaaa…* - Similar to the Tenancy ID, the Account ID can be found in the tenancy information. e.g., *ocid1.oc1..aaaaaaaa...* - Specify the OCI region where you want to host your Securiti Instance, from the menu. e.g., *ca-montreal-1* - Turn on the managed toggle option for controlled or native assets. |
| AZURE | - Account ID - Region - Managed toggle | - Log in to your Azure portal, and your Account ID can be found in the upper right corner of the dashboard. e.g., *12345678-90ab-cdef-1234-567890abcdef* - Specify the AZURE region where you want to host your Securiti Instance, from the menu. Eg, *canadacentral* - Turn on the managed toggle option for controlled or native assets. |

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.

A specific occurrence of a data system created on Securiti platform to integrate a data system. A data system instance is authenticated and activated to integrate the data system with Securiti and enable data scanning.

The physical or virtual location where a data system is hosted. For IaaS, Securiti supports AWS, GCP, AZURE, and OCI.

A platform that provides cloud or hosting services such as AWS, GCP etc.

SaaS, or Software as a Service, is a cloud computing service model that delivers software applications and services over the internet on a subscription basis. In the SaaS model, software is hosted and maintained by a third-party provider, and users can access it remotely through a web browser. This eliminates the need for users to install and manage software on their local devices.

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

The process of enabling and making a data system connector ready for scanning. Activation is the last step in the process of connecting a data system with Securiti. Successful activation takes place after entering correct activation and authentication parameters on the Securiti UI for connector.

Infrastructure as a Service is one of the three primary service models in cloud computing, alongside Platform as a Service (PaaS) and Software as a Service (SaaS). IaaS provides a virtualized computing infrastructure over the Internet, allowing organizations to rent and manage fundamental computing resources such as virtual machines, storage, and networking components on a pay-as-you-go basis.

The cloud term typically refers to cloud computing. Cloud computing is a technology that allows users to access and use computing resources and services over the internet, often from remote data centers.
