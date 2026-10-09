---
title: "Prerequisites for EPod V2"
slug: "prerequisites-for-epod-v2"
updated: 2026-09-24T15:11:13Z
published: 2026-09-24T15:11:13Z
canonical: "helpcenter.securiti.ai/prerequisites-for-epod-v2"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Prerequisites for EPod V2

This document lists all the prerequisites you must meet before deploying Elastic Pods EPod V2 in your existing Kubernetes cluster. Before deployment, you must understand that:

- You must already have a fully configured Kubernetes Cluster before proceeding with the EPod V2.
- The cluster must meet all the versions, networks, memory, and other configurations mentioned in this document before starting the deployment.

> [!NOTE]
> Note
> 
> For optional performance and security, Securiti recommends the following considerations:
> 
> | Workload isolation | Prepare a dedicated Kubernetes cluster for EPod V2 deployment. It guarantees that your application's performance is not impacted by other workloads competing for cluster resources. |
> | --- | --- |
> | Enhanced security | For enhanced security, prepare a dedicated Kubernetes cluster. It ensures that, since the application requires no inbound access, you enforce strict network policies to significantly reduce the attack surface. |
> | Cloud account | If deploying in cloud environments, Securiti recommends having a dedicated cloud account to deploy the pods. |
> | Cluster roles | When deploying the Epod V2 in Kubernetes, you must have full access to create resources in the cluster, including cluster roles. |
> | Access to namespace | Securiti pod needs a dedicated namespace with full permissions inside the namespace to run the Securiti Pods. |

You must meet the following prerequisites when you are deploying EPod V2.

### System requirements

You must meet the following system requirements.

- Kubernetes

| Requirement | Description |
| --- | --- |
| Linux instance | A Linux instance with Kubeconfig to connect to the Kubernetes cluster, from where you run the Helm commands and perform the deployment. |
| Kubectl | 1.30 or higher |
| Kubernetes version | 1.30 or higher |
| Helm version | 3.12.0 or higher |
| Kubernetes | You must set up the Kubernetes cluster with the permissions it requires and the infrastructure to provision persistent volumes by defining a storage class. |
| Kubernetes plugins | You must enable plugins to enable volume provisioning. |
- Node

| Requirement | Quantity |
| --- | --- |
| CPU | 16 cores Nodes in EPodV2 can be larger than 16 CPUs. However, they must always be a multiple of 16 for optimal resource usage. |
| CPU architecture | x86_64 |
| Minimum memory | 64 GiB > [!NOTE] > **Note** > > You must maintain a 4 GB to 1 CPU ratio. |
| Disk | 1 TB |
| vm_max_map_count > [!NOTE] > **Note** > > Set the **vm_max_map_count** only if you deploy Elasticsearch with the pod. | 262144 |
| Minimum number of nodes | 1 |
- Additional requirements

| Requirement | Detail |
| --- | --- |
| Cloud account | If deploying in cloud environments, Securiti recommends having a dedicated cloud account to deploy Securiti pods. |
| Cluster roles | You must define Cluster Roles. The following table contains all cluster roles. |
| Access to namespace | You must provide full access to the namespace. |

### Network prerequisites

Add the following network URL to connect your EPod V2.

- For the US cloud:

| URL | Purpose |
| --- | --- |
| app.securiti.ai, port 443 | Securiti cloud |
| prod-us-west-2-starport-layer-bucket.s3.us-west-2.amazonaws.com, port 443 | For pulling images from Securiti registry |
| privaci-registry.s3.us-west-2.amazonaws.com, port 443 | AWS S3 bucket for metadata, logs storage |
| securiti-state-718391394098.s3.us-west-2.amazonaws.com, port 443 | Storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d31wfa8az5rt1f.cloudfront.net | Securiti appliance bundle download from CDN |
- For the US1 cloud:

