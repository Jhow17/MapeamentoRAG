---
title: "Managing pods (cluster version v1.28+)"
slug: "managing-pods-cluster-version-v128"
type: "index"
canonical: "helpcenter.securiti.ai/managing-pods-cluster-version-v128"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Managing pods (cluster version v1.28+)

1 sub category | 10 articles

## [Using the cluster status dashboard](https://helpcenter.securiti.ai/docs/using-the-cluster-status-dashboard.md)

Updated on 2026-08-10 | Published on 2025-07-22

The Cluster Status dashboard shows the stats of the pod. It helps see the current usage of resources and active jobs. It improves your allocation of system resources if it requires a scale-up or...

## [Updating pod software (cluster version v1.28+)](https://helpcenter.securiti.ai/docs/pod-updating-pod-software.md)

Updated on 2026-08-26 | Published on 2025-07-22

Updating the pod software also updates the cluster version. On the Pods dashboard, Securiti displays an alert for any of your pods that are running application software versions older than three...

## [Upgrading pods cluster version](https://helpcenter.securiti.ai/docs/upgrading-pods-cluster-version.md)

Updated on 2026-08-24 | Published on 2025-07-22

You can perform the upgrade process for Kubernetes clusters used in Securiti Pod v2. This documentation outlines the steps to perform the upgrade, important considerations, and how to troubleshoot any...

## [Backing up and restoring pods](https://helpcenter.securiti.ai/docs/backing-up-and-restoring-pod.md)

Updated on 2026-04-06 | Published on 2025-09-09

You can backup Securiti pods to remote locations, and also restore them from the backups. First, you configure the backup host. After that, you can do immediate backups, schedule recurring backups,...

## [Adding secondary nodes](https://helpcenter.securiti.ai/docs/pods-adding-secondary-nodes-cluster-version-v128.md)

2 articles | Updated on 2026-10-06 | Published on 2025-07-22

You can add up to 4 Standard secondary nodes and 2 Plus secondary nodes to your pod cluster. You deploy each secondary nodes onto a compute instance or VM just like a master node. The compute instance...

## [Migrating to pod cluster version (cluster version v1.28+)](https://helpcenter.securiti.ai/docs/migrating-to-pod-cluster-version.md)

Updated on 2026-03-25 | Published on 2025-08-28

The procedure in this section describes how to migrate an existing pod of cluster version 1.0.12 to a pod of cluster version 1.128+ on the same VM. Prerequisites The cluster is healthy, and you have...

## [Migrating Pod v1.28+ to EPod V2](https://helpcenter.securiti.ai/docs/migrating-pod-v128-to-epod-v2.md)

Updated on 2026-08-02 | Published on 2025-12-09

This guide explains how to migrate from Pod V2 to Elastic Pods V2 (EPod V2). It covers the preparation steps, migration workflow, and post-migration activities required to ensure a smooth transition....

## [Resizing pod VMs (cluster version v1.28+)](https://helpcenter.securiti.ai/docs/pods-resizing-pod-vms.md)

Updated on 2026-08-31 | Published on 2026-08-31

As your requirements change, you can resize pod VMs between the two supported sizes of 16 and 32 vCPUs on the following IaaS platforms. Doing so does not disrupt pod function: AWS GCP Azure Important...

## [Temporarily stopping nodes for maintenance (cluster version v1.28+)](https://helpcenter.securiti.ai/docs/pods-temporarily-stopping-nodes-for-maintenance.md)

Updated on 2025-11-03 | Published on 2025-07-22

To temporarily disable a node for routine server maintenance: kubectl cordon

## [Permanently removing a node (cluster version v1.28+)](https://helpcenter.securiti.ai/docs/pods-permanently-removing-a-node.md)

Updated on 2025-12-09 | Published on 2025-07-22

An existing node can cause problems during a reinstallation, so you should remove it before reinstalling the node. Before removing the node, you must migrate its data to the master node. Follow the...

## [Uninstalling a pod (cluster version v1.28+)](https://helpcenter.securiti.ai/docs/uninstalling-a-pod-cluster-version-v128.md)

Updated on 2025-12-09 | Published on 2025-07-22

Un-register the Pod To uninstall the pod, you must first un-register the pods from the SaaS platform. Follow the steps below to do that: Log in to Securiti with your admin credentials. To open the...
