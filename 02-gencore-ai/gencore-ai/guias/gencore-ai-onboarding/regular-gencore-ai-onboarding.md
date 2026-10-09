---
title: "Regular Gencore AI Onboarding"
slug: "regular-gencore-ai-onboarding"
updated: 2025-12-05T05:06:21Z
published: 2025-12-05T05:06:21Z
canonical: "helpcenter.securiti.ai/regular-gencore-ai-onboarding"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Regular Gencore AI Onboarding

For regular Gencore AI onboarding, you can onboard with a new or pre-configured tenant.

### Onboarding a new tenant

To onboard a new tenant, you can configure data sources and, optionally, deploy on elastic pods.

1. Enter your credentials and log in.
2. Click the Gencore AI tile. The **Welcome** screen for **Gencore AI Onboarding** displays.
3. Click **Continue**. The **Add a Compute Pod** section displays.
4. To add a new computing pod, click **Add Compute Pod**. A curl command displays.
5. Copy the curl command and secure it.
6. To deploy the new pod on your compute instance, execute the CURL command in the relevant terminal window.
7. Once the pod has been successfully deployed and is running, click **Next**.

> [!NOTE]
> **Note**
> 
> You must configure at least one pod to proceed to the next step.
8. Click **Continue** to connect to data systems. The **Connect to Data System** UI displays.
9. To enable a data system, select the corresponding data system and the UI is redirected to the **Data System** listing page for creating and authentication of a new Data system instance.

> [!NOTE]
> **Note**
> 
> You must connect at least one data system to proceed to the next step.
10. To configure a new data system:
  1. Search for and locate the corresponding data system in the list that you want to configure.
  2. To the right of the card, click **Connect**. Securiti redirects you to the created instance of the selected data system:

> [!NOTE]
> **Note**
> 
> You can choose to configure more data systems, or continue to set up AI Models.
    1. Provide the instance related information for your data system.
    2. When you are satisfied with the provided details, click **Create Instance & Continue**.

Once you configure a data system, the text Instance along with the count of the instances display with the data system name.
11. Click **Continue** to configure the model. The **Configure Model Credentials** UI displays.
12. To add a provider:
  1. Click **+ Add Credentials**.
  2. Select a **model**.

> [!NOTE]
> **Note**
> 
> By default, both embedding models and LLMs are displayed. To display embedding models or LLMs:
> 
> 1. Click **Model Type** dropdown.
> 2. Select model type.
13. To configure the model, click **Add Credentials**.
14. Add the required details.
15. To save the changes, click **Save Credentials**. Once the model is saved successfully, the model is listed.
16. Click **Continue** to configure your vector storage. The **Configure Vector Storage Credentials** UI displays.
17. To add a vector storage provider:
  1. Click **+ Add Credentials**.
  2. Select a vector database.
  3. To configure the database, click **Add Credentials**.
  4. Add the required details.
  5. To save the changes, click **Save Credentials**. The vector database is listed.
18. When you are satisfied with the provided details, click **Complete Onboarding**.

### Onboarding on a preconfigured tenant

You can configure additional data sources to existing preconfigured tenants.

1. Enter your credentials and log in.
2. Click the **Gencore AI** tile. The **GenAI Pipelines** UI displays.
3. To add more data sources, click **Gencore AI Onboarding** in the left navigation bar.

The Welcome screen for the Gencore AI Onboarding displays.

![reg_onboarding_welcome_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1c3494fb-e0bd-09b9-e0b4-24b8868ed919(1).png)
4. To proceed with the onboarding process, click **Continue**. The **Add a Compute Pod** section displays.

![Reg_onboarding_add_pod_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0d3e47c1-abfa-37b6-c602-0e1ab75dc944(1).png)
5. To add a new computing pod, click **Add Compute Pod**. A curl command displays.
6. Copy the curl command and secure it.
7. To deploy the new pod on your compute instance, execute the CURL command in the relevant terminal window.
8. Once the pod has been successfully deployed and is running, click **Next**.

