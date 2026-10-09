---
title: "Customizing system data element types"
slug: "data-elements-customizing-system-data-element-types"
status: "update"
updated: 2026-08-12T15:47:14Z
published: 2026-08-12T15:47:17Z
canonical: "helpcenter.securiti.ai/data-elements-customizing-system-data-element-types"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Customizing system data element types

Securiti provides a highly-curated set of system data element types that help to detect sensitive information like social security numbers, credit card numbers, or bank account numbers. These detectors help it identify sensitive or personal items that are under your organization’s control. However, the efficacy of the system data element types is dependent on your dataset as much as the data elements' default settings in our data classification system. In some cases, you might need to fine-tune our system data element type detectors so that they can meet your classification needs. For instance, if you have a large number of 9-digit contract numbers of the form ddd-dd-dddd, you might have to tweak the built-in SSN data element type to avoid false positives.

### Viewing data element types and supported languages, and localities

This section lists the active and inactive data elements existing for your tenant.

Under the **Tenant Entitlements**, you can see a list of supported localities and languages for data element classification.

![List of active localities and languages for tenant entitlements in a data management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 11.05.54 PM.png)

Next is the row of widgets that shows the counts of total and active data element categories and data elements.

![Overview of tenant entitlements, including localities and active data element categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.33.02 PM.png)

To view the list of supported localities and languages, see [List of supported localities and languages for data classification](/v1/docs/data-classifications).

To view the details of data element types:

In Securiti, open Sensitive Data Intelligence, and choose **Data Classification** > **Data Elements**.

Securiti opens the **Data Elements** page, as shown below.

![Overview of data elements and categories in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 11.14.25 PM.png)

> [!CAUTION]
> Warning
> 
> The character limit for naming classification resources and their categories is 50 characters. If a name exceeds this limit,​ Securiti shows an error message. Existing names remain unchanged.

To customize a system data element:

1. From the main menu, choose Sensitive Data Intelligence > Data Classification > **Data Elements**.

![Securiti dashboard showing sensitive data intelligence and data classification options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.33.42 PM.png)

This opens the **Data Elements** page as shown below:

![Overview of data elements and categories in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 11.14.25 PM(1).png)
2. On the **Data Elements** page, from the upper right side of the page, click the filter panel and choose the **Customizable Data Elements** to identify which system data element types are customizable, as shown below.

![Overview of data elements and categories in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.34.25 PM.png)
3. On the **Data Element Detail** panel that slides in from the right, click **Edit** (pencil icon) near the upper right corner of the panel.

![Overview of data elements and categories in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.35.46 PM.png)

> [!NOTE]
> **Note**
> 
> You cannot modify the **General Information** except the **Exclude from evidence collection** toggle.
4. Some data elements might contain sensitive information that you don't want to be identified in evidence collection, for example, falling under the financial or authentication category.

(Optional) To explicitly exclude this data element from being collected in the evidence, enable the **Exclude from evidence collection** option.

![excludeEvidenceoptionSystemDE.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b356eee1-b576-0237-4308-186e01d51b05(1).png)

> [!NOTE]
> **Note**
> 
> This option applies to all future scans. The scan jobs in progress or scheduled do not have any impact.
5. To see the languages and localities enabled for this data element detection, expand the **Scope** section.

![systemDEScope.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-703595a8-e01f-866f-f7e5-9b94e1bce128(1).png)
6. To view People Data Graph settings for **Uniqueness** and **Identifiability**, expand the **People Data Graph** section.

![PDG_SystemDE.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0c49239f-a077-570d-6984-b6cc160a9775(1).png)
7. Scroll down to the **Definition** area.

With the exception of the Active flag under the **General Information** area, none of the fields on any of the other tabs are editable.
8. In the **Definition** area, apply the following settings, then click **Save**.

