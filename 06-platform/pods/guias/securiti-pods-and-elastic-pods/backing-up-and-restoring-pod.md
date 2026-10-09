---
title: "Backing up and restoring pods"
slug: "backing-up-and-restoring-pod"
updated: 2026-04-06T14:16:30Z
published: 2026-04-06T21:00:01Z
canonical: "helpcenter.securiti.ai/backing-up-and-restoring-pod"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Backing up and restoring pods

You can backup Securiti pods to remote locations, and also restore them from the backups. First, you configure the backup host. After that, you can do immediate backups, schedule recurring backups, and restore a pod from a previous backup.

Securiti supports the following sources for storing backups:

| Source | Description |
| --- | --- |
| Secure File Transfer Protocol (SFTP) | It is your existing FTP server with its port open. It must be accessible from the pod. |
| Private Cloud Storage (PCS) | It is your existing PCS. It only supports the PCS from AWS and GCP. If you have not configured PCS already, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |

### Data backed up on pods

During the backup process on Securiti pods, specific types of data are backed up to ensure a comprehensive recovery. The data backed up includes:

- **Configuration**:

It backs up all the pod’s relevant connector configurations.
- **Database**:

It backs up data for the completed and incremental scans from the following databases:
  - Redis
  - Postgres
  - ElasticSearch
  - MinIO

> [!NOTE]
> Note
> 
> - It does not backup database configurations. It only backs up the data stored in the databases.
> - The backup process might take several hours to complete, depending on the size and number of files being backed up. As the amount of data increases, the total backup and restore time might also increase accordingly.
- **Disk directories**:

Backup includes specific directories that contain information specific to the pod.

| Folder name | Folder details |
| --- | --- |
| /certs | It contains certificates that you provide for connecting to the Data Systems. |
| /table-training-samples | It contains the table rows classified during the scans. |
| /source-queue-dumps | It contains the source queue’s dump file created when you pause the scan job. |
| /drivers | It contains the library bundle that enables our app to connect to the data sources. |

#### Data not backed up during the process

The automatic backup process specifically does not include **/secrets** directory because it contains secret credentials and authorization-related information. You can backup this directory manually depending on your requirements. See the directory below.

- `&lt;SECURITI_INSTALLATION_DIR&gt;/securiti-app/secrets`

### Configuring the backup host

1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, select **Settings**.
3. On the System Settings menu, choose **Deployment** > **Pods**, then click a pod.
4. Click the **Backup & Restore** tab.
5. In the **Setup** area, click **Reconfigure**, then apply the the settings for the host where you backup the pod.
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
6. Click **Test & Activate Connection**.

Securiti test the connection using the settings and credentials you entered. If the test succeeds, Securiti sets the connection status to Connected.

If the test fails, double-check the settings or credentials and try again.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RCFISEA5.png)

### Backing up a pod

To backup a pod immediately:

1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, select **Settings**.
3. On the System Settings menu, choose **Deployment** > **Pods**, then click a pod.
4. Click the **Backup & Restore** tab.
5. Under the **Backup Now** in the **Backup Information** section, apply the following settings:

| Name | Usage |
| --- | --- |
| Configuration | This option is marked by default. It includes the pod’s connector configurations to keep the currently applied settings. |
| Database | This option is marked by default. Data for Completed and Incremental Scans by Securiti pods. |
| (Optional) Disk Directories | Mark the checkbox to include specific folders that contain important pod files. |
6. Click **Backup Now**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NWFJU5PF.png)

Securiti backs up the pod.
7. Refresh your browser to update the **Last Successful Backup** field.

### Configuring recurring backups

1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, select **Settings**.
3. On the System Settings menu, choose **Deployment > Pods**, then click a pod.
4. Click the **Backup & Restore** tab.
5. In the Setup Recurring Backup area, click **Edit**.
6. Use the tools to set the backup frequency, then click **Save**.

![backup_restore-scheduler.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-157b3ccb-1c53-b7d5-8495-bfe0cd51d655(2).png)

### Restoring a pod from a previous backup to the same machine

1. To open the main menu, from the upper left corner of the left navigation bar, click the Jewel icon.
2. From the Platform Services section in the new navigation, select Settings.
3. On the System Settings menu, choose **Deployment** > **Pods**, then click a pod.
4. Click the **Backup & Restore** tab.
5. In the **Restore from Backup** area, use the **Restore from Backup** and **Till calendar** tools to define a date range from which to choose a backup.
6. Click Show Backups to display all backups within the date range.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TN5VFJD4.png)
7. From the **Select Backup** menu, choose the backup you want to restore.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Q71WBWD6.png)

> [!NOTE]
> Note
> 
> During backup, you can choose to include Disk Directories. However, during pod restoration, if Disk Directories were backed up, they restore automatically, and you cannot skip them in the restore process.
8. Click **Restore Backup**.

Securiti restores the pod from the selected backup.

> [!NOTE]
> Note
> 
> It does not show the progress of restoration process.

### Restoring a pod from a previous backup to a new machine (disaster recovery)

1. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, select **Settings**.
3. On the System Settings menu, choose **Deployment > Pods**, then click the failed pod that you are replacing.
4. Click the **Master Node** tab.
5. On the **Master Node** tab, choose More **Options > Revoke**. On the confirmation popup, click **Yes**, **Continue**.
6. Reinstall the pod as described in one of these procedures:

Automated pod installation (cluster version v1.28+)

Manual pod installation (cluster version v1.28+)
7. Click the **Backup & Restore** tab.
8. In the Restore from Backup area, use the Restore from Backup and Till calendar tools to define a date range from which to choose a backup.
9. Click **Show Backups** to display all backups within the date range.

From the **Select Backup** menu, choose the backup you want to restore.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TN5VFJD4.png)

> [!NOTE]
> Note
> 
> During backup, you can choose to include **Disk Directories**. However, during pod restoration, if **Disk Directories** were backed up, they restore automatically, and you cannot skip them in the restore process.
10. Click **Restore Backup**.

Securiti restores the pod from the selected backup.

### APIs for backup and restore

Securiti provides APIs for the backup and restore process, making it easier, automated, and flexible. It lets you manage operations with your own custom automation. You can use CLI commands or integrate with your preferred programming language through the API. See the following references for API documentation.

- [API to create the backup of a pod](https://securiti-doc-router.securiti.ai/modules/appliances/apidocs/index.html)
- [API to fetch the backup protocol connection status](https://securiti-doc-router.securiti.ai/modules/appliances/apidocs/index.html)
- [API to retrieve the restore point](https://securiti-doc-router.securiti.ai/modules/appliances/apidocs/index.html)
- [API to create a restore point](https://securiti-doc-router.securiti.ai/modules/appliances/apidocs/index.html)

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Automated secondary node installation (cluster version v1.28+)](/pod-automated-secondary-node-installation.md)
- [Manual secondary node installation (cluster version v1.28+)](/pods-manual-secondary-node-installation.md)
