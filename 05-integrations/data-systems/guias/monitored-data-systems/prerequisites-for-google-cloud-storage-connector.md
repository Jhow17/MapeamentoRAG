---
title: "Prerequisites for Google Cloud Storage connector"
slug: "prerequisites-for-google-cloud-storage-connector"
updated: 2025-10-31T07:43:17Z
published: 2025-11-03T06:14:44Z
canonical: "helpcenter.securiti.ai/prerequisites-for-google-cloud-storage-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Google Cloud Storage connector

Google Cloud Storage Connector supports **Credentials File** and **IAM Service Account** Authentication methods to integrate with Securiti and enable data scanning.

See the sections below for the following prerequisites:

- Acquiring GCP Project ID
- Creating buckets in GCP
- Enabling the Cloud Storage API
- Creating a service account in GCP
- Enabling object versioning for buckets
- Enabling soft deletion policy

After fulfilling these prerequisites, proceed to the following topics based on your selected Authentication method.

- [Using Credentials File authentication](/v1/docs/using-credentials-file-authentication)
- [Using IAM Service Account authentication](/v1/docs/using-iam-service-account-authentication)

### Acquiring GCP Project ID

You must have your GCP Project ID in order to authenticate your Google Cloud Storage Connector with Securiti. To acquire your project ID.

1. Log in to Google Account in [Google Cloud Platform](https://console.cloud.google.com/freetrial/signup/tos?_ga=2.73047379.-1319717460.1558077431)
2. On the landing page, record your GCP Project ID as shown below.

![gcs_projectIDlandingpage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d26c9359-f7e0-cac6-21d2-d9aacade8562.png)
3. To record project ID of a different project, from the top of the page, click your project name.
4. On the popup, from the list of projects, copy and save the required Project ID as shown below.

![gcs_projectID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1381e4f2-daa5-6d49-0cdb-508596b52ecc.png)

### Creating buckets in GCP

You must have a bucket to connect your Google Cloud Storage with Securiti and enable scanning for data in that bucket. To create buckets:

1. On the GCS dashboard, select **Browser** from the left menu, then click **Create Bucket**.

![create_bucket.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-42af05ab-3532-b431-3044-369619fb89fc.png)
2. Enter a bucket name and click **Create**, as shown below.

![enter_a_bucket_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-25f590e8-f990-c4a0-7432-1db7c404d603.png)
3. Record this bucket name to use later.

### Enabling Cloud Storage API

- On Google Cloud Platform, select **Cloud Storage** API and click **Enable** to activate it.

![click_enable.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2cd87278-849e-2e98-c1af-02acdc4b88ed.png)

### Creating service account and role in GCP

You must have a service account with the necessary roles and Permissions in GCP, to connect with Securiti. Follow the steps below to create a role, service account, and assign Permissions in GCP.

1. From the left sidebar, select **IAM & Admin > Roles**.

![gcs_iamtoroles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae0f5ba6-20be-8ece-3ca3-f1359857cfcb.png)
2. On the Roles page for your project, click **Create Role**.

![gcs_createrole.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ee42053-131f-53fb-b11d-9ab0a34f7217.png)
3. Add title for the role and click **Add Permissions**.
4. Add the below Permissions and click **Create** or **Update** if you're editing roles, as shown below.

![gcs_permissions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07bce145-a225-3365-0c88-01d8ba1fd4ba.png)
  - `monitoring.timeSeries.list`
  - `monitoring.viewer`
  - `storage.buckets.get`
  - `storage.buckets.getIamPolicy `
  - `storage.buckets.list `
  - `storage.objects.get`
  - `storage.objects.list`
5. To generate Credentials for the Cloud Storage API, click **Credentials > Create Credentials > Service account**.

![gcs_createcredentialsserviceaccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5bf0f94-2545-f743-819e-ca9a616428e9.png)
6. Add a name for your service account and click **Done**.

![gcs_createserviceaccount.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-df87f15d-08f2-538a-dfd0-0c9329c8af69.png)
7. From the left sidebar, select **IAM** and click **Grant Access** for your service account.
8. On the popup, in the **New Principals** field, enter the email address of the service account created in step 7 and select the role created in step 5. Click **Save**.

![gcs_serviceaccount_rolesprincipals.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c8bb5d04-6f84-2daa-c6d0-274ac32f0e42.png)

### Enabling object versioning for buckets

To let Securiti process all versions of your GCS bucket objects, you must enable object versioning. To enable object versioning:

1. In [Google Cloud console](https://console.cloud.google.com/storage/browser), select your project.
2. Click on the bucket name to enable versioning for it.
3. In **Bucket details**, select the **Protection** tab.

![gcs_protectiontab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08a087d6-e76d-37ce-5eb0-8f93d029bc57.png)
4. In the **Object versioning (for data recovery)** section, click **Object versioning off**.
5. On the **Turn on object versioning?** popup, click **Confirm** to turn on the object versioning.

![gcs_objectver_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-011fe036-081f-ff81-b926-9a6355b3412d.png)

![gcs_objectver_on.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c5bf4b8c-6f7b-ee92-c2bd-d29dec5c619c.png)

### Enabling soft deletion policy

To view the statistics for soft-deleted GCS files in Securiti's **Audit Trail**, you must enable the soft deletion feature in GCP. To enable soft-deletion:

> [!NOTE]
> **Important**
> 
> You must provide the **Monitoring Viewer** (`roles/monitoring.viewer`) role to view statistics for soft deleted and multipart uploads in IAM service account.

1. In [Google Cloud console](https://console.cloud.google.com/storage/browser), select your project.
2. Click on the bucket name to enable versioning for it.
3. In **Bucket details**, select the **Protection** tab.

![gcs_protectiontab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08a087d6-e76d-37ce-5eb0-8f93d029bc57.png)
4. In the **Soft delete policy (for data recovery)** section, click **Edit**.
5. On the **Set a soft delete policy** popup, specify the time to retain the objects after deletion such as, 7 days, as shown below.

![gcs_turnonsoftdelete.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aaae414d-bdae-303d-a551-e684c72102df.png)
6. Click **Save**.

Enabling the policy saves all the soft deleted objects.

![gcs_softdel_on.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0d2b5c2f-3ad6-e5f7-5309-d0bea20b8e85.png)

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
