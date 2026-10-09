---
title: "Recommended pod provisioning (cluster version v1.28+)"
slug: "pods-recommended-pod-provisioning"
updated: 2026-05-07T08:11:07Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/pods-recommended-pod-provisioning"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Recommended pod provisioning (cluster version v1.28+)

### 

When you deploy Securiti pods we recommend that you use these provisioning metrics. See also [Pod prerequisites (cluster version v1.28+)](/v1/docs/pod-prerequisites-cluster-version-v128):

## Cluster sizing

Pod nodes are supported on either 16 or 32 vCPU VMs. Other quantities of vCPUs are not supported:

| Edition | Cluster size | Primary node | Secondary node | Recommendation |
| --- | --- | --- | --- | --- |
| **Standard** | Up to 5 nodes (1 Master + 4 Secondaries) | - vCPU: 16 - Mem: 64G - SSD*: min 1TB - IOPS: min 3000 | - vCPU: 16 - Mem: 64G - SSD*: 1TB - IOPS: 3000 | > [!NOTE] > Note > > Proof-of-concept deployments can start with one node and grow as needed. With the increase of vCPU, you must increase the Memory and SSD with the same ratio of 16 vCPU : 64GB Memory : 1TB SSD, which is also the minimum requirement. \| vCPU \| RAM \| SSD \| \| --- \| --- \| --- \| \| 16 vCPU \| 64GB \| 1TB \| \| 32 vCPU \| 128GB \| 2TB \| |
| vCPU | RAM | SSD |
| 16 vCPU | 64GB | 1TB |
| 32 vCPU | 128GB | 2TB |
| **Plus** | Up to 3 nodes (1 Master + 2 Secondaries) | - vCPU: 32 - Mem: 128G - SSD*: min 2TB - IOPS: min 3000 | - vCPU: 32 - Mem:128G - SSD*: 2TB - IOPS: 3000 |  |
| General purpose SSD |

## Pod Resource Profiles

> [!NOTE]
> Note
> 
> If Resource Profile is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

The Pod Resource Profile feature lets you manage how system resources are allocated within a pod. It provides multiple predefined profiles that optimize resource distribution for specific workloads such as Sensitive Data Intelligence (SDI), policy, or lineage. You can select and switch profiles without restarting pods. This helps maintain optimal performance and efficient resource utilization across different workloads. This feature supports both Pods (cluster version v1.28+) and Elastic Pods V2.

See the table below for available Resource Profiles.

| Resource Profile | Description |
| --- | --- |
| SDI Optimized | This is the default profile that maintains the existing V3 scaling behavior. It gives higher resource priority to the Download Worker for Sensitive Data Intelligence (SDI) processing to ensure faster data ingestion and stable performance. Use this profile for standard SDI workloads. |
| Policy Optimized | This profile prioritizes resources for **Connector-Policy** deployment. It dynamically adjusts memory allocation to favor policy-related tasks and reduces preference for the Download Worker. Use this when running policy intensive operations. |
| Spark Optimized | This profile requires more memory and compute resources for the Spark deployment. It improves performance for data lineage processing and large scale analytical tasks. Use this for workloads requiring heavy Spark computation. If you select Spark profile, you must add 128 GB of additional memory to support it. |

You can apply it to the following stages:

- For Pod (cluster version v1.28+), while using Custom Install, you can select it during the installation or after the installation. After installation, you must update the pod to apply the changes.
- For Elastic Pod V2, you can select it during installation or update it later.

When you deploy a pod with the Policy Optimized or SDI Optimized profiles, you cannot update your pod to Spark Optimized later. It is because Spark Optimized deployment creates and requires some Custom Resource Definitions (CRD) resources which Helm does not create with any other profile.

In order to create CRD resources of Spark Optimized profile after EPod V2 deployment, proceed with the following steps:

1. Download the following CRD files for Spark Optimized resources:

[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sparkoperator.k8s.io_sparkconnects(1).yaml)sparkoperator.k8s.io_sparkconnects12.79 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sparkoperator.k8s.io_sparkconnects(1).yaml)[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sparkoperator.k8s.io_sparkapplications.yaml)sparkoperator.k8s.io_sparkapplications778.39 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sparkoperator.k8s.io_sparkapplications.yaml)[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sparkoperator.k8s.io_scheduledsparkapplications.yaml)sparkoperator.k8s.io_scheduledsparkapplications828.33 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sparkoperator.k8s.io_scheduledsparkapplications.yaml)
2. Apply these files to your Kubernetes Cluster using the following command:

```plaintext
kubectl apply -f sparkoperator.k8s.io_sparkconnects.yaml -f sparkoperator.k8s.io_sparkapplications.yaml -f sparkoperator.k8s.io_scheduledsparkapplications.yaml
```

It creates these resources in the Kubernetes Cluster.

Once it creates these CRD resources, you can then update your pod to Spark Optimized profile.

## Disk partition sizing

| SKU | / (root partition) | Installation directory (usually but not always /mnt) | /tmp |
| --- | --- | --- | --- |
| **Starter** | 75Gb | 900Gb | 50Gb |
| **Standard** |
| **Plus** | 75Gb | 2TB | 50Gb |

> [!NOTE]
> **Note**
> 
> If you want to to avoid a single mount under /mnt, we recommend you provision it like this:
> 
> | Directory | Size |
> | --- | --- |
> | /mnt/installation | 200G |
> | /mnt/rancher | 300G |
> | /mnt/securiti-app | 500G |
> | /usr | 5G |
> | /run | 60G |
> | /var | 30G |
> | /etc | 5G |
> 
> In case you are provisioning multiple mount points, the overall sum of the different mount points such as /usr, /run, /var, etc. can exceed 1TB

## Recommended VM types

On cloud services such as AWS, Azure, and GCP, we recommend that you use these VM types:

| Cloud | VM type |
| --- | --- |
| **AWS** | - m7i.4xlarge (vCPU:16 RAM: 64G) - m7i.8xlarge (vCPU:32 RAM: 128G) |
| **GCP** | - E2-standard-16 (vCPU:16 RAM: 64G) - E2-standard-32 (vCPU:32 RAM: 128G) |
| **Azure** | Dv4-Series: - Standard_D16as_v4 (vCPU:16 RAM: 64G) - Standard_D32as_v4 (vCPU:32 RAM: 128G) |
| CPU architecture must support `x86`. |

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Using the pre-flight diagnostic script (cluster version v1.28+)](/pods-using-the-pre-flight-diagnostic-script.md)
- [Configuring customer-signed certificates (cluster version v1.28+)](/configuring-customer-signed-certificates.md)
