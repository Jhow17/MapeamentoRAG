---
title: "Connecting Microsoft Fabric data system with Securiti"
slug: "new-ui-connecting-microsoft-fabric-data-system-instance-with-securiti"
updated: 2026-02-08T13:40:07Z
published: 2026-02-09T20:00:06Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-microsoft-fabric-data-system-instance-with-securiti"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Microsoft Fabric data system with Securiti

> [!WARNING]
> Important
> 
> If the new UI isn't available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements to activate it.

> [!NOTE]
> Note
> 
> Securiti stores sensitive connector credentials in an encrypted, base-64-encoded form. For self-hosted connectors, these credentials reside on your pod and are also stored in the Securiti cloud. A credential vault can also be used to store credentials for self-hosted connectors. If a vault is being used, credentials are retrieved securely from the vault at runtime on your pod and are not stored in the cloud.
> 
> 
> 
> For Securiti Cloud-hosted connectors, credentials are securely stored only in the Securiti cloud.

## Creating a Microsoft Fabric data system connector instance

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, or **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating Microsoft Fabric (Self Hosted) connector

After creating a Microsoft Fabric connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. > [!WARNING]
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
3. In the **Credentials** section, configure the following settings:

| Setting | Description |
| --- | --- |
| Tenant ID | Enter the Tenant ID that you recorded earlier in [Prerequisites for Microsoft Fabric](/latest/docs/prerequisites-for-microsoft-fabric-connector#acquiring-authentication-credentials). Tenant ID uses an alphanumeric string value. See an example below. *0a1b01a1-ab1b-1a1a-b0b0-101010ab1a01* |
| (Optional) Use Keyring | Enable the toggle to use a credential vault to access credentials. From the **Keyring Typ**e menu, select the Keyring type and select your configured keyring instance in the **Keyring** field. Following Keyring types are supported for Microsoft Fabric: - [Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault) - [HashiCorp](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault) |
| Client ID | Enter the application ID you recorded in the procedure [Prerequisites for Microsoft Fabric](/latest/docs/prerequisites-for-microsoft-fabric-connector#acquiring-authentication-credentials). Client ID uses an alphanumeric string value. See an example below. *0a1b01a1-ab1b-1a1a-b0b0-101010ab1a* |
| Client Secret | Enter the value for Client Secret you recorded earlier, as described in [Prerequisites for Microsoft Fabric](/latest/docs/prerequisites-for-microsoft-fabric-connector#acquiring-authentication-credentials). The client secret uses an alphanumeric string value. See an example below. *0a1b01a1-ab1b-1a1a-b0b0-101010ab1a01* |
4. Click **Test** **Connection** at the bottom of the page.

### Monitoring connection tests and authentication statuses

After authenticating the connector, use this section to review connection test results, verify configured permissions, and check authentication statuses for supported capabilities such as Discovery scans and metadata scans.

For more information, see [Using data system connector authentication statuses](/latest/docs/using-data-system-connector-authentication-statuses).

## Configuring post-authentication scans settings

Proceed to the following topics to configure the post-authentication scans settings for the Microsoft Fabric (self-hosted).

- [Configuring Data Inventory Sync for Microsoft Fabric](/latest/docs/configuring-data-inventory-sync-for-microsoft-fabric)
- [Configuring Discovery scans for Microsoft Fabric](/latest/docs/configuring-discovery-scans-for-microsoft-fabric)
- [Fulfilling Microsoft Fabric DSR requests](/latest/docs/configuring-discovery-scans-for-microsoft-fabric)

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.
