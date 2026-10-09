---
title: "Configuring Store Output"
slug: "configuring-store-output"
updated: 2026-07-06T06:05:56Z
published: 2026-07-06T06:05:56Z
canonical: "helpcenter.securiti.ai/configuring-store-output"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring Store Output

Sn this section, you can enable the toggle if you want to store the file outputs external to a Vector database. To use this functionality, you must have at least one type of storage configured:

- Private Cloud Storage (PCS)
- External storage

> [!NOTE]
> Note
> 
> Securiti generates file output in the following formats:
> 
> - For files with the extension CSV, JSON, NDJSON, XML, and Plain Text, Securiti generates the output file in the same format.
> - For PDF, XLSX, and other non-text formats, Securiti generates the output file as a .txt file.

#### Using Private Cloud Storage

Make sure that your Private Cloud Storage is configured, If it is not configured, see [Configuring Private Cloud Storage](/v1/docs/system-settings-configuring-private-cloud-storage).

To add a Private Cloud Storage:

1. Click **Add**.

![PCS_-_none_selected_-_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-09c4f7b5-aae0-dc21-d3d1-274978dbeb63(1).png)
2. Select the configured instance.

![Store_output_instance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2196dc61-9162-794b-642c-e8d909f843c1(1).png)
3. Add path to a specified location.

![PCS_-_Selected_3_-_DL_Labelled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c54c763d-6a9e-c1d2-0e98-b78ce2d6b1e5(1).png)
4. Save the changes.

#### Using External Storage

If Private Cloud Storage is not configured, when you enable Store Output, it displays an option to configure external storage.

![Ext_Storage_Config_Only_-_DL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fbdf6a96-2239-e71f-780e-312119bd4c04(1).png)

> [!NOTE]
> **Note**
> 
> To configure external storage providers, see [Configuring external storage providers](/v1/docs/configuring-external-storage-providers).

If your external cloud storage is configured:

1. Click **Add**.
2. Select the external storage provider instance.

> [!NOTE]
> **Note**
> 
> You can also add External Storage by clicking **Manage**.
3. Save the changes.

A database for the storage, retrieval, and management of vector data or embeddings. A vector database stores vector embeddings, which are numeric lists that represent text, images, or other content. In GenAI pipelines, embeddings are generated from custom files or from data pulled from a datasource. The vector database then indexes these embeddings so the pipeline can perform fast and accurate similarity searches.
