---
title: "Using the cluster status dashboard"
slug: "using-the-cluster-status-dashboard"
updated: 2026-07-17T07:41:02Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/using-the-cluster-status-dashboard"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Using the cluster status dashboard

The Cluster Status dashboard shows the stats of the pod. It helps see the current usage of resources and active jobs. It improves your allocation of system resources if it requires a scale-up or scale-down. It also helps you see which scan jobs are running, in the queue, or stopped.

To open the pod’s Cluster Status dashboard:

1. In Securiti, from the top left corner of the Dashboard, click the **Jewel** icon.
2. From the Platform Services section, click **Settings > Deployment > Pods**.
3. Select the pod you want to open the **Cluster Status** page for. On the right side of the selected pod, click **Options** (three dots), then click **View**.
4. On the pods dashboard page, click the **Cluster Status** tab to open the pod’s status page.

The Cluster Status tab displays the following categories of data.

- CPU and RAM usage
- Cluster Utilization
- Application Performance
- Cluster Service Status
- Pending Jobs
- Dynamic Pods Status

## CPU and RAM usage

At the top of the **Cluster Status** tab, the first widgets show the machine details and resource usage of the pod.

It helps identify the resource utilization which are critical for the performance of a pod and analyze scaling up or scaling down. System specifications and usage widget displays the following elements:

| Status | Specification |
| --- | --- |
| Node | - No. of nodes - Architecture - Operating system - OS images |
| CPU usage | - Usage percentage - No. of CPU cores |
| RAM usage | - Usage percentage - Total RAM |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-bqztn8ws.png)

## Cluster utilization

**Cluster Utilization** shows you three trendline widgets showing the pod’s utilization details of system resources. It lets you visualize the data from the last 3 hours up to the last 5 days. It helps you understand the pod’s frequency of working and resource utilization. The trendline widgets are:

| Widget name | Widget description |
| --- | --- |
| Pod root disk usage | It displays the total usage of the root directory (main installation directory) as a trendline. |
| Pod CPU usage | It displays the total amount of CPU the pod is currently using. |
| Pod memory usage | It displays the amount of total RAM the pod is currently using. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-7aevb8wa.png)

## Application performance

This section provides details about the application’s performance. It gives insights into activities like scanning jobs, task scheduling, history of scans, and inventory scan results. It lets you identify if any of the jobs failed or if duplicates of any job are running.

It includes the following major categories:

- Discovery scans
- Inventory scans

### Discovery Scan

This system provides comprehensive insights into data scan jobs operating across various data storage, detailing the classification processes, and offering a complete overview of the data scanning jobs.

The data processing jobs have one of the following three states.

| Data processing insights | Description |
| --- | --- |
| Queued-up | These jobs are in the Producer Queues waiting to be picked up by Consumer Queues. All the executable jobs first enter the Producer Queues. |
| In-flight | These jobs are in the Consumer Queues, which are ready to execute. These jobs move to the Downloaders for execution. |
| In-progress | These jobs are currently downloading data for scanning. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-y8jmuf1h.png)

Every job state can have the following insights:

| Category | Description |
| --- | --- |
| Crawler | It displays the number of crawlers that identify and scan for the data storage objects. Once it identifies all the objects to scan and collects relative information, it stops. |
| Objects to scan | It displays the number of objects to scan. |
| Overall | It refers to the total number of jobs or scan actions. |

In the discovery scan jobs, you can see both the results from the currently running scan jobs and the history of completed scan jobs.

### Current scan status

The **Current Scan Status** widget displays the data scanning job statuses that are currently in progress or the queue state. It lets you review the number of scan jobs along with the job details. It also displays the total number of jobs each state contains within the job status widget. The number displays how many jobs are currently in this state. It can contain the following job states.

