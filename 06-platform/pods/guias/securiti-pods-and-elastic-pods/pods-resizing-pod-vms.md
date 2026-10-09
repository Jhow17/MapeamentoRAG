---
title: "Resizing pod VMs (cluster version v1.28+)"
slug: "pods-resizing-pod-vms"
updated: 2026-08-31T12:42:15Z
published: 2026-08-31T12:42:15Z
canonical: "helpcenter.securiti.ai/pods-resizing-pod-vms"
stale: true
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Resizing pod VMs (cluster version v1.28+)

As your requirements change, you can resize pod VMs between the two supported sizes of 16 and 32 vCPUs on the following IaaS platforms. Doing so does not disrupt pod function:

- [AWS](/v1/docs/pods-resizing-pod-vms#aws)
- [GCP](/v1/docs/pods-resizing-pod-vms#gcp)
- [Azure](/v1/docs/pods-resizing-pod-vms#azure)

> [!NOTE]
> **Important**
> 
> We recommend that you only resize a pod VM when the pod is not actively running any scans.

## AWS

In the AWS console, navigate to **EC2 > Instances > Actions > Instance Settings > Change Instance Type** and choose one of the instance types supported for AWS as described in [Supported VM types](/v1/docs/pods-recommended-pod-provisioning#supported-vm-types).

![image-20230802-181432.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-43e91477-a006-f485-05f5-e67dfc3d0c0c(4).png)

## GCP

In the GCP console, navigate to **VM Instances > Edit > Machine Configuration**, choose Series **E2**, and then choose one of the instance types supported for GCP as described in [Supported VM types](/v1/docs/pods-recommended-pod-provisioning#supported-vm-types).

![image__2___1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2569239d-9b1b-4ef2-5795-dd12168abeda(4).png)

## Azure

1. In Azure, manually mount the /mnt directory.

In Microsoft Azure, the default configuration for the /mnt directory is as a temporary disk mount. To adjust the VM size, you must manually mount a disk on the /mnt directory.
2. In the Azure console, navigate to **Virtual Machine (VM)** **> Settings > Size**, and then choose one of the instance types supported for Azure as described in [Supported VM types](/v1/docs/pods-recommended-pod-provisioning#supported-vm-types).

![image-20230802-181134.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-33c7936d-0c1e-b438-5b20-47ee554df862(4).png)

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Updating pod software (cluster version v1.28+)](/pod-updating-pod-software.md)
