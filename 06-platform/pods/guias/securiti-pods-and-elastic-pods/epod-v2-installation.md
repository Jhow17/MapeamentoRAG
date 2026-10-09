---
title: "EPod V2 installation in Securiti"
slug: "epod-v2-installation"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/epod-v2-installation"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# EPod V2 installation in Securiti

This procedure covers pre-installation steps in Securiti and installation steps into your own Kubernetes infrastructure.

## Installing a cluster in Securiti

To install EPod V2, watch the following video and proceed with the steps below.

[Embedded content](https://player.vimeo.com/video/1064990407)

On the Securiti portal:

1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon.
2. From the Platform Services section, click **Settings > Deployment > Elastic Pods V2**.
3. Near the right top of the page, click **+ New Cluster** and choose **Custom Install**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CY6TIOQ0.png)
4. Add the following information in the **Basic Information** tab:

| Field | Description |
| --- | --- |
| Cluster Name | Cluster Name is a unique cluster name to track the pod later. |
| Namespace | Enter the namespace within the Kubernetes cluster where you wish to deploy your application. Make sure the namespace already exists, otherwise, an application might fail the deployment. |
| Kubernetes Distribution | From the dropdown menu, select your Kubernetes distribution where you are installing EPod V2. It automatically selects **Capacity Type Node Selector** values in the **Customization** tab according to your selected distribution. It impacts the following values: - Installation directory - Storage class - Capacity Type Node Selector > [!NOTE] > Note > > If you select **Red Hat Openshift** from the dropdown menu, it introduces a new **OpenShift SCC** tab. For more information, see next optional step. |
| Version | Select the EPod V2 version you want to install or upgrade to. The menu lists the recent published releases, including patch releases. If you do not select a version, EPod V2 uses the latest published release. For existing EPod V2, you can select a version higher than your existing version. EPod V2 uses the version you select for all installation artifacts, including the container images, Helm chart, and installation command. Select the version before you stage the container images in your private registry, so the entire process stays aligned with a single version. |
| (Optional) Add Notes | Notes are optional and help you add some important information you need to keep within the pod. |
| Cluster Location | Enter the cluster location details, which are **Country**, **State/Region**, and **City**. |
| Primary Owner | Select the primary owner from the drop-down menu. By default, the user who is creating the pod is the owner. Enable the **Add co-owner** toggle to add a co-owner. Enabling the **Send notification to all owners** toggle sends the notifications to owners and co-owners. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MQLVBOL2.png)Click **Save and Continue** to proceed.
5. (Optional) If you select **Red Hat OpenShift** in **Kubernetes Distribution** dropdown menu in previous step, a new tab **OpenShift SCC** appears. It contains Security Context Constraints (SCC) for the OpenShift deployment to enable certain features in EPod V2. See the table below for available SCCs:

| Supported SCC | Description | Requires Root access |
| --- | --- | --- |
| NFS/SMB scanning | It enables Epod V2 to connect and scan NFS/SMB data systems. | ✅ |
| Spark Operator | It enables EPod V2 to include the Spark service-account SCC bindings. | ❌ |
| Log Upload | It enables EPod V2 to upload logs to Securiti and display on SaaS application. | ✅ |

To enable any of the available SCCs, proceed with the following steps:

1. Enable the toggle that you wish to enable for your EPod V2.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XP7GC7T9.png)
2. Click **Download SCC Manifest**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-07I4D2Y1.png)

It downloads the SCC manifest `YAML` file into your system.
3. (Optional) Open the file in an editor and update the namespace values in the entire file if you have a different namespace title.
4. Apply the manifest file to your cluster using the following command:

```plaintext
kubectl apply -f securiti-pod-scc.yaml
```

> [!NOTE]
> Note
> 
> If you enable **NFS/SMB scanning** or **Log Upload**, you must enable **Sys Admin** toggle in Customization tab because both require root/administrative access.

After applying, click **Continue**.

1. On the **Select Registry** page, you have two options for choosing a registry to pull application images:

