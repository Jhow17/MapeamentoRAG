---
title: "Frictionless Gencore AI Onboarding"
slug: "frictionless-gencore-ai-onboarding"
status: "update"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/frictionless-gencore-ai-onboarding"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Frictionless Gencore AI Onboarding

To onboard your Gencore AI account, after logging in your tenant:

1. [Create pipeline](/latest/docs/frictionless-gencore-ai-onboarding#create-genai-pipeline1).
2. [Configure data sources](/latest/docs/frictionless-gencore-ai-onboarding#configure-data-sources1).
3. [Configure LLM provider](/latest/docs/frictionless-gencore-ai-onboarding#configure-llm-provider1).
4. [Configure embedding provider](/latest/docs/frictionless-gencore-ai-onboarding#configure-embedding-provider1).
5. [Configure vector database provider](/latest/docs/frictionless-gencore-ai-onboarding#configure-vector-database-provider1).

## Create GenAI pipeline

When you log in to your tenant:

1. Click the **Gencore AI** tile. The **New GenAI Pipeline** popup displays.
2. Enter the pipeline **name**.
3. Optionally enter a **description**.
4. In **Set Up Data Source** or **Upload Files**, choose data to be ingested into your GenAI pipeline from the following sources:
  - **Connect Data Source**: Select to connect to a data system. When you select this, the **Connect Source Data Systems** popup displays where you can connect and authenticate source data systems.

> [!NOTE]
> Note
> 
> If you start with connecting a data source, you can also upload custom files later. For more information, see [Adding custom files](/latest/docs/adding-custom-files).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(124).png)
  - **Upload Files**: Select to upload custom files as your GenAI pipeline data source. When you select this option, the **Upload Files** node displays where you can upload your files.

> [!NOTE]
> **Tip**
> 
> You can choose to upload custom files to get started with your onboarding in case there is no data system to be set up as data source. Additionally, you can choose this option for a faster route to onboarding your tenant and testing purposes. If you start with custom files, you can also connect a data system later. For more information, see [**Data Loader node**](/latest/docs/data-loader).

![Name_and_Upload_Files_selected.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ef27dd8-1d70-51c9-85f5-d066347135c7(1).png)
5. Click **Save & Continue**.

> [!NOTE]
> **Note**
> 
> To use the Gencore AI module, it is mandatory to create at least one pipeline.

To create a pipeline using a template, press **(x)**. Securiti directs you to the **Templates** section. To continue creating the pipeline with a template:

1. Select a template.
2. The **Connect Source Data Systems** popup displays.

## Configure data sources

You can configure the data source in the following ways:

- Configure and authenticate source data systems
- Upload custom files as data source

### Connect and authenticate source data systems

Once the pipeline is created with the source selected as Data System, the **Connect Source Data Systems** popup displays.

![OB2-Add_DS_Azure_Files.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a70526f4-2d1e-47c1-c73c-275cd39d8b2b(1).png)

1. In the **Connect Source Data Systems** popup, select the data system to integrate with.

> [!NOTE]
> **Note**
> 
> To learn more about the supported data systems, see [Managing Data System Connectors](/latest/docs/managing-data-system-connectors).

When you click on a data system, the **Add Connector** Instance popup displays.

> [!NOTE]
> **Note**
> 
> Some information specific to the connector may be pre-populated.
2. In the **Add Connector Instance** popup:
  1. Add **Instance Name**.
  2. Optionally add a **Description**.
  3. Enter relevant credentials.
  4. Click **Save & Continue**.

![OB3-SDA_Azure.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-82933af4-3c62-b194-ef98-0f34d86aa321(1).png)

When you save the details:

> [!NOTE]
> **Note**
> 
> The data system connector must be authenticated for integration.
    - The added connector instance is listed in a grid on the right side panel. You can edit or delete an instance. To delete an added instance, it must be deactivated first.
    - The **Connector Configuration** popup displays. Here you can authenticate the data system connector.
3. In the **Connector Configuration** popup:

To dismiss the popup, click **(x)** or click **Dismiss**. To stop the authentication process, click **Cancel**. When the authentication is complete:

![Authentication in progress for connector configuration for Azure Files with authentication details displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Authentication in progress.png)

To check the details for the created pod, go to **System** **Settings>Deployment>Pods**.

To view the details for the authenticated data system, go to **System** **Settings>Integrations>Data Systems>Monitored.**
  1. Enter credentials and relevant information.
  2. To authenticate and activate the connector, click **Authenticate and Activate Connector**.

The popup displays a message informing the user of the relevant stage i.e. either the authentication is in progress or the authentication is complete.

![Connector configuration for Azure Files, requiring authentication details and activation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Connector config.png)

> [!NOTE]
> **Note**
> 
> When you click **Authenticate and Activate Connector**:
> 
> - If you have an existing pod, the authentication and activation takes place.
> - If you do not have an existing pod:
>   - The pod creation starts.
>   - After the pod is created, the authentication and activation takes place.
> 
> To learn more about Pods, see [Securiti pods and elastic pods](/latest/docs/securiti-pods-and-elastic-pods).
> 
> For information on pod installation for HPE Private Cloud AI (HPE PCAI), please see [Securiti POD installation for HPE Private Cloud AI (HPE PCAI)](/latest/docs/securiti-pod-installation-for-hpe-private-cloud-ai-hpe-pcai).
  3. To reconfigure the data system, click **Reconfigure**.
  - The relevant message displays on the popup.
  - The status of the instance changes to **Active.**
  - The pipeline nodes are enabled.
4. To proceed to the next step, click **Continue**. The **Connect LLM Providers** node displays to configure LLM provider.

### Upload custom files

Once the pipeline is created with source selected as custom files, the **Upload Files** node displays.

![Onboarding interface showing file upload options and supported formats for users.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FO-UploadFiles.png)

1. In the **Upload Files** node, you can upload your file as follows:
  - Drag and drop your file in the node.
  - Click **Choose Files** and upload your file.

![Interface for uploading files with options for connecting various providers and data storage.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UploadFiles-ChooseFiles.png)
2. To save the changes, click **Continue**. The Connect LLM Provider node displays to configure LLM provider.

## Configure LLM provider

To configure the LLM provider, in the **Connect LLM Provider** node:

1. Select the provider and model.
2. To connect your LLM model:
  1. To add a new instance, click **Add credentials**. Securiti directs you to the relevant credentials page for the selected provider and model.
  2. To add another instance, click **Add New**. Securiti directs you to the relevant credentials page for the selected provider and model.

![Frictionless Onboarding - Add new LLM providers](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/OB-LLM-AddNew.png)
3. [Configure the LLM provider](/v1/docs/configuring-llm-providers).
4. Save the changes.
5. Once you configure the LLM provider, click **Continue**. The **Connect Embedding Providers** popup displays to configure embedding generating providers.

## Configure embedding provider

To configure the embedding provider:

1. Select the provider and model.
2. To connect your embedding model:
  1. To add a new instance, click **Add credentials**. Securiti directs you to the relevant credentials page for the selected provider and model.
  2. To add another instance, click **Add New**. Securiti directs you to the relevant credentials page for the selected provider and model.

![Connecting embedding providers with options for various AI services and credentials.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/OB-EP-AddNew(1).png)
3. [Configure the Embedding provider](/latest/docs/configuring-llm-providers).
4. Save the changes.
5. Once you configure the Embedding provider, click **Continue**. The **Connect Destination Vector Storage** popup displays to configure vector storage providers.

### Configure vector database provider

To configure the Vector Database provider:

1. Select the Vector Database provider.
  1. To add a new instance, click **Add credentials**. Securiti directs you to the relevant credentials page for the selected provider.
  2. To add another instance, click **Add New**. Securiti directs you to the relevant credentials page for the selected provider.
2. [​​Configure the Vector Storage provider​​](/latest/docs/configuring-vector-storage-providers).
3. Save the changes.
4. Once you configure the Vector database provider, click **Continue**. The **Data Loader** node popup displays. ![Connecting to Milvus vector storage with options for adding new credentials.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DVS-Add New.png)

When the onboarding is complete, the onboarding grid collapses and the **Onboarding Complete** badge displays in the left panel.

To complete the pipeline creation, see [Creating a new pipeline > Data Loader](/latest/docs/data-loader).

To create another pipeline once one pipeline is configured, see [Creating a new pipeline](/latest/docs/creating-a-new-pipeline).

## Related

- [Gencore AI onboarding](/gencore-ai-onboarding.md)
- [Regular Gencore AI Onboarding](/regular-gencore-ai-onboarding.md)