> [!NOTE]
> **Note**
> 
> At least one pod must be configured to proceed to the next step.
9. Click **Continue** to connect to data systems. The **Connect to Data System** UI displays.

![reg_onboarding_connect_ds_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e46c82bd-dbd2-4011-093b-bc47ed4c5baf(1).png)
10. You can add connections to data systems. To enable a data system, select the corresponding Data system and the UI is redirected to the **Data System** listing page for creating and authentication of a new Data system instance.

> [!NOTE]
> **Note**
> 
> You must connect to at least one pod to proceed to the next step.
11. To configure a new data system:
  1. Search for and locate the corresponding data system in the list that you want to configure.
  2. To the right of the card, click **Connect**. It will redirect you to the create instance of the selected data system:

> [!NOTE]
> **Note**
> 
> You can choose to configure more data systems, or continue to set up AI Models.
    1. Provide the instance related information for your data system.
    2. When you are satisfied with the provided details, click **Create Instance & Continue**.

Once a data system is configured, the text Instance along with the count of the instances display with the data system name.
12. Click **Continue** to configure the model. The **Configure Model Credentials** UI displays the following information:
  - A widget displays the number of providers.
  - The configured model displays with the relevant information.
  - In case of multiple models, you can sort the list of models.

![reg_onboarding_cong_model_creds_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9e3e9593-878c-4743-5706-17d6b2bd5921(1).png)
13. To add a new model provider:
  1. Click **+ Add Credentials**.
  2. Select a model.
  3. To configure the model, click **Add Credentials**.
  4. Add the required details.
  5. To save the changes, click **Save Credentials**. Once the model is saved successfully, the model is listed.

> [!NOTE]
> **Note**
> 
> You can add more providers through the Genstack **Settings** **>LLM Providers** section.
14. To configure an existing model:
  1. Select the **Model**. You can also search for a specific model.
  2. Click **Add Credentials** in the model layout. The **Add Provider Credentials** UI displays.
  3. Add relevant credentials.
  4. To save the details, click **Save Credentials**.
15. You can manage a model as follows:
  - To disable the model, click **Status**. Models are enabled by default.
  - To edit the model details, select **Options** (three dots) and choose **Edit**.
  - To delete the model, select **Options** (three dots) and choose **Delete**.
16. Click **Continue** to configure your vector storage. The **Configure Vector Storage Credentials** UI displays the following information:
  - A widget displays the number of providers.
  - The configured vector database(s) display(s) the relevant information.
  - If multiple database providers are added, you can sort the list of vector databases.

![reg_onboarding_vector_store_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9ef46b59-dfb1-45f4-fb36-eb087f861d9c(1).png)
17. To add a vector database provider:
  1. Click **+ Add Credentials**.
  2. Select a vector database.
  3. To configure the model, click **Add Credentials**.
  4. Add the required details.
  5. To save the changes, click **Save Credentials**. The vector database is listed.
18. To configure an existing vector storage:
  1. Select the **Vector database**. You can also search for a specific vector database.
  2. Click **Add Credentials** in the Vector database layout. The **Add Vector Storage Credentials** UI displays.
  3. Add relevant credentials.
  4. To save the details, click **Save Credentials**.
19. When you are satisfied with the provided details, click **Complete Onboarding**.

The underlying machine learning or deep learning architecture responsible for creating embeddings. The model is trained on large datasets to learn the relationships and representations of words or sentences in a continuous vector space.

A mathematical representation of a quantity with both magnitude and direction. Vectors serve several purposes, including data representation, model parameters, and calculations.

A provider of embeddings generator refers to a system or service that generates word or sentence embeddings.

## Related

- [Gencore AI onboarding](/gencore-ai-onboarding.md)
- [Frictionless Gencore AI Onboarding](/frictionless-gencore-ai-onboarding.md)
