---
title: "Upgrading pods cluster version"
slug: "upgrading-pods-cluster-version"
updated: 2026-08-24T06:38:43Z
published: 2026-08-24T06:38:43Z
canonical: "helpcenter.securiti.ai/upgrading-pods-cluster-version"
stale: true
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Upgrading pods cluster version

You can perform the upgrade process for Kubernetes clusters used in Securiti Pod v2. This documentation outlines the steps to perform the upgrade, important considerations, and how to troubleshoot any issues.

The cluster upgrade can take place in two possible ways:

- Manual upgrade with the procedure available in this document.
- Auto upgrade, which occurs during the process of pod update.

### Key considerations

- **Operating system updates**: Before planning to upgrade the cluster, you must ensure that your operating system (OS) is upgraded to latest version.
- **Configuration Reset:** Upgrading the cluster restarts K3s and resets K3s/Securiti-owned configurations and any inline patches to configmaps (e.g., CoreDNS) will be undone. To avoid this, use the override mechanism described in the [Pod V2 Runbook for CoreDNS Configuration in k3s](/v1/docs/upgrading-pods-cluster-version#overriding-coredns-configuration-in-k3s).
- **Flannel Fix:** Ensure that the flannel fix is applied to all nodes to prevent any misbehaviour during k3s restarts. Run the following command on each node before upgrading:

```bash
sudo bash /mnt/installation/securiti-appliance-installer/poddiagnostics.sh install --fix
```
- **No-Op Upgrade:** If the cluster nodes are already on the latest version, the upgrade will be a no-op (no operation).
- **Version Requirements:** The cluster must be on Pod v1.28+ or higher. The latest supported cluster version is v1.35.5.

> [!NOTE]
> **Note**
> 
> 1. Cluster version upgrade is possible after updating the application version. You must update the application before upgrading the cluster version.
> 2. The cluster upgrade must be completed prior to adding new nodes to the cluster.
> 3. If the upgrade warning banner appearing on Pods.

### Step-by-step upgrade process

1. Get a terminal in the `config-controller` pod using the command below:

```bash
kubectl exec -it deploy/priv-appliance-config-controller -- bash
```
2. Execute the upgrade command:

```bash
securitictl upgrade-cluster 2>&1 | tee /mnt/securiti-app/backup/upgrade.log &
```

For the clusters not installed in */mnt*, use the appropriate path. The log file is in the form */mnt/backup/upgrade.log* for `non-securiti-app` clusters.
3. Monitor the process to complete in approximately 5-10 minutes for a multi-node cluster. The k3s API server will restart, which disconnects the terminal session. Monitor the upgrade status in the log file:

```bash
/mnt/securiti-app/backup/upgrade.log
```
4. Verify that all nodes show as Ready with the updated K8s version by running the following command:

```bash
kubectl get node
```

### Troubleshooting

If the upgrade fails, analyze the failure mode using the following tools:

- `systemctl service status` for k3s or k3s-agent
- `journalctl logs`

Refer to the [Key Considerations section](/v1/docs/upgrading-pods-cluster-version#key-considerations) for common failure modes.

> [!NOTE]
> Note
> 
> Audit logs are not generated when you trigger the cluster upgrade via the `securitictl` command. This issue will be addressed in a future release.

#### Overriding CoreDNS Configuration in k3s

The default CoreDNS configuration in k3s may not always meet the specific needs of users or applications. Any inline changes made directly to the Corefile are reset upon a k3s reboot, which can result in domains not resolving properly from the pods.

#### Symptom

The CoreDNS configuration needs to be overridden, as inline changes made directly can be reset upon a system k3s reboot.

#### Fix

To override the CoreDNS configuration in k3s, follow these steps:

1. Set an environment variable named IP. This IP address will be used by the DNS servers to resolve domain names.

```bash
export IP=<IP-Address>
```
2. Create a ConfigMap named `coredns-custom` in the `kube-system` namespace. Use the following YAML configuration:

```bash
echo 'apiVersion: v1
kind: ConfigMap
metadata:
  name: coredns-custom
  namespace: kube-system
data:
  custom.override: |
    forward . CUSTOM_IP
' > coredns-custom.yaml
```
3. Replace the placeholder `CUSTOM_IP` in the `coredns-custom.yaml` file with the actual IP address specified in the IP environment variable. This can be done using the sed command:

```bash
sed -i "s/CUSTOM_IP/${IP}/g" coredns-custom.yaml
```
4. Apply the configuration changes:

```bash
kubectl apply -f coredns-custom.yaml
```
5. Reload the ConfigMap and enable the Kubernetes Scheduler to restart CoreDNS without downtime:

```bash
kubectl -n kube-system rollout restart deployment coredns
```
6. Ensure that the `coredns-custom` ConfigMap exists in the `kube-system` namespace and contains the desired IP configuration:

```bash
kubectl get cm coredns-custom -n kube-system -o yaml
```

#### 

#### Cleaning up stale K3s data directories after upgrade

A K3s upgrade repoints the `current` symlink at `/mnt/rancher/k3s/data/` to the new version's hash directory, but K3s doesn't delete the previous hash directory. The old directory still contains the previous version's `runc` binary.

#### Symptom

Any vulnerability scanner might keep flagging an outdated `runc` binary after you upgrade the cluster, even though `kubectl get node` command shows every node on the new K3s version.

#### Fix

`securitictl deleteimages`, `crictl rmi --prune`, and `docker system prune` only remove container images. They do not remove the stale host-level directory, so running them doesn't resolve the finding. To clear it, run the following steps as root on each node in the cluster:

1. Confirm every node is fully upgraded before you continue:

```bash
kubectl get nodes -o wide
```

All nodes must show `Ready` at the target K3s version. Do not continue if a node is still mid-upgrade.
2. On the node, preview which directories the cleanup removes:

```bash
DATA_DIR=/mnt/rancher/k3s/data

CURRENT="$(sudo readlink -f"$DATA_DIR/current")"

sudo find "$DATA_DIR" -mindepth 1 -maxdepth 1 -type d ! -name current ! -name cni ! -path "$CURRENT"
```

Confirm that `current` and `cni` are not in the output before you proceed.

> [!CAUTION]
> Warning
> 
> Do not run a broader cleanup command against `/mnt/rancher/k3s/data/` that isn't scoped to exclude `current` and `cni`. Removing the `cni` directory breaks pod networking on that node. Existing pods keep running, but new pods fail to schedule with a "*failed to find plugin*" error.
3. Run the cleanup on the node:

```bash
DATA_DIR=/mnt/rancher/k3s/data

CURRENT="$(sudo readlink -f"$DATA_DIR/current")"

sudo find "$DATA_DIR" -mindepth 1 -maxdepth 1 -type d ! -name current ! -name cni ! -path "$CURRENT" -exec rm -rf {} +
```
4. Verify the result on the node:

```bash
sudo ls -la /mnt/rancher/k3s/data/

sudo /mnt/rancher/k3s/data/current/bin/runc --version
```

Only `current` and `cni` remain, and the reported `runc` version matches the patched version for the installed K3s release.
5. Confirm node and cluster health:

```bash
kubectl get nodes

kubectl get pods -A | grep -v -E "Running|Completed"
```

The node stays `Ready`, and no new unhealthy pods appear.
6. Check for a retained installer package under `/mnt/installation/`, which can also embed an old K3s/runc binary:

```bash
sudo ls /mnt/installation/ 2>/dev/null
```

If a directory such as `securiti-appliance-installer-old` exists, and the current installation is healthy, remove it:

```bash
sudo rm -rf /mnt/installation/securiti-appliance-installer-old
```
7. Repeat step 2 through 6 on every remaining node.

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

Upgrading the software updates both the pod software and the cluster software. There are two ways of upgrading a pod: manually or using an automatically-generated curl command.

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Pod troubleshooting (cluster version v1.28+)](/podtroubleshooting.md)
