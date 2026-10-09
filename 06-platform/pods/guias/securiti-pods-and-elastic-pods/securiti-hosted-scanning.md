---
title: "Securiti Hosted Scanning"
slug: "securiti-hosted-scanning"
updated: 2026-09-18T08:30:36Z
published: 2026-09-18T08:30:36Z
canonical: "helpcenter.securiti.ai/securiti-hosted-scanning"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Securiti Hosted Scanning

## Scenario

As a Data Security Officer, you’re tasked with scanning cloud data stores without overloading your own infrastructure. Running scans internally strained resources and slowed other critical processes. With Securiti Hosted Scanning, the scanning pod runs entirely within Securiti’s environment, using its compute power to scan your cloud data remotely. This reduces internal load while maintaining full visibility into data risk and movement.

## Overview

> [!WARNING]
> Important
> 
> This feature is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

Securiti Hosted Scanning provides a fully hosted and managed infrastructure solution for customers who require seamless scanning of SaaS application data without the burden of cloud resource management. Hosted within Securiti’s cloud environment, these pods eliminate the need for you to deploy or maintain your own infrastructure, making it an ideal choice for businesses with restricted cloud services or limited computing resources.

This solution is primarily aimed at scanning SaaS applications, where you will not incur data egress fees or have to manage public accessibility of on-premise resources.

### Installation

To install the Securiti Managed:

1. If you have purchased Securiti Managed Scanning, Securiti will size and deploy the infrastructure necessary based on the volume of data you will be scanning.
2. After the infrastructure is provisioned, it will be associated with your tenant, and you can begin to connect to data systems and begin scanning.

### Supported features

The Securiti Managed Pod provides you with a unique feature.

| Feature | Details |
| --- | --- |
| Start and stop the pod infrastructure | This feature lets you start and stop the pods whenever you require. Once the pod is stopped, change the pod state to stop. ![start-stop.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-743bbf42-1bce-aea6-fee9-5eda535cd1a4(2).png) |
| Deployment assistance | Deploying the scanning infrastructure is fully managed by the Securiti team. |
| Resource maintenance | Securiti Cloud manages the resources and pod maintenance. |
| Adding a new node while pod creation | You can provide details to the support team about adding nodes to your pod during the initial process. |

#### Unavailable features

Some features that are available in regular pods are restricted because the Securiti team manages the configurational aspects of the pods.

| Feature | Details |
| --- | --- |
| Name | You can’t change the name of the pods. |
| Delete pod via support | You can not delete the pod directly. ![update_and_delete_restrictions.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a73c4f0-5940-0aa6-8ed0-0cf2ed915a6d(2).png) |
| Revoke pod | You can not revoke the pod. |
| Adding a new node later | You can't add a new worker node after the pod is created. |
| Deleting a node | You can't delete any node that is created for you at the time of creation. |
| Backup and restore | As the Securiti team manages the pods, you cannot backup and restore on our cloud instance, therefore, it is restricted. |
| Delay auto upgrade | Currently, you can’t enable the feature to delay the auto upgrade process. The default pods auto upgrades when an update is available. |

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Pod installation (cluster version v1.28+)](/pod-installation-cluster-version-v128.md)