After making your selection, click **Save and Continue**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZCI9V8RS.png)
  - Select **Install from** Securiti **Registry** option to pull application images using Securiti’s registry.

This lets you fetch images from our registry directly and makes the process simple and quick.
  - Select **Install from Custom Registry** if you own a custom registry. This is useful if your clusters are authorized to fetch images from your custom registry only.

If you selected this option, see [Using Custom Registry with Elastic Pods V2](/v1/docs/using-custom-registry-with-epod-v2) to set up a custom registry.
2. On the **Credentials File**, download the credentials file “secrets.json” if you selected **Install from** Securiti **Registry** in **step 6** above.

> [!NOTE]
> **Note**
> 
> The Credentials File stores the authentication details you require to access a Kubernetes cluster. It typically includes usernames, passwords, or API tokens in a secure format such as a kubeconfig YAML file. This file lets you interact with the cluster using tools like kubectl by specifying the cluster and user context.
  1. If you selected **Install from** Securiti **Registry** in the **step 6** above, click **Download Credentials File** and apply the file to your cluster with the following command:

```bash
kubectl apply -f secret.json -n <namespace>
```

Replace **<namespace>** variable with your existing namespace of K8s. If you don’t provide a namespace, it applies to the default namespace. You can create a new namespace using the following command.

```bash
kubectl create namespace default
```

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-X66EVKLU.png)
3. On **Preflight Checks**, validate that your Kubernetes cluster meets all requirements before installation.

> [!NOTE]
> **Note**
> 
> Currently, Preflight checks validate the following permissions:
> 
> - Create
> - Update
> - Read
> - Delete
> 
> The above permissions are validated for the following Kubernetes resources:
> 
> - Priority classes
> - Secrets
> - Deployments
> - Persistent Volume Claims (PVC)
> - Jobs
> - Horizontal Pod Autoscaler (HPA)
> - Configmaps

Perform the following steps to validate that your Kubernetes cluster meets all requirements before installation.
  1. Copy the URL from the **Generate HELM chart URL** and download the Helm Chart file with the following command format.

```plaintext
curl "<SECURITI HELM CHART SIGNED URL>" --output <preflight-check-chart-<VERSION>.tar.gz>
```
  2. Move the downloaded Helm Chart file to your machine, from where you can run Helm Chart commands.
  3. Copy the Helm command from the **Helm Install Instructions** and execute it in the cluster to enable the validation job. Make sure to include the Helm Chart file in the command.
  4. Copy the command from the **View Results** and run it to display the results. You must validate the results and meet the missing requirements before deployment.
  5. Copy the command from the **Cleanup Command** and execute to delete the job from your cluster.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-126MCWCR.png)
4. On the **Monitoring** page:
  1. Enable the **Install Monitoring** toggle to deploy a new Prometheus alongside the Securiti pod.

If you already have a Prometheus deployed and accessible from the cluster, enter the URL for your instance. The pods then utilize it for custom metrics.

> [!NOTE]
> **Note**
> 
> Prometheus monitoring is crucial for pod monitoring and scaling. Without monitoring, auto-scaling will not work. If using an existing Prometheus deployment, ensure that the specified service is accessible to the pod.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BYSG84YF.png)
  2. (Optional) If you already have a Prometheus deployed and accessible from the cluster, proceed with the following steps:
    1. Create a service monitoring configuration file and name it as `servicemonitor.yaml`. See the example file content.

```yaml
apiVersion: monitoring.coreos.com/v1
kind: ServiceMonitor
metadata:
  name: redis-metrics
  namespace: monitoring  # <-- Change this to the namespace where Prometheus is deployed
  labels:
    release: test-prom  # <-- Change this to match your Prometheus release
spec:
  selector:
    matchLabels:
      app.kubernetes.io/component: metrics
  namespaceSelector:
    matchNames:
      - default  # <-- Change this to the namespace where your Redis service is running
  endpoints:
    - port: http-metrics
      interval: 30s
      honorLabels: true
```

You must not use this content as it is. Instead, update the content where it is mentioned.
    2. Execute the following commands sequentially on your Kubernetes Cluster to apply the configurations:
      - Verify that ServiceMonitor and Prometheus Custom Resource Definitions (CRDs) exist.

