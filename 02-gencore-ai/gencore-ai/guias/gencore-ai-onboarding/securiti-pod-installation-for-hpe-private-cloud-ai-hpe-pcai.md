---
title: "Securiti POD installation for HPE Private Cloud AI (HPE PCAI)"
slug: "securiti-pod-installation-for-hpe-private-cloud-ai-hpe-pcai"
updated: 2026-01-14T10:00:19Z
published: 2026-01-14T10:00:19Z
canonical: "helpcenter.securiti.ai/securiti-pod-installation-for-hpe-private-cloud-ai-hpe-pcai"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Securiti POD installation for HPE Private Cloud AI (HPE PCAI)

HPE Private Cloud AI is a purpose-built solution designed to provide fast and easy deployment of private AI applications with a focus on inferencing, Retrieval-Augmented Generation (RAG) (RAG), and fine-tuning. HPE Private Cloud AI is a co-developed HPE and NVIDIA enterprise purpose-built solution included in a completed infrastructure. This is the Securiti Pod installation guide for the deployment of Securiti's Data Plane onto HPE PCAI infrastructure.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Prerequisites:

You must fulfil the following prerequisites before pod installation:

- Successful login to the Securiti Tenant Portal:
  - You must have a valid user account with sufficient privileges in Securiti to deploy pods.
  - You must configure the Securiti tenant must be configured with Helm/Elastic Pod V2 option. If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
- Successful access to HPE AI Essentials portal
- Networking requirements: Ensure the installed pod can establish communication with the Securiti Cloud
- Allowlist Securiti Registry: Verify PCAI Allowlist permits access to the Securiti container registry to pull Docker images.

> [!NOTE]
> **Note**
> 
> Registry location is based on the Securiti tenant URL. See the comprehensive list of container registries around the globe here.

| URL | Purpose |
| --- | --- |
| app.securiti.ai, port 443 | Securiti Cloud |
| packages.securiti.ai, port 443 | Securiti CDN for appliance bundle download |
| manage-support.securiti.ai, port 443 | Remote management support |
| prod-us-west-2-starport-layer-bucket.s3.us-west-2.amazonaws.com, port 443 | For auto-update of the pods |
| privaci-registry.s3.us-west-2.amazonaws.com, port 443 | AWS S3 bucket for metadata, logs storage |
| securiti-state-718391394098.s3.us-west-2.amazonaws.com, port 443 | Storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d31wfa8az5rt1f.cloudfront.net | Securiti appliance bundle download from CDN |

### Create Elastic V2 Pod

To create a pod and download the Helm chart:

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of tiles, click **Deployment** > **Elastic Pod V2**.
3. Near the right top of the page, click **+ New Cluster** and choose **Custom Install**.

![select_new_cluster.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14ef9a75-8671-94ce-cada-c6cff2220bff(3).png)
4. Enter the **Basic Information** against the tab:

| Field | Description |
| --- | --- |
| Cluster Name | Cluster Name is a unique cluster name to track the pod later. |
| (Optional) Add Notes | Notes are optional and help you add some important information you need to keep within the pod. |
| Cluster Location | Enter the cluster location details, which are **Country**, **State/Region**, and **City**. |
| Primary Owner | Select the primary owner from the drop-down menu. By default, the user who is creating the pod is the owner. Enable the **Add co-owner** toggle to add a co-owner. Enabling the **Send notification to all owners** toggle sends the notifications to owners and co-owners. |
5. Click **Save and Continue** to proceed.

![add_basic_info.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-677a343e-b000-e534-c397-d21eba8cc715(3).png)
6. On the **Select Registry** page, you have two options for choosing a registry to pull application images:

After making your selection, click **Save and Continue**.

![select_registry.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d80d294c-4fa9-d56a-a8d5-2b4c8a098a36(1).png)
  - Select **Install from Securiti Registry** option to pull application images using Securiti’s registry.

This lets you fetch images from our registry directly and makes the process simple and quick.
  - Select **Install from Custom Registry** if you own a custom registry. This is useful if your clusters are authorized to fetch images from your custom registry only.

To set up a custom registry, see [Using Custom Registry with Elastic Pods V2](/v1/docs/securiti-pod-installation-for-hpe-private-cloud-ai-hpe-pcai).
7. (Optional) In the **Credentials File**, download the credentials file “secrets.json”.

