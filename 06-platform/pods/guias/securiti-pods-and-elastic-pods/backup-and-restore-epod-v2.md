---
title: "Backup and restore EPod V2"
slug: "backup-and-restore-epod-v2"
updated: 2026-07-02T13:35:16Z
published: 2026-07-02T13:35:16Z
canonical: "helpcenter.securiti.ai/backup-and-restore-epod-v2"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Backup and restore EPod V2

You can backup your EPod V2 to your preferred remote location and restore it from the backups. At first, you must configure the backup host. After that, you can do immediate backups, schedule recurring backups, and restore your EPod V2 from a previous backup.

Securiti supports the following sources for storing backups:

| Source | Description |
| --- | --- |
| Secure File Transfer Protocol (SFTP) | It is your existing FTP server with its port open. It must be accessible from the pod. |
| Private Cloud Storage (PCS) | It is your existing PCS. It only supports the PCS from AWS and GCP. If you have not configured PCS already, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |

> [!NOTE]
> **Note**
> 
> This feature supports internal databases only, which are within EPod V2. The following process does not support external databases. You must manually backup your external database, and restore if you require it. For more information on external database disaster recovery, see [Disaster recovery for external databases](/latest/docs/disaster-recovery-for-external-databases).

### Data backed up on pods

During the backup process on EPod V2, specific types of data categories are backed up to ensure a comprehensive recovery. The data backed up includes:

- Configuration:

It backs up all the pod’s relevant connector configurations.
- Database:

It backs up data for the completed and incremental scans from the following internal databases:
  - Redis
  - ElasticSearch
  - Postgres

### Configuring the backup host

Before performing the backup, you must configure your backup host where it stores your EPod V2 data.

1. Open the EPod V2 **Backup & Restore** tab in your EPod V2.
  1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon and open **Settings**.
  2. Select your EPod V2 and click the 3 dots next to it, then click **View**. It opens the EPod V2 dashboard.
  3. Click the **Backup & Restore** tab.
2. In the **Setup** area, click **Reconfigure**, then apply the the settings for the host where you backup the pod.
  1. To configure it for **SFTP** server, add the following settings:

| Parameter | Description |
| --- | --- |
| Name | Enter any convenient name for the host, in case you have more than one. |
| Storage Type | From the dropdown menu, select SFTP. |
| Port | Enter the port on which your SFTP server is running. |
| Host | Enter the hostname or IP address of the host where you backup the data. |
| Username | Enter the username Securiti uses to log into the host when backing up or restoring the pod. |
| Password | Enter the password for the username. |
| Backup Directory | Enter the full path for the directory where Securiti backups the pod, for example: `/home/securiti-admin/backups` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LT8HRMSD.png)
  2. To configure it for **PCS**, add the following settings:

| Parameter | Description |
| --- | --- |
| Name | Enter any convenient name for the host, in case you have more than one. |
| Storage Type | From the dropdown menu, select Private Cloud Storage. |
| Storage | From the drop down menu, select cloud provider where you have configured your PCS. Currently, it supports the following cloud providers: - AWS - GCP |
| Path | Enter the full path where Securiti backups the pod, for example: `/home/securiti-admin/backups` |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CGRP09D0.png)
3. Click **Test & Activate Connection**.

Securiti tests the connection using the settings and credentials you entered. If the test succeeds, Securiti sets the connection status to Connected.

If the test fails, double-check the settings and credentials and try again.

### Backing up an EPod V2

#### To backup an EPod V2 immediately:

1. Open the EPod V2 **Backup & Restore** tab in your EPod V2.
  1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon and open **Settings**.
  2. Select your EPod V2 and click the 3 dots next to it, then click **View**. It opens the EPod V2 dashboard.
  3. Click the **Backup & Restore** tab.
2. (Optional) Under the Backup Now in the Backup Information section, review the following settings, which are applied by default:

| Name of field | Usage |
| --- | --- |
| Configuration | This option contains the EPod V2’s connector configurations to keep the currently applied settings. |
| Database | This option contains Data for completed and Incremental Scans. |
3. Click **Backup Now**.

![Take_backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-025c3d25-6a75-ff4a-7bfc-9b6b8f3b8bfd(2).png)

### Configuring recurring backups

Configuring recurring backups in EPod V2 automatically triggers backups after each scheduled cycle, either hourly, weekly, or monthly. Follow these steps to set it up.

1. Open the EPod V2 **Backup & Restore** tab in your EPod V2.
  1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon and open **Settings**.
  2. Select your EPod V2 and click the 3 dots next to it, then click **View**. It opens the EPod V2 dashboard.
  3. Click the **Backup & Restore** tab.
2. In the Setup Recurring Backup area, click **Edit**.
3. Use the tools to set the backup frequency, then click **Save**.

![recurring_backup_setup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2ca9148-2eb9-fbc0-d9a5-d3bd572ff046(2).png)

### Restoring an EPod V2 from a previous backup to the same cluster

To restore your EPod V2 data from the previous backup, perform the following steps.

1. Open the EPod V2 **Backup & Restore** tab in your EPod V2.
  1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon and open **Settings**.
  2. Select your EPod V2 and click the 3 dots next to it, then click **View**. It opens the EPod V2 dashboard.
  3. Click the **Backup & Restore** tab.
2. In the **Restore from Backup** area, use the **Restore from Backup and Till** calendar tools to define a date range from which to choose a backup.
3. Click **Show Backups** to display all backups within the date range.
4. From the **Select Backup** menu, choose the backup you want to restore.

![restore_backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9248f030-053e-d5e7-992d-a70652e2a5b8(2).png)
5. Click **Restore Backup**.

Securiti restores the pod from the selected backup.

#### Generate recent logs

If you encounter an error or configuration problem during the backup, you can download and review the pod logs. This provides the logs from the past 3 hours to help you investigate any recent issues. To obtain the log report:

- On the **Backup & Restore** tab, and next to the Pod Diagnostic Report, click **Generate Report**. ![diagnostic_report.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-20bd3039-7d12-ab33-5c1c-c672c03cf9c6(2).png)

It downloads a **.tar** file containing the relevant log files into your system storage. You can review the log files to investigate and resolve the errors.

> [!NOTE]
> **Note**
> 
> If the Generate Report button is disabled, you must activate your pod to generate and download the logs.

## Related

- [EPod V2 installation in Securiti](/epod-v2-installation.md)
- [Prerequisites for EPod V2](/prerequisites-for-epod-v2.md)
