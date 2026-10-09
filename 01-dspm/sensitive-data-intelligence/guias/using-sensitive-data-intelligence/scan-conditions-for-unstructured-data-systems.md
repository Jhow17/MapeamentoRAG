---
title: "Scan Conditions for unstructured data systems"
slug: "scan-conditions-for-unstructured-data-systems"
updated: 2026-09-29T11:20:17Z
published: 2026-09-29T11:20:17Z
canonical: "helpcenter.securiti.ai/scan-conditions-for-unstructured-data-systems"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Scan Conditions in discovery scans for unstructured data systems

This section provides a description of each scan condition available when configuring discovery scans. For every scan condition category, you have the option to include or exclude specific criteria to refine what data is scanned, as shown below.

![Scan Conditions panel listing all available filter categories for a discovery scan](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cfbae474-539a-907e-30bc-45221a55c2e1.png)

You can choose more than one scan condition, as shown below.

![Multiple scan conditions selected together in one discovery scan configuration](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6af23c2a-6591-e417-8370-7a43eebeb85d.png)

> [!NOTE]
> **Note**
> 
> - The supported scan conditions vary for each data system. Some data systems also include custom scan conditions that only apply to them. For more information, see [Configuring connectors for monitored data systems](/latest/docs/configuring-connectors-for-monitored-data-systems).
> - Each scan condition tooltip provides more details about the specific options and the required input format.
> - Input patterns are not identical across data systems. For example, the **File Owner** condition might require a username for one data system and an email address for another.

## Quick reference

