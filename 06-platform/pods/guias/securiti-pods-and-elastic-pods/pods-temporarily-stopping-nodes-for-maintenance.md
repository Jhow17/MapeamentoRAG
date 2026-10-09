---
title: "Temporarily stopping nodes for maintenance (cluster version v1.28+)"
slug: "pods-temporarily-stopping-nodes-for-maintenance"
updated: 2025-10-30T18:18:28Z
published: 2025-11-03T06:11:12Z
canonical: "helpcenter.securiti.ai/pods-temporarily-stopping-nodes-for-maintenance"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Temporarily stopping nodes for maintenance (cluster version v1.28+)

To temporarily disable a node for routine server maintenance:

```bash
kubectl cordon <node name>
kubectl drain <node name> --ignore-daemonsets
```

To restart the node after you finish the maintenance:

```bash
kubectl uncordon <node name>
```

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Updating pod software (cluster version v1.28+)](/pod-updating-pod-software.md)
