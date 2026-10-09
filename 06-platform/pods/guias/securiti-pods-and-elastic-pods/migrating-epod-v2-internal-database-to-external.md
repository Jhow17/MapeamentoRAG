---
title: "Migrating EPod V2 internal database to external"
slug: "migrating-epod-v2-internal-database-to-external"
updated: 2026-07-02T13:13:44Z
published: 2026-07-02T13:13:44Z
canonical: "helpcenter.securiti.ai/migrating-epod-v2-internal-database-to-external"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Migrating EPod V2 internal database to external

This guide explains how to migrate your EPod V2 databases from internal to external. As EPod V2 supports both internal and external databases, if you are already using EPod V2 with an internal database, this process lets you migrate the data from your internal database to your external database.

## Prerequisites

Before proceeding with the migration, you must meet the following requirements.

## 

| Prerequisite | Detail |
| --- | --- |
| Migration Script | You must download the migration script before proceeding with the migration. Click download icon below to download the script. [](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Migration_Script(1).sh)Migration_Script20.68 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Migration_Script(1).sh) |
| External Databases | You must have the following details for the external Redis and Elasticsearch (ES) databases available before configuring: - Host path of the database - Port - Region |

## Migrating the database

Proceed with the following steps to perform the migration.

1. Copy the namespace name your EPod V2 is currently running in, since the EPod V2 can run on any namespace.
2. Export the namespace to your environment variable using the following command.

```bash
export SECURITI_NAMESPACE=<your_namespace_name>
```

1. Pause all the running scans in your EPod V2 using the script. Run the migration helper script in your control VM and select option 1.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/migrating-epod-v2-internal-database-to-external-image-z9vzq4aj.png)
2. With the pre-migration option, scale down the excess resources and take a backup of your databases by selecting option 2 of the script.

It creates a backup in your current directory with the title `backup-dir`.
3. Untar the created backup if it is not unarchived automatically.
4. Edit your existing EPod V2 from the UI.
  1. Open the **Redis** tab and disable **Install Redis** toggle. Then, add the following details:

| Parameter | Description |
| --- | --- |
| Host | Provide the host address of your Redis database. |
| Port | Provide the port on which the Redis database service is currently running. |
| SSL | Enable this toggle to use SSL for communication with your Redis database if it supports it. |
  2. Open the **ES** tab and disable the **Install ES** toggle. Then, add the following details:

| Parameter | Description |
| --- | --- |
| Host | Provide the host address of your Elasticsearch database. |
| Port | Provide the port on which the Elasticsearch database service is currently running. |
| Scheme | From the dropdown menu, choose the supporting scheme. |
| Region | Enter your database region. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/migrating-epod-v2-internal-database-to-external-image-uj1yafpq.png)
5. With the new **values.yaml** file, run the Helm upgrade.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/migrating-epod-v2-internal-database-to-external-image-mjr434um.png)

This applies the newly updated changes to EPod V2.
6. After the pod is functional again with the external database, run the script and choose option 3.

This step restores your backup to the cluster.

Now, your Elastic Pod V2 is functional with the external databases.