| Scan condition | What it does |
| --- | --- |
| [File Extension Category / Object Extension Category](/latest/docs/scan-conditions-for-unstructured-data-systems#file-extension-category-object-extension-category) | Include or exclude files or objects by extension category. For example, `Archive`, `Binary`, etc. |
| [Folder Path](/latest/docs/scan-conditions-for-unstructured-data-systems#folder-path) | Include or exclude files by folder path prefix or regex |
| [Folder Name](/latest/docs/scan-conditions-for-unstructured-data-systems#folder-name) | Include or exclude specific folder names |
| [Object Prefix](/latest/docs/scan-conditions-for-unstructured-data-systems#object-prefix) | Include or exclude objects by prefix. This option is available for object-storage systems only. |
| [Object Tags](/latest/docs/scan-conditions-for-unstructured-data-systems#object-tags) | Include or exclude objects by `key:value` tag |
| [File Owner](/latest/docs/scan-conditions-for-unstructured-data-systems#file-owner) | Include or exclude files by the file owner identity |
| [File Name / Object Name](/latest/docs/scan-conditions-for-unstructured-data-systems#file-name-object-name) | Include or exclude files or objects by name using regex |
| [File Extensions / Object Extensions](/latest/docs/scan-conditions-for-unstructured-data-systems#file-extensions-object-extensions) | Include or exclude specific file or object extensions |
| [Object Size](/latest/docs/scan-conditions-for-unstructured-data-systems#object-size) | Include or exclude files by size range |
| [Created Date](/latest/docs/scan-conditions-for-unstructured-data-systems#date-created) | Include or exclude files by creation date |
| [Last Modified](/latest/docs/scan-conditions-for-unstructured-data-systems#last-modified) | Include or exclude files or objects by last-modified date |

## File extension category / object extension category

Securiti lets you include or exclude files or objects during scanning, enhancing overall scan performance. You can add or remove exclusions based on your specific requirements, as shown below.

![Settings for data system scope and scan conditions with file extension options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fileandobjectextension_scanconditions.png)

> [!NOTE]
> **Note**
> 
> You can select multiple categories based on your requirements.

Use the following table to understand the available options:

| Option | Description |
| --- | --- |
| is | Includes the files or objects with the specified extension type. |
| is not | Excludes the files or objects with the specified extension type. |

There are multiple extension categories to include or exclude from the scan scope.

- AI Model
- Archive
- Audio
- Binary
- Biometric
- Computer-Aided Design
- Configuration
- Crypto Keys & Certificates
- Database File
- Desktop Publishing
- Image
- Machine Readable Data
- Mail
- Markup Text
- Medical
- Plain Text
- Presentation
- Rarer File Types
- Source Code
- Spreadsheet
- Temporary Files
- Text Table
- Time Scheduling
- Video
- Word Processing

## Folder path

Securiti lets you include or exclude files from a specific folder, ensuring it scans only the files within that folder, as shown below.

![Folder Path condition showing match prefix, does not match prefix, and regex options](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ec6d8d7-5f42-a80e-314f-a667eb968fb2.png)

For **Folder Path**, choose from the following options to include or exclude the necessary folder(s):

| Option | Description |
| --- | --- |
| match prefix | Choose files that start with the specified prefix. Securiti evaluates each document against the custom-defined criteria before downloading its content. |
| does not match prefix | Excludes files that start with the specified prefix. |
| match regex | Includes files matching the given regex pattern. |
| does not match regex | Excludes files matching the given regex pattern. |

> [!NOTE]
> **Note**
> 
> These options match the beginning of the folder path, unlike regex, which can match anywhere in the path.

### Examples for folder path

Assume the following folder structure:

1. `Projects/2024/Reports`
2. `Projects/2023/Reports`
3. `Archives/Projects/2024/Reports`
4. `2024/Logs/Projects`

**Using the prefix match "Projects"**

- The match includes options 1 and 2, because they start with `Projects`.
- Options 3 and 4 are excluded.

Using `Projects` with `does not match` prefix excludes options 1 and 2, and includes options 3 and 4.

This is useful for scanning or excluding entire folder structures by their starting path.

**Using the regex match**

Assume the same folder structure as above. Using the regex `.*Projects.*` matches every path, because it looks for `Projects` anywhere in the path, regardless of position. This follows the same logic as `match prefix` and `does not match prefix`, but with more flexible pattern matching.

## Folder name

Securiti lets you include or exclude specific folders, ensuring it scans or excludes only the named folders, as shown below.

![Configuration settings for scanning folder names in application interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/foldername_scanconditions(1).png)

Use the following table to understand the available options for **Folder Name**:

| Option | Description |
| --- | --- |
| contains | Includes the folder whose name matches the given regex pattern. |
| does not contain | Excludes the folder whose name matches the given regex pattern. |

### Example for folder name

Assume the following folder names:

- `Personnel Records`
- `Financial Statements`

Using the regex `.*Financial Statements.*` matches the folder named `Financial Statements` , whereas the `does not contain` follows the same logic in reverse.

## Object prefix

This option applies to data systems that use Object Prefix, as shown below. These include Amazon S3, Google Cloud Storage, and Oracle Object Storage.

![Object Prefix field for including or excluding objects by path prefix](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ea401f0-c287-ef27-f3ad-19a01897a38a.png)

Objects are similar to files, but stored in a flat structure within buckets rather than a hierarchical file system. Use the following table to understand the available options for **Object Prefix**:

| Option | Description |
| --- | --- |
| match prefix | Includes objects that start with the specified prefix. |
| does not match prefix | Excludes objects that start with the specified prefix. |
| match regex | Includes objects matching the given regex pattern. |
| does not match regex | Excludes objects matching the given regex pattern. |

### Examples for object prefix

Assume the following objects in an Amazon S3 bucket:

1. `invoices/2024/January/report.pdf`
2. `invoices/2023/December/summary.xlsx`
3. `receipts/2024/January/payment.csv`
4. `invoices/2024/February/details.docx`
5. `receipts/2023/November/refund.txt`

**Using the prefix match "invoices/2024/"**

- The match includes options 1 and 4, because they start with `invoices/2024/`.
- The match excludes options 2, 3, and 5, because they have a different prefix.

Using `invoices/2024/` with `does not match` prefix excludes options 1 and 4, and includes options 2, 3, and 5.

**Using the regex match**

Using the same object list, matching regex `.*2024/.*\.pdf`:

- The match includes option 1, because it contains `2024/` and ends with `.pdf`.
- The match excludes options 2 through 5, because they don't meet both conditions.

`Does not match` regex with the same pattern excludes option 1 and includes all others. This method is useful for more flexible, granular filtering by naming pattern or content type.

> [!NOTE]
> **Note**
> 
> Securiti retains the scanning strategy selected during connector configuration. Enabling prefix conditions does not override that selection.

## Object tags

Securiti lets you specify object tags relevant to your requirements, to refine the selection and classification of objects during scanning. Enter tags in `key: value` format, as shown below.

![Object Tags field showing key:value pair format for tag-based filtering](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6910645b-d345-4ee6-5694-de7557bfd463.png)

## File owner

The **File Owner** scan condition identifies files based on ownership in the data system. You can include or exclude by file owner using regex patterns, as shown below.

![Advanced settings for file ownership and incremental scan options in a software interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/fileownercondition_scanconidtions_discoveryscans.png)

> [!NOTE]
> Note
> 
> This condition is available only after you mark the **Get File Owner Information** in **Advanced Settings**.

Use the following table to understand the available options:

| Option | Description |
| --- | --- |
| contains | Includes file owner matching the specified regex pattern. |
| does not contain | Excludes file owner matching the specified regex pattern. |

The input format for it differs by data system, for example, one data system might require a username, while another might require the file owner's email address. Verify the expected format in the condition's tooltip before configuring it.

## File name / object name

Securiti lets you specify a file or object name using a regex pattern to match desired files or objects for inclusion or exclusion in the scan, as shown below.

![File Name condition showing contains and does not contain regex pattern fields](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-154c5cfa-ff6a-dcd8-acdd-306572d7a764.png)

Use the following table to understand the available options:

| Option | Description |
| --- | --- |
| contains | Includes files and objects matching the specified regex pattern. |
| does not contain | Excludes files and objects matching the specified regex pattern. |

## File extensions / object extensions

Securiti lets you include or exclude specific file or object extensions in your scan, such as `docx`, `xlsx`, `con`, `conf`, `tmp`, and others, as shown below. It gives you granular control to exclude compressed files, such as `zip`, `gzip`, `lzip`, and similar, from scanning.

![File Extension condition listing selectable extensions such as docx, xlsx, tmp](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2a3d713-ed76-95eb-5fd4-656461bbcb0e.png)

If a file does not fall into the compressed folders category, such as `zip`, `gzip`, `lzip`, and similar, it is downloaded and passed on for classification, where it is again classified based on its content. Hence, some of the `VOB` files or `.AAX` files were classified as they were below 10 GB in size and not part of video file extensions, as shown below.

![List of common video file extensions excluded from download and classification](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0306a29b-b6ad-80fd-eadb-6050d770881d.png)

## Object size

Securiti lets you specify a file-size range to include or exclude files from the scan, as shown below.

![Object Size condition fields for setting minimum and maximum file size](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9fefc74d-c83d-8091-df4d-c8ecf9019e50.png)

The following statements are true for this condition:

- If the file size is 0 bytes, the file is not downloaded regardless of extension, but does appear in the Unstructured Data Explorer under the skip policy.
- If the file size is 10 GB, the file is not downloaded regardless of extension, but does appear in the Unstructured Data Explorer under the skip policy.
- If the file extension is in the common video-format list, the file is not downloaded and does not appear in the Unstructured Data Explorer.

## Created date

Securiti lets you specify a creation date before or after a selected date, to include or exclude files based on their creation timestamp, as shown below.

![Date Created condition with before and after date selector fields](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-97950b5c-de5f-f861-af59-e794022e69bf.png)

## Last modified

Securiti lets you specify a last-modified date before or after a selected date, to include or exclude files and objects based on their modification timestamp, as shown below.

![Last Modified condition with before and after date selector fields](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-12ee281d-ac65-6e0b-da58-b98f7d67649f.png)

For more information, see [Discovery scans for unstructured connectors](/latest/docs/discovery-scans-for-unstructured-connectors).

## Related

- [Discovery scans](/discovery-scans.md)
- [Using the Unstructured Data Scans dashboard](/using-the-unstructured-data-discovery.md)
