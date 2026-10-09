---
title: "Connecting the NFS connector with Securiti"
slug: "connecting-the-nfs-with-securiti"
updated: 2026-07-22T19:32:02Z
published: 2026-07-22T19:32:02Z
canonical: "helpcenter.securiti.ai/connecting-the-nfs-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting the NFS connector with Securiti

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a NFS data system instance

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
| Instance Location | Select one of your preferred Hosting locations from the menu. | - IaaS - SaaS - Private Cloud Storage > [!NOTE] > Note > > IaaS location opens a new menu to select Service Providers. For more information on IaaS locations, see [this section](/latest/docs/connecting-smb-with-securiti#authenticating-the-connector). |
| Country | Select the country of hosting location from the menu. | Country: United States |
| State/Region | Select the State or region inside the hosting country. | State: California |
| City | Enter the city name where the hosting server is located. | City: San Jose |
| Owners | Choose additional co-owners for the Instance if you want. By default, you are the Instance owner. | John.doe@securiti.ai |
8. Click **Create Instance & Continue**.

## Authenticating the connector

After creating an NFS connector instance, in the **Authentication** tab, authenticate your connector:

1. On the **Authentication** page, select the **Pod** you configured earlier in [Pods and Elastic Pods](/latest/docs/securiti-pods-and-elastic-pods).
2. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data. For more information, see [Configuring PCS Destination](/latest/docs/system-settings-configuring-private-cloud-storage).

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
| (Optional) Allow Quarantine actions on this Data system | Enable if you want to use the quarantine feature for your NFS Instance. > [!NOTE] > **Note** > > You must grant read and write privileges to the scanning account for files to be quarantined and the relevant folder where you want to place quarantined files. This toggle is a prerequisite to creating a File Insight Policy in Sensitive Data Intelligence. For more information, see [Using File Quarantine policies with Hyperdrive mode](/latest/docs/using-quarantine-policies-with-hyperdrive-mode). |
| (Optional) Quarantine Path | Enter the **Quarantine path** for the NFS share. > [!WARNING] > **Caution** > > The quarantine path and share name must be different for successful Connector Activation. See an example below. > > Share name: *Test1/folder1* and quarantine path: *Test1/quarantine* > > Connector Activation fails if. > > - Quarantine path and share name have same value. > - Quarantine path is a child or sub path of the share name. > > See the examples below for path values that may result in Activation failure. > > - Share name: *Test2* and quarantine path: *Test2/quarantine* > - Share name: *Test1/folder1* and quarantine path: *Test1/folder1/quarantine* > - Share name: */Test2* and quarantine path: */Test2* |
4. Once you are done, click **Test Connection**.

Securiti activates the connector.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify the configured permissions, and check the authentication statuses for supported capabilities, such as Discovery scans and metadata scans.

For more information, see [Using authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the NFS (self-hosted):

- [Configuring Data Inventory Sync for NFS](/latest/docs/configuring-data-inventory-sync-for-nfs)
- [Configure discovery scans in NFS](/latest/docs/configure-discovery-scans-in-nfs)
