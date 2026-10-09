---
title: "System for Cross-domain Identity Management (SCIM)"
slug: "scim"
updated: 2026-07-16T11:31:48Z
published: 2026-07-16T11:31:48Z
canonical: "helpcenter.securiti.ai/scim"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# System for Cross-domain Identity Management (SCIM)

In Securiti, System for Cross-domain Identity Management (SCIM) lets you synchronize and automatically provision users and groups from your identity provider (IdP), such as Microsoft Azure Entra ID, into Securiti. Once configured, SCIM lets your IdP securely manage user lifecycle operations in Securiti through standardized APIs.

> [!WARNING]
> Important
> 
> You must have your IdP already configured with Single Sign-On (SSO). For more information on SSO, see [Single Sign-On](/latest/docs/system-settings-configuring-single-sign-on).

Securiti authorizes the IdP to perform the following actions:

- Create users and groups
- Update user and group attributes
- Deactivate users
- Delete users and groups

When you create or update a user in your IdP, the change is automatically reflected in Securiti using SCIM APIs and service accounts. This ensures consistent identity management across systems without manual intervention. However, when you delete a user in Securiti, you must assign the roles and permissions the deleting user contains, to another user. Similarly, when you delete a user from your IdP, Securiti also populates the deleting users for you to assign the roles and permissions to another user.

> [!NOTE]
> Note
> 
> If you delete a user from Securiti, and the user still exists in your IdP, the automated provisioning recreates the deleted user in Securiti.

## Supporting IdPs

As SCIM is a standard protocol which can work with several IdPs, Securiti officially supports the following IdPs:

- Microsoft Entra ID
- Okta

## Creating Service Account

Creating a Service Account lets you connect your Service Account API credentials with your IdP to perform authorized actions on user and group in Securiti. With your Service Account API credentials, you are eligible to perform those actions which are in the role your Service Account is holding. So, in order to let your IdP perform user and groups related actions, you must add a role that lets Service Account perform at least the following actions:

- Create user and group
- Read user and group
- Update user and group
- Delete user and group

> [!NOTE]
> Note
> 
> - The Service Account must have at least **Create Read Update Delete** (**CRUD**) permissions.
> - You cannot create a user with higher role than the role assigned to the Service Account.

From the Service Account, you must collect the following details.

- OAuth client ID
- OAuth client secret

To configure your Service Account:

1. Configure a new Service Account and assign roles to it. For more information, see [Creating new Service Account](/latest/docs/create-service-accounts-and-api-keys-en).
2. While creating new API key, on Key Type, select Oauth ID. For more information, see [Generate API key](/latest/docs/create-service-accounts-and-api-keys-en#generate-api-key).
3. Obtain the **OAuth Client ID** and **Oauth Client Secret** and save them for later use.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4825III4.png)

## Configuring SCIM with Azure and Okta

**Azure**

To configure the SCIM in your Microsoft Azure account, proceed with the steps below:

> [!NOTE]
> Note
> 
> Make sure your Microsoft Azure is already configured to with SSO. If your application is not configured with using SSO, you must configure it first. For more information, see [Configure Entra ID](/latest/docs/configuring-entra-id-previously-known-as-azure-ad-single-sign-on).

1. Log in to Microsoft Azure portal using an account with administrative privileges.
2. From the left sidebar, open **Microsoft Entra ID**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SQ16D1U5.png)
3. From the **Microsoft Entra ID** left sidebar, under the **Manage**, click **Enterprise applications**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-R8OO8STF.png)
4. Open your enterprise application that is configured for Securiti SSO.
5. From the left menu bar, click **Manage > Provisioning**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-84YFD15O.png)
6. On the **Overview** page, under **Create configuration** section, click **Connect your application**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8OF7FYTN.png)

This opens the provisioning configuration panel where you set up automatic user and group synchronization.
7. On the **New provisioning configuration** page, add the following parameters:

| Parameter | Description |
| --- | --- |
| Select authentication method | From the dropdown menu, select “OAuth2 client credentials grant”. It creates authentication between Entra ID and Securiti using OAuth2 standard. |
| Tenant URL | Azure sends provisioning requests, such as creating or updating users, to this SCIM endpoint in Securiti. Add the following URL: ```plaintext https://<securiti.ai>/core/v1/user/scim/v2/ ``` Replace `&lt;securiti.ai&gt;` with your application URL. |
| Token endpoint | Azure retrieves the access token from this endpoint before making API calls to Securiti. Add the following URL: ```plaintext https://<securiti.ai>/core/v1/oauth/access_token/<tenant id> ``` - Replace `&lt;securiti.ai&gt;` with your application URL. - Replace `&lt;tenant id&gt;` with your tenant ID. For more information on obtaining tenant ID, see [Configuring Securiti general settings](/latest/docs/system-settings-configuring-securiti-general-settings). |
| Client identifier | Enter the `OAuth client ID` value you obtained from Service Account. |
| Client secret | Enter the `OAuth client secret` value you obtained from Service Account. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CBUKOE9J.png)
8. Once you add the values, click **Test connection**.

