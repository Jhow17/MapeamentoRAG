---
title: "Getting Started with Securiti Pods"
slug: "getting-started-with-securiti-pods-2"
updated: 2026-06-30T07:03:14Z
published: 2026-06-30T07:03:14Z
canonical: "helpcenter.securiti.ai/getting-started-with-securiti-pods-2"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Securiti Pods

## Steps to get started with Pods

With Securiti’s Pods and Elastic Pods V2, you can connect to your private or on-prem data systems to intelligently scan them to classify content, identify personal data, upload hashed values of the personal data to your account, and act as a hop-off point for DSR requests for your on-premises and user-defined data systems.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Pods-design%201.drawio(2).svg)

### Step 1: Understanding the pod prerequisites

Understand the prerequisites for deploying Pod by ensuring that your environment meets the required configurations. The primary requirements include operating system, RAM, CPUs, disk type, and space etc. Additionally, you may require whitelisting URLs and opening ports for intra-node communication.

[Learn more](/latest/docs/prerequisites-1)

### Step 2: Running the pre-flight diagnostic script

Run the pre-flight diagnostic script to ensure that your VM or server is properly provisioned for pod deployment. This script helps identify any potential configuration issues and allows you to troubleshoot and resolve installation problems before proceeding. It's recommended to execute this script every time you install or upgrade a pod to ensure a smooth and successful deployment process.

![download-preflight.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d19ab78a-18fe-2bf6-5535-f765661d8eac(5).png)

[Learn more](/latest/docs/pods-using-the-pre-flight-diagnostic-script)

### Step 3: Installing pods via Securiti platform

| **Quick installation** Quickly deploy a Securiti pod using one of two methods: From the Deployments Page: Deploy a pod and activate connectors later by selecting Quick Install under **System Settings > Deployment > Pods**. From Sensitive Data Intelligence: Deploy a pod to scan specific IaaS resources directly from Sensitive Data Intelligence. [Learn more](/latest/docs/pod-quick-install-guides-cluster-version-v128-en) | ![quick_install.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a25c4e5-4f69-cb2c-7414-954c29bc6fd3(2).png) |
| --- | --- |
| **Custom installation** Choose Automated Install for a standard pod setup with a single CURL command (v1.28+). For custom configurations like HTTP/HTTPS proxy, use Manual Install, which allows step-by-step commands for more control and easier troubleshooting. [Learn more](/latest/docs/podcustom-installation-guides) | ![Manual_install.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f07ca007-29e9-6f93-21c2-dd5fdefb446e(2).png) |

### Step 4: Manage pods cluster

| ![cluster-health-scan-job-status.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8f0bc04b-a57d-bf29-b197-ec66a2a57cc7(6).png) | **Monitoring Pods cluster** Monitor the health and performance of your pod cluster using the Cluster Status Dashboard. It provides real-time insights into the status of nodes, resource usage, and any potential issues. Track CPU and memory consumption, pod availability, and overall cluster health to ensure smooth operation and identify any issues that need attention. [Learn more](/latest/docs/migrating-to-pod-cluster-version) |
| --- | --- |
| ![pod_cluster_version.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-de0bbc89-f8cc-8b04-eec6-48c46b55ebd0(9).png) | **Updating Pods cluster version** Keep your pods up-to-date with the latest software release to ensure optimal performance and security. Securiti alerts you on the Pods Dashboard if any pod is running software more than three releases behind. You can update pods manually via the Securiti UI or schedule automatic updates to ensure continuous compliance with the latest versions. [Learn more](/latest/docs/pod-updating-pod-software) |
| ![Backup_Pod.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-090dfd78-e3de-cc2e-ce8c-b96f35392498(2).png) | **Backup and Restore Pods** Ensure data safety and system reliability by setting up regular backup and restore processes for your Securiti pods. Backups are performed every 24 hours, minimizing potential data loss to a maximum of 24 hours. The process covers essential databases, including Redis, Postgres, and Elasticsearch, safeguarding connector configurations and scan data. In case of failures, crashes, or migrations, these backups allow for quick restoration to ensure business continuity. [Learn more](/latest/docs/backing-up-and-restoring-pod) |
| ![node_addition_manual.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ec936dd1-35b7-6f1a-ce2a-aa1703e232a9(2).png) | **Adding secondary node to the cluster** Expand your pod cluster by adding up to 9 secondary nodes. Each secondary node is deployed onto a compute instance or VM, similar to a master node, and must meet the same prerequisites. For installation, choose Automated Install for standard setups or Manual Install for custom configurations, such as HTTP/HTTPS proxy settings, based on your organization's IT policies. [Learn more](/latest/docs/pods-adding-secondary-nodes-cluster-version-v128) |
| ![Node_addition.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d0e9eac-67dd-a8ed-9562-904a0ce67b1f(2).png) | **Removing nodes from a pods cluster** You can either permanently remove a node from the cluster or temporarily stop a node for maintenance. Permanent removal decommissions the node from the cluster, while temporarily stopping a node allows you to perform maintenance without affecting the overall cluster performance. Both actions help maintain optimal pod operations and resource management. [Learn more](/latest/docs/pods-permanently-removing-a-node) |
| ![Uninstall.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d11e45d-05cc-b312-81dd-b2f012fd900d(2).png) | **Uninstalling a pod** To uninstall a pod, you must first unregister it before deleting it. Start by unregistering the pod from the Pods Dashboard to remove its association with your deployment. Once unregistered, proceed to delete the pod from the environment. This two-step process ensures the pod is fully removed and no longer active in your system. [Learn more](/latest/docs/uninstalling-a-pod-cluster-version-v128) |

