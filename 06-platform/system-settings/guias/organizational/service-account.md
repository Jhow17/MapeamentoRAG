---
title: "Service Accounts"
slug: "service-account"
updated: 2026-03-31T07:55:07Z
published: 2026-03-31T07:55:07Z
canonical: "helpcenter.securiti.ai/service-account"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Service Accounts

Securiti provides the **Service Accounts** feature to generate system-level APIs with specific permissions. Unlike user APIs that inherit the permissions of the API owner, Service Accounts generate APIs with roles and permissions defined in the RBAC. These APIs support integration of the Securiti platform and its modules with third-party applications, independent of any user role.

To open the Service Accounts:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the left navigation, choose **Settings > Organizational > Access Management > Service Accounts**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-l28ta1mu.png)

It opens the landing page of Service Accounts.

## Creating Service Account and API key

Securiti lets you create a Service Account and generate an API key associated with the Service Account. For more information, see [Create Service Accounts and API Keys](/v1/docs/create-service-accounts-and-api-keys-en).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-wlcwoefh.png)

## Using filters

The **Service Accounts** page offers filter capability that lets you list specific data based on the search parameters. After applying the filter, you can also save it.

To use the filter for the available data:

1. On the top left of the **Service Accounts** table, click the plus **(+)** to open the filter popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-zwmj58of.png)
2. Filter contains the following properties and attributes. Add the data in the filter to narrow down the results. Also, use the search bar to search for any specific property or attribute.

Filter includes the following properties:

| Property name | Description |
| --- | --- |
| Owners | It refers to the owners of the Service Accounts. |
| Roles | It refers to the roles attached to the Service Accounts. |
| Created on | It refers to the date when the Service Accounts were created. |

It also includes the following attributes in the properties mentioned above.

| Attribute | Description |
| --- | --- |
| Contains | It filters results that contain the entered value. |
| Is one of | It filters results that match any value from a selected list. |
| Is equal to | It filters results that exactly match the entered value. |
| Before | It filters results created before the selected date. |
| After | It filters results created after the selected date. |
| Between | It filters results created within a specified date range. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-lcuw1uor.png)
3. After adding filter details, click **Apply**. It applies the filter, and shows the results.
4. To clear the applied filter, on the right side of the applied filter, click **Clear Search**. It also provides the same filter below the filter button. However, you cannot save it. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-sy8zdam8.png)

## Saving a filter

To save the applied filter:

1. On the top right of the **Service Accounts** page, click **Save View**.
2. On the right panel, add the following details:

| Field name | Description |
| --- | --- |
| Groups | From the menu, select a group to save with an existing group or create a new one. |
| Name | Enter the name for the saving filter. |
| (Optional) Description | Add the description to the saving filter. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-c3nxh1pg.png)
3. To save the filter, click **Save View**.
4. To load the saved filter, click Saved Views. It opens a **Saved Views** popup on the left side of the screen.
5. From the listed groups, select the required filter. The filter is applied automatically. You can also use the search bar to find your filter by name. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-3g738pds.png)

## Viewing the Service Accounts

It shows you the list of Service Accounts created in your tenant. Each Service Account entry shows the following options:

- Name
- Unique ID
- Assigned roles
- Orgs
- API Keys
- Created on
- Owners

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-kxk5j8mc.png)

On the **Service Accounts** page, use the Options **(three dots)** at the end of each entry to use different operations.

| Operation | Description |
| --- | --- |
| View API Keys List | You can view the list of API Keys added for the chosen Service Account. For more information, see the [Viewing the API Keys for Service Account](/v1/docs/service-accounts-en#viewing-the-api-keys-for-service-account). |
| Generate New API Key | You can generate a new API key for the chosen Service Account. For more information on generating a new API Key, see [Create Service Accounts and API Keys](/v1/docs/service-accounts-en#creating-service-account-and-api-key). |
| Edit Service Account | You can edit the chosen Service Account details. For more information on updating Service Account details, see [Create Service Accounts and API Keys](/v1/docs/service-accounts-en#creating-service-account-and-api-key). |
| Delete Service Account | You can delete the chosen Service Account. When you click **Delete Service Account**, it opens a popup to get confirmation before deleting the account. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-y2jpmpta.png)

## Customizing the visible columns

To view the customizable columns for Service Accounts:

1. On the top right of the Service Accounts table, click **Column Selector** to include or exclude column properties.
2. On the Column Selector popup, mark the checkboxes for the columns you want to display.
3. Click **Apply**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-dk9edilu.png)

## Viewing the API Keys for Service Account

You can view the API Keys created for a specific Service Account by using the procedure below:

1. On the **Service Accounts** page, use the Options **(three dots)** at the end of the chosen entry.
2. From the menu, click **View API Keys List**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-26ev8yc1.png)

It opens a new row containing the API Keys of the chosen Service Account.
3. On the expanded row for the chosen Service Account, click Options **(three dots)**, and then click **View API Key**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-lm6e0684.png)
4. On the **View API Key** popup, you can see the details of the API Key. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-5jui7alt.png)

## Viewing the Service Account metadata explorer

To view the details for each Service Account, such as API Keys, ID, Owners, and Organizations, do the following:

1. On the right side of the chosen Service Account entry, click the **Show Metadata Explorer** icon. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-k0q6cbbn.png)
2. On the popup, you can view the metadata details of the Service Account. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/service-accounts-en-image-7y8dgj91.png)

## Related

- [Create Service Accounts and API Keys](/create-service-accounts-and-api-keys-en.md)
- [Managing Securiti API keys](/managing-credentials-managing-securiti-api-keys.md)
