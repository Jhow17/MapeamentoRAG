---
title: "Installing multiple pods in Cluster"
slug: "installing-multiple-pods-in-cluster"
updated: 2026-07-02T12:20:10Z
published: 2026-07-02T12:20:10Z
canonical: "helpcenter.securiti.ai/installing-multiple-pods-in-cluster"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Installing multiple pods in Cluster

If you want to install multiple application pods in a single cluster under different namespaces, you need to select a different namespace from the previous option. Additionally, you must adjust some other settings in the final values file, as highlighted in the figure below.

![16_Ports_config.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8f92527-e1d4-1a4e-0561-f08346f7f4d3(2).png)

You must set the tag of Kube Metrics Adapter to *false*. If you deleted the first cluster where this value was set to *false*, you might need to update this value to *true* again and run the cluster upgrade on the second cluster.

> [!TIP]
> **Note**
> 
> If you install two EPod V2 instances on a cluster and then delete the first EPod V2, you must enable these APIs and upgrade the cluster with the following settings:
> 
> ```yaml
> tags:
>   kube-metrics-adapter: true
> ```

Apart from the API services, the Ranger policy service node port must be unique for each installed cluster. The default port values for the first node are **31000** and **31001** for HTTPS and HTTP services, respectively. You can choose any other value for the second cluster and beyond.

> [!TIP]
> **Note**
> 
> These values must reside within the range of 30000 to 32767 and must not be in use by any other service.

## Related

- [Upgrading EPod V2](/upgrade-epod-v2.md)
- [Managing EPod V2](/managing-epod-v2.md)
- [Backup and restore EPod V2](/backup-and-restore-epod-v2.md)
