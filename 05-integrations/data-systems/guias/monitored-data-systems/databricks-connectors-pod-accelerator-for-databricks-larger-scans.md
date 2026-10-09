---
title: "Pod accelerator for Databricks larger scans"
slug: "databricks-connectors-pod-accelerator-for-databricks-larger-scans"
updated: 2025-10-30T19:48:48Z
published: 2025-11-03T06:14:28Z
canonical: "helpcenter.securiti.ai/databricks-connectors-pod-accelerator-for-databricks-larger-scans"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Pod accelerator for Databricks larger scans

Databricks is a cloud-based platform with unified analytics and machine learning workspace. Databricks takes advantage of Apache Spark infrastructure, letting users scale their computing resources up or down based on the demands of their workloads.

Apache Spark is widely used in industries for large-scale data processing tasks, and it has become a good choice for organizations dealing with diverse data processing requirements.

Spark framework consumes large data, distributes the data into manageable chunks, and then performs content classification (CC) on this chunk of data within the same process. A single large file can be distributed across multiple executors and processed parallelly. Spark can give the whole view of the data or statistics of scanning without relying on central databases. Scaling is horizontal and very robust, tried and tested for very huge data loads.

> [!NOTE]
> **Note**
> 
> The **Hyperscale scan feature** is a premium feature available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable it for your Securiti tenant.

> [!NOTE]
> **Note**
> 
> Once you attach the Spark instance to your Databricks account, Securiti performs all the scan jobs on Spark.

To use the hyperscale scan feature for Databricks, follow these steps:

