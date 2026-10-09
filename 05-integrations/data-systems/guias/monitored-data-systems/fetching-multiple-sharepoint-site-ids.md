---
title: "Fetching Multiple SharePoint Site IDs"
slug: "fetching-multiple-sharepoint-site-ids"
updated: 2025-12-12T13:02:44Z
published: 2025-12-12T13:02:44Z
canonical: "helpcenter.securiti.ai/fetching-multiple-sharepoint-site-ids"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fetching Multiple SharePoint Site IDs

#### Generate Access Token

The access Token will be generated for the application having Full Control Permissions.

1. In Postman, click **New** and choose **Collection** to create a new API collection in SharePoint.

![newPostmanCollection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73aa5629-a41e-f0a4-13f3-c8f94a1ea96e.png)
2. Enter a suitable collection name, for example, **Sharepoint Demo Collection**.

![renameCollection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a84d9ad-0712-420f-769e-0a7ba32b8fe1.png)
3. Choose the **Authorization** tab from the left panel, choose Oauth 2.0 as the Auth Type, and configure the Token by providing the following information:
  1. Enter a name that will help you identify the app Token, for example, **SharePoint App Token**.
  2. Select **Client Credentials** in the drop-down list against **Grant Type**.
  3. Add your domain to this URL and paste it in the Access Token URL:
    - *https://login.microsoftonline.com/<your-domain>/oauth2/v2.0/token*
  4. Paste the client ID and client secret that were generated during the creation of the App with full control.
  5. Add this URL to the scope textbox *https://graph.microsoft.com/.default*.
  6. Keep the client Authentication option to the default Send as **Basic Auth Header**.
    - Once you have entered all the details, click **Get New Access Token**.

![getNewAccessToken.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22220051-e951-b3c3-28ea-5ee9c9bd38e9.png)
    - A new popup appears. Click **Proceed**.

![TokenSuccess.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-61064663-1261-e217-326b-2f1e1b72af0e.png)
    - Another popup appears. Click **Use Token**.

![UseToken.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7b4b42a-d1bf-f7ce-78f6-1b71a492282d.png)

#### Request Postman to fetch all SharePoint site IDs

1. Click on “add a request” to create a new GET request in your collection.

![addARequest.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c01d43b9-b50a-89eb-d469-5546d9efe3a3.png)
2. To list all the Site IDs in your SharePoint account, use this API URL. For example, *https://graph.microsoft.com/v1.0/sites$top=9999&select=id*
3. Make sure to select the Auth Type Bearer Token.
4. Click **Send**.

![bearerToke.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f7059a4a-b74e-3709-15a9-6f347510a2f3.png)

Now you will be able to see the list of all the Site IDs in your SharePoint account.

![siteIDResponse.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36e2a4aa-2dda-49c2-0d80-9dc05ace84c7.png)
5. In order to copy the Site IDs in bulk for the CSV, choose the Visualize tab, then choose **Table** in the visualize response dropdown. We do not have to manually copy each ID, and we can copy Site IDs in bulk from the Table.

![VisualizeResponse.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63098930-9642-266a-17a3-2111f56528c6.png)

Once it is done, you can be able to see the Site IDs in a Table. You can copy the IDs you need collectively or **Select All** and copy them to your CSV file.

![sites.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa812ebf-dd47-f988-1488-7f0b08a3d366.png)

> [!WARNING]
> **Important**
> 
> The default pagination limit for Microsoft Graph API is 5000 (5K) results per page, so each Get Request returns the maximum 5K results. If you have more than 5K sites in your account, you can click on *@odata.next* Link field URL in your current response. It takes you to a different **Request** tab, once you hit send it will return you the remaining results.

#### Fetching all SharePoint Sites

1. Create a new **Get Request**.
2. To list all the sites in your SharePoint account, use this API *https://graph.microsoft.com/v1.0/sites?top=9999*.
3. Make sure to select the **Auth Type** Bearer Token and click Send.
4. This will return whole Sites, including Site ID, Sitename, and Site URL (hiding Site ID, URL, and hostname for security purposes in the snapshot)

![allSites.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a388c88-e0e0-42fe-18b4-239f07ab78c7.png)

> [!NOTE]
> **Note**
> 
> If your Token expires, go to your collection authorization tab and refresh the Token. Then use the new Token to send API requests.
