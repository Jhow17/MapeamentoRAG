---
title: "Supported file formats for MIP sensitivity labels"
slug: "supported-file-formats-for-mip-sensitivity-labels"
updated: 2026-08-26T12:46:00Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/supported-file-formats-for-mip-sensitivity-labels"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Protected labeling support by file format

Securiti supports the following file formats for protected Microsoft Purview Information Protection (MIP) sensitivity labeling through Data Labeling policies. The support depends on both the file format and the connected data system.

| File format category | Supported formats | Labeling support |
| --- | --- | --- |
| Image formats | - `.jfi` - `.jfif` - `.jif` - `.jpe` - `.jpeg` - `.jpg` - `.png` - `.tif` - `.tiff` | Securiti supports only unprotected labeling for image formats. |
| Text formats | - `.csv` - `.json` - `.log` - `.md` - `.tsv` - `.txt` - `.xml` - `.yaml` - `.yml` | Securiti supports only protected labeling for text formats on the following data systems: - Amazon S3 - Azure Blob Storage - Azure Files - Box - NFS - Microsoft 365 OneDrive - Microsoft 365 SharePoint - SMB - Securiti for Box When Securiti applies a protected sensitivity label to a text file, it retains the file's original extension. For example, if Securiti applies a protected sensitivity label to `sample.txt`, the file remains `sample.txt`. To open and decrypt a protected text file, download it from the source data system and use Microsoft Information Protection Viewer, which is available on Windows. Before opening the file, enable file name extensions and change the file extension based on the file format: - For a `.txt` file, change the `.txt` extension to `.ptxt`. For example, rename `sample.txt` to `sample.ptxt`. - For other supported text formats, append `.pfile` to the file name. For example, rename `sample.csv` to `sample.csv.pfile`. After changing the extension, open the file in Microsoft Information Protection Viewer to decrypt and view its contents. > [!WARNING] > Important > > If you change the extension of a protected text file directly in the source data system, the file's metadata also changes. Run a discovery scan after changing the extension so that Securiti reflects the updated file information. |
| Microsoft Office formats | - `.docm` - `.docx` - `.pdf` - `.ppsx` - `.pptx` - `.vdw` - `.vsd` - `.vsdm` - `.vsdx` - `.vss` - `.vssm` - `.vssx` - `.vst` - `.vstm` - `.vstx` - `.xlsb` - `.xlsm` - `.xlsx` For Microsoft 365 OneDrive and Microsoft 365 SharePoint, the following Microsoft Office formats are not supported for protected labeling: - `.doc` - `.dot` - `.dotm` - `.dotx` - `.potm` - `.potx` - `.pps` - `.ppsm` - `.ppt` - `.pptm` - `.xls` - `.xlt` - `.xltm` - `.xltx` | Securiti supports protected labeling for Microsoft Office formats on the following data systems: - Amazon S3 - Azure Blob Storage - Azure Files - Box - NFS - Microsoft 365 OneDrive - Microsoft 365 SharePoint - SMB - Securiti for Box For Microsoft 365 SharePoint Online and Microsoft 365 OneDrive, Securiti uses Microsoft Graph APIs to determine the current protection state of a file and to apply a sensitivity label. Securiti calls the `extractSensitivityLabel` API to determine whether the file is protected. If the file is protected, Securiti calls the `assignSensitivityLabel` API to update the label. In this scenario, any custom metadata attributes selected in the policy are not applied because the API does not support updating custom metadata attributes. If the file is not protected, Securiti follows the standard labeling process by downloading the file, applying the sensitivity label using the Microsoft Purview Information Protection (MIP) SDK, and then re-uploading the labeled file to Microsoft 365 SharePoint Online or Microsoft 365 OneDrive, replacing the original file. |

The `assignSensitivityLabel` API is an asynchronous metered Microsoft Graph API. Securiti uses this API to update the sensitivity label on files that are already protected in Microsoft 365 SharePoint Online or Microsoft 365 OneDrive. Because Microsoft recognizes these files as protected, external applications cannot download, modify, and re-upload them. Instead, Securiti uses the `assignSensitivityLabel` API to update the label directly within the Microsoft data system. To set up the `assignSensitivityLabel` API, see [Enable metered APIs and services in Microsoft Graph](https://learn.microsoft.com/en-us/graph/metered-api-setup).

> [!WARNING]
> Important
> 
> Each `assignSensitivityLabel` API call costs approximately $0.00185 (around 500 files per dollar). Securiti does not call this API in every case. For example, if you disable the **Override already applied label** option, Securiti does not apply a new label, so no charge is incurred.
