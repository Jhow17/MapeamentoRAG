---
title: "Fine-tuning classification resources"
slug: "fine-tuning-classification-resources"
description: "This section covers the fine tuning for classification resources"
status: "update"
updated: 2026-09-29T11:26:52Z
published: 2026-09-29T11:26:52Z
canonical: "helpcenter.securiti.ai/fine-tuning-classification-resources"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Fine-tuning classification resources

Securiti recommends using a small set of data elements, content profiles, or file categories in your scans so they're identified instantly in the scan results you can view on the structured, unstructured, or streaming dashboards.

The first step in fine-tuning classification is configuring the system-defined or custom classification resources, such as data elements, content profiles, file formats, dictionaries, and exact data indexes for your structured, unstructured, and streaming data. These resources are then used to configure a discovery scan.

## Use case

A typical financial organization needs to ensure that personal data, such as customer Personally Identifiable Information (PII) and sensitive financial information, is identified and classified. This data might spread across different unstructured data systems in the form of emails, documents, PDFs, images, and so on.

The organization wants to ensure compliance with privacy laws, such as GDPR, to minimize the risk of exposing sensitive customer data in unstructured data systems. When you've configured your organization's data system, such as Microsoft SharePoint Online or Amazon S3, you can use the following resources as an example to configure your classification.

## Data elements

Configure your specific data elements before starting the discovery scans. You can include the following:

- Names, email addresses, social security numbers, and account numbers to identify PII.
- Credit card numbers, IBANs, or other sensitive payment data.
- Scanned documents or images with text-based information, such as passports and ID cards.
- Specify a regex, dictionary, or keywords for each data element mentioned above, if needed.

You can use a combination of regex, dictionary, and keywords for robust detection. For example, regex can detect patterns like credit card numbers, while dictionaries can identify product names, and keywords can identify specific business terms.

### Regex

You can specify regex patterns to include or exclude in the discovery scan, as shown below.

![System settings interface displaying data classification options and matching rules for data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/specifyingregex_dataelement.png)

Examples of regex include:

**Email**

For email, a valid expression might be: `\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b` (matches alphanumeric and special characters).

**Credit card number**

For a credit card number, a valid regex might be: `\b\d{4}[- ]?\d{4}[- ]?\d{4}[- ]?\d{4}\b` (matches 16-digit credit card numbers with optional hyphens or spaces).

> [!NOTE]
> Note
> 
> You can also include or exclude regex patterns when you configure a discovery scan for your relevant data system.

### Dictionary

You can specify dictionaries to include or exclude in the discovery scans, as shown below.

![System settings interface showing data classification options and expected misfiring rates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configuringdictionaries_dataelement.png)

Examples of dictionaries include:

- Bank Codes
- Bank Names

### Keyword

You can use relevant phrases or a combination of words as keywords.

![System settings interface displaying data classification options and matching rules for keywords.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configuringkeywords_dataelements.png)

Examples of keywords when working with the data about advertising can be as following:

- Bank Statement
- Mortgage
- Loan

### Proper use of the misfiring rate

Keep the following points in consideration:

- No need to use anchors if the misfiring rate is **Zero** or **Low**.
- No need for anchors for unique data elements such as **SSN** or **MAC address**.
- A low firing rate refers to a low confidence level, whereas a higher firing rate refers to a higher confidence level. For example, if you have 10 accurate detections out of 20, your confidence rate is 50%.
- For **Moderate** or **High** misfiring rates, you may need additional anchors to aid detection, such as a bank account number or a credit card number.

### Using positive and negative regex

- Use the positive anchors when there is a potential data element to be detected. The positive anchors provide supporting evidence that the data element should be reported.
- Using the negative anchor causes Securiti to discard the data element as a false positive.

You can specify anchors when configuring data elements, as shown below.

![System settings for data classification, including regex and anchor keywords for identification.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/specifyinganchors_dataelement.png)

For more information, see [configuring custom data elements](/latest/docs/configuring-custom-data-element-types) and [configuring system data elements](/latest/docs/data-elements-customizing-system-data-element-types).

## Content profiles

You can configure content profiles to detect sensitive information from documents of different file formats, as shown below. You can also use exact data indexes and profiles, as well as dictionaries and regex patterns, as specified above.

![System settings interface showing inclusion and exclusion criteria for data classification rules.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configuringcontentprofiles.png)

For more information, see [configuring content profiles](/latest/docs/configuring-content-profiles).

## File formats

> [!NOTE]
> Note
> 
> File formats is only available for unstructured data.

You can also specify file formats and file types, such as **Doc**, **Gdoc**, **Docx**, **PDF**, and **Conf**, as shown below.

![Overview of file formats for word processing applications and their categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/configuringfileformats.png)

> [!NOTE]
> Note
> 
> You can also include or exclude file formats when you configure a discovery scan for your relevant data system.

For more information, see [configuring file formats](/latest/docs/configuring-file-formats).

## Dictionaries

> [!NOTE]
> Note
> 
> Dictionaries is only available for unstructured data.

You can use dictionaries to identify product names, such as Bank Name and Bank Code, as shown below.

![Interface for adding a financial dictionary with keywords and categories in system settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/addingadictionary.png)

For more information, see [configuring dictionaries](/latest/docs/configuring-dictionaries).

## Exact data index

> [!NOTE]
> Note
> 
> Exact Data index is only available for structured and unstructured data.

Exact data indexes are used to enhance the precision and efficiency of classification and discovery by creating indexes for specific data elements, such as PII, financial, or sensitive data.

Create an exact data index first that can be used in exact data profiles.

1. You can use a CSV file containing a set of data elements to create an exact data index, and click **Scan Data System Instances**.

![exactDataIndex.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1b60150c-0b1f-382c-1557-adba84d4fe92.png)
2. You can see the data elements identified under **Schema**.

![ediSchemaNav2_0.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-35188f65-0b55-b933-42aa-7c789bedb820.png)
3. To make any of your data elements part of the exact data index, include them from the **Include Field in Index** column.
4. Next, configure the exact data profiles and use the exact data index you've already created. In the **Primary Field**, choose a data element that was included in the index, and similarly, for the **Secondary Field**, choose another one.

![exactDataProfilesDefinition.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fa25a50-d613-1ec5-32ea-2d1a59e3478d.png)

For more information, see [Using exact data indexes and profiles](/latest/docs/using-exact-data-indexes-and-profiles).

## Related

- [Discovery scans](/discovery-scans.md)
- [Discovery scans for streaming connectors](/discovery-scans-for-streaming-connectors.md)