```bash
kubectl get crd servicemonitors.monitoring.coreos.com
kubectl get crd prometheuses.monitoring.coreos.com
```
      - Verify if the Prometheus instance is running.

```bash
kubectl get prometheus -A
```
      - Apply the ServiceMonitor configuration YAML.

```bash
kubectl apply -f servicemonitor.yaml
```
      - Verify if the ServiceMonitor is created in the default namespace.

```bash
kubectl get servicemonitor -n default
```
      - Wait for the Prometheus Operator to reconcile the configuration.

```bash
sleep 60
```
      - Get the service URL for your Prometheus instance.

```bash
kubectl get svc -n monitoring
```
      - Execute the command in the config controller pod for debugging or metric checks.

```bash
kubectl exec -it deploy/priv-appliance-config-controller -n <namespace> -- sh
```
      - Query Prometheus to check if the redis_key_size metric is available.

```bash
curl -s "http://test-prom-kube-prometheus-prometheus.monitoring.svc.cluster.local:9090/api/v1/query?query=redis_key_size"
```
    3. Disable the Install Monitoring toggle and add the accessible URL of the Prometheus service with its port. For example, `http://prometheus.monitoring.svc.cluster.local:9090`. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H0P4ZT3W.png)
  3. Click **Save and Continue**.
5. On the **Metrics** page:
  1. Enable the **Install Metrics** toggle to deploy the metrics server alongside the Securiti pod if your Kubernetes cluster does not already have a Metrics server running.

Securiti requires a Metrics server in the cluster for monitoring resource utilization.
  2. Click **Save and Continue** to continue.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MBSVQZ38.png)
6. In the **Redis** page:

> [!NOTE]
> Note
> 
> You can migrate your EPod V2 database from internal to external after installation. For more information, see [Migrating EPod V2 internal database to external](/latest/docs/migrating-epod-v2-internal-database-to-external).
  - To install the Redis database internally in your Kubernetes cluster:
    1. Enable the **Install Redis** toggle.
    2. Select the **Redis Size** dropdown menu to list available memory sizes.
    3. Select any predefined memory size for your Redis database from the available list.

> [!NOTE]
> Important
> 
> Once you select a memory size, you can increase the size later on, but you can’t decrease its size.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0JHXSR84.png)

> [!NOTE]
> Note
> 
> To upgrade the internal Redis database, see [Upgrade internal database](/v1/docs/upgrade-epod-v2#upgrade-internal-databases).
  - To use your external Redis database for your EPod V2:
    1. Disable the **Install Redis** toggle.
    2. Verify that your external Redis database version matches the following details.

> [!WARNING]
> Caution
> 
> The following Redis database versions are not supported:
> 
> - ElastiCache Serverless
> - Any Redis with cluster support

| Database | Supported version | Description |
| --- | --- | --- |
| Redis | ElastiCache Redis OOS 7.x | Managed Redis by AWS (open source 7.x) |

See the benchmark for Redis supported in AWS environments below.

| Specification | Value |
| --- | --- |
| Service | AWS ElastiCache for Redis |
| Engine version | 7.1.0 |
| Cluster mode | Disabled (standalone) |
| Instance/Node type | cache.r7g.large (13.07 GiB RAM) |
| Shards | 1 |
| Number of nodes | 1 |
| Data tiering | Disabled |
    3. Enter the following details in the respective fields.

| Field name | Field description |
| --- | --- |
| Host | It is the URL that directly points to your external Redis database. It can be an IP address or a host URL. |
| Port | It is the port of the URL on which Redis is running. If you leave this port empty, it will use 6379 as a default port. |
| SSL | Check the **SSL** toggle for using TLS to connect to the Redis database. Select if your database supports TLS. |

These configurations reflect in the **values.yaml** file at step Step 2. If your Redis database contains a password, update the password manually in values.yaml file.

> [!NOTE]
> Important
> 
> - It doesn’t support a serverless ElastiCache database.
> - Redis can work without setting up a password; however, it is highly recommended to set up a strong password.
> - You can’t use one external database with multiple installed appliances. Instead, you must install a new external Redis database for each appliance.
    4. Click Save and Continue.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-I3H1ORZT.png)
