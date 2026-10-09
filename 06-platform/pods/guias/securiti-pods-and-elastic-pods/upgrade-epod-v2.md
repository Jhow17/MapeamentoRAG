---
title: "Upgrading EPod V2"
slug: "upgrade-epod-v2"
updated: 2026-08-10T18:20:59Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/upgrade-epod-v2"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Upgrading EPod V2

This procedure covers upgrading EPod V2 using one of the following methods.

- [Upgrade using Custom registry](/v1/docs/upgrade-epod-v2#upgrade-using-custom-registry)
- [Upgrade using Securiti registry](/v1/docs/upgrade-epod-v2#upgrade-using-securiti-registry)
- [Removing legacy SCC resources on OpenShift](/latest/docs/upgrade-epod-v2#removing-legacy-scc-resources-on-openshift)
- [Upgrade internal databases](/v1/docs/upgrade-epod-v2#upgrade-internal-databases)

## Upgrade using Custom registry

Upgrade your EPod V2 using the following steps.

1. Navigate to EPod V2 and open List of Images:
  1. Open **EPod V2** page and search your pod to upgrade.
  2. On the right side of the EPod V2, click options (three dots) and then Edit. It opens the EPod V2 page.
  3. Upgrade your Securiti images:
    1. Open **List of Images** tab. It contains the latest versions of images.
    2. Pull the images and push them to the custom registry.

![15_List_of_images.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf6c641b-73bb-8480-3f4b-e33eba2651b1(2).png)
    3. Update your override values with the latest image versions from the **List of Images** tab and incorporate them into the override file to reflect the latest versions.

![13_App_version_selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5ed9d06-001b-7064-c129-4ef7d4fa8839(5).png)
2. The **Summary** tab is not visible directly. Open **Customization** tab and click **Save and Continue** to proceed to **Summary** tab.
3. Use the signed URL from the **Generate HELM chart URL** in your Linux instance to download the Helm chart.

```bash
curl <SECURITI HELM CHART SIGNED URL> --output <securiti-appliance-chart-<VERSION>.tar.gz>
```

For example:

```plaintext
Curl “<Helm chart url>” --output securiti-appliance-chart-1.122.0-07rc.tar.gz
```

Replace the value of *<VERSION>* with the version value that is under the Helm install instructions field, as shown below:

![13_App_version_selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5ed9d06-001b-7064-c129-4ef7d4fa8839(5).png)
4. Use the new `values.yaml` file by copying the content. You can add or update different configurations in the `values.yaml` file. For more information, see [EPod V2 installation in Kubernetes cluster](/latest/docs/epod-v2-installation-in-kubernetes-cluster).

![values_yaml.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-382bb4e5-43f1-971f-e578-eb05652b0e83(5).png)
5. Next, use the following commands to generate variables for your upgrade command.

```bash
export NS=<your installation namespace>
```
6. Deploy the EPod V2:

**Deploy via Control Node**

If you are deploying the EPod V2 using Control Node, proceed with the following next steps:

1. Run the Helm install command under Helm Install Instructions. This step might take a few minutes to complete.

> [!WARNING]
> Important
> 
> - If you are running Inventory Scans and DSR scans using SaaS connectors, you must pause the scans or finish the scans before applying the Helm Chart for upgrade. If you do not pause or finish the scan and apply the Helm Chart, it aborts the Helm upgrade.
> - When you apply the Helm Chart:
>   - Securiti pauses your running Data Discovery Scans
>   - Upgrades EPod V2
>   - Resumes your Data Discovery Scan automatically
  - If you are using the Securiti registry, run the following command. Replace the tar file name with the one you obtained in the previous step from the Helm Install Instruction field.

```bash
helm upgrade -n default --install priv-appliance securiti-appliance-chart-1.122.0-12rc.tar.gz -f values.yaml
```
  - If you use the custom registry, run the following command. Replace the tar file name with the one you obtained in the previous step from the Helm Install Instruction field.

```bash
helm upgrade -n default --install priv-appliance securiti-appliance-chart-1.122.0-12rc.tar.gz -f values.yaml -f custom-override-values.yaml
```

Running the Helm command downloads the credential file, installs Helm, and registers the pod.

**Deploy via ArgoCD pipeline**

If you are deploying the EPod V2 using ArgoCD CI/CD pipeline, proceed with the following next steps:

1. Review and save a copy of the ignoreDifferences YAML file currently in your repository.

> [!NOTE]
> Note
> 
> You must note any entries you added or removed from the default configuration you provided during installation. During upgrade, as you do not include this file, so any fields previously ignored by ArgoCD will be reconciled against the Helm chart values. Ensure any runtime-managed values you want to preserve (such as replica counts) are explicitly set in values.yaml before proceeding.
2. Set the following value to `False` in `values.yaml` :

```yaml
tags:
  deployer-service: false
```
3. Upload the following files to your code repository:
  - Copied `values.yaml` file
  - Helm Chart that you downloaded earlier
  - *Ignore Differences* YAML file

> [!WARNING]
> Important
> 
> - For the `Ignore differences` YAML file, you must ensure that this file in your repository matches the file content mentioned in [EPod V2 installation page](/latest/docs/epod-v2-installation-in-kubernetes-cluster). If the file content is updated in the installation page, you must include this file to upload in your repository.
> - If you are running Inventory Scans and DSR scans using SaaS connectors, you must pause the scans or finish the scans before applying the Helm Chart for upgrade. If you do not pause or finish the scan and apply the Helm Chart, it aborts the Helm upgrade.
> - When you apply the Helm Chart:
>   - Securiti pauses your running Data Discovery Scans
>   - Upgrades EPod V2
>   - Resumes your Data Discovery Scan automatically
4. Execute your pipeline to deploy EPod V2 in your Kubernetes cluster.

## Upgrade using Securiti registry

Upgrade your EPod V2 using the following steps.

1. Navigate to EPod V2 and open List of Images:
  1. Open **EPod V2** page and search your pod to upgrade.
  2. On the right side of the EPod, click options (three dots) and then Edit. It opens the EPod V2 details page.
2. The **Summary** tab is not visible directly. Open **Customization** tab and click **Save and Continue** to proceed to **Summary** tab.
3. Use the signed URL from the **Generate HELM chart URL** in your Linux instance to download the Helm chart.

> [!WARNING]
> Important
> 
> - If you are running Inventory Scans and DSR scans using SaaS connectors, you must pause the scans or finish the scans before applying the Helm Chart for upgrade. If you do not pause or finish the scan and apply the Helm Chart, it aborts the Helm upgrade.
> - When you apply the Helm Chart:
>   - Securiti pauses your running Data Discovery Scans
>   - Upgrades EPod V2
>   - Resumes your Data Discovery Scan automatically

```bash
curl <SECURITI HELM CHART SIGNED URL> --output <securiti-appliance-chart-<VERSION>.tar.gz>
```

For example:

```bash
Curl “<Helm chart url>” --output securiti-appliance-chart-1.122.0-07rc.tar.gz
```

Replace the value of *<VERSION>* with the version value that is under the Helm install instructions field, as shown below:

![13_App_version_selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5ed9d06-001b-7064-c129-4ef7d4fa8839(5).png)
4. Use the new `values.yaml` file by copying the content and updating the Redis password in its content.

![values_yaml.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-382bb4e5-43f1-971f-e578-eb05652b0e83(5).png)
5. Next, use the following commands to generate variables for your upgrade command.

```bash
export NS=<your installation namespace>
```
6. Finally, run the following upgrade command. If you have your custom-override-values.yaml file, run the second command.

```bash
helm upgrade -n $NS --install priv-appliance securiti-appliance-chart-1.143.0-08rc.tar.gz -f values.yaml --timeout=900s --set download-worker.replicaCount=1
```

Run the following command to include your custom-override-values.yaml file.

```bash
helm upgrade -n $NS --install priv-appliance securiti-appliance-chart-1.143.0-08rc.tar.gz -f values.yaml -f custom-override-values.yaml --timeout=900s --set download-worker.replicaCount=1
```

## Removing legacy SCC resources on OpenShift

If you upgrade EPod V2 on OpenShift, the upgrade job does not remove legacy SCC resources that includes `ClusterRoleBindings`, `SCCs`, and `ClusterRoles`, from an earlier installation. OpenShift continues to assign the legacy resources to your pods instead of the new namespaces. If you skip this cleanup, any security fixes delivered through the new SCCs do not take effect on your pods. The upgrade job cannot remove these resources automatically because it does not have cluster role access, so you must delete them manually after the upgrade completes.

To remove them, proceed with the following steps:

1. If you still have the `securiti-pod-scc.yaml` file from your earlier installation, run the following command to remove the legacy resources:

```bash
kubectl delete -f securiti-pod-scc.yaml
```
2. If you no longer have this file, list the `SCC`, `ClusterRole`, and `ClusterRoleBinding` resources associated with your installation:

```bash
oc get scc,clusterrole,clusterrolebinding -o name | grep -E 'securiti-appliance-monitor-status|securiti-appliance-privileged|securiti-appliance-restricted'
```

This command lists both the legacy and the new namespaced resources together. Compare the names and note only the legacy, bare-named resources before you continue.
3. Delete the legacy resources using their exact names. If you used the default resource names:

```bash
oc delete clusterrolebinding securiti-appliance-privileged-scc-binding securiti-appliance-restricted-scc-binding securiti-appliance-restricted-spark-scc-binding securiti-appliance-monitor-status-scc-binding

oc delete scc securiti-appliance-privileged securiti-appliance-restricted

oc delete clusterrole system:openshift:scc:securiti-appliance-privileged system:openshift:scc:securiti-appliance-restricted system:openshift:scc:securiti-appliance-monitor-status-privileged
```

If you renamed these resources during your earlier installation, delete those names instead.

After you remove the legacy resources, your pods switch to the new namespaced SCCs automatically.

## Upgrade internal databases

> [!NOTE]
> Note
> 
> You can migrate your EPod V2 database from internal to external after installation. For more information, see [Migrating EPod V2 internal database to external](/latest/docs/migrating-epod-v2-internal-database-to-external).

You can resize your internal databases in an already installed cluster, with the requirement that your storage class must support volume expansion.

To resize Redis or Elasticsearch database:

1. Check if the storage class already supports expansion using the following command.

```bash
kubectl get storageclass <your-storage-class-name> -o yaml | grep -i allowVolumeExpansion
```

It gives the following ouput:

```plaintext
[root@ip-192-168-42-19 ec2-user]# kubectl get storageclass ebs-sc -o yaml | grep -i allowVolume
  allowVolumeExpansion: trueallowVolumeExpansion: true
```

Skip the next step if the output is true.
2. (Optional) If volume expansion is not found or output is false, you can enable it by running the following command:

```bash
kubectl patch storageclass <storage-class-name> -p '{"allowVolumeExpansion": true}'
```
3. Patch your current Persistent Volume Claim (PVC) to increase its request storage to the desired size. See the list of PVCs below:

| **Storage service** | **PVC** |
| --- | --- |
| Redis | redis-data-priv-appliance-redis-master-0 |
| Elasticsearch | priv-appliance-elasticsearch-master-priv-appliance-elasticsearch-master-0 |
4. Select the storage size based on your memory size. For Redis, see the comparison table below:

| **Memory Size** | **Storage Size** |
| --- | --- |
| 8000 Mi | 32Gi |
| 16000 Mi | 64Gi |
| 32000 Mi | 128Gi |

For Elastic Search, see the comparison table below:

| **Memory Size** | **Storage Size** |
| --- | --- |
| 12288 Mi | 8Gi |
| 24576 MI | 12GI |
| 32768 Mi | 16Gi |

Validate your expansion with the following command.

```bash
kubectl get pvc -w
```
5. Update your Stateful Set (STS) based on your configurations in the steps above.
  1. List down your STS using the following command.

```bash
kubectl get sts -n <namespace>
```
  2. From the output of the above command, identify the STS you want to delete, and copy the name of the storage you want to update based on the PVC you created in **step 3**.
  3. Delete the STS with the following command.

```bash
Kubectl delete sts <statefulset-name> --cascade=orphan -n <namespace>
```

> [!NOTE]
> Note
> 
> The Orphan Flag is required because the PVC is immutable. When used, it ensures that the Pod and the PVC remain intact.
6. Finally, run the helm upgrade command on the latest version of the `values.yaml`, as described in [Upgrade using Custom registry](/latest/docs/upgrade-epod-v2#upgrade-using-custom-registry) or [Upgrade using Securiti registry](/latest/docs/upgrade-epod-v2#upgrade-using-securiti-registry), to have your new database size reflect on the cluster.

## Related

- [Backup and restore EPod V2](/backup-and-restore-epod-v2.md)
- [EPod V2 installation in Securiti](/epod-v2-installation.md)