| **Structured Classification** Securiti fuses signals from a table's header and content to classify columns of data. These settings help guide the AI that performs this fusion. |
| --- |
| Positive Table Header Terms | (Optional) Use the tools to enable and construct a list of terms that, when present in a column header, indicate that the column may contain the data element type. Securiti searches for these terms in headers, both as exact and nearly-exact substrings, using some natural language processing to prevent false positives. We recommend that you use substrings that are expected to be strongly associated with columns of this type. You can specify different sets of terms for different languages; this benefits some of the language-dependent processing used to assess headers. However, Securiti processes all languages enabled for your Securiti tenant. To reset the positive table header terms to default, click the **Reset to Default** button. |
| Negative Table Header Terms | (Optional) Use the tools to enable and construct a list of terms that, when present in a column header, indicate that the column does not contain the data element type. Securiti searches headers for these terms as case-insensitive substrings. To reset the negative table header terms to default, click the **Reset to Default** button. |
| Header and Content Confidence Threshold Settings | Securiti evaluates the Header Confidence Threshold and Content Confidence Threshold settings together to determine whether a database column contains sensitive data and determines the classification accuracy. Although Header and Content Confidence can be configured separately, they do not operate in isolation. - Header (column name) Confidence: How strongly the column name must resemble known keywords. - Content (column values) Confidence: How strongly the actual data values in the column must resemble the expected data type. Both settings have five levels each, ranging from Very High to Very Low. - A **Very High** threshold means the column name must almost exactly match a keyword. - A **High** threshold means the column name must closely match a keyword, with only small variations allowed. - A **Medium** threshold means the column name should have a noticeable resemblance to keywords, though minor differences are acceptable. - A **Low** threshold means the column name can be somewhat different from keywords, but should share some similarity. - A **Very Low** threshold means the column name can differ significantly from known keywords. To reset the **Header Confidence Threshold** to default, click the ​**Reset to Default​​** button. Content Confidence affects how strongly the actual data must resemble the target data type. - A **Very High** threshold means nearly all values must match the expected type. - A **High** threshold means most values must strongly resemble the expected type, with rare mismatches - A **Medium** threshold means a majority of values should fit the expected type, though some variation is acceptable. - A **Low** threshold means a noticeable portion of values should match the expected type, but exceptions are allowed. - A **Very Low** threshold means a small portion of values need to resemble the expected data type. To reset the **Content Confidence Threshold** to default, click the ​**Reset to Default​​** button. By adjusting **Header Confidence** **Threshold** and **Content Confidence Threshold**, you can achieve a balance between: - **Strictness** (avoiding false positives): set both confidences to **High** or **Very High**. - **Flexibility** (catching subtle cases): set one or both confidences to **Low** or **Very Low**. |
| Perform only column header classification | > [!NOTE] > **Note** > > This option applies only to structured data systems. Mark the **Perform only column header classification** checkbox to enable header-only classification for custom elements based on the defined regex. Enabling this option lets Securiti perform the header-only classification for columns with no or limited data. |
| Column header Regex | If you enabled the **Perform only column header classification** checkbox, the **Column header Regex** options get enabled. Specify the relevant regex pattern(s) for column header classification. Regex pattern(s) take precedence over the detection of the system detectors. If the match is found, no other detection would be required. > [!NOTE] > **Note** > > We have a validation limit of a minimum of 1 and a maximum of 10 regexes that you can enter here. ![systemDEDefinitionsSettings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8974af73-00f0-7978-bb5e-74d6fa4bea29(1).png) |
| **Detector(s)** Securiti uses detectors to find text that may apply to this Data Element. Securiti may have multiple detectors for a Data Element that correspond to different formats of the Data Element or to different data sources. Most settings for semi-structured and unstructured data are found here (i.e., are detector-specific) because a data element type may have more than one format, with different formats having their own detection requirements and error rates for different file formats. This level of granularity can be helpful for deep fine-tuning. For each detector, configure the following settings. |
| Status | Use the toggle to activate or deactivate the specific detector. |
| Data Source Type | Use the tools to limit the detector to a specific set of data formats. For example, if you expect the detector to have a low false-positive rate in tabular data but a high false-positive rate in unstructured data, you can limit it to tabular data and apply other detectors to unstructured data. Tabular data includes databases as well as CSV/TSV, Avro, and Parquet files. You can also use available options for semi-structured and unstructured columns in tabular data. To reset source types to default, click the **Reset to Default** button. |
| Confidence Threshold | Choose a level that tells Securiti how much confidence it should have that detections are of the correct data element type when Securiti finds them in structured data (tables) that lack column headers. Securiti considers the confidence from the column header separately. For highly unique formats such as MAC addresses, you might choose Very High. For data that Securiti could not be effectively classified without a strong header, such as bank account numbers or vehicle license plate numbers, you might choose Very Low. To reset the **Confidence Threshold** level to default, click the **Reset to Default** button. |
| **Unstructured Classification** For unstructured data classification, configure the following settings. To customize a system data element, you must use the right combination of positive, negative, and global anchors to achieve optimal results. - You might need multiple iterations to achieve good classification results. These iterations are helpful due to the relationship between positive, negative, and global positive anchors, which help establish reliable data extraction points. - As you can see the content and header confidence should also be fine-tuned to improve the accuracy of the detection process. - Since these configurations for fine-tuning are enforced at the tenant or organization level, any changes in the underlying data need further adjustments in the custom data elements to align with the new information. |
| Requires a nearby positive anchor for detection | Positive anchors act as reference points that signal the presence of relevant data elements when they are in proximity to specific indicators. By strategically setting these anchors, we can establish a framework where, upon encountering potential data elements, the system can evaluate the surrounding context to determine if sufficient supporting evidence exists for reporting that data element. This approach helps to filter out irrelevant or ambiguous data, improving the quality of the information extracted. Choose whether the detector reports a data element only when a positive anchor is nearby (does not apply to simple tabular data). |
| Positive Anchor Regexes | Positive anchors serve as contextual markers that can significantly influence the system's decision-making process when it comes to recognizing relevant data. Configure positive anchors to customize your data elements for enhancing detection accuracy by acting as contextual markers that validate potential data elements. By placing these anchors near key data elements, the system can gather supporting evidence from surrounding text, ensuring that only contextually relevant data is reported, thereby improving the overall efficacy of the data extraction process. Configure the **Positive Anchor Confidence** ranging from Very Low to Very High, depending on the sensitivity of the data element. |
| Negative Anchor Regexes | Negative anchors serve as specific contextual indicators that signal when a potential data element should be disregarded. This process enhances data integrity by reducing the likelihood of incorrect data being reported, as it provides a systematic way to filter out elements that lack validity or relevance. Configure negative anchors to customize your data elements for enhancing detection accuracy by acting as contextual markers that validate potential data elements by discarding irrelevant detections that may lead to false positives. |
| Global Positive Anchor Regexes | Global anchors act as key markers that, when found on the same page or before a potential data element, indicate that the element is likely relevant and should be reported by Securiti. For instance, if a specific header or category label appears before a potential data element, it reinforces the idea that this element is important and valid for reporting. Configure global anchors that, when present on the same page or prior to a potential data element, provide supporting evidence that Securiti should report the potential data element. ![sysemDEDetectorsSettings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-178f7c1f-7bf4-ed36-a5a6-d26173bdee3d(1).png) |
| Global Negative Anchor Regexes | Global Negative Anchor is a term that, if present anywhere in a document, suppresses detection of the data element. Mark **Use the system's default anchor regexes** to use the default configuration, or select **No** to specify a custom regex value. Each entry must be a valid regex pattern and cannot exceed 500 characters. ![Input field for global negative anchor regexes with example regex value provided.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-09 at 12.26.09 PM.png) > [!NOTE] > Note > > Global Negative Anchor Regexes suppress detections at the chunk (roughly the size of a single page of text) level, and not across the entire file. If the anchor term and the sensitive value are in different chunks, which can happen with larger files, the suppression may not work for that detection. |

