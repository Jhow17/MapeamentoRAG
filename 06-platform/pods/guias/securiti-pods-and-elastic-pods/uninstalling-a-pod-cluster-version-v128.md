---
title: "Uninstalling a pod (cluster version v1.28+)"
slug: "uninstalling-a-pod-cluster-version-v128"
updated: 2025-12-09T13:08:10Z
published: 2025-12-09T13:08:10Z
canonical: "helpcenter.securiti.ai/uninstalling-a-pod-cluster-version-v128"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Uninstalling a pod (cluster version v1.28+)

### Un-register the Pod

To uninstall the pod, you must first un-register the pods from the SaaS platform. Follow the steps below to do that:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in new navigation, select **Settings**.
4. On the System Settings menu choose **Integrations > Data systems**.
5. For every on-premises connector instance that uses the pod:
  1. Click the card for the instance to open it.
  2. Click the **Connector** tab
  3. In the Connector Status area, click **More Options** and choose **Deactivate & Purge Data**.
  4. When Securiti prompts you to confirm, click **Deactivate & Purge**.
6. On the System Settings menu choose **Deployment > Pods**.
7. For each node listed on the card for the pod, click **Options** (three dots) and choose **Delete**.

![NodeDeleteAttempt.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bae5684f-cb98-533b-3603-acfb301bd2d3(2).png)
8. On the card for the pod itself, click **Options** and choose **Delete**.

Securiti deletes the pod and removes it from the page.

![ClusterDeleted.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86ec1d7a-66e4-d1be-85a5-dd7df1d61b76(2).png)

### Deleting the pod

You must also delete the pod from your cluster. Enter the following commands on your host system:

- **Uninstalling the pod cluster**

```bash
pid=$(ps aux | grep securiti-appliance-installer | grep -v 'grep' | awk '{print $2}') && [[ -n "$pid" ]] && sudo kill "$pid" && sleep 1 && kill -INT $$
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
/mnt/installation/securiti-appliance-installer/helm uninstall priv-appliance
k3s-uninstall.sh (master node)
rm -f <SECURITI_INSTALL_DIR>/installation/securiti-appliance-installer/*.yaml
# Delete all app data (cannot be recovered)
rm -rf <SECURITI_INSTALL_DIR>/rancher
rm -rf /etc/rancher
```
- **Removing the node from a cluster**

```bash
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
k3s-agent-uninstall.sh (secondary node)
rm -f <SECURITI_INSTALL_DIR>/installation/securiti-appliance-installer/*.yaml
# Delete all app data (cannot be recovered)
rm -rf <SECURITI_INSTALL_DIR>/rancher
rm -rf /etc/rancher
```

If you want to permanently remove a node from the cluster, see [Permanently removing a node (cluster version v1.28+)](/v1/docs/pods-permanently-removing-a-node).

## Related

- [Pod installation (cluster version v1.28+)](/pod-installation-cluster-version-v128.md)
- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
