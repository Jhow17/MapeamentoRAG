---
title: "Exact data matching use cases"
slug: "exact-data-matching-use-cases"
updated: 2026-07-06T17:49:12Z
published: 2026-07-06T17:49:12Z
canonical: "helpcenter.securiti.ai/exact-data-matching-use-cases"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Exact data matching use cases

Exact Data Matching refers to a situation when there is a 100 % exact match between the source data and the target data. It’s a precise form of data classification (or sensitive-data detection) that doesn’t rely on approximation.

- It reduces false positives only if the exact value (or values) you’re concerned about will trigger the match, not any data that merely resembles it.
- This makes it especially useful in contexts where you have a list of known sensitive values (like unique IDs, account numbers, etc) and you want to detect when that precise data appears.
- It supports stronger data-governance, compliance and data-loss-prevention efforts because you’re not reacting to ambiguous pattern-matches, but to real, known values.

## Key considerations for using exact data matching

- It works best when you know the sensitive values ahead of time and have them under control (structured records, well-managed datasets).
- Since the match must be exact, this method is less tolerant of data variations (typos, formatting differences, abbreviations etc.) than fuzzy or pattern-based methods.
- Data quality is critical: if the value list is incomplete, outdated, or formatted differently, matches may be missed (false negatives).
- There may be scalability and performance considerations when the dataset of values is very large and needs frequent updating.

## Important features related to Exact Data Index

| Primary Field | The primary field acts as the unique identifier per row/record. in your source dataset. They’re used as the anchor for the indexed record and to maintain one-to-one correspondence between entries in your index and records in your database. |
| --- | --- |
| Index Field | Index fields are the actual data elements you want the system to detect in scanned content, for example, customer IDs, SSNs, or account numbers. |
| Example | Together, they create a structured and secure fingerprint set that allows high-confidence, low-false-positive detection of sensitive data. **Primary Field (Employee ID)** - 12345 - 6789012 **Indexed Fields** - Name, Email, SSN |

## Important features related to custom data elements

| **Limit to Exact Data Matches** | This option lets you choose an existing exact data index only if it has created a successful index. |
| --- | --- |
| **Match Percentage** | > [!WARNING] > Important > > The **Match Percentage** only works for Structured and Semi-structured data. The **Match Percentage** defines how closely a data element must match the reference index to be classified as an exact match. This field appears when an exact data index is selected. You can set any value between 1–100 to adjust confidence. > [!NOTE] > Note > > Use lower thresholds for broader testing and higher ones for production scans where precision is critical If no value is set, Securiti calculates the threshold automatically based on the header similarity and expected misfiring rate. |
| **Regex** | You can configure regex patterns for your custom data elements to find an exact match. For example, for an 8 digit number it can be a fixed regex pattern ^\d{8}$. |

**Sample table**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-O11STYLP.png)

## Using the exact data index with one column

This example shows using an exact data index with a custom data element which is set as an index and primary field in the index and choosing it from the **Sensitive Data** section of discovery scan.

| Exact data index Primary field | Custom data element with regex | Exact data profile | Discovery scan | Expected outcome |
| --- | --- | --- | --- | --- |
| Choose a column as an index and primary field **Example** Col1: Emp_no (6 to 8 digits) | Custom data element: **Custom_empno** Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** to less than 50% | (Optional) Choose Custom_empno as **Primary Field** | Do not choose any data element in the Sensitive Data area Do not choose exact data profile | **Custom_empno** is not detected because of: **Match Percentage** is less than 50% Data element not selected in discovery scan |
| Choose a column as an index and primary field **Example** Col1: Emp_no (6 to 8 digits) | Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** to greater than to 50% | (Optional) Choose **Custom_empno** as primary fields | Choose **Custom_empno** data element in the Sensitive Data area | Detection of **Custom_empno** is true because of **Match Percentage** is greater than 50%. |

## Using the exact data index with multiple columns

This example shows multiple data elements in an exact data index with each one having custom data element set as the index and primary fields in the index, and choosing it from the Sensitive Data section of the discovery scan.

> [!NOTE]
> **Note**
> 
> - In this case, you don't have to configure an exact data profile. You must only select the custom data elements in the discovery scan's Sensitive Data section.
> - If you have unstructured data, the Match Percentage does not matter as the regex pattern will be matched against the data element defined in the exact data index and it provides a 100% match.