| URL | Purpose |
| --- | --- |
| app1.securiti.ai, port 443 | Securiti cloud |
| storage.googleapis.com, port 443 | For storing states on the cloud |
| us-docker.pkg.dev | For pod auto updates |
- For the Canada cloud:

| URL | Purpose |
| --- | --- |
| app3.securiti.ai, port 443 | Securiti cloud |
| privaci-montreal-registry.s3.ca-central-1.amazonaws.com, port 443 | AWS S3 bucket for metadata, logs storage |
| securiti-montreal-state-718391394098.s3.ca-central-1.amazonaws.com, port 443 | Storage provided by Securiti for storing assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| prod-ca-central-1-starport-layer-bucket.s3.ca-central-1.amazonaws.com, port 443 | For pulling images from Securiti registry |
| d1wxubre8y9029.cloudfront.net | Securiti appliance bundle download from CDN |
- For the EU cloud:

| URL | Purpose |
| --- | --- |
| app.eu.securiti.ai, port 443 | Securiti cloud |
| privaci-eu-registry.s3.eu-west-1.amazonaws.com, port 443 | AWS S3 bucket for metadata, logs storage |
| securiti-eu-state-718391394098.s3.eu-west-1.amazonaws.com | Storage provided by Securiti for storing assessment attachments, DSR attachments, evidence files produced by discovery scans etc. This is used only if private storage is not configured. |
| prod-eu-west-1-starport-layer-bucket.s3.eu-west-1.amazonaws.com, port 443 | For pulling images from Securiti registry |
| d17vfm9hd4ph8q.cloudfront.net | Securiti appliance bundle download from CDN |
- For the Indonesia cloud:

| URL | Purpose |
| --- | --- |
| app2.securiti.ai, port 443 | Securiti cloud |
| privaci-jakarta-registry.s3.ap-southeast-3.amazonaws.com, port 443 | AWS S3 bucket for metadata, logs storage |
| prod-ap-southeast-3-starport-layer-bucket.s3.ap-southeast-3.amazonaws.com, port 443 | For pulling images from Securiti registry |
| securiti-jakata-state-718391394098.s3.ap-southeast-3.amazonaws.com, port 443 | Storage provided by Securiti for storing assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d2nhybc0go9etk.cloudfront.net | Securiti appliance bundle download from CDN |
- For the Australia cloud:

| URL | Purpose |
| --- | --- |
| app4.securiti.ai, port 443 | Securiti cloud |
| privaci-sydney-registry.s3.ap-southeast-2.amazonaws.com, port 443 | AWS S3 bucket for metadata, logs storage |
| prod-ap-southeast-2-starport-layer-bucket.s3.ap-southeast-2.amazonaws.com, port 443 | For pulling images from Securiti registry |
| securiti-sydney-state-718391394098.s3.ap-southeast-2.amazonaws.com, port 443 | Storage provided by Securiti for storing assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d2ukknqt0z03bc.cloudfront.net | Securiti appliance bundle download from CDN |
- For the UAE cloud:

| URL | Purpose |
| --- | --- |
| app5.securiti.ai, port 443 | Securiti cloud |
| privaci-uae-registry.s3.me-central-1.amazonaws.com, port 443 | AWS S3 bucket for metadata, logs storage |
| prod-me-central-1-starport-layer-bucket.s3.amazonaws.com, port 443 | For pulling images from Securiti registry |
| securiti-uae-state-718391394098.s3.me-central-1.amazonaws.com, port 443 | Storage provided by Securiti for storing assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| d1k2hmyn0i0qdq.cloudfront.net | Securiti appliance bundle download from CDN |
- For the India cloud:

| URL | Purpose |
| --- | --- |
| app6.securiti.ai | Securiti cloud |
| prod-ap-south-1-starport-layer-bucket.s3.ap-south-1.amazonaws.com | For pulling images from Securiti registry |
| securiti-mumbai-state-718391394098.s3.ap-south-1.amazonaws.com | Storage provided by Securiti for storing assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| privaci-mumbai-registry.s3.ap-south-1.amazonaws.com/ | AWS S3 bucket for metadata, logs storage |
| dhth5mgsbl3e0.cloudfront.net | Securiti appliance bundle download from CDN |
- For the KSA cloud:

