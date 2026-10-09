---
title: "Securiti pods and elastic pods"
slug: "securiti-pods-and-elastic-pods"
status: "update"
updated: 2025-12-03T08:17:53Z
published: 2025-12-03T08:17:53Z
canonical: "helpcenter.securiti.ai/securiti-pods-and-elastic-pods"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Securiti pods and elastic pods

You use pods and elastic pods to connect with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

Elastic pods are functionally equivalent to regular pods, but because they are cloud-based are much more scalable. You can easily increase their capacity to match your processing needs.

This table compares the features of pods and elastic pods:

| Feature | Pods (all cluster versions) | Elastic pods |
| --- | --- | --- |
| Auto-scaling | Not supported | Supported |
| Secondary Nodes | Supported | Not necessary because of auto-scaling |
| Database (Redis, Postgres, ES) | Embedded | Internal and External both |

For both pods and elastic pods, there are two basic types of installation::

| Installation type | Description |
| --- | --- |
| Quick Install | Quickly deploys a pod or elastic pod on a compute instance in any of several common IaaS platforms. You can choose to either install the pod software on an existing compute instance or deploy a new compute instance and install the pod software on it. |
| Custom Install | Lets you install a pod or elastic pod on IaaS or private cloud infrastructure that you provide, and over which you have complete control. Custom installation gives you complete freedom to adapt the pod or elastic pod to suit your specific needs. |
