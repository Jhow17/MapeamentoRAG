---
title: "Vertex AI vector store set up"
slug: "vertex-ai-vector-store-set-up"
updated: 2025-12-15T02:31:40Z
published: 2025-12-17T22:00:02Z
canonical: "helpcenter.securiti.ai/vertex-ai-vector-store-set-up"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Vertex AI vector store set up

You can set up Vertex AI vector store as per the guidelines below.

> [!NOTE]
> **Note**
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

### Prerequisites:

To set up a GCP Vertex AI vector store on GCP for use in a GenAI pipeline, you must have:

- Set up a GCP Project and Billing Account
- Enable the Vertex AI API
- Authenticate via Service Accsount Creation

### Setting up a GCP project and billing account

To learn how to set up the GCP project and billing account, follow the instructions on: [Get set up on Google Cloud - Vertex AI](https://cloud.google.com/vertex-ai/docs/start/cloud-environment).

### Authenticating via Service Account Creation

Gencore AI requires a GCP Service Account to authenticate.

1. Open the **GCP Console**. Select your desired project.
2. On the left pane, select **APIs and Services > Credentials**.

![GCP_APIs_and_Services_-_Credentials_labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-658c9a50-2c59-84dc-5991-a66400265cc1(1).png)
3. Click **Create Credentials**, then select **Service account**.
4. Configure your service account:
  1. **Service Account details**: Enter any account name, ID and description of your choice.
  2. Grant suitable **Role Permissions**.

> [!NOTE]
> **Note**
> 
> For the purpose of this tutorial, the service account will be given full permissions as an owner. No IAM conditions are created to give unconditional permissions.
  3. Grant Users access to this service account: Enter your GCP email for users.Your created Service account displays on the Credentials page under the Service Accounts heading.
5. Click on your service account, then navigate to the **Keys** tab.
6. Click **Add Key > Create new key**.
7. Select the **JSON Key type** and click **Create**.

The private key downloads in a JSON format. Secure this file safely as it must be updated in Gencore AI.

### Defining the GCP Setup

To set up the GCP:

- Create a bucket
- Select embeddings model
- Create and deploy index

#### Creating a bucket

To create a Bucket that will be the underlying store for your database::

1. Navigate to the [GCP Cloud Storage page](/v1/docs/securiti-pods-and-elastic-pods). Click on the **Buckets** tab on the left.
2. Click **Create**.
3. Follow the on screen steps to configure your bucket.
4. Select a single region for your bucket.

> [!NOTE]
> **Note**
> 
> Multi- and Dual-region buckets are not yet supported.
5. Secure the details for Bucket Name and its region (e.g. us-west1) as you must provide these on the Gencore AI platform.

> [!NOTE]
> **Note**
> 
> Gencore AI requires a new, empty bucket. Do not utilize a pre-existing bucket for your index, and do not use this bucket for any other purposes (a separate index, a separate GenCore pipeline, etc.).
  - You can view the list of your bucket names and their hosted regions [here](/v1/docs/securiti-pods-and-elastic-pods).
  - Do not prefix the bucket name with “gs://”.

Do not edit this bucket manually. Instead use the GenAI Pipeline controls to manage your bucket.

#### Selecting embeddings model

Before creating an index, select your embeddings model as the index you create takes the dimensions as a parameter. Once you have selected an embeddings model on the Gencore UI, take note of the dimensions of your embeddings.

To select your embedding model, refer to Gencore AI's Model Cards, or create a sample embedding.

> [!NOTE]
> **Note**
> 
> Secure the details of the Embeddings Dimensions, as you will need this information when creating an Index.

#### Creating an index

Create an Index by following Google’s guide [here](https://cloud.google.com/vertex-ai/docs/vector-search/create-manage-index#create_index-console).

> [!NOTE]
> **Note**
> 
> GCP offers two types of indexes:
> 
> - Batch Update Indexes
> 
> Streaming Update Indexes.
> 
> Only Batch Update indexes are supported in a GenAI Pipeline.

You can view your created indexes [here](https://console.cloud.google.com/vertex-ai/matching-engine/indexes?_ga=2.53300271.664955154.1711651965-712661386.1710440671&amp;_gac=1.20912458.1711665257.Cj0KCQjwqpSwBhClARIsADlZ_Tm6lQxOqJGJAr_KSX81GYZuckHoV70sRmf1To2jTpFqScfUNFaF9L0aAnoMEALw_wcB&amp;project=securiti-genstack-dev). Each index has both a ‘name’ (also referred to as a display name) and an ‘ID’. Secure your Index ID from the ID column as you must provide it in Gencore AI.

#### Deploying index

Deploy Index by following Google’s guide [here](https://cloud.google.com/vertex-ai/docs/vector-search/deploy-index-vpc). The created index must now be deployed to an endpoint (either public or private).

To choose between a public or private endpoint, refer to the description [here](https://cloud.google.com/vertex-ai/docs/vector-search/setup/setup#choose-endpoint).

- To deploy to a public endpoint, follow these [steps](https://cloud.google.com/vertex-ai/docs/vector-search/deploy-index-public).
- To deploy to a private endpoint in a VPC network, follow these [steps](https://cloud.google.com/vertex-ai/docs/vector-search/deploy-index-vpc).

**Endpoint ID**:You can view a list of your created endpoints [here](https://console.cloud.google.com/vertex-ai/matching-engine/index-endpoints). Secure your Endpoint ID from the ID column as you must provide it in Gencore AI.

**Deployed Index ID**: Your Endpoints are displayed on the GCP Console [here](https://console.cloud.google.com/vertex-ai/matching-engine/index-endpoints).

- To view the Index ID, click on your deployed Index.

Secure your Deployed Index ID as you must provide it in Gencore AI.

### Providing details on Gencore AI

To provide details on Gencore AI :

- Create credentials.
- Enter information on Gencore AI.

#### Creating credentials

1. Navigate to the Gencore AI Credentials Page for Vector Stores.
2. Select “Vertex AI” as your provider.

#### Entering information in Gencore AI

1. In **Add Vector Storage Credentials**, add required parameters secured during the earlier steps.

![Add_Vector_Storage_credentials.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-268acfd6-47c8-83ec-50d2-73a7d5da649e(1).png)
  1. Enter the **Name** for the set of credentials.
  2. Provide the **Project ID**.
  3. Provide the **Region** for your bucket resource.
  4. Provide the **Bucket** detail.
  5. Provide the **Index ID**.
  6. Provide the **Index Endpoint ID**.
  7. Provide the **Deployed Index ID**.
  8. Provide the detail for the **Update Method** as “batch”.
  9. In **Service Account Credentials JSON**, upload the download Private Key.
2. Save details.

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

The underlying machine learning or deep learning architecture responsible for creating embeddings. The model is trained on large datasets to learn the relationships and representations of words or sentences in a continuous vector space.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

An endpoint is a specific URL or URI (Uniform Resource Identifier) that an API exposes for communication.

A mathematical representation of a quantity with both magnitude and direction. Vectors serve several purposes, including data representation, model parameters, and calculations.

## Related

- [Configuring vector storage providers](/configuring-vector-storage-providers.md)
- [Vector Database](/vector-database.md)