| Exact data index Primary field | Custom data element with regex | Exact data profile | Discovery scan | Expected outcome |
| --- | --- | --- | --- | --- |
| Choose more than one column as index and primary field **Example** Col1: emp_no (6-10 digits) Col2: cust_no (6-10 digits) Col3: order_no (6-10 digits) | Configure the following custom data elements: - Custom_empno - Custom_custno - Custom_orderno Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** to less than 50% Use a regex pattern in the form of: - ^\d{6}$ - ^\d{8}$ - ^\d{10}$ | (Optional) Choose the **Custom_empno, Custom_custno, Custom_orderno** as primry fields | Do not choose any data element in the **Sensitive Data** area Do not choose exact data profile | No detection for Custom_empno, Custom_custno, and Custom_orderno because these were not selected in discovery scan. |
| Choose more than one column as index and primary field **Example** Col1: emp_no (6 digits) Col2: cust_no (8 digits) Col3: order_no (10 digits) | Configure the following custom data elements: - Custom_empno - Custom_custno - Custom_orderno Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** to greater than 50% Use a regex pattern in the form of: - ^\d{6}$ - ^\d{8}$ - ^\d{10}$ | (Optional) Choose the **Custom_empno, Custom_custno, Custom_orderno** as primary fields | Choose Custom_empno, Custom_custno, Custom_orderno in the **Sensitive Data** area | Detection of Custom_empno, Custom_custno, and Custom_orderno is true because **Match Percentage** is set greater than 50% |
| Choose more than one column as index and primary field Example: Col1: emp_no (6-10 digits) Col2: cust_no (6-10 digits) Col3: order_no (6-10 digits) | Configure the following custom data elements: - Custom_empno - Custom_custno - Custom_orderno Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** greater than 50% for Custom_empno and Custom_custno and less than 50% for Custom_orderno Use a regex pattern in the form of: - ^\d{6}$ - ^\d{8}$ - ^\d{10}$ | (Optional) Choose the **Custom_empno, Custom_custno, Custom_orderno** as primry fields | Choose Custom_empno, Custom_custno and Custom_orderno in the **Sensitive Data**area. Choose exact data profile. | The Custom_empno and Custom_custno data elements detected successfully because the **Match Percentage** is greater than 50% Custom_orderno is not detected because **Match Percentage** is less than 50% |

## Using exact data profiles to secure PII information

This use case shows the detection when the exact data profile is used with the exact data index and running discovery scans with and without selecting the data element and exact data profile.

| Exact data index Primary field | Exact data profile | Discovery scan | Expected outcome |
| --- | --- | --- | --- |
| Choose SSN as an index and primary field and First Name, and Last Name as index fields. | Choose SSN as a primary and First Name and/or Last Name as secondary fields. | Disable the **Allow Exact Data Profile** option from the **Advanced Settings**. Do not choose any data elements in the **Sensitive Data** area Choose the exact data profile. | Detection of SSN, First Name and Last Name failed because no data elements were selected in the discovery scan and the **Allow Exact Data Profile** option was disabled. |
| Choose SSN as an index and primary field and First Name, and Last Name as index fields. | Choose SSN as a primary and First Name and/or Last Name as secondary fields. | Enable the **Allow Exact Data Profile** option from the **Advanced Settings**. Do not choose any data elements in the **Sensitive Data** area Choose the exact data profile. | Detection of SSN, First Name and Last Name failed because no data elements were selected in the discovery scan and the **Allow Exact Data Profile** option was enabled. |
| Choose SSN as an index and primary field and First Name and Last Name as index fields. | Choose SSN as a primary and First Name and/or Last Name as secondary fields. | Enable the **Allow Exact Data Profile** option from the **Advanced Settings**. Choose SSN, First Name and Last name data elements in the Sensitive Data area Do not choose the exact data profile. | Detection of SSN, First Name and Last Name was failed because exact data profile was not selected. |
| Choose SSN as an index and primary field and First Name and Last Name as index fields. | Choose SSN as a primary and First Name and/or Last Name as secondary fields | Enable the **Allow Exact Data Profile** option from the **Advanced Settings**. Choose SSN and do not choose the First Name and Last Name in the **Senstive Data** area. Choose the exact data profile. | Detection of SSN was successful but the detection of First Name and Last Name was failed because these data elements were not selected in the discovery scan. |

## Using exact data profiles to secure employee credit card information

This use case shows the detection to secure employee credit card number when the exact data index is used with the custom data element and running discovery scans with and without selecting data elements and the exact data profile.

