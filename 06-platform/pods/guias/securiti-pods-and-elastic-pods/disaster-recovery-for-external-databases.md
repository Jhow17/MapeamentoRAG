---
title: "Disaster recovery for external databases"
slug: "disaster-recovery-for-external-databases"
updated: 2026-08-10T20:07:53Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/disaster-recovery-for-external-databases"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Disaster recovery for external databases

This document covers the procedure for restoring your external databases backups into EPod V2. Securiti does not perform backup related actions on your external databases so you must manage the backup and restore processes of your external databases that you configured with EPod V2.

> [!WARNING]
> Important
> 
> Securiti assumes that you have already restored your external database backup for the disaster recovery process.

To proceed with disaster recovery using the restored external database in EPod V2, proceed with the following steps:

1. Open your EPod V2 page.
  1. In Securiti, from the upper left corner of the left navigation bar, click the **Jewel** icon.
  2. From the Platform Services section, click **Settings > Deployment > Elastic Pods V2**.
2. Revoke your EPod V2.
  1. On the **Elastic Pods V2** page, select a pod you wish to revoke.
  2. On the right side of your selected pod, click **Options** (three dots).
  3. From the menu, select **Revoke**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K58A0HHR.png)

If this button is disabled, it means that your EPod V2 is already revoked.
3. Using the same appliance or cluster, verify that the credentials for your external databases are up to date if there are any changes due to the disaster recovery process.
4. Install a new EPod V2.

**Regular installation**

1. During installation, you must consider the following actions:
  - Use the same namespace of previous EPod V2 in new installation.
  - Use the same cluster ID from UI of previous EPod V2 in new installation.
  - While configuring new EPod V2, on the **Summary** tab, update the following tag in `values.yaml` file.

```yaml
tags:
  deployer-service: false
```

> [!NOTE]
> Note
> 
> Disabling this tag does not let you register your EPod V2 with the **Register Instruction** command.

For more information, See [EPod V2 installation](/latest/docs/epod-v2-installation-1).
2. Clean up the registration keys from your external Redis that reference your previous EPod V2 using the following command:

```bash
kubectl exec -n "$SECURITI_NAMESPACE" deploy/priv-appliance-config-controller -- securitictl deleteredis -n is_registered -y
```

Replace `$SECURITI_NAMESPACE` with your namespace value.
3. Manually register your EPod V2 again from the UI using **Register Instruction** command.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZCBUI8DD.png)

It registers your appliance within your Kubernetes cluster.

**Installation with autoscaling**

1. During installation, you must consider the following actions:
  - Use the same namespace of previous EPod V2 in new installation.
  - Use the same cluster ID from UI of previous EPod V2 in new installation.
  - While configuring new EPod V2, on the **Summary** tab, update the following tag in `values.yaml` file.

```yaml
tags:
  deployer-service: false
```

> [!NOTE]
> Note
> 
> Disabling this tag does not let you register your EPod V2 with the **Register Instruction** command.
  - Include the following values in `values.yaml` file. It ignores the included resources that stops it from restoring it to previous state after registering the appliance.

```yaml
spec:
 ignoreDifferences:
  - group: apps
   kind: Deployment
   name: priv-appliance-download-worker
   jsonPointers:
    - /spec/replicas
   jqPathExpressions:
    - .spec.template.spec.containers[] | select(.name == "cc-detector").resources
    - .spec.template.spec.containers[] | select(.name == "cc-detector").env[] |
     select(.name == "HEAP_SIZE" or .name == "EDM_SIZE").value
  - group: apps
   kind: Deployment
   name: priv-appliance-access-mgmt-worker
   jsonPointers:
    - /spec/replicas
  - group: apps
   kind: Deployment
   name: priv-appliance-access-mgmt-worker-jdbc
   jsonPointers:
    - /spec/replicas
  - group: apps
   kind: Deployment
   name: priv-appliance-html-converter
   jsonPointers:
    - /spec/replicas
  - group: apps
   kind: Deployment
   name: priv-appliance-dd-connector-async
   jsonPointers:
    - /spec/replicas
  # HPA - ignore minReplicas/maxReplicas managed by external scaling
  - group: autoscaling
   kind: HorizontalPodAutoscaler
   name: priv-appliance-download-worker
   jsonPointers:
    - /spec/minReplicas
    - /spec/maxReplicas
  - group: autoscaling
   kind: HorizontalPodAutoscaler
   name: priv-appliance-connector-policy
   jsonPointers:
    - /spec/minReplicas
    - /spec/maxReplicas
  # KEDA ScaledObjects - ignore min/max replica counts managed externally
  - group: keda.sh
   kind: ScaledObject
   name: priv-appliance-download-worker
   jsonPointers:
    - /spec/minReplicaCount
    - /spec/maxReplicaCount
  - group: keda.sh
   kind: ScaledObject
   name: priv-appliance-connector-policy
   jsonPointers:
    - /spec/minReplicaCount
    - /spec/maxReplicaCount
```

For more information, See [EPod V2 installation](/latest/docs/epod-v2-installation-1).
2. Clean up the registration keys from your external Redis that reference your previous EPod V2 using the following command:

```bash
kubectl exec -n "$SECURITI_NAMESPACE" deploy/priv-appliance-config-controller -- securitictl deleteredis -n is_registered -y
```

Replace `$SECURITI_NAMESPACE` with your namespace value.
3. Manually register your EPod V2 again from the UI using **Register Instruction** command.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZCBUI8DD.png)

It registers your appliance within your Kubernetes cluster.