7. Similar to **Redis**, on the **Elastic Search** page:

> [!NOTE]
> Note
> 
> You can migrate your EPod V2 database from internal to external after installation. For more information, see [Migrating EPod V2 internal database to external](/latest/docs/migrating-epod-v2-internal-database-to-external).
  - To install an internal Elasticsearch database in your Kubernetes cluster:
    1. Enable the **Install ES** toggle.
    2. Select the **ES Size** dropdown menu to list available memory sizes.
    3. Select any predefined memory size for your Elasticsearch database from the available list.

> [!WARNING]
> Important
> 
> Once you select a memory size, you can increase the size later on, but you can’t decrease its size.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-HOYYLA2E.png)

> [!NOTE]
> Note
> 
> To upgrade the internal Redis database, see [Upgrade internal database](/latest/docs/upgrade-epod-v2#upgrade-internal-databases).
8. To use your external Elasticsearch database in your EPod V2:
  1. Disable the **Install ES** toggle.
  2. Verify that your external Elasticsearch database version matches the following details.

| Database | Supported version | Description |
| --- | --- | --- |
| Elasticsearch | Elasticsearch ES7 | Official Elastic product (version 7) |
| OpenSearch | OpenSearch 1.3 | Forked from Elasticsearch 7.10 by AWS |

See the benchmark for Elasticsearch supported in AWS environments below.

| Specification | Value |
| --- | --- |
| Service | AWS OpenSearch service |
| Engine version | OpenSearch 1.3 |
| Instance/Node type | r7g.medium.search (1 vCPU, 8GiB RAM) |
| Number of data nodes | 1 |
| Storage type | EBS gp3 |
| Storage size | 200 GiB |
| Provisioned IOPS | 4000 |
| Provisioned throughput | 400 MiB/s |
| Dedicated master nodes | No |
  3. Enter the following details in the respective fields.

| Parameter | Description |
| --- | --- |
| Host | It is the URL that directly points to the external Elasticsearch database. It can be an IP address or a host URL. |
| Port | It is the port of the URL on which your Elasticsearch is running. If you leave this port empty, it will use 6379 as a default port. |
| Scheme | It is the connection scheme to connect with Elasticsearch using either HTTP without TLS encryption or HTTPS with TLS encryption. |
| Region | It is the cloud region for your Elasticsearch database instance. The default value for the Region field is “us-west-2”, which is AWS supported region. For any other region of AWS or any other cloud, please enter your ES region value. |
  4. (Optional) Configure the connection to external Elasticsearch with a password if required. You must set the password in **values.yaml** file.

These configurations reflect in the `values.yaml` file on [step 2](/v1/docs/epod-v2-installation#installing-in-your-kubernetes-infrastructure).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7I7KKBIE.png)
  5. Click **Save and Continue**.
9. On the **Resource Allocation** page:
  1. Insert the memory you want to allocate to Securiti application in your K8s cluster. For the minimum and maximum memory you can allocate, see the following table.

| Amount of memory allocation | Minimum | Maximum |
| --- | --- | --- |
| For Internal database | 64000 MiB (62.5 GiB) | 384000 MiB (375 GiB) |
| For external database | 64000 MiB (62.5 GiB) | 3200000 MiB (3125 GiB) |

> [!NOTE]
> **Note**
> 
> Securiti requires Memory to CPU ratio to be 4GB:1.
> 
> - Securiti deployment relies on this value to determine the allocated memory.
> - Securiti uses this value to determine the scaling of different components in the deployment.
> 
> The pods scale up to a maximum of the value specified here. If you increase the memory allocation in the cluster but don't update it here, Securiti deployment will not recognize the change.
  2. (Optional) If you want to use resource quota on install namespace, refer to the table below for resource limit:

| Number of nodes | Memory | CPU |
| --- | --- | --- |
| 1 | 131 GiB | 37 cores |
| 5 | 803 GiB | 241 cores |
| 10 | 1,643 GiB | 496 cores |
| 20 | 3,323 GiB | 1,006 cores |
| 50 | 8,363 GiB | 2,536 cores |
  3. (Optional) From the Pod Resource Profile dropdown menu, select the preferred Resource Profile for your EPod V2. When selecting ​Spark optimized​ profile, you must select extra 128 GB or memory. For more information on Resource Profiles, see [Pod Resource Profiles](/v1/docs/pods-recommended-pod-provisioning).

> [!WARNING]
> Important
> 
> - Securiti does not support two Spark Optimized profiles deployments within a single cluster. It supports only one Spark Optimized profile per Kuberneter cluster.
> - When you deploy EPod V2 with the Policy Optimized or SDI Optimized profiles, you cannot update your pod to Spark Optimized later. It is because Spark Optimized deployment creates and requires some **Custom Resource Definitions** (**CRD**) resources which Helm does not create with any other profile.
> 
> For more information on creating CRD resources of Spark Optimized profile after EPod V2 deployment, see [Pod Resource Profiles](/latest/docs/pods-recommended-pod-provisioning#pod-resource-profiles).
  4. Under **GPU Configuration** section, you can run Tritan server pods on GPU-supported nodes by specifying the number of GPU nodes and configuring tolerations. Tolerations work alongside node taints, when a node has a taint applied, it prevents other pods from scheduling on it. Adding a matching toleration here or applying the default value provided on the UI on your nodes lets EPod V2 schedule only on those tainted GPU nodes.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

To configure it, apply the following settings:

| Field | Description |
| --- | --- |
| GPU Node Count | Enter the number of GPU nodes available in your Kubernetes cluster. The value must be greater than 0. |
| Tolerations | Configure the toleration to match the taint applied to your GPU nodes. It ensures EPod V2 schedule only on those nodes and prevents other workloads from being placed on them. Each toleration entry consists of the following four fields. |
| Effect | It defines how the taint restricts pod scheduling. It supports the following effects: **NoSchedule**: Pods without a matching toleration are strictly not scheduled on the node. **PreferNoSchedule**: Kubernetes avoids scheduling pods without a matching toleration on the node, but it is not strictly enforced. **NoExecute**: Pods without a matching toleration are not scheduled on the node, and any already running pods without the toleration are evicted immediately. |
| Operator | Defines how the key-value match is evaluated. Select Equal to match only when both the key and value correspond exactly to the taint on the node. |
| Key | Enter the label key of the taint applied to your GPU node. It also provides a default key value to apply on your nodes. |
| Value | Enter the value associated with the taint key. For example, `true`. |
| + Add Toleration | Click to add another toleration entry if your cluster has multiple taint configurations on GPU nodes. |
  5. Once done, click **Save and Continue**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LW59X0WA.png)
10. On the **Customization** page, apply the following settings:

| Setting | Description |
| --- | --- |
| Custom Labels | Add custom labels to the Securiti pod in the form of a key-value pair. See the example below. *{“Environment”: “Production”}* Use these labels in Helm charts to identify, filter, and select resources. |
| Custom Annotations | Add custom annotations to the pod in the form of key-value pair. See the example below. *{“monitoring/alert-threshold”: “5”}* Use annotations to add metadata that provides additional information for tools, scripts, or automation processes. |
| Node Selector | Add a node selector for the Pods as a key-value pair. It helps if your infrastructure runs multiple applications on different nodes. Use a node selector to control where the Pods deploy by assigning them to specific nodes based on key-value pairs. |
| Tolerations | Add the Toleration against the Taints you have applied to your nodes to manage the cluster scheduler for EPod V2. The Toleration value you provide here applies to the pods, so that the pods only schedule on the specific nodes accordingly. You must provide the values in the following JSON format. `[{"key": "dedicated", "value": "securiti", "effect": "NoExecute", "operator": "Equal"}]`. \| Key \| Value description \| \| --- \| --- \| \| Key \| It is the label of the taint you are tolerating. \| \| Operator \| It is the matching operator for a specific key-value match on the node. It can be one of the following: - Equals - Exists \| \| Value \| A string value that must match the taint’s value. > [!NOTE] > Note > > If your Operator value is “exists”, then skip this “Value” field. \| \| Effect \| It is the effect of the taint on the pod’s scheduling. It can be one of the following: - NoSchedule - PreferNoSchedule - NoExecute \| |
| Key | Value description |
| Key | It is the label of the taint you are tolerating. |
| Operator | It is the matching operator for a specific key-value match on the node. It can be one of the following: - Equals - Exists |
| Value | A string value that must match the taint’s value. > [!NOTE] > Note > > If your Operator value is “exists”, then skip this “Value” field. |
| Effect | It is the effect of the taint on the pod’s scheduling. It can be one of the following: - NoSchedule - PreferNoSchedule - NoExecute |
| Storage Class | If you are installing the pod in any non-default Storage Class, add your custom Storage Class name in this field. The EPod V2 uses the provided Storage Class for all its Persistent Volume Claims (PVC). Once you proceed with the installation, you cannot change it later on. The only way you can change the Storage Class is to fully reinstall the EPod V2. |
| Cluster Domain | Add your custom cluster domain for the EPod V2 installation so that the pods on different nodes can communicate with each other via the internal cluster domain you provide. If you leave this field empty, it utilizes the default cluster domain, which is `.cluster.local`. |
| Capacity Type Node Selector | Enable this toggle if you use Spot node instances for EPod V2. This toggle populates the label values for On-demand and Spot node instances according to your **Kubernetes Distribution** from **Basic Information** tab. EPod V2 identifies the On-demand and Spot nodes on the basis of the populated values. > [!NOTE] > Note > > If you are using any other Kubernetes distribution or already using other values for On-Demand and Spot instances, you must update these values accordingly. \| Field \| Description \| \| --- \| --- \| \| Capacity Type Label \| Kubernetes cluster uses this value to identify if the node is On-Demand or Spot. \| \| On Demand Value \| This label identifies that the connected node is On-Demand instance. \| \| Spot Value \| This label identifies that the connected node is Spot instance. \| |
| Field | Description |
| Capacity Type Label | Kubernetes cluster uses this value to identify if the node is On-Demand or Spot. |
| On Demand Value | This label identifies that the connected node is On-Demand instance. |
| Spot Value | This label identifies that the connected node is Spot instance. |
| Autoscaler Type | From the dropdown menu, select your existing auto-scaler type of your Kubernetes cluster. As the auto-scaling method already exists in your cluster, it deploys EPod V2 with the same configurations to scale. It supports the following auto-scaling: - Horizontal Pod Autoscaler (HPA) - Kubernetes Event-Driven Autoscaling (KEDA) - Internal > [!NOTE] > Note > > - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation. > - Securiti provides this autoscaler and it operates without requring any additional cluster-level permissions. Select Internal if your Kubernetes environment has restricted permissions and does not support cluster-scoped components required by HPA or KEDA. Internal autoscaling operates within EPod V2. Use the following command in your EPod V2 to tune the Internal autoscaler settings for a specific deployment without redeploying Helm values: ```bash securitictl override-internal-scaler ``` With the command above, you must include the following flags to perform certain supporting actions. It supports the following flags: \| Flag \| Description \| \| --- \| --- \| \| `--deployment` \| Specifies the target deployment to apply the override to. Use the exact deployment name as it appears in your Kubernetes cluster. This flag is required with all other flags. See the following example command: `securitictl override-internal-scaler --deployment download-worker --max-replicas 8` \| \| `--max-replicas` \| Overrides the maximum number of replicas the Internal Autoscaler can scale up to for the specified deployment. The value must be greater than or equal to the current `--min-replicas` value. See the following example command: `securitictl override-internal-scaler --deployment download-worker --max-replicas 10` \| \| `--min-replicas` \| Overrides the minimum number of replicas the Internal Autoscaler maintains for the specified deployment. The value must be less than or equal to the current `--max-replicas` value. See the following example command: `securitictl override-internal-scaler --deployment download-worker --min-replicas 2` \| \| `--scaling-enabled` \| Enables or disables autoscaling for the specified deployment. Set to `true` to enable scaling or `false` to freeze the replica count at its current value. See the following example command: `securitictl override-internal-scaler --deployment download-worker --scaling-enabled false` \| \| `--delete` \| Removes the override configuration for the specified deployment and restores it to the default scaler settings defined in the Helm chart. See the following example command: `securitictl override-internal-scaler --deployment download-worker --delete` \| |
| Flag | Description |
| `--deployment` | Specifies the target deployment to apply the override to. Use the exact deployment name as it appears in your Kubernetes cluster. This flag is required with all other flags. See the following example command: `securitictl override-internal-scaler --deployment download-worker --max-replicas 8` |
| `--max-replicas` | Overrides the maximum number of replicas the Internal Autoscaler can scale up to for the specified deployment. The value must be greater than or equal to the current `--min-replicas` value. See the following example command: `securitictl override-internal-scaler --deployment download-worker --max-replicas 10` |
| `--min-replicas` | Overrides the minimum number of replicas the Internal Autoscaler maintains for the specified deployment. The value must be less than or equal to the current `--max-replicas` value. See the following example command: `securitictl override-internal-scaler --deployment download-worker --min-replicas 2` |
| `--scaling-enabled` | Enables or disables autoscaling for the specified deployment. Set to `true` to enable scaling or `false` to freeze the replica count at its current value. See the following example command: `securitictl override-internal-scaler --deployment download-worker --scaling-enabled false` |
| `--delete` | Removes the override configuration for the specified deployment and restores it to the default scaler settings defined in the Helm chart. See the following example command: `securitictl override-internal-scaler --deployment download-worker --delete` |
| Kube Metrics Adapter | Enable or disable to the toggle to install or restrict custom Metrics API to support HPA auto-scaling. > [!NOTE] > Note > > As Kube Metrics Adapter supports HPA auto-scaling, you cannot enable it if you select KEDA in **Autoscaler Type** dropdown menu. |
| Sys Admin | Enable the toggle to run containers with root/administrative privileges. It is required for the following features: - NFS/SMB file share scanning - Log upload to Securiti |
| - RPS HTTPS Node Port - RPS HTTP Node Port | If you have Apache Ranger Policy Service (RPS) available in your Kubernetes cluster, enter its port number for HTTPS or HTTP. The default port values for the first node are 31000 and 31001 for HTTPS and HTTP services, respectively. For installing multiple clusters, you must update the port number and must be between the range of 30000 to 32767 and must not be in use by any other service. |
| Enable proxy | Turn on Enable proxy toggle to configure proxy for your EPod V2. Enabling it displays new fields on the UI. It introduces the following new fields. |
| Proxy Host: Enter the proxy IP or domain name of your proxy host system. It routes all your EPod V2’s network traffic through this proxy host. |
| Proxy Port: Enter the port of your proxy host. |
| (Optional) Proxy Username: Enter the username of your proxy host if it is required to connect to the proxy host. |
| (Optional) Proxy Password: Enter the password of your proxy host if it is required to connect to the proxy host. |
| (Optional) No Proxy: Enter those IP address or host names that you wish to exclude from the proxy list. It does not include them in any proxy related operation. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2QNBLEQR.png)

Click **Save and Continue**.

It takes you to **Summary** page.
11. On the **Summary** tab:
  1. You can then see the Helm install instructions. You must stay on this tab until the installation is complete. Copy all the values and save them in case you close this page. Proceed to the next section to install the application using the commands from this tab, [Installing in your Kubernetes infrastructure](/latest/docs/epod-v2-installation-in-kubernetes-cluster).

![summary_installation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-289ee117-6b5d-69e0-e9b6-793cc69b2c10(2).png)

## Related

- [Prerequisites for EPod V2](/prerequisites-for-epod-v2.md)
- [Upgrading EPod V2](/upgrade-epod-v2.md)
- [Installing multiple pods in Cluster](/installing-multiple-pods-in-cluster.md)