| Job state | State description |
| --- | --- |
| Scheduled | These scan jobs are in the queue and ready to be picked with a sequence. |
| Running | These scan jobs are currently running inside the pod and actively scanning the data. |
| Paused | These scan jobs are currently in a paused state. |
| Paused scheduled | These scan jobs are in the process of transitioning to a paused state. Once this operation completes, it successfully transitions to the pause state. |
| Cancelled | These jobs are the cancelled jobs. |
| Cancelled scheduled | These jobs were in the schedule but cancelled by the user. |
| Error | These jobs encountered errors while executing and ended unsuccessfully. |
| Time out | These scans did not complete or initiate within the set time frame. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-d7qxqlem.png)

It also lets you view the jobs list and details of each job state, along with the details of the job. To see the details:

1. Select the state of the job you want to open details for.
2. To the right side of the job status within the job status widget, it displays a hyperlinked number showing the total number of jobs it contains. Click on the number. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-7ew6xlxb.png)

It opens the **Discovery Scans** popup. It displays the following fields within the popup.

| Field title | Field description |
| --- | --- |
| Scan Name | It displays the main title of the scan job. Clicking on this title redirects you to the **Discovery Scans** page, where you can see the details of this job. |
| Latest Scan Results | It shows the latest results of the scan job. Click on **View Results**, and it redirects you to the Sensitive Data Intelligence page, where you can see all the results of this job in real time. The results can take you to either the Structured Data or Unstructured Data page. |
| Job Status | It displays the current status of the jobs. |
| Discovery Scan Description | It displays the description of the job if you have added any. Otherwise, it shows a blank line. |
| Target Type | It shows the storage target the job is running against. For example, SFTP, or Amazon S3. |
| Column Selector | It lets you select specific columns to see on the **Discovery Scan** popup. It provides the following features: - Select and display specific lists of columns. - Restore the default list selection. |

1. To close it, at the bottom of the popup, click Close.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-d39y7hal.png)

### Scan History

The **Scan History** widget provides a comprehensive list of job types that are either complete or cancelled, meaning they are no longer in any active or ready queue. It displays the total number of jobs for all supported categories. However, it doesn’t display the jobs popup showing all details and metadata of the job's history.

It displays the following categories of job statuses:

| Job state | State description |
| --- | --- |
| Scheduled | These scan jobs are in the queue and ready to be picked with a sequence. |
| Running | These scan jobs are currently running inside the pod and actively scanning the data. |
| Paused | These scan jobs are currently in a paused state. |
| Paused scheduled | These scan jobs are in the process of transitioning to a paused state. Once this operation completes, it successfully transitions to the pause state. |
| Cancelled | These jobs are the cancelled jobs. |
| Cancelled scheduled | These jobs were in the schedule but cancelled by the user. |
| Error | These jobs encountered errors while executing and ended unsuccessfully. |
| Time out | These scans did not complete or initiate within the set time frame. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-rh8iokka.png)

### Inventory Scan

An inventory scan provides details about the metadata of in-scope data storage for the scan. It scans the storage services and the relevant information. It displays the following types of job scan statuses:

| Job state | State description |
| --- | --- |
| Scheduled | These scan jobs are in the queue and ready to be picked with a sequence. |
| Running | These scan jobs are currently running inside the pod and actively scanning the data. |
| Paused | These scan jobs are currently in a paused state. |
| Paused scheduled | These scan jobs are in the process of transitioning to a paused state. Once this operation completes, it successfully transitions to the pause state. |
| Cancelled | These jobs are the cancelled jobs. |
| Cancelled scheduled | These jobs were in the schedule but cancelled by the user. |
| Error | These jobs encountered errors while executing and ended unsuccessfully. |
| Time out | The scan did not complete or initiate within the set time frame. |

The **Scan Status** widget displays all states of jobs under inventory scans. The number against each type of job shows the total number of jobs in that state. To view the list of jobs:

1. Select the scan status to list its jobs.
2. Click on the number next to the scan status. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-7511nx71.png)

This opens the **Inventory Scan** Insights popup listing all the jobs. It displays the following fields within the popup:

