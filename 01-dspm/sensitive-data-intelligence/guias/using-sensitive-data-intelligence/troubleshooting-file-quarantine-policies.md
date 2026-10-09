---
title: "Troubleshooting File Quarantine policies"
slug: "troubleshooting-file-quarantine-policies"
updated: 2026-08-02T14:20:40Z
published: 2026-08-02T14:20:40Z
canonical: "helpcenter.securiti.ai/troubleshooting-file-quarantine-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting File Quarantine policies

This article covers the possible issues that can occur when reverting quarantined files using a File Quarantine policy. As a first troubleshooting step, ensure that your new File Quarantine policy uses the same folder path as the original policy that was deleted. Using a different folder path can prevent files from being reverted and may cause them to remain quarantined permanently.

For more information, see [Using File Quarantine Policies](/latest/docs/using-file-quarantine-policies).

## Legacy quarantine with "Documents" folder path

If you have quarantined your OneDrive files using a File Quarantine policy with "Documents" as the folder path, and you later deleted that policy, you must use "Documents" as the folder path in your new File Quarantine policy to revert those files.

> [!WARNING]
> Important
> 
> This only applies to files you quarantined before release 1.132.

## Files quarantined with "/" as folder path

If you have quarantined your SMB or NFS files using a File Quarantine policy with "/" as the folder path, and you later deleted that policy, you must use "/" as the folder path in your new File Quarantine policy to revert those files.

## Quarantine destination has been deleted

If the central quarantine destination used by the original File Quarantine policy has been deleted, create a new central quarantine destination with the same configuration as the deleted destination. Then, create a new File Quarantine policy that uses this destination to revert the quarantined files.
