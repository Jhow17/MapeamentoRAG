---
title: "File skip and error reasons"
slug: "file-skip-and-error-reasons"
updated: 2026-09-29T11:31:29Z
published: 2026-09-29T11:31:29Z
canonical: "helpcenter.securiti.ai/file-skip-and-error-reasons"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# File skip and error reasons

In some cases, Securiti skips files and generates file errors during the discovery scan. The following are some reasons for these errors and skipped files, and whether the files are recoverable or not in that particular case.

> [!NOTE]
> Note
> 
> - **File Recovery = Yes** means the file is scanned correctly in the subsequent scans.
> - **File Recovery = No** means the file is not scanned in the current and subsequent scans.

## Common reasons and recovery status

Use the following table to understand the file skip and error reasons:

| Reason | File Recovery |
| --- | --- |
| There is an issue reading the downloaded file | No |
| The policy applied to the file cannot be identified | No |
| The policy applied to the file cannot be evaluated | No |
| The file exceeds the file size limit configured in the policy | No |
| The file exceeds the file size limit of the system | No |
| File download error | No |
| File download error related to API | No |
| Disruption during the file download or corrupt file | No |
| File decryption error or password-protected file | No |
| The connector base URL is not received | No |
| The application requested URL is not received | No |
| The file is in compressed format or zipped file | No |
| System issue during file processing | No |
| Connector is deactivated | No |
| Connector configuration issue | No |
| No scan mode is configured in the connector | No |
| Folder or file prefix mismatch | No |
| There is an issue with the file URL | No |
| File metadata is not found | No |
| The file was recently updated | Yes |
| The file is modified during the scan | Yes |
| The connector scan is restarted | No |
| The file is not found or deleted | No |
| There is an error while writing the file | No |
| System resources are busy writing other files | No |
| The dimensions of the image file do not match the configured image dimensions | No |
| Publicly available file | No |
| Binary file or no usable text content in the file | No |
| Insufficient information in the file | No |
| The file is too old | No |
| The file type is configured to be skipped during classification | No |

For more information, see [Configuring connectors for monitored data systems](/latest/docs/configuring-connectors-for-monitored-data-systems) and [Policies](/latest/docs/policies).

## Related

- [Discovery scans](/discovery-scans.md)
- [Using the Unstructured Data Scans dashboard](/using-the-unstructured-data-discovery.md)
