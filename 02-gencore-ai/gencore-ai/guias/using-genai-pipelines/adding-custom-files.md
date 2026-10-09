---
title: "Adding custom files"
slug: "adding-custom-files"
updated: 2026-08-10T15:08:56Z
published: 2026-08-10T15:08:56Z
canonical: "helpcenter.securiti.ai/adding-custom-files"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Adding custom files

Gencore AI lets you upload specific, local files (e.g., a spreadsheet) that you need to be processed immediately by a pipeline. The data is ingested and processed by the pipeline's configured nodes (Sanitization, Vectorization, etc.) alongside data from existing connectors.

You can choose to upload custom files in cases where there is no data system to be set up as data source. Additionally, you can choose this option for a faster route to onboarding your tenant and testing purposes.

> [!NOTE]
> Important
> 
> This feature is for pipeline data processing and analysis and is not used to train or fine-tune LLM models. Securiti stores custom files in the configured Private Cloud Storage (PCS).

​

To upload custom files:

1. In the **Custom Files** section, click the **Custom files** toggle to activate it. or more detail, see Adding custom files.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(256).png)

> [!NOTE]
> Note
> 
> A custom file is a user-provided file containing specific data for targeted analysis or processing.

Securiti displays the **Custom files** section.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(257).png)
2. In **Select Pod**, select from an existing list of pods. To add a pod, click **Add Pod**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(234).png)

1. Upload the custom file:

- Drag-and-drop to upload file.
- Click **Choose Files** to upload the required file.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(235).png)

You can upload multiple files. If any error occures during upload, Securiti displays a relevant error message. To learn how to upload custom files through API, see [Data ingestion through API](/latest/docs/data-loader#data-ingestion-through-api).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(236).png)

To view details about an error, click the **information** icon.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(237).png)

To manage the custom files:

- To retry uploading a file, click the **Retry** icon.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(238).png)
- To retry uploading all failed files, click **Retry All**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(239).png)
- To filter and view only files with errors, enable the **Contain Errors** toggle.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(240).png)
- To remove a file with errors, click the **delete** (×) icon next to the file.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(241).png)

- To delete an uploaded file, click the **delete** icon.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(242).png)

To confirm deletion, click **Delete File** in the confirmation popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(243).png)

- To remove a file with errors, click the **delete** (×) icon next to the file.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-W50L6BP0.png)
