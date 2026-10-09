---
title: "Troubleshooting for SMB connector"
slug: "troubleshooting-for-smb-connector"
updated: 2025-10-31T06:50:07Z
published: 2025-11-03T07:34:02Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-smb-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for SMB connector

This document covers troubleshooting possible issues during SMB Authentication, scanning, and Configuration.

#### Missing ‘created date’ for files

If you face an error like `NT_STATUS_OBJECT_NAME_NOT_FOUND` when scanning SMB volumes, it can occur due to the following reasons:

- The file does not exist
- `alt name` does not exist on the file, and `smbclient` is being used to retrieve file information such as the created date.

> [!NOTE]
> **Important**
> 
> You can only set short names programmatically for existing files using manual methods or scripts. There is no bulk short name generation for multiple files at once unless they are recreated or moved.

To resolve this issue, follow the steps below to enable short name generation for your SMB files:

1. Run the following command to check the short name generation settings on the SMB volume. Replace `D:` with the appropriate drive letter for the SMB share.

```bash
fsutil behavior query disable8dot3 D:
```
2. If short name generation is disabled, enable it by running the following command:

```bash
fsutil behavior set disable8dot3 0
```

Running this command enables the creation of short file names for new files.

> [!NOTE]
> **Important**
> 
> You must enable `8dot3` for SMB version 1.0 to retrieve the file creation date.
3. If the `disable8dot3` setting is not working or if there are still issues, ensure registry settings for short name creation by following the steps below:
  1. Open Run (press Win + R), type regedit, and press OK.
  2. Navigate to the following path:

```bash
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem
```
  3. Right-click on `NtfsDisable8dot3NameCreation` and select **Modify**.
  4. Change its value to 0.
  5. Restart the system so the change takes effect.
4. Enable short name generation for your existing files as explained below:
  - For single files: Run the following command in case of a single file:

```plaintext
fsutil file setshortname D:\SMBE\HelloE.txt hellpe.txt
```
  - For multiple files: Currently, there is no automated method for bulk updating existing files to generate short names. However, you can manually copy the files to another directory or run the below Powershell script to automate the generation of short names for multiple files in a folder:

```plaintext
echo "Creating temporary directory for shortname generation"
$tempPath = [System.IO.Path]::GetTempPath() + [System.IO.Path]::GetRandomFileName()
New-Item -ItemType Directory -Path $tempPath
$pathToRead = Read-Host "Enter the folder path"
$dir = Get-Item -Path $pathToRead
if (Test-Path -Path $dir.FullName -PathType Directory) { $originalName = $dir.FullName echo "Processing $originalName" $tempName = Join-Path $tempPath ($dir.Name) Copy-Item -Path $originalName -Destination $tempName -Recurse Remove-Item -Path $originalName -Force -Recurse Move-Item -Path $tempName -Destination $originalName Remove-Item -Path $tempPath
} else { echo "Please enter a valid share directory"
}
```

This script processes the directory, assigns short names, and regenerates the file's created date metadata.
5. After making these changes, re-run the SMB scan to verify that the created date is now extracted correctly.
