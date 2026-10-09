---
title: "Create Service Accounts and API Keys"
slug: "create-service-accounts-and-api-keys-en"
updated: 2026-07-29T05:15:51Z
published: 2026-07-29T05:15:51Z
canonical: "helpcenter.securiti.ai/create-service-accounts-and-api-keys-en"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Create Service Accounts and API Keys

# Create Service Accounts and API Keys

This page covers the following topics:

- [Create Service Account](/v1/docs/create-service-accounts-and-api-keys-en#create-service-account)
- [Generate API key](/v1/docs/create-service-accounts-and-api-keys-en#generate-api-key)

## Create Service Account

To create a new Service Account:

1. To open the **Service Accounts** page, from the upper left corner of the navigation bar, click the **Jewel** icon.
2. On the left navigation, choose **Settings > Organizational > Access Management > Service Accounts**.
3. On the top right of the **Service Accounts** page, click **New Account and API Credentials** and then select **Create New Service Account**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IQTV9CCF.png)

It opens **Create New Service Account** popup.

1. On the **Create New Service Account** popup, add the following parameters:

| Parameter | Description |
| --- | --- |
| Service Account Name | Enter the name for your Service Account. See the example below. *Appliance Administrator Service Account*. |
| (Optional) Description | Enter the description for your Service Account. See the example below. *Service Account for Appliance API key*. |
| (Optional) Assign Owners | From the menu, select the owners for your Service Account. > [!NOTE] > Note > > Assigned owners can edit or delete the Service Account. |
| Assign Roles | From the dropdown menu, select roles for your Service Account. It only lists the roles which are eligible for Service Accounts. For more information on making a role eligible for the Service Account, see [Create a new role](/latest/docs/roles-in-securiti#create-a-new-role). > [!NOTE] > Note > > When you assign the role(s) to the Service Account, it inherits all the permissions assigned to the roles. |
| Assign Orgs | From the menu, select the organization that this Service Account can access for data. |
| (Optional) Go to next step to generate API key | Mark the checkbox to jump directly to the [API creation](/v1/docs/create-service-accounts-and-api-keys-en#generate-api-key) after Service Account creation. Leave the checkbox unmarked to only create the Service Account and generate the API later. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-service-accounts-and-api-keys-en-image-08ctbail.png)

1. Click **Create Service Account**.

It redirects you to the **Service Accounts** page, where you can see the newly created Service Account in the list. For more information, see [Service Accounts](/v1/docs/service-accounts-en).

## Generate API key

> [!NOTE]
> Note
> 
> You can directly move to the **Generate New API Key** popup from the Service Account popup by marking the **Go to next step to generate API key** checkbox, as discussed above.
> 
> Otherwise, you have an option to generate a new API key for the Service Account separately, as discussed in the procedure below.

To generate a new API key for a Service Account:

1. Open the Service Accounts page. On the top right of the page, click **New Account and API Key**, and then select **Generate New API Key**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-service-accounts-and-api-keys-en-image-lzv954gv.png)

It opens the **Generate New API Key** popup.

1. On the **Generate New API Key** popup, add the following parameters:

| Parameters | Description |
| --- | --- |
| Service Account | From the menu, select the Service Account you want to associate with this API key. |
| Key Type | From the menu, choose the type of API key for the intended use: - Simple - Oauth ID |
| API Key Name | Enter a unique name to identify the API key. See the example below. *Appliance Administrator API Key*. |
| Description | Enter a short description to specify the purpose of the API key. See the example below. *API Key for Pod creation and status monitoring*. |
| Expiration Period | From the menu, select he number of days the API key remains valid before it expires: - 30 Days - 60 Days - 180 Days - 720 Days |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-service-accounts-and-api-keys-en-image-4wphuj0c.png)

1. Click **Generate API Key**.

It generates the API key and displays it in **API Key and Secret** popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-service-accounts-and-api-keys-en-image-tu5mn046.png)

1. Copy and save the **API key** and **API Secret** values, as the **Secret** value displays only once.

While integrating the Securiti APIs in your system, you must provide these values for authorized access. For more information, see [System Settings API Documentation](https://securiti-doc-router.securiti.ai/modules/system-settings/apidocs/index.html).

## Related

- [Service Accounts](/service-accounts.md)
- [Managing Securiti API keys](/managing-credentials-managing-securiti-api-keys.md)
