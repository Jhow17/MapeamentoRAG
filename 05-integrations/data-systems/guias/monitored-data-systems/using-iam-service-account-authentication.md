---
title: "Using IAM Service Account authentication"
slug: "using-iam-service-account-authentication"
updated: 2026-04-28T04:37:07Z
published: 2026-04-28T04:37:07Z
canonical: "helpcenter.securiti.ai/using-iam-service-account-authentication"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Using IAM Service Account authentication

The IAM Service Account Authentication method securely authenticates and grants access to Google Cloud Storage (GCS) using a service account within Google Cloud Platform (GCP). This method uses service account impersonation, that lets one service account act on behalf of another service account.

Service account impersonation facilitates delegating Permissions from one service account to another, without the need to share service account keys or Credentials. For more information, see [Official Google Cloud documentation on service account impersonation](https://cloud.google.com/iam/docs/service-account-impersonation).

### Prerequisites

Fulfil the following prerequisites to use IAM Service Account Authentication successfully. For more information, see [Prerequisites for Google Cloud Storage connector](/latest/docs/prerequisites-for-google-cloud-storage-connector).

- A GCP account with administrative Permissions.
- A running Pod (VM) running in GCP.
- Two service accounts configured as follows:

> [!NOTE]
> **Important**
> 
> You must have the required roles and Permissions assigned to the target service account as described in [Creating service account in GCP.](/v1/docs/prerequisites-for-google-cloud-storage-connector)
  - **Source service account**: This service account is assigned to the VM and has the `cloud-platform` scope enabled for impersonation.
  - **Target service account**: This service account is impersonated by the source service account and has all the necessary Permissions to access Google Cloud Storage buckets, as described in [Creating service account in GCP](/latest/docs/prerequisites-for-google-cloud-storage-connector).

### Verifying service account roles

You must provide and verify the necessary roles and Permissions assigned to your source and target service accounts. This can be accomplished using both Google Cloud Console UI and CLI.

**Option 1: Using Google Cloud Console UI:**

1. Navigate to the [IAM & Admin > IAM](https://console.cloud.google.com/iam-admin/iam) section.
2. Verify that your target service account has the necessary roles according to your use case, for example; "Storage Admin".
3. Verify that your source service account has the **Service Account Token Creator** (`roles/iam.serviceAccountTokenCreator`) role at the organization or project level.

**Option 2: Using Google Cloud Console CLI:**

- To verify your source service account's roles, run the below command in CLI:

```plaintext
gcloud projects get-iam-policy PROJECT_ID --format=json | grep "SOURCE_SERVICE_ACCOUNT_EMAIL"
```
- To verify your target service account's roles, run the below command in CLI:

```plaintext
gcloud projects get-iam-policy PROJECT_ID --format=json | grep "TARGET_SERVICE_ACCOUNT_EMAIL"
```

### Enabling service account impersonation

You must grant the necessary roles and Permissions to your Target Service Account to enable source service account impersonation. This can be accomplished using both Google Cloud Console UI and CLI.

**Option 1: Using Google Cloud Console UI:**

1. Go to **IAM & Admin > Service Accounts**
2. Select the Target Service Account to impersonate.
3. Click **Permissions** tab and on the lower left side of the page, select **Grant Access**.
4. In the popup, in the **New principals** field, enter the email of your source service account.
5. In the **Assign Roles** section, from the **Role** menu, select **Service Account Token Creator**(roles/iam.serviceAccountTokenCreator).
6. Click **Save.**

![gcs_IAMtargetserviceaccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f3eb1269-8454-8708-ac43-a20728c8598a.png)

**Option 2: Using Google Cloud Console CLI:**

- To set the service account email and role for your target service account, run the below command in the CLI:

```plaintext
gcloud iam service-accounts add-iam-policy-binding \
    TARGET_SERVICE_ACCOUNT_EMAIL \
    --member="serviceAccount:SOURCE_SERVICE_ACCOUNT_EMAIL" \
    --role="roles/iam.serviceAccountTokenCreator"
```

### (Optional) Configuring OAuth scopes on VMs

If your source service account is attached to a VM, you must ensure it has the proper OAuth scopes. This can be accomplished using both Google Cloud Console UI and CLI.

**Option 1: Using Google Cloud Console UI:**

> [!NOTE]
> **Important**
> 
> For existing Virtual Machines (VMs) in Google Cloud, scopes cannot be modified directly after creation. To modify scopes, stop the VM, enable the required scopes, and then restart the VM.

1. When creating a VM, click **Advanced options** to expand the section.
2. Select **Security > Service Account**.
3. Select your source service account and in **Access scopes**, do one of the following:
  - Select **Allow full access to all Cloud APIs**

![gcs_vm_fullaccess.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47922898-15aa-040d-8f19-365ee5e145c1.png)
  - Select **Set access for each API** and set the **Cloud Platform** API to **Enabled**.

![gcs_vm_cloudapi.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-454eccb5-9a76-ea07-d413-d34cc8a3e01c.png)
4. Click **Save**

**Option 2: Using Google Cloud Console CLI:**

- To set the OAuth scopes for new VMs, run the below command in the CLI:

```plaintext
gcloud compute instances create INSTANCE_NAME \
    --service-account=SOURCE_SERVICE_ACCOUNT_EMAIL \
    --scopes=https://www.googleapis.com/auth/cloud-platform
```
- To update the OAuth scopes for existing VMs, run the below command in the CLI:

```plaintext
# Stop the VM
gcloud compute instances stop INSTANCE_NAME 

# Update the VM's service account and scopes
gcloud compute instances set-service-account INSTANCE_NAME \ --service-account=SOURCE_SERVICE_ACCOUNT_EMAIL \ --scopes=https://www.googleapis.com/auth/cloud-platform 

# Start the VM
gcloud compute instances start INSTANCE_NAME
```

### Verifying service account impersonation

You can test impersonation by listing buckets using the impersonated account. Access the Pod (VM) and run the following command:

```plaintext
gcloud storage ls --impersonate-service-account=TARGET_SERVICE_ACCOUNT_EMAIL
```

Proceed to [(New UI) Connecting Google Cloud Storage with Securiti](/latest/docs/new-ui-connecting-google-cloud-storage-with-securiti) or [Activate the Google Cloud Storage connector in Securiti](/latest/docs/activate-the-google-cloud-storage-connector-in-securiti).

For more information on troubleshooting common errors, see [Troubleshooting for Google Cloud Storage connector](/latest/docs/troubleshooting-for-google-cloud-storage-connector).