### Steps to get started with Elastic Pod V2

Elastic Pod V2 (EPod V2) provides a scalable solution for dynamically adjusting resources in response to changing workloads. Designed to support installation in your existing Kubernetes environment or a dedicated cluster, EPod V2 provides optimized performance and efficiency. It automatically scales up or down based on real-time demand, ensuring your system can handle varying loads without over-provisioning. This flexibility enhances resource utilization while maintaining seamless operations in cloud and on-premises environments.

The deployment procedure for all the clouds is the same, as the deployment takes place within a Kubernetes cluster.

#### Step 1: Understanding Elastic Pods V2 prerequisites

| Elastic Pods V2 prerequisites help you understand all the system requirements and procedures you must follow before the installation. It includes: - System prerequisites - Network prerequisites - OpenShift SCC requirements (for OpenShift deployments only) - (Optional) Priority Classes [Learn more](/latest/docs/prerequisites-for-epod-v2) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NM3HDXQQ.png) |
| --- | --- |

#### Step 2: Elastic Pods V2 installation

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/getting-started-with-pods-en-image-vlgn2dz6.png) | **Installing Elastic Pods V2** The installation of Elastic Pods V2 in your Kubernetes cluster starts with setting up the configurations. It includes: - Selecting the source of application containers - Preflight check to validate that the cluster meets requirements - Settings for the monitoring tool - Settings for data storage - Settings for memory allocation Once the initial setup is complete, deploy Elastic Pods V2 in your Kubernetes cluster with the already provided command. [Learn more](/latest/docs/epod-v2-installation-1) |
| --- | --- |

#### Step 3: Upgrading Elastic Pods V2

| Once the newer version of Elastic Pods V2 is out, upgrade your pods to the latest version. It lets you: - Upgrade using Securiti registry - Upgrade using custom registry - Upgrade internal databases [Learn more](/latest/docs/upgrade-epod-v2) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/getting-started-with-pods-en-image-z0alm5h3.png) |
| --- | --- |

#### Backup and restore Elastic Pods V2

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/getting-started-with-pods-en-image-s95osvzm.png) | You can backup the Elastic Pods V2 to your preferred internal or external location and restore from it. It lets you upgrade the pod, migrate the infrastructure, and implement disaster recovery plans safely. It lets you backup: - Connector's configurations - Databases [Learn more](/latest/docs/backup-and-restore-epod-v2) |
| --- | --- |

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

A cluster is comprised of a primary node and up to nine secondary nodes.

## Related

- [Pods (cluster version v1.28 and later)](/pods-cluster-version-v128-and-later.md)
- [Elastic Pods V2](/elastic-pods-v2.md)
- [Securiti Hosted Scanning](/securiti-hosted-scanning.md)
- [Pods release notes](/pods-release-notes.md)