> [!NOTE]
> **Note**
> 
> The Credentials File stores the authentication details you require to access a Kubernetes cluster. It typically includes usernames, passwords, or API tokens in a secure format such as a kubeconfig YAML file. This file lets you interact with the cluster using tools like kubectl by specifying the cluster and user context.
  - If you selected **Install from Securiti Registry** in step 7 above, click **Download Credentials File** and apply the file to your cluster with the following command:

```bash
kubectl apply -f secret.json -n <namespace>
```

Replace **<namespace>** variable with your existing namespace of K8s. If you don’t provide a namespace, it applies to the default namespace. You can create a new namespace using the following command.

```bash
kubectl create namespace default
```
8. On the **Monitoring** page:
  1. Enable the **Install Monitoring** toggle to deploy a new Prometheus alongside the Securiti pod.

If you already have a Prometheus deployed and accessible from the cluster, enter the URL for your instance. The pods then utilize it for custom metrics.

> [!NOTE]
> **Note**
> 
> Prometheus monitoring is crucial for pod monitoring and scaling. Without monitoring, auto-scaling will not work. If using an existing Prometheus deployment, ensure that the specified service is accessible to the pod.
  2. Click **Save and Continue**.

![select_monitoring_tool.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-428ff6c7-ce8c-303e-d566-522a07b36da5(3).png)
9. On the **Metrics** page:
  1. Enable the **Install Metrics** toggle to deploy the metrics server alongside the Securiti pod if your Kubernetes cluster does not already have a Metrics server running.

Securiti requires a Metrics server in the cluster for monitoring resource utilization.
  2. Click **Save and Continue** to continue.

![select_matrics.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-98d23f1d-0196-68e9-7137-eef6114d7e44(3).png)
10. In the **Redis** page, **Install Redis** toggle is enabled by default. Securiti deploys a Redis database backed by a persistence volume in the Kubernetes cluster.
  1. Click **Save and Continue**.

![select_Redis.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07819a51-5b91-fe0c-445d-65fe6094a60e(3).png)
11. Similar to Redis, on the Elastic Search page:
  1. The **Install ES** option is enabled by default.

The application deploys an Elastic Search database backed by a persistence volume in the Kubernetes cluster.
  2. Click **Save and Continue**.

![select_ES.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce05c875-e8c6-8dcb-7493-7c8187fe192f(3).png)
12. On the **Max Memory** page, .
  1. Insert the memory you want to allocate to Securiti application in your K8s cluster. The minimum memory you can allocate for an EPod V2 is 64000MiB.

> [!NOTE]
> **Note**
> 
> Securiti requires a memory-to-CPU ratio to be 4 GB:1.
> 
> - Securiti deployment relies on this value to determine the allocated memory.
> - Securiti uses this value to determine the scaling of different components in the deployment.
> 
> The pods scale up to a maximum of the value specified here. If you increase the memory allocation in the cluster but don't update it here, Securiti deployment will not recognize the change.
  2. Once done, click **Save and Continue**.

![add_memory.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f29d469b-a907-a160-80c8-e5fc75a80592(3).png)
13. On the **Customization** page, apply the following settings:

| Setting | Description |
| --- | --- |
| Namespace | Enter the namespace within the Kubernetes cluster where you wish to deploy your application. Make sure the namespace already exists, otherwise, an application might fail the deployment. |
| Custom Labels | Add custom labels to the Securiti pod in the form of a key-value pair. See the example below. *{“Environment”: “Production”}* Use these labels in Helm charts to identify, filter, and select resources. |
| Custom Annotations | Add custom annotations to the pod in the form of key-value pair. See the example below. *{“monitoring/alert-threshold”: “5”}* Use annotations to add metadata that provides additional information for tools, scripts, or automation processes. |
| Node Selector | Add a node selector for the pods as a key-value pair. It helps if your infrastructure runs multiple applications on different nodes. Use a node selector to control where the pods deploy by assigning them to specific nodes based on key-value pairs. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(232).png)
14. Click **Save and Continue**.

It takes you to **Summary** page.
15. On the **Summary** tab:
  1. You can then see the Helm install instructions. You must stay on this tab until the installation is complete. Copy all the values and save them in case you close this page. Proceed to the next section to install the application using the commands from this tab. ![add_helm_command.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-710e592b-b2d6-faaa-4f89-c4c5835b34b0(1).png)

### Using Custom Registry with Elastic Pods V2

Selecting Custom Registry lets you move the images from the Securiti registry into your custom registry. This is helpful when you have restricted your clusters and infrastructure to pull images from only a single controlled registry. Make sure your cluster, where you intend to install the Epod V2, has access to your custom registry. To proceed with it, follow these steps:

1. On the **Credentials File** tab:
  1. Download Credentials File to download the file that contains the credentials that you need to pull the images from the Securiti registry into your custom registry.

![14__Cred_file_zoom_in.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-efc1619a-bc8b-5e15-0577-0132f65a0e01(1).png)
  2. Move the downloaded file into the “**~/.docker/config**” directory.
  3. Click **Save and Continue**.
2. On the **List of Images** tab, you see a list of images. Copy the list and save it in your preferred directory.

![15__List_of_images.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-601eefc5-e458-27d9-4002-eada9dfb8947(1).png)
  1. Now you must pull the images and push them into your own custom registry depending upon your infrastructure policies. Use the following command.

```dockerfile
docker pull <image>:<tag>
```

See the example below.

```dockerfile
docker pull app.securiti.ai/foundri/dd-connector:<tag>
docker tag <my-registry>/foundri/dd-connector:<tag>
docker push <my-registry>/foundri/dd-connector:<tag>
```

You must repeat the above steps for all the images.

> [!NOTE]
> **Note**
> 
> You must use the same image repository and tag names from the List of Images page.

If the custom registry requires authentication, the application uses a Kubernetes secret to pull the images. Create a Kubernetes secret named registrykey and apply it to the install namespace. The config.yaml file and all deploying images automatically reference this secret name.

### Download Package

To download the package, use the signed URL provided under the Generate HELM chart URL to download the helm chart.

```bash
curl <SECURITI HELM CHART SIGNED URL> --output
<securiti-appliance-chart-<VERSION>.tar.gz>
```

For example:

```bash
curl “<Helm chart url>” --output
securiti-appliance-chart-1.122.0-07rc.tar.gz
```

Replace the value of version with the version value that is under the Helm install instructions field as shown below:

### Installing multiple pods in a cluster

If you want to install multiple application pods in a single cluster under different namespaces, you need to select a different namespace from the previous option. Additionally, you must adjust some other settings in the final values file, as highlighted in the figure below.

You must set both `enableCustomMetricsAPI` and `enableExternalMetricsAPI` to false. If you deleted the first cluster where these values were set to true, you might need to set these values to true again and run the cluster upgrade on the second cluster.

> [!NOTE]
> **Note**
> 
> If you install two pods on a cluster and then delete the first Pod, you must enable these APIs and upgrade the cluster with the following settings:
> 
> ```yaml
> "enableCustomMetricsAPI=true"
> "enableExternalMetricsAPI=true"
> ```
> 
> Apart from the API services, the Ranger policy service node port must be unique for each installed cluster. The default port values for the first node are **31000** and **31001** for HTTPS and HTTP services, respectively. You can choose any other value for the second cluster and beyond.

> [!NOTE]
> **Note**
> 
> These values must reside within the range of 30000 to 32767 and must not be in use by any other service.

### Installing the Pod via Helm Chart onto HPE PCAI

To install the pod through Helm Chart onto HPE PCAI:

1. Login to [HPE GreenLake](https://common.cloud.hpe.com).
2. Navigate to the **Private Cloud AI>Tools>Frameworks**.
3. Click **Import Framework**.
4. Update information as follows:
  - Upload the logo and upload the tar
  - update the values.yaml
5. Run the commands on cluster

```bash
>kubectl apply -f secret.json -n securiti
```
6. Register the appliance by running the command under the Register instructions section.

```bash
>kubectl -n  exec -it 
deploy/priv-appliance-config-controller -- securitictl register -l “<license>”
```

### Verifying Installation

To verify the installation, return to the Securiti Portal and on **Deployment > Elastic Pod V2**, the pod should self register and display a green sign.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(173).png)

### Upgrading the Helm Chart

To upgrade the Helm Chart, copy the string from HELM Install Instructions.

```bash
>helm upgrade -n securitiai --install priv-appliance 
securiti-appliance-chart-1.125.1-02p.tar.gz -f values.yaml --timeout=9000
```

```bash
Unset:
helm upgrade <release_name> <chart_name>.tgz -f values.yaml
```

### Uninstalling the Helm Chart

To uninstall the Helm Chart, run the following command:

```bash
Unset:
helm uninstall <release_name>
```

Verify resource cleanup with `kubectl get pods` and `kubectl get services`.

Retrieval-Augmented Generation (RAG) is an architectural approach designed to enhance the performance of large language model (LLM) applications by incorporating custom data. It achieves this by retrieving relevant data or documents related to a given question or task and supplying them as context to the LLM.
