---
title: "Connect Microsoft 365 Lists connector with Securiti"
slug: "connecting-microsoft-365-lists-connector-with-securiti"
updated: 2026-07-31T06:06:10Z
published: 2026-07-31T06:06:10Z
canonical: "helpcenter.securiti.ai/connecting-microsoft-365-lists-connector-with-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connect Microsoft 365 Lists connector with Securiti

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
> You must allowlist the following URLs on your firewall for the Microsoft 365 Lists to ensure proper functionality of Sensitive data Intelligence (SDI) and Data Subject Rights (DSR) to work as expected:
> 
> - [https://graph.microsoft.com](https://graph.microsoft.com)
> - [https://login.microsoftonline.com](https://login.microsoftonline.com)
> 
> Additionally, you need to allowlist either of the following URLs:
> 
> - *.[sharepoint.com](http://sharepoint.com) OR
> - https://{{customer_tenant_name}}.[sharepoint.com](http://sharepoint.com) AND https://{{customer_tenant_name}}-[my.sharepoint.com](http://my.sharepoint.com)
> 
> You need to allowlist the following URLs depending on the selection of the Cloud menu on the Connector Activation screen.
> 
> | Cloud | URL |
> | --- | --- |
> | Microsoft Graph for US Government L4 | [https://graph.microsoft.us/](/v1/docs/securiti-pods-and-elastic-pods) |
> | Microsoft Graph for US Government L5 (DOD) | [https://dod-graph.microsoft.us/](/v1/docs/securiti-pods-and-elastic-pods) |

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Settings**.
4. From the **System Settings** menu, choose **Integrations** > **Data Systems** > **Monitored**.

1. Locate and expand the tile for the Microsoft 365 Lists Connector, then click **Create Instance**.
2. Near the top of the page, click the **Basic Information** tab and apply the following settings:

| Instance Name | Enter a convenient name for the Instance. We recommend that you use the application name you entered earlier. |
| --- | --- |
| Instance Location | Select your preferred Hosting Location and configure the Service provider settings where applicable. Provide Country, State/Region, and City information. |
| Owners | Choose the primary owner and additional co-owners for the Instance if you want. By default, you are the primary owner. (optional) Mark the checkbox for **Send notification to all owners**. |
3. At the bottom of the page, click **Create Instance & Continue**.
4. Near the top of the page, click the **Connector** tab and apply the following settings:

| **Setting** | **Description** |
| --- | --- |
| Connect with Pod | Select the Pod you configured earlier. |
| PCS Destination | > [!WARNING] > Important > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as: - Table Training Sample files - Sensitive Data Intelligence protection evidence files - Scan Summary > [!NOTE] > Note > > DSR Automation, Assessment Automation, and the transient metadata used during scanning continue to use the Default PCS configured for your tenant until those modules adopt multi-PCS support. You can also migrate the data from one PCS to another while reconfiguring the connector. To migrate data from one PCS to another: 1. On the activated data system instance, click on the **Reconfigure** link. 2. From the **PCS Destination** menu, select the PCS where you want to migrate the data. 3. Click **Reconfigure connector**. Securiti shows you the migration progress bar to check the status of migration. Sensitive data is stored on the existing PCS bucket until the migration is complete. |
| Cloud | Choose the Cloud. For most installations, you choose "Microsoft Graph global service." |
| Tenant Name | Enter the Microsoft 365 tenant name for Lists app. The tenant name uses a string value. See an example below. *SecuritiInc* |
| Tenant ID | Enter your Tenant ID you acquired in [Grant permissions and obtain credentials in Microsoft 365 Lists](/v1/docs/grant-permissions-and-obtain-credentials-in-microsoft-365-lists). - Tenant ID follows the string format. See the example below. *0a1b01a1-aob1b-1a1a-b0b0-101010ab1a01* |
| (Optional) Use Keyring | Enable the **Use Keyring** toggle if you have used a Credential vault to store the Keyring. |
| From the **Keyring Type** menu, select one of the following supported keyrings. - **HashiCorp:** You can store Client ID, Private Key, and Certificate Thumbprint. For more infomration, see [Configuring HashiCorp credential vaults](/latest/docs/configuring-credential-vaults-hashicorp-credential-vault). - **Azure Key Vault:** You can store Client ID, Private Key, and Certificate Thumbprint. For more infomration, see [Configuring Azure Key Vault](/latest/docs/configuring-credential-vaults-azure-key-vault). - **CyberArk Vault:** You can store Client ID and Private Key. For more infomration, see [Configuring CyberArk Vault](/latest/docs/cyberark-credential-vault). > [!NOTE] > Note > > Microsoft 365 Lists Keyrings require the private key to be stored in Base64-encoded format. Before adding the private key to the vault, encode the `.pem` file using the following command: > > `cat test.pem \| base64 \| tr -d '\n'` > > Store the generated Base64-encoded output as the private key value in the credential vault. |
| From the **Keyring** dropdown, select the keyring configured under the selected type. |
| Client ID | Enter the application ID you recorded in the procedure [Grant permissions and obtain credentials in Microsoft 365 Lists](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-365-lists). The client or application ID uses a string value. See an example below. *12345678-abcd-1234-efgh-123456abcdef* |
| Certificate ThumbPrint | Provide the Certificate thumbprint you recorded in [Grant permissions and obtain credentials in Microsoft 365 Lists](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-365-lists). The Certificate thumbprint uses an alphanumeric string value. See an example below. *34F34D57A1233EAB12345F67ABC89012D34EF5AB* |
| Private Key | Upload the private key (.pem) file you generated in [Grant permissions and obtain credentials in Microsoft 365 Lists](/latest/docs/grant-permissions-and-obtain-credentials-in-microsoft-365-lists). The private key file uses a .pem file extension usually. See an example below. *securiti_private_key.pem* |
| (Optional) Root domain for different regions | Provide comma separated list of root site collections for multiple regions. Skip this field if you want to scan the default site collection. See an example below. *request.sharepoint.com, datasubjectrequest.sharepoint.com* |
5. Near the bottom of the page, click **Authenticate & Activate Connector**.
6. Proceed to [Configure discovery scan in Microsoft 365 Lists](/latest/docs/configure-discovery-scans-in-microsoft-365-lists).