| Exact data index Primary field | Custom data element | Exact data profile | Discovery scan | Expected outcome |
| --- | --- | --- | --- | --- |
| Choose Credit Card Number as an index and primary field Choose First Name and Last Name as index fields | Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** less than 50% | Choose Credit card number as a primary and First Name and/or Last Name as secondary fields | Do not choose any data element in the Sensitive Data area. Choose exact data profile | Detection of Credit card number, First Name and Last Name failed because no data elements were selected in discovery scan. |
| Choose Credit Card Number as an index and primary field Choose First Name and Last Name as index fields | Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** greater than 50% | Choose Credit card number as a primary and First Name and/or Last Name as secondary fields | Choose Credit Card Number, First Name and Last name data elements in the **Sensitive Data** area. Choose exact data profile | Detection of Credit Card Number, First Name and Last Name was successful because these data elements were selected in discovery scan. |
| Choose Credit Card Number as an index and primary field Choose First Name and Last Name as index fields | Use exact data index in the **Limit to Exact Data Match** and set **Match Percentage** greater than 50% | Choose Credit card number as a primary and First Name and/or Last Name as secondary fields | Choose Credit Card Number. Do not choose First Name and Last name data elements in the **Sensitive Data** area. Choose exact data profile. | Detection of Credit Card Number was successful but the detection of First Name and Last Name was failed because these data elements were not selected in discovery scan. |

## Using the exact data index with custom data elements and Match Percentage

This example shows how an exact data index can be used to detect a custom data element

> [!NOTE]
> **Note**
> 
> If the **Match Percentage** is set to 50% or less, data elements would not be detected. When the table has 50% data in rows and 50% blank rows, that data element is detected with 25% accuracy of in other words the misfiring rate would be 0.25.

There is a table having data only in the first row (row 0) and rows from 2 to 999 have Null values.

> [!NOTE]
> **Note**
> 
> If the **Match Percentage** < 50%, there would be no match. For a detection to match, set the **Match Percentage** > 50%.

| Exact data index Primary field | Custom data element with regex | Exact data profile | Discovery scan |
| --- | --- | --- | --- |
| Choose SSN as an index and primary field | Use the exact data index in a custom data element and set **Match Percentage** < 50% | N/A | Set sampling to the first row |
| Choose SSN as an index and primary field | Use the exact data index in a custom data element and set **Match Percentage** > 50% | N/A | Set to full scan |

> [!NOTE]
> **Note**
> 
> - It is recommended to continue scanning until all 1000 rows get filled to perform the calculation.
> - If the **Match Percentage** < 50%, there would be no match. For a detection to match, set the **Match Percentage** > 50%.

## Using the exact data index in custom data elements with different Match Percentages and a set of sample data

> [!NOTE]
> **Note**
> 
> A sample of 500 rows can be tested as long as the Match Percentage is less than the fraction of a full column matching the exact data index.

| Exact data index Primary field | Custom data element with regex | Exact data profile | Discovery scan | Expected outcome |
| --- | --- | --- | --- | --- |
| Choose SSN as an index and primary field | Use the exact data index in a custom data element and set **Match Percentage** to 100% | N/A | Set sampling to 500 rows in the **Advanced Settings**. Choose SSN, First Name and Last name data elements in the **Sensitive Data** area. | 100% detection of SSN, First Name and Last Name |
| Choose SSN as an index and primary field | Use the exact data index in a custom data element and set **Match Percentage** to 75% | N/A | Set sampling to 500 rows in the **Advanced Settings**. Choose SSN, First Name and Last name data elements in the **Sensitive Data** area. | 100% detection of SSN, First Name and Last Name |
| Choose SSN as an index and primary field | Use the exact data index in a custom data element and set **Match Percentage** to 60% | N/A | Set sampling to 500 rows in the **Advanced Settings**. Choose SSN, First Name and Last name data elements in the **Sensitive Data** area | 99% detection of SSN, First Name and Last Name |
| Choose SSN as an index and primary field | Use the exact data index in a custom data element and set **Match Percentage** to 55% | N/A | Set sampling to 500 rows in the Advanced Settings. Choose SSN, First Name and Last name data elements in the **Sensitive Data** area. | 99% detection of SSN, First Name and Last Name |
| Choose SSN as an index and primary field | Use the exact data index in a custom data element and set **Match Percentage** to 50% | N/A | Set sampling to 500 rows in the **Advanced Settings**. Choose SSN, First Name and Last Name data elements in the **Sensitive Data** area | 25% detection of SSN, First Name and Last Name |

## Limitations of misfiring in the exact data match threshold

If we use the **Limit to Exact Data Match** option for a custom data element with zero misfiring rate and a regex pattern, the regex itself should be wide enough to have an exact match.

> [!NOTE]
> **Note**
> 
> You cannot see the detection because of the regex pattern since the exact data matching cannot provide data to the dashboards, so the count we see in the dashboards is a full count of the table rows not the detection result.
