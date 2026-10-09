---
title: "Configuring external storage providers"
slug: "configuring-external-storage-providers"
updated: 2026-06-10T07:08:49Z
published: 2026-06-10T07:08:49Z
canonical: "helpcenter.securiti.ai/configuring-external-storage-providers"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring external storage providers

**Scenario**

As a Data Governance Officer, you're responsible for ensuring GenAI outputs are stored securely and in the right locations. Without flexible storage options, teams risk scattering data or breaching policies. By configuring **external storage providers** such as, S3 or Azure, you define where outputs are saved. This allows you to align storage with governance rules, scale efficiently, and support cross-cloud environments.

On the **External Storage Providers** page, you can configure instances of external storage providers to be able to store outputs or content into a defined external storage. You can define multiple storage solutions for a provider.

To open the **External Storage Providers** page, go to **Settings>Integrations>External Storage Providers**.

### Prerequisites

To configure an external storage provider, you must have an active account on your external storage provider portal. To see the list of supported external storage providers, [Supported External Storage Providers](/v1/docs/configuring-external-storage-providers#supported-external-storage-providers).

In case of **Databricks**, see [**Configuring Gencore AI integration with Databricks vector search**](/latest/docs/configuring-external-storage-providers#configuring-gencore-ai-integration-with-databricks-vector-search).

> [!NOTE]
> **Important**
> 
> In case of Databricks, if you modify the Private Cloud Storage (PCS) from AWS to any other cloud, you may encounter an error.

### Adding an external storage provider

To add and configure an external storage provider:

1. On the top right of the page, click **+ Connect Provider**. The **External Storage Providers** popup displays.

![Interface displaying external storage providers with a button to connect a provider.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ESP-connectProvider.png)
2. In the **External Storage Providers** popup:
  1. Click on a provider to select it. You can also search for a specific provider.

![External_Storage_Providers_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-da60e58e-aaee-13e4-411d-8dbc32f920b3(1).png)
  2. On the **Add Instance** popup for the selected provider:
    1. Add **Instance Name**.
    2. Optionally add a **description**.

![AmazonS3-IT_add_instance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7b3efeb-b9f8-92e5-4023-bf02e78318b2(1).png)
  3. To save the details, click **Save & Continue**. Securiti displays the integration configuration popup for the created instance.
3. In the **Integration Configuration** popup, add the details relevant to the provider.
  1. Add details and credentials for the relevant cloud.
    - **Amazon S3**:
      - Authentication Type
      - Region & Session Details
      - Bucket and Access Information
    - **Databricks**: Cloud Access Credentials
    - **Google Cloud Storage**:
      - Cloud Details
      - Bucket Information
    - **Microsoft Azure**:
      - Cloud Details
      - Credentials
  2. In the **Owner Information**, specify the owners for the instance:
    1. Type owner details.
    2. Press **Enter**. The owners are added.

![Owner_info.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a988fb2f-a18c-861c-5b8d-ba5083fb4a6a(1).png)
  3. In the **Access Type**, select the instance as:
    - **Public**: Any user with external access can use this instance.
    - **Private**: Only owners with CRUD permissions can use this instance.

![ESP_Access_Type.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-501c83fc-5e86-50de-33ba-5c839c417818(1).png)
  4. To save the details, click **Authenticate & Activate Storage**.

When the external storage provider is configured, Securiti lists it.

### Managing external storage providers

To manage your external storage provider, on the selected instance, click the **Options** (three-dot) menu. You have two options:

- Edit: You can edit name, description, credentials and authentication information.
- Delete

![External storage providers list showing Amazon S3 and options to edit or delete.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ESP-Options.png)

- To edit the instance, click **Edit**.
- To delete the instance:
  1. Click **Delete**.
  2. To confirm instance deletion, click **Delete Instance**.

![Ext_Storage_Delete_Confirmation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5cddb4b0-2692-9f70-ef20-b4dd3ab86b1a(1).png)

> [!NOTE]
> **Note**
> 
> To gain insights on how you can build safe, enterprise-grade AI systems and AI agents using their proprietary data with Databricks, see [Accelerating Safe Enterprise AI with Gencore Sync & Databricks](/v1/docs/securiti-pods-and-elastic-pods).

### Configuring Gencore AI integration with Databricks vector search

To configure Databricks vector search, see the details below.

#### Prerequisites

You need the following before integrating Gencore AI with Databricks:

- **Private Cloud Storage**: Databricks requires AWS private cloud storage the AWS private cloud storage bucket. configured. PCS bucket should be accessible from databricks instance profile. The access needed on role assigned to databricks:

```plaintext
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::<pcs_bucket>"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:PutObject",
                "s3:GetObject",
                "s3:DeleteObject",
                "s3:PutObjectAcl"
            ],
            "Resource": [
                "arn:aws:s3:::<pcs_bucket>/*"
            ]
        }
    ]
}
```

- **Personal access token**: Create a **Personal Access Token** within Databricks.

> [!NOTE]
> **Important**
> 
> Token are per user and limited to a maximum of 730 Days. This integration to Databricks requires re-registration.
- **Configure External Storage Databricks**: Obtain the following details:
  - Obtain the database Instance URL from your Databricks workspace.
  - Obtain personal access token.
- **Configure Warehouse External Connection**: In your Databricks account, after account and workspace validation, copy S3 PCS Bucket Name.

![PCS bucket name](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PCS bucket name.png)
- Provision user ID/group credentials.
- Create external data.
- For **CloudFoundation**, create database resources and roles to **Private Cloud Storage Bucket - AWS**.
  - Add any additional tags required for your organization.
  - Create Stack.
  - Monitor cloud foundation template status until successful.
- Provision `Reader Role` to external data.
- Configure Gencore Pipeline Output Directory.

#### Provision user ID/Group credentials to create External Location

You need the CREATE EXTERNAL LOCATION privilege on the metastore to run this command.

1. Open SQL Editor.
2. Enter the following command:

`GRANT CREATE EXTERNAL LOCATION ON METASTORE TO &lt;your-user-or-group&gt;;`

> [!NOTE]
> **Important**
> 
> Contact your Databricks admin to grant you this privilege, or have a metastore admin execute the command for you.

#### Create External Data

To create external data, on Databricks account:

1. Navigate to **Workspace>Catalog>External Data**.

![Databricks interface showing the Catalog section and options for accessing external data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Databricks workspace create external.png)
2. Click **Create external location**.

![Databricks interface showing external data locations and options to create new locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create external location button HL.png)
3. Select **AWS Quickstart** and click **Next**.

![Creating a new external location in AWS with Quickstart and Manual options available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create new ext location - select.png)
4. Input `S3:/&lt;bucket name&gt;` from [Securiti.ai](http://Securiti.ai) PCS Bucket Name.

![Instructions for creating an external location in AWS with a bucket name.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create external - bucket name HL.png)
5. Generate token and secure it to be used.

![Instructions for creating an external location with AWS and generating a new token.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Create external - Personal access token HL.png)
6. Click **Launch in Quickstart**.

![Instructions for creating an external location with AWS, including bucket name and access token.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Launch in QS.png)

> [!NOTE]
> **Important**
> 
> Before launching in Quickstart, ensure your already logged into AWS. Failure to auth to AWS requires you to restart [Create External Data](/latest/docs/configuring-external-storage-providers#create-external-data) steps.

#### Provision Reader Role to External Data

To provision reader role to external data, in Databricks:

1. Copy your External Data/Connector Name from `https://&lt;tenant id&gt;.cloud.databricks.com/explore/locations`.
2. Open workspace.
3. Open SQL Editor.

Enter the following command:

`GRANT READ FILES `

` &nbsp;ON EXTERNAL LOCATION &lt;External Data / Name&gt;`

` &nbsp;TO &lt;your-user-or-group&gt;;`

#### Configure Gencore Pipeline Output Directory

In Databricks, to configure Gencore Pipeline Output Directory:

1. Log in to your Securiti tenant.
2. In your GenAI pipeline, select **Data Loader** or **Data Sanitizer**.
3. Select **Store Output** as Databricks.
4. Input the location using dot notation from your databricks catalog.

### Supported External Storage Providers

Gencore AI supports the following external storage providers:

- Amazon S3
- Databricks
- Google Cloud Platform
- Microsoft Azure

A provider of embeddings generator refers to a system or service that generates word or sentence embeddings.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Assistant API](/assistant-api.md)
