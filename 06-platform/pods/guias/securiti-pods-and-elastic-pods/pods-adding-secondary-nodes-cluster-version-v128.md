---
title: "Adding secondary nodes (cluster version v1.28+)"
slug: "pods-adding-secondary-nodes-cluster-version-v128"
status: "update"
updated: 2026-10-06T07:52:36Z
published: 2026-10-06T07:52:36Z
canonical: "helpcenter.securiti.ai/pods-adding-secondary-nodes-cluster-version-v128"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Adding secondary nodes

You can add up to 4 Standard secondary nodes and 2 Plus secondary nodes to your pod cluster. You deploy each secondary nodes onto a compute instance or VM just like a master node. The compute instance or VM must meet the same prerequisites as that of a master node. See [Pod prerequisites](/v1/docs/pod-prerequisites-cluster-version-v128) (cluster version v1.28+) for more information.

Choose automated installation if you want a standard secondary node installation for typical on-premises data systems. Choose manual if you must customize the node installation, for example, to configure HTTP or HTTPS proxy (based on your organization's internal IT policies).

> [!NOTE]
> **Note**
> 
> 1. If you deployed the original cluster using manual installation mode, you must add secondary nodes using manual installation.
> 
> 2. Before adding a secondary node, you must upgrade your Cluster to the latest cluster version.

- [Automated secondary node installation](/v1/docs/pod-automated-secondary-node-installation) (cluster version v1.28+)
- [Manual secondary node installation](/v1/docs/pods-manual-secondary-node-installation) (cluster version v1.28+)

## Related

- [Automated secondary node installation (cluster version v1.28+)](/pod-automated-secondary-node-installation.md)
- [Manual secondary node installation (cluster version v1.28+)](/pods-manual-secondary-node-installation.md)
- [Upgrading pods cluster version](/upgrading-pods-cluster-version.md)
