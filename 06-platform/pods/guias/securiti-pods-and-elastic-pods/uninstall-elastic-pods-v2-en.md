---
title: "Uninstall Elastic Pods V2"
slug: "uninstall-elastic-pods-v2-en"
updated: 2025-12-09T13:33:31Z
published: 2025-12-09T13:33:31Z
canonical: "helpcenter.securiti.ai/uninstall-elastic-pods-v2-en"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Uninstall Elastic Pods V2

# Uninstall EPod V2

Uninstalling EPod V2 lets you remove the complete pod, namespace, configurations, and databases. It completes the cleanup process of the EPod, removing all necessary data. It lets you redeploy the pod from scratch within the same namespace. It is useful when:

- When you completely remove the Pod along with its data from the cluster.
- When the first installation attempt fails and you need to reinstall it.

> [!WARNING]
> Important
> 
> As it deletes the data from all databases. If you have any data in the database, you must secure the files before the uninstallation process.

## EPod V2 uninstallation command

To uninstall the pod, execute the following commands in your Kubernetes cluster:

1. Set the release name to the variable.

```bash
release=priv-appliance
NAMESPACE="<your namespace where EPod V2 is installed>"
```

1. Uninstall the specified Helm release in the given namespace and wait until completion.

```bash
helm uninstall "$release" -n "$NAMESPACE"
```

1. Force delete all pods in the specified namespace.

```bash
kubectl delete pods --all -n "$NAMESPACE" --force --grace-period=0 2>/dev/null
```

1. Force delete all PersistentVolumeClaims (PVCs) in the specified namespace.

```bash
kubectl delete pvc --all -n "$NAMESPACE" --force --grace-period=0 2>/dev/null
```

1. Force delete the entire namespace.

```bash
kubectl delete ns "$NAMESPACE" --force --grace-period=0
```

> [!NOTE]
> Note
> 
> If your installation exists in the *default* namespace, you must not delete it.

After the above procedure, it deletes your entire namespace and the data within it.
