---
title: "Connecting Amazon Redshift with Securiti"
slug: "connecting-amazon-redshift-with-securiti"
updated: 2026-07-01T19:55:28Z
published: 2026-07-01T19:55:28Z
canonical: "helpcenter.securiti.ai/connecting-amazon-redshift-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Amazon Redshift with Securiti

This topic covers activation of the Amazon Redshift connector.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating an Amazon Redshift data system instance

Perform the following steps to create a Data system instance for self-hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| **Parameter** | **Explanation** | **Example** |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | The **Hosting Location** is automatically set to **IaaS**. | IaaS |
| Service Provider | This field is automatically set to your data system's service provider. | AWS |
| Account ID | Enter the AWS **Account ID** for your data system account. The account ID uses an alphanumeric string value. | `1234567891011` |
| Region | Select the region from the menu. | `us-east-2` |
| Managed | Enable the toggle to differentiate between native and non-native (dark) assets. |  |
| Country | Select the **country** from the dropdown where the data source or resource is located. | `Australia` |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | `Australian Capital Territory` |
| (Optional) City | Enter the **city** where the data source or resource is located. | `Canberra` |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | `John.doe@securiti.ai` |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | `Alex.doe@securiti.ai` |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Amazon Redshift connector

After creating an Amazon Redshift connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. Under the **Drivers** section, select the driver files. For more information, see [Uploading JDBC driver files in Securiti](/v1/docs/uploading-jdbc-driver-files-in-securiti).

Check the [Amazon Redshift documentation](https://docs.aws.amazon.com/redshift/latest/mgmt/configuring-connections.html) that work with the version of your database.
3. > [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as:

  - Table Training Sample files
  - Sensitive Data Intelligence protection evidence files
  - Scan Summary

> [!NOTE]
> Note
> 
> DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support.

You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another:

  1. On the activated data system instance, click on the **Reconfigure** link.
  2. From the **PCS Destination** menu, select the PCS where you want to migrate the data.
  3. Click **Reconfigure connector**.

Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete.
4. In the **Credentials** section, configure the following settings:

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Authentication Type | N/A | Select the authentication method from the menu. The following authentication methods are supported for Amazon Redshift. - **Basic** - **IAM Roles** |
| Host | - Basic - IAM Roles | Enter the host name or cluster endpoint you recorded [Prerequisites for configuring Amazon Redshift](/latest/docs/prerequisites-for-configuring-amazon-redshift). You can copy the cluster endpoint from the AWS Redshift console. See an example below. `org-dev-syd-system.clo3kmg28iol.us-west-2.redshift.amazonaws.com` |
| Port | - Basic - IAM Roles | Enter the port number of where your appliance is installed. Specify the value recorded in [Prerequisites for configuring Amazon Redshift](/latest/docs/prerequisites-for-configuring-amazon-redshift). Port number uses an integer value. See an example below. `5439` |
| Database | - Basic - IAM Roles | Enter the database name you recorded in [Prerequisites for configuring Amazon Redshift](/latest/docs/prerequisites-for-configuring-amazon-redshift) . See an example below. `MyRedShiftDatabase` |
| (Optional) Use Keyring | Basic | You can enable the Use Keyring toggle if you want to use a keyring to manage credentials for the instance as described in [Using keyrings](/latest/docs/managing-credentials-using-keyrings). Then choose the **Keyring Type**, following keyring types are supported for Amazon Redshift: - [AWS Secrets Manager](/latest/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) - [CredStash](/latest/docs/configuring-credential-vaults-credstash-credential-vault) - [CyberArk](/latest/docs/cyberark-credential-vault) - [CyberArk Conjur](/latest/docs/configuring-credential-vaults-cyberark-conjur-credential-vault) - [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) |
| User | - Basic - IAM Roles | In case you are not using keyring, enter the username of the user authenticated by the database. Username uses a string value. See an example below. `admin` |
| Password | Basic | In case you are not using keyring, enter your Amazon Redshift instance password you recorded in [Prerequisites for configuring Amazon Redshift](/latest/docs/prerequisites-for-configuring-amazon-redshift) . |
| AWS Account | IAM Roles | Enter the Amazon Redshift account ID you recorded in [Obtain credentials for role based authentication in Amazon Redshift](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-redshift). AWS Account identifiers use a numeric value. See an example below. `123456789012` |
| AWS IAM Role | IAM Roles | Specify the AWS role that can be used by the appliance to authenticate with Amazon Redshift. This role should be created in the same Amazon Redshift account as the above account ID. See [Obtain credentials for role based authentication in Amazon Redshift](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-redshift), for more information. IAM role uses a string value. See an example below. `securiti_role` |
| AWS Region *(****IAM Roles*** *authentication only)* | IAM Roles | The region field is automatically populated based on the value selected in the **Region** field in the **Basic Information** tab, as described above. |
| (Optional) Additional Connection String options | - Basic - IAM Roles | Specify any additional JDBC connection string options (delimited by '&') that are specific and special for this data store. > [!NOTE] > **Important** > > Specify the cluster identifier if Redshift proxy is being used with **IAM Roles** authentication method. The cluster ID can be fetched from the **General Info** section for your Redshift instance. |
| (Optional) Store Sample file on PCS | - Basic - IAM Roles | - **Store Sample files on PCS** toggle is disabled by default. > [!NOTE] > **Note** > > In EPod V2 deployments, Securiti disables this toggle if PCS is not configured in yourtenant. Without PCS, support for storing sample files is unavailable for structured orhybrid data systems. - Keep the toggle disabled to store table training sample files locally on the pod, ensuring they remain within your local environment. - Enable this toggle if you wish to store table training sample files in Private Cloud Storage (PCS). > [!NOTE] > **Note** > > This functionality can only be enabled if Private Cloud Storage is already configured in your tenant. In case of reconfiguring a connector, files stored prior to the reconfiguration remain in their existing location, pods or PCS, until you perform a re-scan, after which Securiti stores sample files in the newly configured location. |
5. Click **Test Connection** at the bottom of the page.

Securiti activates the connector.

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for Amazon Redshift:

- [Configure discovery scans in Amazon Redshift](/latest/docs/configure-discovery-scans-in-amazon-redshift)
- [Fulfilling DSR requests for Amazon Redshift](/latest/docs/fulfilling-dsr-requests-for-amazon-redshift)
