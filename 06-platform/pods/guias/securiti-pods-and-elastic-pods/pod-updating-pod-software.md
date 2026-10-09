---
title: "Updating pod software (cluster version v1.28+)"
slug: "pod-updating-pod-software"
updated: 2026-08-24T08:27:18Z
published: 2026-08-26T21:00:28Z
canonical: "helpcenter.securiti.ai/pod-updating-pod-software"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Updating pod software (cluster version v1.28+)

Updating the pod software also updates the cluster version.

On the Pods dashboard, Securiti displays an alert for any of your pods that are running application software versions older than three releases prior to the current Securiti release, as shown below. We strongly recommend that you keep your pods updated with the latest software release.

> [!WARNING]
> Important
> 
> - Your security tools might block the update of pods. See [Pod FAQs](/latest/docs/pod-faqs) for allowlisting the necessary directories.
> - If you are running Inventory Scans and DSR scans using SaaS connectors, you must pause the scans or finish the scans before applying the Helm Chart for upgrade. If you do not pause or finish the scan and apply the Helm Chart, it aborts the Helm upgrade.
> - When you apply the Helm Chart:
>   - Securiti pauses your running Data Discovery Scans
>   - Upgrades Pods
>   - Resumes your Data Discovery Scan automatically

![Pods_cluster_version.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cf5e8815-94af-76bc-a0f8-eb59b83dfc03(2).png)

### Updating a pod through the Securiti user interface (UI)

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the System Settings menu choose **Deployment > Pods**.
4. For the pod you want to update, choose **Options > Update Now**.

### Configuring a pod to automatically update

You can configure a pod to automatically update whenever new software is available.

1. In Securiti, click the jewel at the bottom of the **Dashboard**.
2. From the list of options, select **Settings**.
3. From the System Settings menu choose **Deployment > Pods**.
4. For the pod you want to configure, click the master node.
5. On the page for the pod, click the **Master Node** tab.
6. In the Enable Auto Update area, enable the toggle for **Enable Auto Update**.
7. Near the upper right corner of the page, click **Save**.

#### Pod upgrade staging

> [!TIP]
> **Note**
> 
> This feature is supported only for 1.127 and above releases.

Pod upgrade staging feature lets you hold the current pod version and maintain the automatic upgrades to one release before the latest release. The staging option is configurable for both tenants and individual pods.

It also enables an acceptance testing process, allowing you to validate the compatibility of the new pod version with internal systems and processes before upgrading to production.

Perform the following steps to use the pod upgrade staging feature:

1. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable the **pod upgrade staging** feature.
2. Under the **Master Node** tab, use the **Stay on Previous Release** toggle to enable or disable it.

### Updating an existing Airgapped Pod (cluster version v1.28+)

Updating the software updates both the pod software and the cluster software.

To update an airgapped pod:

1. Download the latest bundle from the Securiti portal.

> [!TIP]
> **Note**
> 
> The installation bundle for both **installation** and **update** are same.
2. Copy the install bundle to the node:

```bash
scp securiti-appliance-installer-airgap-<version>.tar <user@server:path>
```

for example,

```bash
scp securiti-appliance-installer-airgap-<version>.tar ubuntu@192.168.86.115:/tmp
```
3. Extract the files:

```bash
ssh ubuntu@192.168.86.115
sudo su
cd <path where installer tar copied>
mv securiti-appliance-installer-airgap-<version>.tar /tmp/securiti-appliance-installer.tar.gz
INSTALLATION_DIR=/mnt/installation/securiti-appliance-installer
mkdir -p "$INSTALLATION_DIR"
sudo tar -xf /tmp/securiti-appliance-installer.tar.gz -C "$INSTALLATION_DIR" --strip-components=1
cd "$INSTALLATION_DIR"
```
4. Set the environment variables for airgap.

```bash
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml 
export SECURITI_AIRGAP=true 
export SECURITI_SKIP_DOWNLOAD=true
export SECURITI_NODE_JOIN_TOKEN=$(cat /mnt/rancher/k3s/server/node-token | sed 's/^.*::server://')
```
5. (Optional) If you are using older versions of operating systems (OS) than those listed in [Pod prerequisites (cluster version v1.28+)](/latest/docs/pod-prerequisites-cluster-version-v128), you must set the following environment variable to `true`. However, this workaround will get deprecated in future releases requiring you to meet the supported OS versions.

```bash
export SECURITI_SKIP_OS_CHECKS=true
```
6. Execute the update using the following command:

```bash
bash install.sh
```

> [!TIP]
> **Note**
> 
> Wait for at least fifteen minutes before proceeding with the next step.
7. Restart K3s and restart all the pods.

```bash
systemctl restart k3s
kubectl delete pods --all
```

For the multi-node cluster, you must also execute the following command on all your working nodes’ machines:

```plaintext
systemctl restart k3s-agent
```

Restarting k3s-agent does not upgrade the k3s version on the worker nodes. For multi-node airgap clusters, run the following command to upgrade k3s on all worker nodes:

```bash
securitictl upgrade-cluster
```
8. To delete older images, execute the following command:

```bash
kubectl exec -it deploy/priv-appliance-config-controller  -- securitictl deleteimages
```

For using this command:

```bash
kubectl exec -it deploy/priv-appliance-config-controller  -- securitictl deleteimages [flags]

Flags:
  -c, --current-version string   current image version
  -h, --help                     help for deleteimages
  -v, --version string           delete images of the following version

Example:
kubectl exec -it deploy/priv-appliance-config-controller  -- securitictl deleteimages -c <current-version>
```

> [!NOTE]
> Note
> 
> This command removes unused container images only. It doesn't remove the previous K3s version's extracted binaries, including `runc`, from `/mnt/rancher/k3s/data/`. If a vulnerability scanner keeps flagging an old `runc` binary after a cluster upgrade, see [Upgrading pods cluster version](/latest/docs/upgrading-pods-cluster-version#cleaning-up-stale-k3s-data-directories-after-upgrade).

## Related

- [Upgrading pods cluster version](/upgrading-pods-cluster-version.md)
- [Pod troubleshooting (cluster version v1.28+)](/podtroubleshooting.md)
- [Using the pre-flight diagnostic script (cluster version v1.28+)](/pods-using-the-pre-flight-diagnostic-script.md)
