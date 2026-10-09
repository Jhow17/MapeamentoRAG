---
title: "Data Sanitizer"
slug: "data-sanitizer"
updated: 2026-07-20T21:00:00Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/data-sanitizer"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Data Sanitizer

The Data Sanitizer stage lets you configure masking or redaction conditions to apply to the data loader. During this stage the data loaded is scanned and classified to extract context to be used in the conditions defined.

For the ingested data, you can ensure that data supplied does not contain sensitive information that may be unwantedly retrieved and used in a response by the LLM.The Data Sanitizer stage lets you configure masking or redaction conditions to apply to the data. During this stage the data loaded is scanned and classified to extract context to be used in the conditions defined.

Some of the challenges Securiti’s Gencore AI addresses for data sanitization include:

- **Familiarity with datasets**: When working with well-known or semi-structured datasets, data scientists or users can handle data preparation and cleaning. However, this process becomes challenging when there is limited familiarity with the dataset.
- **Data volumes**: For smaller data volumes, such as a few PDFs, both technical and non-technical resources can review and verify sensitive data remediation. At larger scales, however, it may be difficult to confirm that all or specific sets of sensitive data have been properly remediated.
- **Data Access Rights**: In highly secure environments, engineers may have read access to source data but lack an intermediate location to store and redact it. This limitation increases the likelihood of shadow activities where unsanitized data is directly fed into pipelines.

## Prerequisites

- [Data loader](/latest/docs/data-loader) node is configured and data is ingested.

> [!WARNING]
> Important
> 
> For output generation, Securiti supports file sizes up to **5 MB** per file. If a file exceeds this limit, the pipeline does not generate an output file.

## Adding a masking condition

To add a masking condition:

1. Click **Add** (+) to enable the **Data Sanitizer** node.
2. Click **+ Add a masking condition**. The pipeline wizard opens a popup for adding a mask condition.

![Data Sanitizer interface showing options for masking conditions and storing output settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data Sanitizer - Masking Condition Add.png)
3. Enter the **condition name**.

![Masking condition name](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Sanitization Masking name.png)
4. To create the scope for the condition, under Evaluate Expression:
  1. Click **Add** [+]. The pipeline wizard opens the **Add a Masking Condition** popup.

![Add masking behaviour](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/masking behaviour - add.png)
  2. Select **Entity**.

![Select entity in masking](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select entity.png)
  3. To add a property, click **Options (three-dot menu)**.

![Add property in masking expression](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Add property.png)
  4. Select **property**.

![Select property in masking expression](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select property.png)
  5. Select personal data elements. You can select both system and custom data elements.

> [!NOTE]
> Note
> 
> When selecting personal data elements for masking, please note the following:
> 
> - If only system-defined personal data elements are selected, Securiti applies the corresponding masking rules based on the selected personal data elements or their combination.
> - If only custom personal data elements are selected, Securiti applies generic masking only.
> - If both system-defined and custom personal data elements are selected, Securiti applies generic masking only.

![Select data elements in masking expression](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Select data elements.png)
  6. To save the expression, click **Apply**. You can remove the expression by clicking **Clear**.

![Masking expression](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Expression.png)

> [!NOTE]
> **Note**
> 
> To understand how to create an expression, see the [Graph Explorer docs](/latest/docs/using-graph-explorer).

When you create an expression, you have the option to view the JSON code.
    - To copy this JSON code, click **Copy** (clipboard icon).
    - To download the JSON code, click **Download** (downward arrow).
    - To view information about the JSON code, click **Help**.
    - To close the JSON code, click **X** (close).

![Masking expression - JSON](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/masking - json.png)
5. Select the masking function. These are based on standard ways to mask data (letters, numbers or both) based on its classification. For example, if the personal data element contains letters e.g. First Name or Last Name, the masking options include an option for masking all letters. However, if the personal data element contains numbers e.g. Credit card, the masking options include an option for masking all digits.

![Options for masking sensitive data in a user interface with various functions listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Masking - All list.png)

The Input/output Examples section displays examples for the masked data.

![Masking behavior settings for sensitive data with examples of input and output.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Masking - Mask with rand alphanum.png)
6. When you have provided the details for the masking function, click **Save**. You can add multiple masking conditions.

> [!WARNING]
> Important
> 
> You can use a personal data element in only one masking condition. Once selected in a masking condition, you cannot select it in any other masking condition. For different personal data elements, you can create separate masking conditions within the same pipeline. For example, configure one masking condition to apply partial masking to email addresses and another to apply generic full masking to a custom personal data element.
7. To select **Store Output**, click the toggle. See [how to configure Store Output](/latest/docs/configuring-store-output).

![Store_output_disabled.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a3821fd-5dc2-7024-5363-96bfe44293ea(3).png)
8. When you are satisfied with the provided details, click **Save and Continue** to proceed to the **Embeddings Generator** stage.

## Managing masking conditions

You can manage your masking conditions as follows.

- To disable or enable a masking condition, click the toggle with the masking condition.

![Data sanitizer - masking added](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Data Sanitizer - mask added - status toggle.png)
- To edit or delete, click the **Options** (three-dot menu) to the right of the masking condition and choose any of the following options:
  - **Edit**: Edit the masking condition.
  - **Delete**: Delete the masking condition.

## Testing ingested data in Data Sanitizer

To make sure that the data source is configured and sensitive content is not exposed at the output, you can test the nodes after configurations.

In this case, it is mandatory to select and [configure Store Output](/latest/docs/configuring-store-output).

> [!NOTE]
> **Note**
> 
> The embedding generator and vector database nodes must be disabled.

1. When you are satisfied with the provided details in the Data Sanitizer node, click **Save and Continue**. Securiti enables the **Run** button.
2. Click **Run** to check if the files are being retrieved properly with the masking conditions applied to it.

Embeddings are numerical representations of objects (such as words, sentences, or documents) in a continuous vector space, and they are often used to capture semantic relationships and context.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Data Loader](/data-loader.md)
