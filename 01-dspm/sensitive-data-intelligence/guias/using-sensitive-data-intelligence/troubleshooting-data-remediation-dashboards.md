---
title: "Troubleshooting for data remediation actions"
slug: "troubleshooting-data-remediation-dashboards"
updated: 2026-07-22T12:52:20Z
published: 2026-07-22T12:52:20Z
canonical: "helpcenter.securiti.ai/troubleshooting-data-remediation-dashboards"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for data remediation actions

This article covers the possible issues that can occur when reverting quarantined files from the File Quarantine, File Insights, and File ROT dashboards in Data Remediation. As a first troubleshooting step, ensure that the connector has read and write access to both the quarantine location and the original file location, and that the original folder or directory is still available and accessible.

For more information, see [Using Data Remediation Dashboards](/latest/docs/using-data-remediation-dashboards).

## Revert failures for quarantined files

If a revert action fails, you can review the failure status and details from the Data Remediation dashboard to identify which files failed and take corrective action before retrying.

File governed by multiple policies

If a file is governed by more than one quarantine or remediation policy, one policy may have already reverted the file. When attempting to revert again, Securiti finds no file at the expected location and the revert fails.

To verify this:

1. Filter by **File Name** and **Status** = Quarantine / Revert.
2. Check whether another policy has already reverted the file.
3. If the file still shows Quarantined, it was not reverted by another policy.

## Missing original path

If the folder, site, or directory where the file was originally located has been deleted, renamed, or moved since the file was quarantined, Securiti is unable to locate the original path and the revert fails.

Ensure the original folder, site, or directory is still available and accessible before retrying the revert action.

## Change in file name or ID

If a scan is configured with **Incremental Sync** set to **TRUE**, Securiti only detects modified or newly uploaded files. This can cause revert failures in the following scenario:

1. A file is quarantined.
2. You manually move the file to another folder.
3. You re-upload the file with the same name but in a different path.
4. Because this is a new upload, a new File ID is generated.
5. A revert attempt uses the old File ID, which no longer matches any file.
6. The revert operation fails with a `File not found` error.

If a file already exists at the original location, rename or remove it before retrying the revert action.

## Connector is inactive or unauthenticated

If the connector associated with the quarantine policy is inactive or has lost authentication, Securiti cannot access the quarantine location or the original file path, causing the revert to fail.

Confirm that the connector is active and successfully authenticated before retrying the revert action.
