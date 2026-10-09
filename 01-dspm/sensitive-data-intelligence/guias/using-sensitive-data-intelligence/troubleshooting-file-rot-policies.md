---
title: "Troubleshooting File ROT policies"
slug: "troubleshooting-file-rot-policies"
updated: 2026-08-05T12:33:17Z
published: 2026-08-05T12:33:17Z
canonical: "helpcenter.securiti.ai/troubleshooting-file-rot-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting File ROT policies

This article covers the possible issues that can occur when reverting ROT files using a File ROT policy. As a first troubleshooting step, ensure that your new File ROT policy uses the same folder path as the original policy that was deleted. Using a different folder path can prevent files from being reverted and may cause them to remain permanently.

For more information, see [Using File ROT Policies](/latest/docs/using-file-rot-policies).

## Legacy quarantine with "Documents" folder path

If you have quarantined your OneDrive files using a File ROT policy with "Documents" as the folder path, and you later deleted that policy, you must use "Documents" as the folder path in your new File ROT policy to revert those files.

> [!WARNING]
> Important
> 
> This only applies to files you quarantined before release 1.132.

## Files quarantined with "/" as folder path

If you have quarantined your SMB or NFS files using a File ROT policy with "/" as the folder path, and you later deleted that policy, you must use "/" as the folder path in your new File ROT policy to revert those files.

## Quarantine destination has been deleted

If the central quarantine destination used by the original File ROT policy has been deleted, create a new central quarantine destination with the same configuration as the deleted destination. Then, create a new File ROT policy that uses this destination to revert the quarantined files.