| URL | Purpose |
| --- | --- |
| app7.securiti.ai, port 443 | Securiti cloud |
| me-central2-docker.pkg.dev | For pod auto updates |
| https://storage.cloud.google.com/securiti-state-419004438835 | Storage provided by Securiti for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |
| https://storage.cloud.google.com/securiti-artifacts-402060762925 | GCP storage for metadata, logs storage |
- For the Qatar cloud

| sURL | Purpose |
| --- | --- |
| app8.securiti.ai, port 443 | Securiti cloud |
| https://storage.cloud.google.com/securiti-artifacts-818816799760 | GCP bucket for metadata and logs storage |
| me-central1-docker.pkg.dev | For pod auto updates |
| https://storage.cloud.google.com/securiti-state-818816799760 | Storage provided by Securiti for storing assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. This is used only if private storage is not configured. |

- Pods only initiate outbound connections to Securiti. Securiti does not initiate inbound traffic to the pods. If your firewall restricts outbound traffic by IP address instead of URL, allowlist the fixed or static IP addresses in the table below.

> [!NOTE]
> Note
> 
> You do not need to allowlist Securiti NAT IP addresses for pod operations. You only need them when Securiti cloud accesses your resources directly, for example with [Private Cloud Storage](/latest/docs/private-cloud-storage) or a [SaaS data system connector](/latest/docs/data-systems-connector).

#### Allowlisting Fixed or static IP addresses

| Production instance | Endpoint | IP address |
| --- | --- | --- |
| US Cloud | - `app.securiti.ai` - `dbaas.securiti.ai` | - `3.33.255.181` - `15.197.226.17` |
| `edc.app.securiti.ai` | - `99.83.154.190` - `75.2.75.41` |
| `wf-mt.app.securiti.ai` | - `99.83.192.141` - `13.248.185.49` |
| EU Cloud | - `app.eu.securiti.ai` - `dbaas.eu.securiti.ai` | - `13.248.146.34` - `76.223.10.152` |
| `edc.app.eu.securiti.ai` | - `13.248.157.18` - `76.223.17.131` |
| `wf-mt.app.eu.securiti.ai` | - `3.33.157.145` - `13.248.203.29` |
| US GCP Cloud | - `app1.securiti.ai` - `dbaas1.securiti.ai` | `130.211.15.136` |
| `wf-mt.app1.securiti.ai` | `34.117.180.251` |
| `edc.app1.securiti.ai` | `34.149.178.111` |
| Indonesia Cloud (Jakarta) | - `app2.securiti.ai` - `dbaas2.securiti.ai` | - `15.197.177.4` - `99.83.174.152` |
| `edc.app2.securiti.ai` | - `75.2.80.61` - `35.71.139.160` |
| `wf-mt.app2.securiti.ai` | - `75.2.24.0` - `35.71.162.135` |
| Canada Cloud (Montreal) | - `app3.securiti.ai` - `dbaas3.securiti.ai` | - `3.33.247.163` - `15.197.223.53` |
| `edc.app3.securiti.ai` | - `13.248.237.13` - `99.83.252.143` |
| `wf-mt.app3.securiti.ai` | - `75.2.30.3` - `99.83.173.145` |
| Australia Cloud (Sydney) | - `app4.securiti.ai` - `dbaas4.securiti.ai` | - `75.2.95.27` - `99.83.242.162` |
| `edc.app4.securiti.ai` | - `13.248.177.10` - `99.83.131.159` |
| `wf-mt.app4.securiti.ai` | - `52.223.22.58` - `99.83.129.186` |
| United Arab Emirates (UAE) Cloud | - `app5.securiti.ai` - `dbaas5securiti.ai` | - `75.2.112.22` - `76.223.121.184` |
| `edc.app5.securiti.ai` | - `13.248.249.42` - `76.223.78.161` |
| `wf-mt.app5.securiti.ai` | - `99.83.204.142` - `52.223.10.36` |
| India Cloud (Mumbai) | - `app6.securiti.ai` - `dbaas6.securiti.ai` | - `75.2.73.43` - `99.83.227.174` |
| `edc.app6.securiti.ai` | - `99.83.199.138` - `75.2.111.48` |
| `wf-mt.app6.securiti.ai` | - `99.83.153.136` - `15.197.164.36` |
| Kingdom of Saudi Arabia (KSA) Cloud | `app7.securiti.ai` | - `34.54.157.214` |
| State of Qatar Cloud | `app8.securiti.ai` `http://dbaas8.securiti.ai/` | - `34.54.165.185` |
| `app8.securiti.ai` | - `34.8.52.253` |

