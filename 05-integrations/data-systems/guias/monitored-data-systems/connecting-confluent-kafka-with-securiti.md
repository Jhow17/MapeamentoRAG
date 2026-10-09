---
title: "Connecting Confluent Kafka with Securiti"
slug: "connecting-confluent-kafka-with-securiti"
updated: 2026-06-23T07:19:59Z
published: 2026-06-23T07:19:59Z
canonical: "helpcenter.securiti.ai/connecting-confluent-kafka-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Confluent Kafka with Securiti

This topic covers activation of the Confluent Kafka (Self-hosted) connector.

## Creating a Confluent Kafka data system connector instance

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations** > **Monitored Data Systems**
4. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
5. On the **Add** **Integration** page, click the **Self-Hosted** tab.
6. From the data system list, choose your relevant data system.
7. On the **Basic Information** tab, complete the following parameters to create an instance:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
8. In the **Hosting** **Location**, select the following available hosting locations:
  - **SaaS**
  - **Private Cloud**
  - **IaaS**

> [!NOTE]
> Note
> 
> For SaaS and private Cloud hosting location, below mentioned IaaS configurations must be skipped.

For the IaaS hosting location, complete the following parameters for each service provider:

**IaaS-AWS**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **AWS.** | AWS |
| Account ID | To obtain the **Account ID**, log in to your AWS Management Console, and your account ID can be found in the upper right corner of the dashboard. | `012345678901` |
| Region | Specify the AWS region where you want to host your Securiti instance. | `us-east-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-GCP**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **GCP**. | GCP |
| Project ID | To obtain the **Project ID**, log in to your Google Cloud Console, select your project, and the Project ID can be found on the project dashboard. | `project-123456` |
| Region | Specify the GCP region where you want to host your Securiti instance. | `us-east-1` |
| Resource Name / Instance Id | In the **Resource Name / Instance Id**, enter the instance id for BigTable or Cloud SQL (MySQL, Postgres or SQLServer) instance, bucket name for cloud storage or dataset name for BigQuery. | `my-bigtable-instance` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-OCI**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your service provider as **OCI**. | OCI |
| Tenancy Id | To obtain the **Tenancy Id**, log in to your OCI Console, navigate to your tenancy details, and the Tenancy Id can be found in the tenancy information. | `ocid1.tenancy.oc1..aaaaaaaa` |
| Account Id | Similar to the Tenancy ID, the **Account ID** can be found in the tenancy information. | `ocid1.oc1..aaaaaaaa` |
| Region | Specify the OCI region where you want to host your Securiti instance. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

**IaaS-Azure**

| Parameter | Explanation | Example |
| --- | --- | --- |
| Service Provider | Select your Service provider as **Azure**. | Azure |
| Subscription ID | Enter the subscription id for your Azure resource. | - |
| Resource Group | Enter the resource group for your Azure resource. | - |
| Server / Storage Account Name | In the **Server / Storage Account Name**, enter the server name for SQL Server or Cosmos DB, or the storage account name for Blob Storage/File Share. | - |
| Region | Specify the AZURE region where you want to host your Securiti instance. | `us-luke-1` |
| Managed | Enable the **Managed** toggle to let Securiti differentiate between native and non-native assets (Dark assets). | - |

1. After configuring the hosting location and service provider information, continue by completing the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Country | Select the country from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the state or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the city where the data source or resource is located. | Calgary |
| Owners | Choose the primary owner for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (Optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (Optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
2. At the bottom of the page, click **Create and Continue**.
3. It redirects you to the **Authentication** page.

## Authenticating Confluent Kafka connector

After creating a Confluent Kafka (Self-hosted) connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. In the **Broker Information** section, enter your **Host** and **Port** you acquired in [Obtain credentials in Confluent Kafka](/latest/docs/obtain-credentials-in-confluent-kafka). See the example below.

Host: `admin.org-kaf.abc.kafka.us-west-2.example.com`

Port: `8020`
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
4. In the **Authentication Information** section, configure the following settings:

| Setting | Authentication Type | Description |
| --- | --- | --- |
| Authentication Type | N/A | Select your authentication method. You can choose one of the following options from the menu. - **Plain Text** - **SSL Without Client Authentication** - **SSL With Client Authentication** - **SSL plain text** - **SASL SSL** For more information on the Authentication parameters required for each type, see [Obtain credentials in Confluent Kafka](/latest/docs/obtain-credentials-in-confluent-kafka). |
| (Optional) Use Keyring | N/A | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** dropdown, select one of the following supported keyrings. - **HashiCorp**: For more information, see [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). For more information on credential vaults, see [Configuring credential vaults](/latest/docs/managing-credentials-configuring-credential-vaults). |
| From the **Keyring** dropdown, select the keyring configured under the selected type. For more information on keyrings, see [Managing keyrings](/latest/docs/managing-credentials-using-keyrings). |
| Upload PKCS12 File (trust store) | - SSL Without Client Authentication - SSL With Client Authentication - SASL SSL | Upload the PKCS12 trust store file containing trusted CA certificates used to verify the Kafka broker's identity. |
| Truststore Password | - SSL Without Client Authentication - SSL With Client Authentication - SASL SSL | Enter the password required to access and validate the uploaded trust store file. |
| Upload PKCS12 File (key store) | - SSL With Client Authentication | Upload the PKCS12 key store file containing the client certificate and private key for Kafka authentication. |
| Mechanism Type | - SASL plain text - SASL SSL | Select the authentication mechanism used to connect to Kafka. |
| User Id | - SASL plain text - SASL SSL | Specify the username used to authenticate with the Kafka cluster. |
| User Secret | - SASL plain text - SASL SSL | Provide the password or secret associated with the specified user account for Kafka authentication. |
| Kafka Connect Internal Topics | N/A | Enter the specific Kafka topics that you have created in [Obtain credentials in Confluent Kafka](/latest/docs/obtain-credentials-in-confluent-kafka). To automatically create kafka internal topics, mark the **Automatically create kafka internal topics checkbox**. |
5. In the **Schema Registry** section, configure the following settings:

| Setting | Description |
| --- | --- |
| (Optional) Schema Registry Server URL | Enter the HTTP or HTTPS URL used to access Schema Registry Server you recorded in [Obtain credentials in Confluent Kafka](/latest/docs/obtain-credentials-in-confluent-kafka). See the example below. `https://10.151.231.240:8082` |
| Subject Name strategy | Select the strategy your Schema Registry Server uses from the menu. - **Topic Name Only** - **Record Name Only** - **Topic and Record Names** |
| (Optional) Schema registry protected by basic Authentication | Enable the option to protect your Schema registry with Basic Authentication method. When you mark this checkbox, you must provide the following parameters. - Schema Registry Username - Schema Registry Password |
| Data Format Type | Select the data format type for a given topic to define Schema registry from the menu. - JSON - AVRO - JSON With Schema |
6. Click **Test** **Connection** at the bottom of the page

### Monitoring the Overview page and authentication statuses

After authenticating the connector, in the **Overview** section:

- Review connection test results.
- Verify the configured permissions.
- Authenticate the statuses for supported capabilities.

For more information, see [Using the connectors overview page](/latest/docs/new-ui-using-connectors-overview-page).

To monitor the authentication statuses, click **View Diagnostic Report** or the **Authentication** tab. For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Confluent Kafka:

- [Configure discovery scans in Kafka](/latest/docs/configure-discovery-scans-in-kafka).

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
