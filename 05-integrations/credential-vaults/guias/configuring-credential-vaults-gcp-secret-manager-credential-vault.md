---
title: "GCP Secret Manager credential vault"
slug: "configuring-credential-vaults-gcp-secret-manager-credential-vault"
updated: 2026-08-28T06:17:53Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/configuring-credential-vaults-gcp-secret-manager-credential-vault"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# GCP Secret Manager credential vault

Securiti supports credential vaults that you can use to manage privileged account secrets for data systems that you integrate with Securiti.

> [!NOTE]
> **Note**
> 
> The Credential Vaults feature is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.

In Securiti, you configure one instance of GCP Secret Manager for each GCP project.

## Roles and permissions

Securiti implements role-based access control on actions that can be performed for credential vaults and keyrings, such as keyring creation. For more information on roles and their permissions, see [Data Systems RBAC permissions](/v1/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-default-roles).

Refer to the matching procedure to configure GCP Secret Manager credential vaults and create Keyrings.

### 1. Obtain the project ID

1. If you haven't already done so, log in to the GCP console.
2. From the list of projects, choose **Manage all projects**.
3. GCP shows you the names and IDs for all the projects of which you are a member.
4. Record the project ID of the project for which you are configuring GCP Secret Manager in Securiti.

### 2. Choose or create a service account

The service account you use later to create the service key file must have the following roles at a minimum:

- Secret Manager Secret Accessor (roles/secretmanager.secretAccessor)
- Secret Manager Viewer (roles/secretmanager.viewer)

In the GCP console, choose a service account with these roles, or create one as described in [Create service accounts](https://cloud.google.com/iam/docs/service-accounts-create).

### 3. Create the service key file

If you have already downloaded a JSON format service key file for the service account, you can use that, otherwise you must create a new one. GCP Console only lets you download the key file once.

To create a new JSON-format key and download its file:

1. In the GCP console, near the upper left corner of the window click **Menu** (three lines) and choose **IAM & Admin > Service Accounts**.
2. Choose the service account you created or identified in [Choose or create a service account](/v1/docs/gcp-secret-manager-credential-vault).
3. On the Keys tab, choose **Add Key > Create new key**.
4. On the Create Private Key for <service account> popup, mark the radio button for **JSON**, then click **Create**.

GCP downloads the service key file to your downloads folder.

### 4. Service key file placement to the pod(s)

Securiti offers two methods for placing Service key file to Pod nodes while configuring GCP Secret Manager credential vaults.

Choose one of the following methods to place the Service key file to Pod:

1. [Uploading and placing service account key file to Pod nodes](/v1/docs/gcp-secret-manager-credential-vault)
2. [Service account key file encryption and automation to Pod](/v1/docs/gcp-secret-manager-credential-vault) (Preferred).

This method lets Securiti encrypts the customer credentials and automates the vault secret process. Additionally, it saves you from the hassle of adding credential file on every Pod node.

#### Method 1: Uploading and placing service account key file to Pod nodes

For each node of each pod, you use to scan the GCP project, use SCP to copy the file to a location such as /mnt/secrets. You might have to first copy the file to the pod, and then log in to the machine and move the file into the /mnt directory

> [!NOTE]
> **Important**
> 
> Starting from release 1.133.0, the method of manually uploading keys to pod nodes is deprecated.

1. From your machine, use SCP to copy the file onto the node, for example:

```bash
scp -i -/.ssh/aws.pem -/Downloads/servicekeyfile.json ec2-user@10.100.51.4:/home/ec2-user/
```
2. Log in to the node and create the /mnt/secrets directory, then move the file into that directory, for example:

```bash
mkdir /mnt/secrets
mv servicekeyfile.json /mnt/secrets/
```
3. Proceed to [Configure the GCP Secret Manager vault instance in Securiti](/v1/docs/gcp-secret-manager-credential-vault).

#### Method 2: Service account key file encryption and automation in Pod (Preferred)

You can configure the service key file for all nodes using the matching procedure.

1. Open the appliance-config pod as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-E77HZKOR.png)
2. On your appliance-config-controller pod, run the following command:

```bash
kubectl exec -it deployment/priv-appliance-config-controller -- securitictl configure-vault-secret
```

It asks you to select vault types.
3. Select **GCP Secret Manager** from the list of vault types as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HQC3DATA.png)
4. Refer to the matching procedure to obtain Vault ID in Securiti.

> [!NOTE]
> **Note**
> 
> You can get a Vault ID from an active GCP Secret Manager **Instance**.
  1. Open **System Settings**. Choose **Integrations > Credentials > Credential Vaults**.
  2. Choose the **GCP Secret Manager** instance you want to connect.

> [!NOTE]
> **Important**
> 
> If you do not have an active GCP Secret Manager Instance, create a new instance using the [5. Configure the GCP Secret Manager vault instance in Securiti](/v1/docs/gcp-secret-manager-credential-vault).
  3. On the top of the GCP Secret Manager **Instance** in the URL address bar, copy the URL. See the example below.