1. Create a Pod or an elastic Pod to connect with Databricks for scanning. See [configure Pod or elastic Pod](/v1/docs/securiti-pods-and-elastic-pods) for more information.
2. Create a Databricks instance for scanning:
  1. Create Databricks credentials to be used by Securiti to connect to Databricks. See [Acquire credentials in Databricks using username and password](/v1/docs/acquire-credentials-in-databricks-using-username-and-password) for more information.
  2. Grant permissions and obtain credentials that you are using in Databricks, see [Grant permissions and obtain credentials and drivers in Databricks](/v1/docs/grant-permissions-and-obtain-credentials-in-databricks). You require these permissions when you create a Spark instance.
  3. Create a particular Databricks instance on the Databricks domain. See [Configure Databricks Instance for AWS cloud](https://www.databricks.com/product/instance-types) for more information.

> [!NOTE]
> **Note**
> 
> The recommended instance type is **i3.xlarge** as it provides significant scalability.
3. Configure connection to the Spark instance in Securiti for using hyperscale scan for Databricks. See [Create a Spark instance](https://docs.google.com/document/d/1gq-PZdfKppxE9Rx3cfwjirRAEq5Q6jAsS9vpnx6jOkc/edit#heading=h.onlohx3fqpr9) for more information.
4. Enable Databricks to use the Spark instance. See [Activate the Databricks connector](/v1/docs/activate-the-databricks-connector-in-securiti) for more information.
5. Configure the discovery scan for Databricks. See [Configure discovery scans for Databricks](/v1/docs/configuring-discovery-scans-in-databricks) for more information.

> [!NOTE]
> **Note**
> 
> To select an instance type of Databricks cluster for hyper scale scan, the instance should have at least 4 VCPUs and 30.5GB memory as recommended by [AWS](/v1/docs/securiti-pods-and-elastic-pods) for **i3.xlarge** instance.

### Creating a Spark instance

Configuring Databricks on Apache Spark involves setting up a Databricks workspace and configuring the necessary Spark settings.

#### Prerequisites

Follow the steps below before you configure a Spark instance:

1. [Creating Databricks workspace](https://docs.databricks.com/en/administration-guide/workspace/quick-start.html) to configure AWS resources. For this make sure you have the VPC and NAT gateway already configured.
2. Creating Databricks credentials to be used by Securiti to connect to Databricks, For more information, see [Acquire credentials in Databricks using username and password](/v1/docs/acquire-credentials-in-databricks-using-username-and-password).
3. Granting permissions and obtaining credentials that you are using in Databricks. For more information, see [Grant permissions and obtain credentials and drivers in Databricks](/v1/docs/grant-permissions-and-obtain-credentials-in-databricks).
4. Create a particular Databricks instance on the Databricks domain. For more information, see [Configure Databricks Instance for AWS cloud](https://www.databricks.com/product/instance-types).

Below are the general steps to configure Apache Spark for Databricks:

1. In Securiti Settings, go to **Deployment**, and select **Spark**.
2. Click **+ Create Instance** and apply the following settings.

| Parameter | Description |
| --- | --- |
| Accelerator | Accelerator toggle uses the hyper scale features for detections and classification of Sensitive data elements for your data system. To use the hyper scale scan, enable the Accelarators toggle and choose Spark on Databricks. |
| Host URL | It is the host URL where your Databricks workspace is hosted. Enter the Databricks host URL you recorded in [Databricks instance types](https://www.databricks.com/product/instance-types). Example: - *https://<account-id>.cloud.databricks.com* |
| Access Key | It is the name of the Databricks access key. It lets external applications or services interact with Databricks resources, such as managing clusters, submitting jobs, reading and writing data, and performing administrative tasks. Enter the access key you have recorded in [Acquire credentials in Databricks using username and password](/v1/docs/acquire-credentials-in-databricks-using-username-and-password). |
| Worker Node Type | It is the worker node type ID. Worker nodes fall under the Spark cluster. They are responsible for executing computations, storing data, managing resources, and ensuring fault tolerance in distributed data processing applications. Enter the worker note type ID you have recorded in [Databricks instance types](https://www.databricks.com/product/instance-types). |
| Driver Node Type | It is the driver node type ID and falls under the Spark cluster. The driver node is responsible for orchestrating the Spark application, including managing the overall execution flow, distributing tasks to worker nodes, and aggregating results. Enter the driver note type ID you have recorded in [Databricks instance types](https://www.databricks.com/product/instance-types). |
| Minimum No. of Workers | You have the flexibility to set the minimum number of worker notes according to your requirements. Enter the minimum number of workers you recorded in [Databricks instance types](https://www.databricks.com/product/instance-types). |
| Maximum No. of Workers | You have the flexibility to set the maximum number of worker notes according to your requirements. Enter the maximum number of workers you recorded in [Databricks instance types](https://www.databricks.com/product/instance-types). |
| AWS instance profile ARN | Amazon Resource Names (ARNs) are used to uniquely identify and grant permissions to AWS resources. Databricks, when hosted on AWS, also has its own set of ARNs for different resources. Enter the AWS instance profile ARN configured for Databricks from [Configure S3 with the ARN profile](https://docs.databricks.com/en/connect/storage/tutorial-s3-instance-profile.html). > [!NOTE] > **Important** > > It is important to check the AWS documentation for the most up-to-date and accurate information regarding Databricks ARNs, as specifications and formats may change over time. For information on managing instance profiles in Databricks workspace, see [Manage instance profile in Databricks workspace](https://docs.databricks.com/en/administration-guide/workspace-settings/manage-instance-profiles.html). |
| Tags | In Databricks, these tags provide a way to categorize and organize resources based on your specific needs, making it easier to manage, track, and analyze them. Enter the custom tags according to your requirements. |
| Storage Type | It is recommended to use AWS S3 as a storage type to get optimal performance. Enter the name of the storage type where you want your detection and classification data to be stored during the scanning process. Enter the storage type and AWS S3 permissions that you configured in [Configure S3 access with the ARN instance profile](https://docs.databricks.com/en/connect/storage/tutorial-s3-instance-profile.html). |
| File Path | Enter the path and choose a region. |
| Authentication Method | Choose a specific authentication method to securely authenticate and access the Databricks environment based on your identity and authorization policies. If you are selecting IAM roles as an authentication method, either you can use the same ARN or assign that to the appliance. Assign Read, Write, and Delete permissions and assign one role to the appliance as well, or use the same instance profile to assign to the appliance. For IAM Roles only - Enter the AWS account and the IAM role information you recorded in the AWS Management console. For more information, see [Configure S3 access with ARN instance profile](https://docs.databricks.com/en/connect/storage/tutorial-s3-instance-profile.html). |

> [!NOTE]
> **Note**
> 
> Once you attach the Spark instance to the Databricks then Securiti performs all the scans on Spark.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
