---
title: "Connecting the NFS connector in Securiti (Hyperdrive)"
slug: "connecting-the-nfs-connector-in-securiti-hyperdrive"
updated: 2026-09-11T12:20:41Z
published: 2026-09-11T12:20:41Z
canonical: "helpcenter.securiti.ai/connecting-the-nfs-connector-in-securiti-hyperdrive"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Connecting the NFS connector in Securiti (Hyperdrive)

****Create a data system instance****

Perform the following steps to create a Data system instance:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the **Platform Services** section in the navigation, select **Data Systems**. It takes you to the Monitored Data Systems page under Integrations.
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add Integration** page, click the **Self Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, apply the following settings:

| **Parameter** | **Description** | **Examples** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the Instance. We recommend using the application name you entered when configuring the application in NFS. | NFS - Data |
| Instance Location | Select one of your preferred Hosting locations from the menu. | - IaaS - SaaS - Private Cloud Storage > [!NOTE] > Note > > IaaS location opens a new menu to select Service Providers. For more information on IaaS locations, see [this section](/latest/docs/connecting-the-nfs-connector-in-securiti-hyperdrive#hosting-location-for-data-system-instance). |
| Country | Select the country of hosting location from the menu. | Country: United States |
| State/Region | Select the State or region inside the hosting country. | State: California |
| City | Enter the city name where the hosting server is located. | City: San Jose |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | John.doe@securiti.ai |
8. Click **Create Instance & Continue**.

## Authenticating the connector

After creating an NFS connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Outpost** you configured earlier in [Outpost deployment.](/latest/docs/outpost-deployment-in-aws)
2. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data. For more information, see [Configuring PCS Destination](https://helpcenter.securiti.ai/latest/docs/system-settings-configuring-private-cloud-storage).

> [!NOTE]
> Note
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
3. In the **Credentials** section, configure the following settings:

| **Parameter** | **Description** |
| --- | --- |
| Host | Enter your server IP address in *xxx.xxx.xxx.xxx* format. See the example below. 192.158.1.38 |
| Path | Enter the NFS share name beginning with a slash (/). See the example below. */var/usr/general* |
| (Optional) Timeout | Enter the timeout value for the access Token, if any. |
| (Optional) Reading size | Specify the maximum size of data blocks that can be requested from the NFS server in a single read operation. It is calculated in bytes. See the example below. *8192 bytes (8 Kb)* |
| (Optional) Writing size | Enter the maximum size of data blocks that can be requested from the NFS server in a single write operation. It is calculated in bytes. See the example below. *8192 bytes (8 Kb)* |
| (Optional) Evaluate Data system size | Mark the checkbox to evaluate the Data system size during Authentication. The option discovers and calculates metrics for multiple shares. Securiti calculates resource size on a weekly basis to keep the data size value up to date. |
| (Optional) Allow Quarantine actions on this Data system | Enable if you want to use the quarantine feature for your NFS Instance. > [!NOTE] > **Note** > > You must grant read and write privileges to the scanning account for files to be quarantined and the relevant folder where you want to place quarantined files. This toggle is a prerequisite to creating a File Insight Policy in Sensitive Data Intelligence. For more information, see [Creating a File Insights policy to quarantine files](/v1/docs/configuring-file-insights-policies). |
| (Optional) Quarantine Path | Enter the **Quarantine path** for the NFS share. > [!WARNING] > **Caution** > > The quarantine path and share name must be different for successful Connector Activation. See an example below. > > Share name: *Test1/folder1* and quarantine path: *Test1/quarantine* > > Connector Activation fails if. > > - Quarantine path and share name have same value. > - Quarantine path is a child or sub path of the share name. > > See the examples below for path values that may result in Activation failure. > > - Share name: *Test2* and quarantine path: *Test2/quarantine* > - Share name: *Test1/folder1* and quarantine path: *Test1/folder1/quarantine* > - Share name: */Test2* and quarantine path: */Test2* |
4. Click **Authenticate & Activate Connector**.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the NFS (Hyperdrive):

- [Configuring Data Inventory Sync for NFS](/v1/docs/configuring-data-inventory-sync-for-nfs)
- [Configure discovery scans in NFS](/v1/docs/configure-discovery-scans-in-nfs)
- [Fulfilling DSR requests for NFS](/latest/docs/fulfilling-dsr-requests-for-nfs)

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
