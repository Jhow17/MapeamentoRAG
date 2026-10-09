---
title: "Migrating Pod v1.28+ to EPod V2"
slug: "migrating-pod-v128-to-epod-v2"
updated: 2026-07-31T12:05:09Z
published: 2026-08-02T12:00:11Z
canonical: "helpcenter.securiti.ai/migrating-pod-v128-to-epod-v2"
stale: true
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Migrating Pod v1.28+ to EPod V2

This guide explains how to migrate from Pod V2 to Elastic Pods V2 (EPod V2). It covers the preparation steps, migration workflow, and post-migration activities required to ensure a smooth transition.

EPod V2 improves performance, scalability, and cluster stability as it supports the cloud-provided cluster services. When migrating from Pod V2 to EPod V2, the system uses a helper script to pause scans, take backups, move data, install the new cluster, and restore your existing state.

## Prerequisites

Before proceeding with the migration, you must consider and meet the following requirements.

| Prerequisite | Description |
| --- | --- |
| Migration script | You must download the migration script before proceeding with the migration. Click the download icon below. [](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Podv2_to_EPodV2_migration_script.sh)Podv2_to_EPodV2_migration_script22.27 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Podv2_to_EPodV2_migration_script.sh) |
| Auto Updates | You must disable auto updates for the cluster, as they could lead to an undesired state during migration. |
| Control VM Access | You must have access to the Control VM of the desired cluster where you are installing the EPod V2. |
| Configuration File | Add `is_migration: true` in the **values.yam**l file that is present in the UI for installing EPod V2. |

> [!WARNING]
> Important
> 
> Any table training samples stored on Pod v2 will be lost after migrating to EPod V2.

## Migrating the pod

Proceed with the following steps to perform the migration.

1. Pause the running scan jobs using the helper script.
  1. In the cluster, run the migration helper script and choose option 1.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/migrating-pod-v1.28-to-epod-v2-image-e88xabgh.png)

This process might take up to a few hours, depending on the number of running scans.
2. Perform the pre-migration steps on your cluster.
  1. Run the script and choose option 2. This will scale down the excess resources and take a backup of the database. It creates and migrates the backup archive into your current directory. It also converts the Pod V2 into EPod V2 on the UI, and revoke the appliance locally.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/migrating-pod-v1.28-to-epod-v2-image-p7bwgl62.png)

The backup file name is **backup-dir**.
3. Copy the created backup to your control VM from where you are planning to install EPod V2.
4. Untar the created backup if it is not unarchived automatically.
5. Revoke the same EPod V2 from the UI.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-G66P1PUS.png)
6. Start installation process for the same EPod V2. For more information, see [EPod V2 installation](/v1/docs/epod-v2-installation).
7. During EPod V2 installation, at **Summary** tab, while copying the content of **values.yaml** file, you must add `is_migration: true` parameter to the YAML file before applying it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/migrating-pod-v1.28-to-epod-v2-image-b0vy4rzu.png)
8. Proceed with the installation of EPod V2 and wait for the completion. On completion, the cluster becomes active on the UI.
9. Export the namespace to the environment variable after installing EPod V2 to ensure the backup is restored correctly to the relevant EPod V2 installation using the following command:

```bash
export SECURITI_NAMESPACE=<your_namespace_name>
```
10. Run **option 3** of the script to restore the backup to the EPod V2 cluster. This also includes restoring Redis database keys.
11. After the restore is complete, validate the count of Redis keys using the information from the pre-migration option.

It restores the scans at the end of the post-installation option. The UI also reflects the older path of scans until the scans resume.

> [!NOTE]
> Note
> 
> When you upgrade your new EPod V2, you must remove `is_migration` parameter from **values.yaml**.
