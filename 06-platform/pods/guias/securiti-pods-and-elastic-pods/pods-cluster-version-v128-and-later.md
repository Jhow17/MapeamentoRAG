---
title: "Pods (cluster version v1.28 and later)"
slug: "pods-cluster-version-v128-and-later"
status: "update"
updated: 2025-11-13T06:56:57Z
published: 2025-11-13T06:56:57Z
canonical: "helpcenter.securiti.ai/pods-cluster-version-v128-and-later"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Pods (cluster version v1.28 and later)

## Scenario

As a Data Security Officer, you’re responsible for isolating sensitive data environments to minimize risk. Managing shared cloud infrastructure made it harder to enforce strict data boundaries. With Pods VM, you deploy the Securiti application in a dedicated virtual machine like an EC2 instance on AWS, keeping all storage and databases self-contained. This ensures data isolation, simplifies audits, and strengthens your security posture.

## Overview

The topics in this section describe installing and managing Securiti ​​pods of cluster version 1.28 and later.

The ​Securiti​ application deploys in your environment to perform scanning and all related operations internally. It helps your organization keep the data and scan evidence manageable within your premises. It improves scan maintenance, security, and meets compliance. ​Securiti​​ supports the deployment in both premises:

- Cloud environment
- On-premises environment

For cloud, we support all types of cloud service providers for deployment; however, you must meet some prerequisites for a successful deployment.

## Understanding a Securiti pod

The ​Securiti ​pods are a list of container images that you can deploy in your cloud environment. This pod version requires you to create and deploy the containers into a standalone virtual machine. The specifications of the virtual machine are available on the [Pod Prerequisites](/v1/docs/pod-prerequisites-cluster-version-v128) page. The containers after successful deployment can connect to the ​Securiti platform, where you can operate the pod, schedule the scans, specify where to store the evidence, take backups, and restore them. The platform also displays the pod usage in your environment. Usually, the usage is high when it's scanning the data.

For the installation, Securiti provides a complete guide for deploying the pod. For VM-based pods, Securiti provides an installer that deploys every dependency and package along with the Securiti application. For troubleshooting and diagnosis, Securiti also provides a diagnostic script that helps you find out the problems in the pod. It ensures that the deployment process remains smooth.

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Using the pre-flight diagnostic script (cluster version v1.28+)](/pods-using-the-pre-flight-diagnostic-script.md)
- [Pod quick install guides cluster version v1.28](/pod-quick-install-guides-cluster-version-v128-en.md)
- [Pod custom installation guides (cluster version v1.28+)](/podcustom-installation-guides.md)