| Field name | Field description |
| --- | --- |
| Connector ID | It shows the connector ID that lets you search the jobs associated with this connector ID. |
| Job Status | It displays the job status. For example, cancelled. |
| Datasource ID | It displays the unique ID of the data source the scan runs against. |
| Start Time | It displays when the job started. |
| End Time | It displays when the job ended. |
| Ingestion Completed | It displays whether the ingestion is completed or not. |
| Column Selector | It lets you select specific columns to see on the Discovery Scan popup. It provides the following features: - Select specific lists of columns - Restore the default list selection |

1. To close the popup, at the bottom, click **Close**.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-fatfvx0x.png)

It also displays the trendline widgets showing the following data within the timeframe.

| Trendline name | Trendline description | Trendline duration |
| --- | --- | --- |
| Data Scan Throughput (GB/h) | It displays the trendline of data scans performed in Gigabytes per hour. It lets you analyse how much data you scan. | It visualizes data from the past 6 hours to a maximum of 2 days. |
| Application Replica Scaling | It displays the total and in use replicas, which are responsible for scanning the data. At the bottom of the trendline, **Max Replias** value displays the total number of scanning replicas. | Hovering over the trending line visualizes how many replicas are currently working to scan the data. |
| Task Queue | It displays the trendline of the number of jobs in the queue. As more processes execute from the queue, the trendline decreases. | It visualizes data from the past 15 minutes to a maximum of 3 hours. |
| QoS Queue | It displays the trendline of the priority queue, where the jobs with high priority execute before other jobs. | It visualizes data from the past 15 minutes to a maximum of 3 hours. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-y9nv3phb.png)

## Cluster Service Status

**Cluster Service Status** widgets contain all the services that are in support and available within the cluster to run the pod successfully. It includes storage, monitoring, and management services of various kinds, which are also prerequisites for the pod to run in a cluster.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-P5R16TPN.png)

You can view the status of some services from the UI. To view this:

1. Select a service to view its status.
2. Click on the hyperlinked View Status next to the name of the service. If you don’t see it, the status for that service is not available.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-nlomjxkt.png)

It opens a service titled popup page that contains a table displaying the status of the service with the following information:

| Title | Description |
| --- | --- |
| Status | It displays the health status of the service. |
| Label | It shows which component of the service is unhealthy if the service is unhealthy; otherwise, it remains empty. |
| Message | It contains a detail about the service. It usually displays the activities and details about the service. |

1. To close the popup, at the bottom, click Close.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-w9oa5n40.png)

## Pending jobs

The **Pending Jobs** section lists the jobs that have been initialized but are not in the running state. This section shows the jobs that are initialized but not yet in the running state. You can use this information to help troubleshoot pod issues relating to stalled jobs.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/using-the-cluster-status-dashboard-en-image-ycywbxvj.png)

## Dynamic pods status

The **Dynamic Pods Status** displays the current state of non-core service pods in the environment. It highlights pods that are actively running, have recently completed their tasks, or have failed. This view helps monitor the health and activity of auxiliary components beyond the core system services. It displays the following information:

| Title | Description |
| --- | --- |
| K8s Pod Name | It displays the title of the pod. |
| Data System Instance Type | It displays the title of the data storage that the instance is scanning against. |
| Connector ID | It displays the connector ID through which it connects to the data storage for scanning. This ID helps identify the specific connector. |
| Status | It displays the status of the pod’s job. |

It can contain multiple pages of data; therefore, you can swipe between different pages. To swipe to the next or previous page, at the bottom left of the Dynamic Pod Status, click the **left** or **right arrow** button. Right arrow swipes to the next page, while left arrow swipes to the previous page.

## Related

- [Pod installation (cluster version v1.28+)](/pod-installation-cluster-version-v128.md)
- [Pod troubleshooting (cluster version v1.28+)](/podtroubleshooting.md)
