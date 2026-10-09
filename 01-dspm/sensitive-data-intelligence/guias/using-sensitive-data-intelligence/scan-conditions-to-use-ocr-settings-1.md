---
title: "Scan conditions to use OCR settings"
slug: "scan-conditions-to-use-ocr-settings-1"
description: "This section covers the overview of scan conditions to use OCR settings"
status: "update"
updated: 2026-09-29T11:29:54Z
published: 2026-09-29T11:29:54Z
canonical: "helpcenter.securiti.ai/scan-conditions-to-use-ocr-settings-1"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Scan conditions to use OCR settings

### 

Image text extraction using OCR settings works alongside scan conditions, where you choose file or object extension categories. However, scan conditions take higher precedence over OCR settings.

If you exclude image and archived files in scan conditions, OCR scanning does not apply, and Securiti's content classifier skips those files. The results are downloaded without OCR processing.

| Scan Conditions option | OCR Settings | Description |
| --- | --- | --- |
| Include the **Archive** file type from the **Scan Conditions** | Enable the **Extract text from compressed and archived files** option from the **Advanced Settings** of the discovery scan | Securiti downloads and scans the archive file. Text is extracted from any supported image files within the archive using OCR. |
| Include the **Archive** file type from the **Scan Conditions** | Disable **Extract text from compressed and archived files** from the **Advanced Settings** of discovery scans | Securiti downloads the archive file and sends it to the content classifier. However, the content classifier skips it without scanning because text extraction is disabled. |
| Exclude the **Archive** file type from the **Scan Conditions** | Enable **Extract text from compressed and archived files** from the **Advanced Settings** of discovery scans | Securiti skips the archive file based on the scan condition. OCR settings have no effect because scan conditions take higher precedence. |
| Exclude the **Archive** file type from the **Scan Conditions** | Disable **Extract text from compressed and archived files** from the **Advanced Settings** of discovery scans | Securiti skips the archive file based on the scan condition. Both settings result in the file being excluded from scanning. |

## Scan Conditions to use files and objects

| Scan Conditions option | OCR Settings | Description |
| --- | --- | --- |
| Include the image file type from the **Scan Conditions** > **File Extension Category** or **Object Extension Category** Example: **image** | Enable **Extract text from images using OCR** from the Advanced Settings of discovery scans | Securiti downloads and scans the image file. Text is extracted from the image using OCR and used for sensitive data classification. |
| Include the image file type from the **Scan Conditions** > **File Extension Category** or **Object Extension Category** Example: **image** | Disable **Extract text from images using OCR** from the Advanced Settings of discovery scans | Securiti downloads the image file and sends it to the content classifier. However, the content classifier skips it without scanning because OCR is disabled. |
| Exclude the image file type from the **Scan Conditions** > **File Extension Category** or **Object Extension Category** Example: **image** | Enable **Extract text from images using OCR** from the Advanced Settings of discovery scans | Securiti skips the image file based on the scan condition. OCR settings have no effect because scan conditions take higher precedence. |
| Exclude the image file type from the **Scan Conditions** > **File Extension Category** or **Object Extension Category** Example: **image** | Disable **Extract text from images using OCR** from the Advanced Settings of discovery scans | Securiti skips the image file based on the scan condition. Both settings result in the file being excluded from scanning. |

For more information, see [OCR-supported document types](/latest/docs/ocs-supported-document-types).

## Related

- [OCR-supported document types](/ocs-supported-document-types.md)