### Enabling or disabling a data element

- To disable a data element, select a data element from the list and disable the **Active** toggle. Securiti shows a modal of affected content profiles before you proceed to save. The modal only appears if there are affected content profiles related to the data classification of a data element. You can cancel it or proceed to click the **Confirm and Disable** button to disable a data element.

> [!NOTE]
> **Note**
> 
> When you use a data element in an exact data profile and you use that exact data profile in a content profile, deactivating the data element should have transitive dependencies. When you deactivate or disable such a data element, you may see a model of the affected content profile to be deactivated, as well as the relevant exact data profiles.
> 
> ![disableDE.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dcef4934-2f63-8f41-5550-07c4f82841e5(1).png)
> 
> You can cancel it or proceed to click the **Confirm and Disable** button to disable the exact data profile, data element, document category, or file format.
> 
> You can enable that data element, exact data profile, and content profiles separately.
- To enable a data element, select a data element from the list and enable the **Active** toggle.

### Troubleshooting vulnerable regex patterns

A vulnerable regular expression (regex) is a pattern that may cause performance issues, slow down the system, or be bypassed due to an inefficient or unsafe pattern design. Detecting these patterns helps prevent potential security risks or application crashes.

If a regex pattern in your data element is potentially vulnerable, Securiti displays an error message on the top right of the Data Elements page, with the vulnerable portion for quick identification.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(612).png)

For a better understanding of providing a safe regex pattern, see [Regular Expression Denial of Service - ReDoS](https://owasp.org/www-community/attacks/Regular_expression_Denial_of_Service_-_ReDoS).

The uniqueness attribute defines how many different values of a data element an individual may contain. For example, a person can have multiple credit card numbers associated with them, but cannot have multiple driver’s license numbers.

The identifiability is a unique attribute associated with data elements. This means that a data element may be used to identify an individual and no other person shares the same value of that data element for example SSN, driver’s license number, or medical record number.

## Related

- [Customizable system data element types](/customizable-system-data-element-types.md)
- [System data element types](/system-data-element-types.md)