*https://test.securiti.com/#/settings/credential-vaults?inst=****12201****&tab=BASIC_INFORMATION*

Vault ID is **12201** in this URL which starts after "inst=".
5. Enter the **Vault ID as shown below.**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HYO6LCUG.png)

When you enter a vault ID, it opens a new editor.
6. On the new editor as shown below, paste code copied from the JSON credentials file that you downloaded in the [Create Service Key File](/v1/docs/gcp-secret-manager-credential-vault) above.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CQN0N1PF.png)

A success message appears.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XLWUL88R.png)
7. Save the information in the editor.

> [!NOTE]
> **Note**
> 
> Use the keyboard commands to save the credential file information and exit from the editor. Commands can vary depending on the operating system you are using.
8. Proceed to [Configure the GCP Secret Manager vault instance in Securiti](/v1/docs/gcp-secret-manager-credential-vault).

### 5. Configure the GCP Secret Manager vault instance in Securiti

In Securiti, create one GCP Secret Manager instance for each GCP project.

1. In Securiti, open the main menu and select **Integrations > Credential Vaults**.
2. On the Credential Vaults page, near the upper right corner of the page, click **Add Integration** to create a new instance.
3. From the catalog of available credential vaults, select **GCP Secret Manager**.
4. On the **Basic Information** tab, enter a name and location for the GCP Secret Manager vault instance, and if you want, also choose additional co-owners (by default you are the owner).
5. Click **Create Instance & Continue**.
6. In the **Authentication** tab, select a pod(s) from the **Pod Configuration** menu where a vault authenticates.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.
7. In the **Authentication** tab, provide the following:

| Setting | Description |
| --- | --- |
| Authentication Method | Choose **IAM Roles**. |
| Project ID | Enter the project ID. |
| (Optional) Service Account Key Path | Enter the path and filename where you placed the service account JSON key file earlier, for example, `/mnt/secrets/servicekeyfile.json` > [!NOTE] > **Note** > > You can leave Service Account Key Path empty for method 2 [Service account key file encryption and automation to Pod](/v1/docs/gcp-secret-manager-credential-vault) . > > After release 1.133.0, this field is not required. |
8. Click **Test and Save**.
9. On the **Test Connection** popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
10. View the connection status in the **Overview** tab.

### 6. Create keyrings

Create keyrings that point to the connector secrets that you have placed in your key vault:

1. In System Settings, open **Integrations > Credentials > Keyrings** and click **Create Keyring**.
2. On the Add Keyring popup, apply the following settings, then click **Add Keyring**:

| Setting | Description |
| --- | --- |
| Keyring Name | Enter a descriptive name for the keyring. |
| Keyring Description | (Optional) Enter a description for the keyring. |
| Keyring Type | Choose **GCP Secret Manager**. |
| Connector Type | Choose the type of data system for the keyring. |
| Vault Instance | Choose the GCP Secrets Manager credential vault you configured earlier. |
| User Key | Choose the user key configured in GCP Secret Manager. |
| Password Key | Choose the password key configured in GCP Secret Manager. |

### 7. Configure data systems to use the keyrings

Currently, Securiti supports GCP Secret Manager keyring storage for the following data systems:

- Google BigQuery
- Google Cloud SQL for MySQL
- Google Cloud SQL for PostgreSQL
- Google Cloud SQL for SQL Server
- Google Cloud Storage

> [!NOTE]
> **Note**
> 
> For Google Cloud Storage connector, the secret must be stored in base64 format for the keyring to work successfully. To encode the secret in base64, see [online encoder](/v1/docs/securiti-pods-and-elastic-pods).

For each such data system where you want to use GCP Secret Manager:

1. In Securiti, open **System Settings** and choose **Integrations > Data Systems > Monitored**.
2. Create a new data system instance, and on the Connector tab apply the following settings, then click **Authenticate & Activate Connector**:

| Setting | Description |
| --- | --- |
| Use Keyring | Enable the toggle. |
| Keyring Type | Choose **GCP Secret Manager**. |
| Keyring | Choose the keyring you created earlier in [6. Create keyrings](/v1/docs/gcp-secret-manager-credential-vault). |

Can be both Reviewer and Respondet. As a Reviewer they can review but can't approve the assessment. As Respondent, they can add comments and help with the answers but can't submit the assessment.

Authentication is a fundamental process in information security, access control, and many other contexts where security and trust are important. It is typically achieved through the presentation of credentials or evidence that establishes the identity of the party seeking access or authorization.

## Related

- [CredStash credential vault](/configuring-credential-vaults-credstash-credential-vault.md)
- [CyberArk Conjur credential vault](/configuring-credential-vaults-cyberark-conjur-credential-vault.md)
