---
title: "Elastic Pods V2"
slug: "elastic-pods-v2"
status: "update"
updated: 2026-06-11T08:10:50Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/elastic-pods-v2"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Elastic Pods V2

## Scenario

**Scenario**

As a Data Security Officer, you must ensure that the applications are scalable within your cloud infrastructure while maintaining complete visibility into all running applications at a single point. Managing multiple applications on different infrastructures or dividing resources among different Kubernetes clusters might lead to mismanagement. With Elastic Pods V2, you deploy the application directly into your existing Kubernetes cluster. It lets you manage logs, dashboards, and set alerts within a single application. This simplifies oversight and strengthens control over applications, data, and compliance.

## Overview

Elastic Pods V2 (EPod V2) is a new deployment model that lets you integrate our application within your Kubernetes (K8s) ecosystems, either existing or dedicated cluster. You can install the Securiti application in your cloud-based or on-site Kubernetes environments, eliminating the need for a Linux stack. This simplifies deployment, enhances operational control, and streamlines processes.

### Existing Pod VM vs EPod V2

Securiti's VM-based Pods necessitated that customers furnish a Linux VM, upon which we would install Kubernetes and the associated application services. All the services associated with the pod reside within the VM environment.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/elastic-pod-v2-en-image-qxhta9hv.jpg)

EPod V2 offers a more efficient deployment solution if you already have a Kubernetes (K8s) infrastructure.

EPod V2 lets you use your own services, such as:

- Redis
- Elastic Search
- Monitoring tools
- Metrics services within the namespace ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Epod V2 architecture diagram.png)

## Deployment model comparison

| Feature | Pod VM | EPod V2 |
| --- | --- | --- |
| Deployment | - On-premises - Cloud | - On-premises - Cloud |
| Privileges requirements | Requires root access to install K8s and troubleshoot | Doesn’t require root access for installation > [!NOTE] > Note > > Kubernetes components run as the root user in the cluster. |
| Upgrade model | Automatic | Manual (auto upgrade is coming soon) |
| Natively Elastic | No | Yes |
| Leverage existing Kubernetes infrastructure | No | Yes |
| Scanning Images | Securiti manages images for both Kubernetes and Securiti applications. It doesn’t let you scan application images before installation. | Securiti manages images for Securiti application only. It lets you scan application images before installation. |

## Related

- [Prerequisites for EPod V2](/prerequisites-for-epod-v2.md)
- [EPod V2 installation in Securiti](/epod-v2-installation.md)
- [Upgrading EPod V2](/upgrade-epod-v2.md)
