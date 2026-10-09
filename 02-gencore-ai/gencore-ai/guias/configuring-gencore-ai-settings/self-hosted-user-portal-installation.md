---
title: "Self-hosted user portal installation"
slug: "self-hosted-user-portal-installation"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/self-hosted-user-portal-installation"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Self-hosted user portal installation

For self-hosted user portal installation, see the details below.

## Prerequisites

- ​​[System requirements​​](/v1/docs/configuring-user-portal#system-requirements)
- ​​[Network prerequisites​​](/v1/docs/configuring-user-portal#network-requirements)
- [​​Cluster roles​​](/v1/docs/configuring-user-portal#cluster-roles)

### System requirements

- **​​Ingress**:​​ Ensure your environment has an active Ingress Controller (such as NGINX) provisioned with an IP address, and update your DNS records to route your custom domain to that IP address. Ensure a valid TLS certificate for your domain is available in your cluster — either through a certificate automation tool (such as cert-manager) or a certificate you provide yourself. Once these prerequisites are met, configure the Ingress Controller, TLS certificate, and annotations as described in the [Configuring Ingress](/latest/docs/self-hosted-user-portal-firewall-deployment#configuring-ingress-controller).
- **Kubernetes**:

| Requirement | Description |
| --- | --- |
| Linux instance | A Linux instance with Kubeconfig to connect to the Kubernetes cluster, from where you run the Helm commands and perform the deployment. |
| Kubectl | 1.30 or higher |
| Kubernetes version | 1.30 or higher |
| Helm version | 3.12.0 or higher |
| Kubernetes | You must set up the Kubernetes cluster with the permissions it requires and the infrastructure to provision persistent volumes by defining a storage class. |
| Kubernetes plugins | You must enable plugins to enable volume provisioning. |
- **Node**:

| Requirement | Quantity |
| --- | --- |
| CPU | 16 cores > [!NOTE] > Note > > Nodes can be larger than 16 CPUs. However, they must always be a multiple of 16 for optimal resource usage. |
| CPU architecture | x86_64 |
| GPU | 2 cores > [!WARNING] > Important > > A minimum number of 2 nodes is required. The platform automatically distributes models across the available Triton servers and GPUs. Operators do not need to manually configure model placement or routing. |
| GPU Architecture | NVIDIA L4, Minimum memory 32 GiB (must maintain a 16 gb to 1 gpu) You must add the following taint to the gpu node pool: key = "nvidia.com/gpu" value = "present" effect = "NO_SCHEDULE" > [!NOTE] > Important > > This is required when you select the On-premises Firewall Deployment option. For autoscaling requirements, see [Autoscaling](/latest/docs/configuring-user-portal#gpu-architecture-autoscaling) requirements. |
| Minimum memory | 64 GiB > [!NOTE] > Note > > You must maintain a 4 GB to 1 CPU ratio. |
| Disk | 1 TB |
| Minimum number of nodes | 1 |

- **Additional requirements**:

| Requirement | Detail |
| --- | --- |
| Cloud account | If deploying in cloud environments, Securiti recommends having a dedicated cloud account to deploy Securiti pods. |
| Cluster roles | You must define [Cluster Roles](/latest/docs/configuring-user-portal#cluster-roles). |
| Access to namespace | You must provide full access to the namespace. |

### Network requirements

Add the following network URL:

- For the US cloud:

| URL | Purpose |
| --- | --- |
| app.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| prod-us-west-2-starport-layer-bucket.s3.us-west-2.amazonaws.com, port 443 | It is the URL for pulling images from Securiti registry. |
| privaci-registry.s3.us-west-2.amazonaws.com, port 443 | It is the URL of the cloud bucket for storing metadata and logs. |
| securiti-state-718391394098.s3.us-west-2.amazonaws.com, port 443 | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d31wfa8az5rt1f.cloudfront.net | It is the CDN URL for downloading the appliance bundle for installation. |
- For the US1 cloud:

| URL | Purpose |
| --- | --- |
| app1.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| storage.googleapis.com, port 443 | It is the URL for storing states on the cloud. |
| us-docker.pkg.dev | It is the URL for Pod's auto-updating and upgrading. |
- For the Canada Cloud:

| URL | Purpose |
| --- | --- |
| app3.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| prod-ca-central-1-starport-layer-bucket.s3.ca-central-1.amazonaws.com, port 443 | It is the URL for pulling images from Securiti registry. |
| privaci-montreal-registry.s3.ca-central-1.amazonaws.com, port 443 | It is the URL of the cloud bucket for storing metadata and logs. |
| securiti-montreal-state-718391394098.s3.ca-central-1.amazonaws.com, port 443 | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d1wxubre8y9029.cloudfront.net | It is the CDN URL for downloading the appliance bundle for installation. |
- For the EU Cloud:

| URL | Purpose |
| --- | --- |
| app.eu.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| prod-eu-west-1-starport-layer-bucket.s3.eu-west-1.amazonaws.com, port 443 | For pulling images from Securiti registry |
| privaci-eu-registry.s3.eu-west-1.amazonaws.com, port 443 | It is the URL of the cloud bucket for storing metadata and logs. |
| securiti-eu-state-718391394098.s3.eu-west-1.amazonaws.com | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d17vfm9hd4ph8q.cloudfront.net | It is the CDN URL for downloading the appliance bundle for installation. |
- For the Indonesia Cloud:

| URL | Purpose |
| --- | --- |
| app2.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| prod-ap-southeast-3-starport-layer-bucket.s3.ap-southeast-3.amazonaws.com, port 443 | It is the URL for pulling images from Securiti registry. |
| privaci-jakarta-registry.s3.ap-southeast-3.amazonaws.com, port 443 | It is the URL of the cloud bucket for storing metadata and logs. |
| securiti-jakata-state-718391394098.s3.ap-southeast-3.amazonaws.com, port 443 | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d2nhybc0go9etk.cloudfront.net | It is the CDN URL for downloading the appliance bundle for installation. |
- For the Australia Cloud:

| URL | Purpose |
| --- | --- |
| app4.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| prod-ap-southeast-2-starport-layer-bucket.s3.ap-southeast-2.amazonaws.com, port 443 | It is the URL for pulling images from Securiti registry. |
| privaci-sydney-registry.s3.ap-southeast-2.amazonaws.com, port 443 | It is the URL of the cloud bucket for storing metadata and logs. |
| securiti-sydney-state-718391394098.s3.ap-southeast-2.amazonaws.com, port 443 | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d2ukknqt0z03bc.cloudfront.net | It is the CDN URL for downloading the appliance bundle for installation. |
- For the UAE Cloud:

| URL | Purpose |
| --- | --- |
| app5.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| prod-me-central-1-starport-layer-bucket.s3.amazonaws.com, port 443 | It is the URL for pulling images from Securiti registry. |
| privaci-uae-registry.s3.me-central-1.amazonaws.com, port 443 | It is the URL of the cloud bucket for storing metadata and logs. |
| securiti-uae-state-718391394098.s3.me-central-1.amazonaws.com, port 443 | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d1k2hmyn0i0qdq.cloudfront.net | It is the CDN URL for downloading the appliance bundle for installation. |
- For the India Cloud:

| URL | Purpose |
| --- | --- |
| app6.securiti.ai | It is the host URL of the Securiti application within the defined region. |
| prod-ap-south-1-starport-layer-bucket.s3.ap-south-1.amazonaws.com | It is the URL for pulling images from Securiti registry. |
| privaci-mumbai-registry.s3.ap-south-1.amazonaws.com/ | It is the URL of the cloud bucket for storing metadata and logs. |
| securiti-mumbai-state-718391394098.s3.ap-south-1.amazonaws.com | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| dhth5mgsbl3e0.cloudfront.net | It is the CDN URL for downloading the appliance bundle for installation. |
- For the KSA Cloud:

| URL | Purpose |
| --- | --- |
| app7.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| me-central2-docker.pkg.dev | It is the URL for pulling images from Securiti registry. |
| https://storage.cloud.google.com/securiti-state-419004438835 | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| https://storage.cloud.google.com/securiti-artifacts-402060762925 | It is the URL of the cloud bucket for storing metadata and logs. |
- For the Qatar Cloud:

| URL | Purpose |
| --- | --- |
| app8.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| me-central1-docker.pkg.dev | It is the URL for pulling images from Securiti registry. |
| https://storage.cloud.google.com/securiti-artifacts-818816799760 | It is the URL of the cloud bucket for storing metadata and logs. |
| https://storage.cloud.google.com/securiti-state-818816799760 | It is the storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |

#### Autoscaling

Securiti supports horizontal autoscaling for self-hosted deployments to handle varying workloads. Autoscaling is managed through **Kubernetes Horizontal Pod Autoscaler (HPA)** using external Prometheus metrics via `kube-metrics-adapter` . There are two categories of autoscaling:

| Type | Scales on | Node type | Enabled by default |
| --- | --- | --- | --- |
| GPU based | GPU utilization | GPU | Yes |
| CPU based | Request count | CPU | Yes |

For either type of autoscaling to function, one of the following must be true:

- Cluster Autoscaler is enabled on the relevant node pool (GPU or CPU), so new nodes are provisioned

automatically when pods are pending.
- Sufficient nodes are pre-provisioned in the cluster to accommodate the maximum number of replicas.

**GPU based autoscaling:**

The **Triton Inference Server** runs on dedicated GPU nodes and scales based on GPU utilization. When the utilization exceeds the configured threshold (default: 80%), the system creates additional replicas. Each replica requires its own GPU node.

> [!NOTE]
> Important
> 
> The value of **maximum node** and **tritonInferenceServerMaxReplicas** should be same as each instance of triton inference server needs one gpu node.

![Installation instructions for configuring the Triton server with autoscaling settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/triton-server-invalues-yaml.png)

### Cluster Roles

Cluster roles define the permissions the application requires to perform essential operations within the Kubernetes cluster. These roles let the application execute tasks like diagnostics, backups, resource management, and custom metrics publishing for autoscaling. Securiti provisions the least privileged cluster roles for permissions needed for non-namespace-scoped resources in the Kubernetes cluster.

> [!NOTE]
> Note
> 
> The installation of Gencore AI self hosted deployment automatically creates specific cluster roles. You can verify that all of these roles have been created. No other roles are required.

| Cluster Role Name | Permissions granted |
| --- | --- |
| ```yaml securiti-config-controller-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/config-controller/templates/common-rbac.yaml # Common RBAC configuration for config-controller # Common minimum ClusterRole permissions for all installation types apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: securiti-config-controller-<namespace> rules: # Node-level permissions (read-only) - needed by all install types - apiGroups: - "" resources: - nodes verbs: - get - list - watch # Pod metrics permissions (common to both installation types) - apiGroups: - metrics.k8s.io resources: - pods verbs: - get - list - watch ``` |
| ```yaml securiti-register-job-cluster-role-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/deployer-service/templates/rbac.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: securiti-register-job-cluster-role-<namespace> rules: - apiGroups: [""] resources: ["nodes"] verbs: ["get", "list"] ``` |
| ```yaml kube-metrics-adapter-server-resources-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/kube-metrics-adapter/templates/rbac.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: kube-metrics-adapter-server-resources-<namespace> rules: - apiGroups: - custom.metrics.k8s.io resources: - '*' verbs: - get - list - watch - create - update - patch - delete - apiGroups: - extensions resources: - podsecuritypolicies resourceNames: - appliance-psp-root verbs: - use ``` |
| ```yaml external-metrics-server-resources-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/kube-metrics-adapter/templates/rbac.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: external-metrics-server-resources-<namespace> rules: - apiGroups: - external.metrics.k8s.io resources: - '*' verbs: - get - list - watch - create - update - patch - delete - apiGroups: - extensions resources: - podsecuritypolicies verbs: - use ``` |
| ```yaml kube-metrics-adapter-resource-reader-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/kube-metrics-adapter/templates/rbac.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: kube-metrics-adapter-resource-reader-<namespace> rules: - apiGroups: - "" resources: - namespaces - pods - services - configmaps verbs: - get - list - apiGroups: - extensions resources: - podsecuritypolicies verbs: - use ``` |
| ```yaml kube-metrics-adapter-resource-collector-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/kube-metrics-adapter/templates/rbac.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: kube-metrics-adapter-resource-collector-<namespace> rules: - apiGroups: - "" resources: - events verbs: - create - patch - apiGroups: - "" resources: - pods verbs: - list - apiGroups: - apps resources: - deployments - statefulsets verbs: - get - apiGroups: - extensions resources: - ingresses verbs: - get - apiGroups: - extensions resources: - podsecuritypolicies verbs: - use - apiGroups: - autoscaling resources: - horizontalpodautoscalers verbs: - get - list - watch ``` |
| ```yaml $prometheusPushgatewayClusterRoleName-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/prometheus/templates/rbac/pushgateway-clusterrole.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: labels: component: "pushgateway" app: prometheus release: securiti-appliance chart: prometheus-11.12.0 heritage: Helm name: $prometheusPushgatewayClusterRoleName-<namespace> rules: [] ``` |
| ```yaml $prometheusSeverClusterRoleName-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/prometheus/templates/rbac/server-clusterrole.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: labels: component: "server" app: prometheus release: securiti-appliance chart: prometheus-11.12.0 heritage: Helm name: $prometheusSeverClusterRoleName-<namespace> rules: - apiGroups: - "" resources: - nodes - nodes/proxy - nodes/metrics - services - endpoints - pods - ingresses - configmaps verbs: - get - list - watch - apiGroups: - "extensions" - "networking.k8s.io" resources: - ingresses/status - ingresses verbs: - get - list - watch - nonResourceURLs: - "/metrics" verbs: - get ``` |
| ```yaml securiti-worker-<namespace> ``` | ```yaml # Source: securiti-appliance/charts/worker/templates/rbac.yaml # Common RBAC configuration for all worker environments # ClusterRole for cluster-wide resources only with minimal permissions apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: securiti-worker-<namespace> rules: # Node-level permissions (read-only) - apiGroups: - "" resources: - nodes verbs: - get - list - watch ``` |

### Installation

This procedure covers pre installation steps in Securiti and installation steps into your own Kubernetes infrastructure.

#### Installing in your Kubernetes infrastructure

For installation, perform all the following steps on your Linux instance from which the Kubernetes server and network are accessible. SSH into the cluster where the chart has to be installed and from the **Installation Instructions** popup:

1. Use the signed URL provided under the **Download Helm chart** URL to download the Helm chart. Copy the signed URL and add it into the following command to download and save it.

```yaml
curl "<SECURITI HELM CHART SIGNED URL>" --output <securiti-gencore-self-hosted-<VERSION>.tar.gz>
```

For example:

```yaml
curl “<Helm chart url>” --output securiti-gencore-self-hosted-chart-1.136.0-13rc.tar.gz
```

![Instructions for downloading the HELM chart using wget or cURL from the URL.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download HELM chart from URL(1).png)

Replace the value of ​<VERSION>​​ with the version value that is under the Helm install instructions field as shown below:

![Installation instructions for deploying Gencore self-hosted services with command details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Install Command(1).png)
2. Copy the contents of the values file under Download `values.yaml` into a file and name it as `values.yaml`. Make sure to modify the password fields in the content before proceeding.

> [!NOTE]
> Important
> 
> The name of the file placed on the cluster must be `values.yaml`.
  - Redis
  - Postgres
  - Pubsub
  - Weaviate

![Configuration settings for Redis and PostgreSQL with sensitive information highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/download yaml fl.png)
3. Run the Helm install command under Helm Install Instructions. This step might take a few minutes to complete.

![Command to deploy Gencore self-hosted services using Helm upgrade with placeholders.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inst command.png)
4. Run the following command. Replace the tar file name with the one you obtained in the previous step from the Helm Install Instruction field. Additionally, set the namespace and release-name, accordingly. Since we have made changes to the folder, the command installs from the folder.

```yaml
helm upgrade -n <namespace> --install <release-name> <securiti-gencore-self-hosted-chart<VERSION>.tar.gz> -f values.yaml --timeout=900s --set global.license="{{applianceLicense}}"
```

Make sure to replace the appliance license present in the Install Command.

![Command to deploy Gencore services with license key and timeout settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/FW selected - appliance.png)

> [!NOTE]
> Note
> 
> In case of using multiple pods in a cluster, refer to [**Installing multiple pods in a cluster**](/latest/docs/configuring-user-portal#installing-multiple-pods-in-a-cluser).
5. Once deployment is completed, your Gencore AI integrations should be accessible on the self-hosted deployment domain.

- User Portal
- [Messaging integration - Slack](/v1/docs/creating-custom-slack-app)
- [Web widgets](/v1/docs/configuring-web-widgets)
- [Conversation API](/v1/docs/assistant-api)
- [Standalone firewall APIs](/v1/docs/configuring-firewall-apis)

#### Upgrade

Upgrade your firewall deployment using the following steps.

1. Navigate to **System Settings>Gencore AI>User Portal>Custom Deployment**.
2. Under **Custom Deployments**, find your custom deployment.
3. On the right side of your custom deployment, click **Options** (three dots) and then click **Installation Instructions**.

![Settings for enabling custom deployment with options for adding or editing deployments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/CD options Install Instruct.png)
4. Use the signed URL provided under the Download Helm chart URL to download the Helm chart. Copy the signed URL and add it into the following command to download and save it.

```yaml
curl "<SECURITI HELM CHART SIGNED URL>"<VERSION>.tar.gz>
```

For example:

```yaml
curl “<Helm chart url>” --output securiti-gencore-self-hosted-chart-1.136.0-07rc.tar.gz
```

![Instructions to download the HELM chart using wget or cURL from the provided URL.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Download HELM chart from URL.png)

Replace the value of <VERSION> with the version value that is under the Helm install instructions field as shown below:

![Installation instructions for deploying Gencore self-hosted services with command details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Install Command(2).png)
5. Copy the contents of the values file under Download `values.yaml` into a file and name it as `values.yaml`. Make sure to modify the password fields in the content before proceeding.
  - Redis
  - Postgres
  - Pubsub
  - Weaviate

![Configuration settings for Redis and Postgres in a YAML file format.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/download yaml fl(1).png)

> [!NOTE]
> Important
> 
> The name of the file placed on the cluster must be `values.yaml`.
6. Run the Helm install command under Helm Install Instructions. This step might take a few minutes to complete.

![Command to deploy Gencore self-hosted services using Helm upgrade with placeholders.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inst command(1).png)

Run the following command. Replace the tar file name with the one you obtained in the previous step from the Helm Install Instruction field. Additionally, set the namespace and release-name, accordingly. Since we have made changes to the folder, the command installs from the folder.

```yaml
helm upgrade -n <namespace> --install <release-name> <securiti-gencore-self-hosted-chart<VERSION>.tar.gz> -f values.yaml --timeout=900s --set global.license="{{applianceLicense}}"
```

#### Installing multiple pods in a cluster

If you want to install multiple application pods in a single cluster under different namespaces, in `values.yaml` you must set the `kube-metrics-adapter` tag to `false`.

```yaml
tags:
  kube-metrics-adapter: false
```

> [!WARNING]
> Important
> 
> If you install two pods on a cluster and then delete the first pod, you must enable this tag on the second pod and upgrade the cluster with the following settings:
> 
> ```yaml
> tags:
>   kube-metrics-adapter: true
> ```

![Installation instructions for system settings with highlighted kube-metrics-adapter option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/multiple pods - kube-metrics-adapter-true.png)

#### Navigating the User Portal

To go to your generated User Portal, use the **Portal URL** provided in User Portal settings.

- To start a new conversation:
  1. Click **New Chat**.
  2. Select the pipeline.

> [!NOTE]
> **Note**
> 
> You can create multiple chats with the same pipeline. Every new chat creates a separate conversation thread. This helps users interact with the same knowledge base in multiple chats.
- You can manage chats as follows:
  - Rename
  - Delete
- To search for a channel, type key words in the Search box.
- To log out, click the logout icon at the bottom of the left panel.
