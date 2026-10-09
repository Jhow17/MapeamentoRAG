---
title: "Using Service Principal to authenticate Azure Files"
slug: "using-service-principal-to-authenticate-azure-files"
updated: 2026-07-30T08:18:57Z
published: 2026-07-30T08:18:57Z
canonical: "helpcenter.securiti.ai/using-service-principal-to-authenticate-azure-files"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Using Service Principal to authenticate Azure Files

This section contains information about how to configure Azure Files using Service Principal. For that, you need to register an application in Microsoft Entra ID. For activation via a Storage Account, see [here](/v1/docs/obtain-authentication-credentials-in-azure-storage-account).

Use the matching procedure below.

1. To register an application in Microsoft Entra ID:

See [this resource](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant#register-an-application-in-microsoft-entra-id) for more information on registering an application in Microsoft Entra ID.
  1. Log in to [portal.azure.com](https://login.microsoftonline.com/organizations/oauth2/v2.0/authorize?redirect_uri=https%3A%2F%2Fportal.azure.com%2Fsignin%2Findex%2F&amp;response_type=code%20id_token&amp;scope=https%3A%2F%2Fmanagement.core.windows.net%2F%2Fuser_impersonation%20openid%20email%20profile&amp;state=OpenIdConnect.AuthenticationProperties%3D34asirEApnqXTgHwa0nlS_tzZvPYSZNEpQQwoge4xFDX-eHxemOqewgjblpQV-CNsX0PTOgxb0zM7pnrTxMNzyd9-A2-YRNBkTZeHPB6CtGowiUpj2ELpiP1Q7LyAAVet05MRuRX4yHKJDL8PAdgSjv6KxpK-WlT3Laa9D95-Ha-yA9rdNA2Ilo_Rd1GXvYFtxCpBBRTt1xwp8-UlRWWv-jXN7E_pXawGIUPwc7Sr854gYaAF0F2bGzRfwww1Z-IPUZxZbbHS1Q2UMlnpLuQFS97k3mcDfbxF8vC9GCJA6amv4b6vFcZSM_Omwv9UiKzv9GPEI62O0TKIrXwWKa1GnfQAAUXsb9qLWc4autL5CHw6vMbxjosm_oI8y3-wuSSnFjf2swE66zqUJ9nxE_LjUUA62-AnJODt0UksErG2MQvpn1g5PJDwrC_qTWZBNbjsNIjZnX-Mkw6aCW9Hpf7SNPKGIX7iNQAQC53dT2lEkzGbWhkGT5pm9j2cOGvgE7E&amp;response_mode=form_post&amp;nonce=638421100404121072.ZDNkMGQwNzUtYjVlNi00Njg1LThmOTItZWUyZDM2YmZmMTdhY2FkNTYxMWItMTA0NS00ODkxLWJiYjctNzI5MDg0N2Y0M2Mz&amp;client_id=c44b4083-3bb0-49c1-b47d-974e53cbdf3c&amp;site_id=501430&amp;client-request-id=bbcb22f5-42a0-496c-bec2-f4397f16dcec&amp;x-client-SKU=ID_NET472&amp;x-client-ver=6.34.0.0)
  2. On the homepage, choose **Microsoft Entra ID**.
  3. Click **Add** and enter the application name. You may leave other settings to their default values.
  4. Click **Create**
2. Once you have successfully created the ID, do the following:
  1. On the dashboard of your Microsoft Entra ID, in the left sidebar, select **Expose an API**.
  2. In the right-hand side window, click **Add** next to the **Application ID URI** and click **Save**.

![unnamed_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d3629420-a299-bdda-185d-0a618013b42d.png)
  3. In the left sidebar, click **Overview**, and in the **Client secrets** tab, click **+ New client secret**.

![unnamed__1__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5266472-4545-5fd8-2b30-4297625c963a.png)
  4. Click **New secret pair** and enter a name for the secret key, then click **Add**.
3. To assign the Storage File Data Privileged Reader role to the application:

See [this article](https://learn.microsoft.com/en-us/azure/databricks/connect/storage/aad-storage-service-principal) for more information on how to associate your storage account with Microsoft Entra ID.
  1. Select the storage account you want to link to your Microsoft Entra ID application.
  2. Choose **Access Control (IAM)**
  3. On the following page, click **+ Add** and select the **Add role assignment** option from the dropdown menu.
  4. From the list of roles, expand `Storage File Data Privileged Reader`, and mark the checkbox for the Microsoft Entra ID application you created earlier to add it. To use Data Labeling policy, also provide the `Storage File Data Privileged Contributor` role.

![unnamed__4__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66a14107-689c-91e4-b936-3e730fae08c9.png)
4. Also, you must provide custom permissions for APIs such as "ListShares" and "CalculateShareSize."

> [!NOTE]
> **Note**
> 
> These custom permissions are required for Microsoft Entra ID against the storage account you've opted for. This is because few APIs use the Microsoft Storage resource provider instead of legacy management APIs. OAuth is not supported for legacy management API.
  1. Navigate to the resource group you've associated the storage account with.
  2. In the left sidebar, select **Access control (IAM) > Roles**, and from the actions menu (three horizontal dots), click **Clone**.

![Screenshot_2024-01-30_at_8_08_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ab9666a-052a-eb8b-f0f3-c8b6fe0db461.png)
  3. On the **Basics** tab, in the **Custom role name** field, enter a name and click **Next**.

![unnamed__1__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4079f9d1-8c35-6a58-bc49-a8f672110ff7.png)
  4. On the **Permissions** tab, select **Add permissions > Microsoft Storage** and click **Add**.

![unnamed__2__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a4d0493-b0ef-4444-d101-3899a8ffe5b6.png)

Make sure to add these permissions:
    - `List File Services`
    - `Get File Service Properties`
    - `Get File Share`
    - `List File Shares`
  5. Go back to the Access control (IAM) page and select **Add role assignment > {custom role}** you created in step 4(c), and save.
  6. On the **Members** tab, click **+ Select members** and choose your Microsoft Entra ID application, then save.

![unnamed__3__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9aba8761-585b-dbcb-fbdf-1f0b4f797250.png)
5. Record the following parameters to activate the Azure Files connector using Active Directory, as shown below:
  - **Account Name** - The storage account name you have used to link the Microsoft Entra ID.

![unnamed__3__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-469da7df-07a2-eba4-283c-577aa2f0f1cf.png)
  - **Application ID (Client ID)** - Your Microsoft Entra application ID.

![unnamed__4__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8bd175e8-f271-5801-1ca0-9198fba24128.png)
  - **Tenant ID** - The directory associated with your Microsoft Entra ID.

![unnamed__5__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47a39a64-0601-9525-7206-0c8bca08acd7.png)
  - **Client Secret** - The secret key you generated at the time of app creation.

![unnamed__6__1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-49bde907-e4fb-256c-5c58-1db896705d07.png)
  - **Subscription ID** - The ID of your Azure account.
  - **Resource Group Name** - The name of the group your storage account is associated with.

![unnamed_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d21cbbad-2157-7922-bf60-ce2c4b2cc4f2.png)
6. Proceed to [Connecting the Azure Files data system](/latest/docs/connecting-the-azure-files-with-securiti).