### OpenShift SCC requirements

To deploy EPod V2 in OpenShift infrastructure, you must apply the Security Context Constraints (SCC) files to your Kubernetes cluster. This ensures that the pods run in a restricted or unrestricted environment as per the requirements.

If you deploy EPod V2 in an OpenShift cluster, you must apply SCC to your Kubernetes cluster. The recommended way to download and apply SCCs is from the **OpenShift SCC** tab during installation. For more information, see [EPod V2 installation](/latest/docs/epod-v2-installation). If you need to apply SCCs before installation, you can download the SCC files below.

> [!NOTE]
> Note
> 
> All the SCC files provided below contain a default namespace of `securiti-pod`. You must update the namespace in each file before applying it if you are using a different namesapce.

**Restrict pod privileges (non-root)**

This SCC restricts pods to non-root users, ensuring they operate without elevated privileges. This restriction excludes the Monitor Status feature, which requires root-level access to collect logs.

To apply the restricted SCC, proceed with the following steps.

1. Download the restricted SCC file from the download icon below:

[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scc-rbac-restricted(3).yaml)scc-rbac-restricted4.89 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scc-rbac-restricted(3).yaml)
2. (Optional) Open the file in an editor and update the namespace if you have a different namespace title.
3. Apply the namespace to your Kubernetes cluster using the command below:

```bash
kubectl apply -f scc-rbac-restricted.yaml
```
4. Proceed with the standard installation process defined in [EPod V2 installation](/latest/docs/epod-v2-installation).
5. Validate the following values in `values.yaml` file before applying them during the installation.
  - Ensure that the following value in `values.yaml` is set to false.

```yaml
...
tags:
  monitor-status: false
```
  - Ensure that the following value in `values.yaml` is also set to false.

```yaml
global:
  ...
  enable_sys_admin: false
```

**Enable report generation (non-root)**

Enabling report generation lets you download the **Pod Diagnostic Report** of EPod V2. For OpenShift, this feature is not enabled by default. It requires `Host Path` in it and does not require any root access for the pods. You can apply it with any of the above SCCs.

To apply the report generation SCC, proceed with the following steps:

1. Download the Report Generation SCC file from the download icon below.

[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scc-hostpath.yaml)scc-hostpath1.82 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/scc-hostpath.yaml)
2. (Optional) Open the file in an editor and update the namespace if you have a different namespace title.
3. ```bash
kubectl apply -f scc-hostpath.yaml
```
4. Proceed with the standard installation process defined in [EPod V2 installation](/latest/docs/epod-v2-installation).

### Cluster roles

EPod V2 no longer requires cluster roles for general operations. The only remaining cluster role is the `kube-metrics-adapter`, listed in the table below:

> [!NOTE]
> **Note**
> 
> This role applies only if you use the HPA autoscaler type. EPod V2 automatically creates the kube-metrics-adapter cluster role during installation, if you use the HPA autoscaler type. You can verify it after installation.

