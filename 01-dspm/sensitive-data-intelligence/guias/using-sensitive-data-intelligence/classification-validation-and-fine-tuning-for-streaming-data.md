---
title: "Classification validation and fine tuning for streaming data"
slug: "classification-validation-and-fine-tuning-for-streaming-data"
updated: 2026-09-29T11:25:33Z
published: 2026-09-29T11:25:33Z
canonical: "helpcenter.securiti.ai/classification-validation-and-fine-tuning-for-streaming-data"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Classification validation and fine tuning for streaming data

If your discovery scan is for streaming data, use this article to review its classification results and fine-tune the scan if needed.

## Reviewing classification results

You can review classification results for streaming data from **Streaming Data Discovery** and **Scan Definitions** page.

### Streaming Data Discovery

To validate results from the **Streaming Data Discovery** dashboard, follow the steps below.

1. Open the **Data Systems** page and search for your data system, e.g., **Kafka**. Click **Topic Training** to identify if there is an exact match of your relevant data elements.
2. The **Topics** and **Field Name** entries contain the column names from your data system. The **Data Element Type** entries contain the training or classification results that Securiti identified.
3. To change the data element type, click the **Add Data Element Type** (plus icon) to choose the relevant data element from the list.

![tableTrainingNav2_0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0d8fde2-0132-203d-0c19-4ca350c655b0.png)

### Scan Definitions

To validate results from the **Scan Definitions** page, follow the steps below.

1. Under the Scan Definitions section, see details of your classification and discovery scan results. To review the classification evidence, log in to your data system's PCS to verify and compare the classification outcome with the source.
2. After you review the classification outcome from your data system console or cloud account, if you find any discrepancies in the identified data elements or content profiles, you can update or customize changes as described in [Fine-tuning classification and discovery scans](/latest/docs/classification-validation-and-fine-tuning-for-streaming-data#finetuning-the-discovery-scan).
3. Rescan your data after making the above changes.

## Fine-tuning the discovery scan

If review shows the scan needs adjustment, go back to its configuration and review **Data System Scope**, **Advanced Settings**, and **Sensitive Data**.

### Data system scope

To review and update the data system scope, follow the steps below:

1. Open your discovery scan.
2. Confirm you've selected the correct data system instance.
3. Review the Data System Scope to confirm the topics you've chosen are correct, as shown below.

![Configuration settings for Kafka connector, including topic specification options and regex patterns.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/datasystemscope_streamingdata.png)

### Advanced settings

To review and update the advanced settings, follow the steps below:

1. Confirm the sample size is appropriate. For more information, see [Discovery scans for streaming connectors](/latest/docs/discovery-scans-for-streaming-connectors).
2. To skip values such as Unknown, NA, Null, or Not Available, enable **Skip empty fields and fields below.**
3. Enable **Perform field classification on fields previously learned** and **Include newly discovered topics into the scan scope** to let Securiti include the previously scanned fields and retain the results of previous manual classification, as shown below.

![Settings for field classification including sampling options and data scanning preferences.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/advancedsettings_streamingdata.png)

### Sensitive data

To review and update the sensitive data settings, follow the steps below:

1. Review the data elements, content profiles, and exact data profiles selected.
2. Add or remove any as needed, including custom-created ones, as shown below.

![Interface displaying sensitive data categories and structured content profiles for data discovery.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sensitivedata_streamingdata.png)

> [!NOTE]
> Note
> 
> If a resource wasn't activated, open its configuration page and select it for this scan.
3. Rescan your data after making changes.

For more information, see [Fine-tuning classification resources](/latest/docs/fine-tuning-classification-resources).
