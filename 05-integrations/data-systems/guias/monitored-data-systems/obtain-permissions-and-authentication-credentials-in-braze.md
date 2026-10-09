---
title: "Obtain permissions and authentication credentials in Braze"
slug: "obtain-permissions-and-authentication-credentials-in-braze"
updated: 2026-07-30T09:47:04Z
published: 2026-07-30T09:47:04Z
canonical: "helpcenter.securiti.ai/obtain-permissions-and-authentication-credentials-in-braze"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permissions and authentication credentials in Braze

Braze uses API key authentication method and requires the following parameters for connector activation in Securiti.

- API key
- Instance ID
- Domain *(required for self-hosted connector)*
- Region
- Target Data System *(required for self-hosted connector)*

Use the matching procedure below to obtain permissions and authentication credentials in Braze connector.

> [!NOTE]
> **Important**
> 
> We assume you have a Braze instance running or have access to its admin to obtain the necessary permissions and parameters required before connector activation.

1. To obtain the API Key for REST API requests:
  1. Log in to the portal and on the left menu, select **Developer Console**.

> [!NOTE]
> **Important**
> 
> See [mapping table](https://www.braze.com/docs/api/basics#endpoints) provided in Braze documentation to find the portal login link for your instance.

![Developer_Console.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d1f13884-2e30-3908-231b-c044bc0ef81e.png)
  2. Under the **API Settings** tab, go to the **REST API Keys** section and click **Create New API Key**.

![Create_New_API_Key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95450d10-32fe-c4d5-a592-26f71c3bb0d1.png)
  3. Enter a name for your API Key in the API Key Name field and enable the following minimum permissions.

![Minimum_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-152063c4-c2f3-c07c-4498-6dadd389479e.png)
    - users.export.ids
    - users.export.segment
    - segments.list
  4. (Optional) To whitelist IPs, you can enter the addresses and subnets near the bottom of the page, as shown below.

Toggle on the **Opt in to Braze IP Whitelisting if you plan to make Braze-to-Braze webhooks** if you want to enable that option.

> [!NOTE]
> **Important**
> 
> Enter the appliance IP in the IP Addresses field. That lets the appliance call on the API successfully.

![IP_whitelist.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fe9699aa-3f06-e2df-f709-9ed9676293c0.png)
  5. Click **Save API Key** and record the generated API Key for later use.

> [!NOTE]
> **Note**
> 
> You must generate a new API Key to change the existing configuration.
  6. Once the API Key with the selected permissions is saved, the newly created API Key with the provided name is visible under the **Rest API Keys** section.

![braze_apikeys.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a0e6c3c6-4226-5c0e-6ecb-e188cf8435b4.jpg)
2. Additionally, you must specify a REST endpoint for API requests because Braze manages different dashboard instances. Dashboard instances differ based on US or EU regions. See [The mapping table](/v1/docs/securiti-pods-and-elastic-pods) in Braze documentation to find the instance assigned to your account.
3. Record the following for later use.

See the screenshot below for an example.

![braze_urls.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-56fdec47-540a-5bc3-9e46-279c58a248cb.png)
  - Instance ID: The instance number mentioned in the first column of the mapping table.
  - Domain: Locality where the instance is located.
  - Region: Geographical region of your instance.
  - *(For self-hosted connector)* Target Data System: From the menu, select "default" or "AWS S3" (if you have a Braze instance configured to use an AWS S3 bucket for bulk exports).

> [!NOTE]
> **Note**
> 
> You must activate the AWS S3 connector in Securiti with the same account integrated with your Braze instance. Running a Discovery Scan for this AWS S3 connector is not required.

See [Amazon S3 connectors](/v1/docs/amazon-s3-connectors-1) and [Braze S3 integration](/v1/docs/securiti-pods-and-elastic-pods) for more information.
4. Proceed to [Connecting the Braze (Self Hosted) with Securiti](/latest/docs/connecting-braze-with-securiti) or [Connecting the Braze (Securiti-Cloud) with Securiti](/latest/docs/connecting-the-braze-cloud-with-securiti).

## Related

- [Prerequisites for Braze (self-hosted) connector](/prerequisites-for-braze-self-hosted-connector.md)