| **Cluster role name** | **Permissions granted** | Description |
| --- | --- | --- |
| kube-metrics-adapter-server-resources-<namespace> | ```yaml # Source: securiti-appliance/charts/kube-metrics-adapter/templates/rbac.yaml apiVersion: rbac.authorization.k8s.io/v1 kind: ClusterRole metadata: name: kube-metrics-adapter-server-resources-<namespace> rules: - apiGroups: - custom.metrics.k8s.io resources: - '*' verbs: - get - list - watch - create - update - patch - delete - apiGroups: - extensions resources: - podsecuritypolicies resourceNames: - appliance-psp-root verbs: - use ``` | This role is only required for HPA auto-scaler type. |

### Priority Classes

Priority Classes are optional and Securiti now supports in-application quota management, which lets EPod V2 manage workload scheduling and quota enforcement without cluster-level PriorityClass resources. If you use in-application quota management, you do not need to configure Priority Classes. If you prefer to use Priority Classes, Securiti supports the following three types:

- Ondemand
- Scanjob
- SQL

For the Securiti provided configuration file of each Priority Class, see the table below.

| Priority Class name | YAML configuration file content |
| --- | --- |
| Ondemand | ```yaml apiVersion: scheduling.k8s.io/v1 description: This priority class to enforce resource quota for on-demand pods with limited capacity. kind: PriorityClass metadata: annotations: meta.helm.sh/release-name: priv-appliance meta.helm.sh/release-namespace: securiti-pod creationTimestamp: "2025-05-22T13:29:34Z" generation: 1 labels: app.kubernetes.io/instance: priv-appliance app.kubernetes.io/managed-by: Helm app.kubernetes.io/name: priv-appliance app.kubernetes.io/namespace: securiti-pod name: pods-ondemand-securiti-pod resourceVersion: "30141954" uid: 4c190f10-a270-4966-ba7f-2bc02ae87fbe preemptionPolicy: Never value: 10 ``` |
| Scanjob | ```yaml apiVersion: scheduling.k8s.io/v1 description: This priority class to enforce resource quota for scanjob pod with restricted resources. kind: PriorityClass metadata: annotations: meta.helm.sh/release-name: priv-appliance meta.helm.sh/release-namespace: securiti-pod creationTimestamp: "2025-05-22T13:29:34Z" generation: 1 labels: app.kubernetes.io/instance: priv-appliance app.kubernetes.io/managed-by: Helm app.kubernetes.io/name: priv-appliance app.kubernetes.io/namespace: securiti-pod name: pods-scanjob-securiti-pod resourceVersion: "30141955" uid: a3d3f096-c8a7-43b8-9232-3ebd0c6208ee preemptionPolicy: Never value: 10 ``` |
| SQL | ```yaml apiVersion: scheduling.k8s.io/v1 description: This priority class should be used for SQL pods only with resource constraints. kind: PriorityClass metadata: annotations: meta.helm.sh/release-name: priv-appliance meta.helm.sh/release-namespace: securiti-pod creationTimestamp: "2025-05-22T13:29:34Z" generation: 1 labels: app.kubernetes.io/instance: priv-appliance app.kubernetes.io/managed-by: Helm app.kubernetes.io/name: priv-appliance app.kubernetes.io/namespace: securiti-pod name: pods-sql-securiti-pod resourceVersion: "30141953" uid: 8b594ff7-66b2-4142-af6e-c2a2515a4240 preemptionPolicy: Never value: 100000 ``` |

You can also apply your custom priority class during EPod V2 installation. For more information, see [EPod V2 installation](/latest/docs/epod-v2-installation).

Each cluster has a primary node. You can add processing capacity to the pod by adding up to nine secondary nodes.

## Related

- [EPod V2 installation in Securiti](/epod-v2-installation.md)
- [Upgrading EPod V2](/upgrade-epod-v2.md)
- [Elastic Pods V2](/elastic-pods-v2.md)