This verifies that Azure connects and authenticates with Securiti using these credentials.
9. Once the test is successful, at the bottom of the page, click **Create**.
10. On the **Overview** page, on the left menu bar, select **Manage** **>** **Provisioning**.

It opens the **New provisioning configuration** page.
11. On the **New provisioning configuration** page, click **Start Provisioning**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YE0D1WHF.png)

It activates automatic synchronization between Azure and Securiti.
12. Map the attributes in Azure. It ensures that SCIM correctly maps user data, such as name, email, and roles, from Azure to corresponding fields in Securiti. To map the attributes, follow the steps below:
  1. On the **Overview** page, under **Manage** section, click **Attribute mapping**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4T0UAXVE.png)
  2. On the **Attribute mapping** page, under the **Name** column in the table, click on the **Provision Microsoft Entra ID Users** link**.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EZNX7ZYN.png)

It lists all attributes on the **Attribute mapping** page.
  3. At the bottom of the **Attribute mapping** page, mark the **Show advance options** checkbox**.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A2WPDP2W.png)
  4. Under the **Supported Attributes** section, click on the **Edit attribute list for customappsso** link**.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RGSNDKRC.png)

It opens **Edit Attribute List** page.
  5. At the end of **Edit Attribute List** page, add a new row in the table with the following data:

> [!WARNING]
> Important
> 
> - If you do not map the **roles** attribute, it does not fetch the role of the user from your IdP automatically. In this case, it assigns the single role to the user from your configured SSO.

Only add values in those columns which are mentioned in the table below:

| Column name | Value |
| --- | --- |
| Name | `roles` |
| Type | `string` |
| Multi-value? | Mark the checkbox |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H6AHVP2E.png)

This action requires a "roles" attribute during user provisioning, as every user in Securiti must have an assigned role.
  6. Once you add the value, at the top of the Edit Attribute List, click **Save**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6K69CY3Y.png)

Once it saves the attribute, it redirects you to **Attribute Mapping** page.
  7. On the **Attribute Mapping** page, click **Add New Mapping**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BOLY1WQQ.png)

It adds a new mapping for the "roles" attribute to populate and send it from Azure to Securiti during provisioning.
  8. On the **Edit Attribute** page, add the attribute mapping details. The table below contains details of values you must as it is.

See the table below for mapping attribute values for “roles”.

> [!NOTE]
> Note
> 
> For role, enter its exact name as appears in Securiti.

| Parameter | Value |
| --- | --- |
| Mapping type | `Expression` |
| Expression | `AppRoleAssignmentsComplex([appRoleAssignments])` |
| Target attribute | `role` |
| Match objects using this attribute | `No` |
| Apply this mapping | `Always` |

If you are using multiple organizations, you must add the attribute values for it too. See the table below for mapping attribute values for adding organization.

> [!NOTE]
> Note
> 
> For organizations, enter its exact name as appears in Securiti. To assign the user with multiple organizations, separate the organization names with comas but no spaces. For the organization name that contains commas, enclose the name in double quotes, for example "orgadmin,users".

| Parameter | Value |
| --- | --- |
| Mapping type | `Direct` |
| Source attribute | `companyName` |
| Target attribute | `urn:ietf:params:scim:schemas:extension:enterprise:2.0:User:organization` |
| Match objects using this attribute | `No` |
| Apply this mapping | `Always` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2QOQYG27.png)

It configures Azure to extract role assignments from the application and map them to the "roles" field in Securiti, and map organization automatically. The expression dynamically includes any roles assigned to users in Azure during the provisioning process.
  9. Once you add the values, at the bottom of this page, click **Ok**.

It adds the Attribute Mapping page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-387I074J.png)

It configures Microsoft Azure (Entra ID) to establish a SCIM-based connection with Securiti and automatic provisioning of users and groups in Securiti.

**Okta**

To configure the SCIM in your Okta, proceed with the steps below:

> [!NOTE]
> Note
> 
> Make sure your Okta is already configured to Securiti with SSO. If your application is not configured with using SSO, you must configure it first. For more information, see [Configuring Okta single sign-on](/latest/docs/configuring-okta-single-sign-on).

1. Log in to Okta portal using an account with administrative privileges.
2. From the **Admin Console** left side bar, choose **Applications** > **Applications**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-T2D1NGZ0.png)
3. Click on your application name that also has its SSO enabled with Securiti.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EGW7PV0N.png)
4. On the **Application** page, under **General** tab, in the **App Settings** section, click **Edit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-19ARSPXE.png)
5. In the **App Settings** section, mark the **SCIM** radio button.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CXW8J1H8.png)
6. Once you add it, at the bottom of screen, click **Save**.

Now the **Provisioning** section appears on **Application** page.
7. Under the **Provisioning** tab, in **SCIM Connection** section, click **Edit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-R7JG8W4R.png)
8. In the **SCIM Connection** section, add the following details in the parameters:

| Parameter | Value |
| --- | --- |
| SCIM connector base URL | `https://&lt;securiti.ai&gt;/core/v1/user/scim/v2/` Replace `&lt;securiti.ai&gt;` with your application URL. |
| Supported provisioning actions | Mark the following fields: - Import New Users and Profile Updates - Push New Users - Push Profile Updates - Push Groups |
| Authentication mode | From the dropdown menu, select **OAuth 2**. It brings **OAuth 2** section below. |
| Grant Type | `Client Credentials` |
| Access token endpoint URI | ```plaintext https://<securiti.ai>/core/v1/oauth/access_token/<tenant_id> ``` - Replace `&lt;securiti.ai&gt;` with your application URL. - Replace `&lt;tenant id&gt;` with your tenant ID. For more information on obtaining tenant ID, see [Configuring Securiti general settings](/latest/docs/system-settings-configuring-securiti-general-settings). |
| Client ID | Enter the `OAuth client ID` value you obtained from Service Account. |
| Client Secret | Enter the `OAuth client secret` value you obtained from Service Account. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Q332EE9Y.png)
9. Once you add these details, click **Save**.

It tests the added credentials and authenticates with the Securiti application on the **SCIM connector base URL**.

Once the SCIM connection is successful, it opens **Provisioning to App** section.
10. On the right side of **Provisioning to App** section, click **Edit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CA4TJAH1.png)

It unblocks the checkboxes in **Provisioning to App** section.
11. On the **Provisioning to App** section, perform the following actions:
  1. Mark the Enable checkboxes for the following elements:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0WT60L9K.png)
    - Create Users
    - Update User Attributes
    - Deactivate Users
  2. On the right bottom, click **Save**.
12. On the same tab, scroll below to **Application Attribute Mappings** section. On this section, click **Go to Profile Editor**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2B9M3FD1.png)

It opens **Profile Editor** page.
13. On the **Profile Editor** page, under **Attributes** section, click **+ Add Attribute**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MKOQQ5UY.png)

It opens **Add Attribute** popup.
14. On the **Add Attribute** popup, add the following values:

| Parameter | Value |
| --- | --- |
| Data type | `string array` |
| Display name | `Roles` |
| Variable name | `roles` |
| External name | It fetches automatically from **Variable name**. However, you must ensure that both values must be same. |
| External namespace | `urn:ietf:params:scim:schemas:core:2.0:User` |
| Attribute type | `Group` |
| Group Priority | `Use Group Priority` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GA4197D2.png)

Once you add the above attributes, click **Save**.
15. Return to your application’s main page by selecting **Applications > Applications** and click your application name and open the **Assignments** tab.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-573JX5DT.png)
16. On the **Assignments** tab, click **Assign**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OME17UBF.png)
17. From the menu, select **Assign to People**.

It opens **Assign Application to People** popup displaying list of users.
18. Select a user. On the right side of the user name, click **Assign**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0JSPTM6H.png)

It opens details of the user within same popup.
19. On the **Assign Application to People** popup, add the role and organization to the user.

> [!NOTE]
> Note
> 
> - For the role and organization, add the exact same role and organization name as in Securiti.
> - To add multiple organizations, add a coma between organization names without any space. If there is a coma within the name of organization, enclose the name in double quotes, for example "orgadmin,users".

To add another role, below the role field, click **Add Another** and add a second role.
20. Once you assign the role and organization, click **Save and Go Back**.

Okta starts provisioning the assigned users and groups to Securiti through SCIM. Any future user lifecycle changes in Okta, such as creating, updating, deactivating, or deleting users, automatically synchronize with Securiti based on the configured provisioning settings.

### Provisioning and updating a user from IdP

When you provision a new user in your IdP, SCIM automatically creates a new user in Securiti.

It displays the **Source** of user as SCIM.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y17GED3P.png)

When you update a user in your IdP, it also reflects the update automatically in Securiti.

For more information on **Users** page, see [Managing Securiti users](/latest/docs/configuring-access-management-managing-securiti-users).

### Deleting a user from IdP

When you delete a user from your IdP, it deletes according to your applied regulations. However, in Securiti, you must allocate its assigned permissions and roles to another user with either similar or higher role. So, when you delete a user from your IdP, Securiti asks you to assign the permissions first.

When you delete a user in your IdP, follow the below steps to delete the user from Securiti:

1. Open **Users** page in Securiti.
  1. In Securiti, click the jewel at the bottom of the **Dashboard**.
  2. From the list of options, select **Settings**.
  3. From the **Settings** menu, choose **Organizational > Access Management > Users**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H3WPO8XC.png)
2. When you delete a user from IdP, it displays the following note. From the note, click **Reassign resources**.

It also updates its status as **Deletion Pending**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8S1JVT8V.png)

It opens **Reassign Resources** popup.
3. On the Reassign Resources popup, assign the resources to another user with the steps below:
  1. Select a user you are assigning the roles of to another user.
  2. In the **Assign Resources To** column following the same row of deleting user, select the dropdown menu.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KXO6388V.png)
  3. From the dropdown menu, select a user.

> [!NOTE]
> Note
> 
> You can assign role and delete multiple users at the same time.
  4. Click **Reassign and Delete** to successfully reassign and delete the user from Securiti.

It follows the standard process for deleting a user from Securiti.
