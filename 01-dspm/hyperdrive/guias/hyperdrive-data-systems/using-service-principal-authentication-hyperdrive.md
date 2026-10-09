---
title: "Using Service Principal to authenticate Azure Blob Storage (Hyperdrive)"
slug: "using-service-principal-authentication-hyperdrive"
updated: 2026-05-25T20:16:01Z
published: 2026-05-25T20:16:01Z
canonical: "helpcenter.securiti.ai/using-service-principal-authentication-hyperdrive"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Using Service Principal to authenticate Azure Blob Storage (Hyperdrive)

This section contains information about how to configure Azure Blob Storage using the following authentication methods.

- Service Principal (previously known as Azure AD)
- Service Principal using Certificate (see step 5 of the procedure below)

To use Service Principal Authentication (SPA) methods for your Azure Blob Storage, you need to register an application in the Active Directory, also known as Microsoft Entra ID.

### Authentication procedure

#### Step 1 - Register an application in the Azure Portal.

> [!NOTE]
> **Note**
> 
> To activate the connector for Azure Blob Storage, you need to register an application using Microsoft Entra ID. This registration process involves creating a unique identifier for the application and configuring permissions that allow it to access relevant resources.

1. Log in to your [Microsoft Azure](https://portal.azure.com/) admin console.
2. On the **Home** page under the **Azure services** section, click **App registrations**.

![Home-page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c3251629-3409-a24d-ee18-15989dd3ae91.png)
3. On the **App registrations** page, click **+ New registration**

![new-registration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5e74a3c-4abb-0ba5-4e75-3a6a62050a40.png)
4. On the **Registration an application** page, apply these settings:
  1. Enter a convenient name, for example, "Securiti connector."
  2. Leave other settings as default.
  3. Near the bottom of the page, click **Register**.

For more information on registering an application in Microsoft Entra ID, see [this resource](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant#register-an-application-in-microsoft-entra-id).

#### Step 2 - Add application ID URI and configure client secret

Perform the following steps to add application id URI and configure client secret:

1. On the left sidebar, choose **Expose an API** then click **Add**.

![expose-api.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7beaa6db-a12e-c5f2-186e-9c98735c7099.png)
2. On the **Edit application ID URI** popup, click **Save**.

![aplication-URI.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b75ac06f-a4ae-36c1-efc7-5c2776c92f81.png)

Note the **Application ID URI** on the **Expose an API** page.
3. **Configure application secret:**
  1. In the left sidebar under the **Manage**, click **Certificates & secrets**. On the "Certificates & secrets" page, click **+ New client secret**.

![new-client-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-538c9eb6-1506-8cd7-7078-29c593f87ca3.png)
  2. On the **Add a client secret** popup:
    - Enter a description for the secret, for example, “Azure Blob Storage connector secret.”
    - Choose an expiration term. We recommend one year.
    - Click **Add** to add the secret to the list. ![add-a-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9df92994-afdc-11c7-6071-5c5dc82c1f87.png)
  3. Under the **Client secrets** tab, copy the secret by clicking **Copy to Clipboard** in front of **Value**, as shown below.

![copy-secret.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-674f40a4-4daf-2746-d30b-6518b9226284.png)
  4. Record the new **Client Secret** to use it connector activation.

#### Step 3 - Assign the `Storage Blob Data Reader` role to the application

Perform the following steps to assign the Storage Blob Data Reader role to the Azure Blob Storage application create earlier.

1. On the top left click hamburger icon to open the left sidebar.
2. On the left sidebar, click **Storage accounts.**

![sidebar-Blob.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9cc9bacd-5b3f-21bd-b875-6dc708f89b2d(1).png)
3. Select the storage account you want to link to your Microsoft Entra ID application.

![Storage_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c14604de-eef8-6387-560f-be452ebb008f(1).png)

It opens the Storage account sidebar.
4. On the left storage account sidebar, choose **Access Control (IAM)**.
5. On the top left of **Access Control (IAM)** page, select **Add role assignment** from the **+Add** menu.

![IAM-role-add.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7beb9c5a-efef-8153-725d-bb1d7d47e8fa.png)
6. On the **Add role assignment** page, configure the following settings:
  1. Under the **Role** tab, search **Storage Blob Data Reader** role from the list of **Job function roles**.
  2. Click on the **Storage Blob Data Reader** role and click **Next**.

![assign_role.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-039b25fc-8084-fb58-b326-14ddf61affc7.png)
  3. Under the **Members** tab, configure the following settings:
    1. Click on the **+ Select members** link.
    2. On the **Select members** popup, search the Azure Blob Storage app you want to assign the "Storage Blob Data Reader" role.
    3. After selecting the Azure Blob Storage app, click **Select**.

![storage-role-app.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da1d9045-4f87-2224-099c-459c636ed525.png)
  4. Click **Review + assign**.

![review_assign.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-614b6444-486a-0aef-047c-e5565ff8ca80.png)

It assigns the "Storage Blob Data Reader" role to the Azure Blob Storage application you created earlier.

For more information on how to associate your storage account with Microsoft Entra ID, see [Microsoft Azure documentation](https://learn.microsoft.com/en-us/azure/databricks/connect/storage/aad-storage-service-principal).

#### Step 4 - Obtain activation credentials in Azure Blob Storage application

Perform the following steps to record more activation credentials.

1. Record the **Account Name**:
  - On the top left, copy the storage account name you have used to link the Microsoft Entra ID.

![storage-account-name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2d75920-f03e-543b-d481-9db117d50623.png)
2. Record **Application ID (Client ID)** and **Tenant ID**.
  1. On the left sidebar of Azure Blob Storage app in Microsoft Entra ID, click **Overview** and record the "Application (Client) ID" by clicking the **Copy to Clipboard** icon for later use.
  2. Record the following by copying it.
    - **Application (Client) ID**
    - **Tenant ID**

![client-ten-id.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74970ad3-c75c-7baa-d7bb-73c598e09bc0.png)
3. From the **Overview** page for your storage account, record the values for **Resource group** and **Subscription ID**, as shown below.

![azureblobs_resourcesubscid.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-075188b6-7e3d-1b6c-cf77-f23a01b58523.png)
4. Proceed to [Connecting Azure Blob Storage (Self Hosted) with Securiti (Hyperdrive)](/latest/docs/connecting-azure-blob-storage-self-hosted-with-securiti-hyperdrive) if you want to **Service Principal** authentication.

In case of the **Service Principal with Certificate** authentication, proceed to the next step before activating the connector.

#### Step 5 - Additional steps for Service Principal with Certificate authentication

To use the **Service Principal with Certificate** authentication method, follow the procedure below.

1. Create an Azure Blob Storage app and
2. Obtain the following credentials as mentioned above in Service Principal app registration:
  - Client ID
  - Tenant ID.
3. From the left menu, select **Certificates & Secrets**.
4. Under the **Certificates** section, click **Upload Certificate**.

![certificate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eadbc7b9-dd6e-cab7-3de0-5ee2aa415079.png)
5. Perfrom the following steps to create a certificate and private key.
  1. Run the below openssl command on your console.

```plaintext
openssl req -subj "/CN=myclientcertificate/O=Securiti.ai, Inc./ST=CA/C=US" \
   -new -newkey rsa:4096 -sha256 -days 730 -nodes -x509 -keyout key.pem -out cert.pem
```
  2. Save the certificate file and private key file to use later for connector activation.
6. Upload your certificate file to use for authentication.

![upload-certificate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7b50c1d-699c-6d24-a04e-937a204f2a0b.png)

### Enabling resource size evaluation for Azure storage account

You can enable the resource size evaluation for your Azure storage account, where Securiti calculates the accumulative size of all containers in the storage account.

> [!NOTE]
> **Note**
> 
> - Resource size evaluation for Azure Blob Storage is supported for **Service Principal** and **Service Principal with Certificate** authentication types only.
> - You must use pod version 1.130.0 and above to enable this feature.

To enable resource size evaluation for your account:

1. For your storage account, on the left storage account sidebar, choose **Access Control (IAM)**.
2. On the top left of **Access Control (IAM)** page, select **Add role assignment** from the **+Add** menu.

![azureblob_addrole.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-76d7231c-d723-02d2-978a-e51b172d4d16.png)
3. On the **Add role assignment** page, under the **Role** tab, search **Monitoring Reader** role.
4. On the **Monitoring Reader** role and click **Next**.

![azureblob_monitoringreader.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a9dd5b80-2143-a126-71fa-fa93e6cbc695.png)
5. Under the **Members** tab, click **+ Select members**.
6. On the **Select members** popup, search the Service Principal by name or ID and select it.

![azureblob_assignrole.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0b5aa59b-2509-341c-28c4-dc7be7300862.png)
7. Click **Review + assign**.

Next, you must record the **Resource ID** for your account. To access the Azure storage account **Resource ID**:

1. For your storage account, on the left storage account sidebar, choose **Overview**.
2. Near the upper right corner of the page, click **JSON view**.

![azureblob_viewjson.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a6589cb3-3c9a-e8a0-76dd-acc484c81456.png)
3. From the **Resource JSON** popup, copy the **Resource ID**, as shown below.

![azureblob_resourceID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2694beb4-1f7e-2448-e8d6-48e289d8b9b6.png)

Proceed to [Connecting Azure Blob Storage (Self Hosted) with Securiti (Hyperdrive)](/latest/docs/connecting-azure-blob-storage-self-hosted-with-securiti-hyperdrive).
