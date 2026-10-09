---
title: "EPod V2 installation in Kubernetes cluster"
slug: "epod-v2-installation-in-kubernetes-cluster"
updated: 2026-07-16T11:09:34Z
published: 2026-07-16T11:09:34Z
canonical: "helpcenter.securiti.ai/epod-v2-installation-in-kubernetes-cluster"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# EPod V2 installation in Kubernetes cluster

Perform all the following steps on your Linux instance from which the Kubernetes server and network are accessible.

> [!WARNING]
> Important
> 
> - There are two `values.yaml` files provided during installation:
>   - `Values.yaml` file available on the installation page.
>   - `Values.yaml` file available inside the zip archive.
> - If you are reinstalling because a previous installation failed, you must uninstall EPod V2 before starting the reinstallation. For more information, see [Uninstall Elastic Pods V2](/v1/docs/uninstall-elastic-pods-v2-en).

1. Download the Helm chart files into your local storage using one of the following methods:
  1. Use the Helm chart signed URL to download the files in a compressed format to your local storage with the following steps:
    1. On the **Helm Install Instructions** page, use the signed URL provided under the **Generate Helm chart URL** to download the Helm chart. Copy the signed URL and add it to the following command to download and save it.

```bash
curl "<SECURITI HELM CHART SIGNED URL>" --output <securiti-appliance-chart-<VERSION>.tar.gz>
```

For example

```bash
curl “<Helm chart url>” --output securiti-appliance-chart-1.122.0-07rc.tar.gz
```

![GenerateHelmChartURL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dd129996-dd5a-30aa-706d-ec69cee39030(2).png)
    2. Replace the value of **<VERSION>** with the version value that is under the **Helm install instructions** field as shown below:

![13_App_version_selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5ed9d06-001b-7064-c129-4ef7d4fa8839(4).png)
  2. Manually log into the Docker repository using the credentials provided below, and download the Helm chart files into your local storage with the following steps:
    1. Authenticate with the Securiti container registry using the following command:

```bash
docker login <app.securiti.ai> -u securiti -p <License_token>
```

Replace `&lt;app.securiti.ai&gt;` with your application URL. See [Configuring fixed IP addresses for Securiti SaaS end points](/latest/docs/configuring-fixed-ip-addresses-for-securiti-saas-end-points).

Replace `&lt;License_token&gt;` with the license value. From the **Helm Install Instruction** value, obtain the value of `global.license` and replace it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KL1Z5E1L.png)
    2. Pull the Helm chart from the Securiti registry using the following command:

```bash
helm pull oci://<app.securiti.ai>/securiti/securiti-appliance --version <1.141.1-01p>
```

Replace `&lt;app.securiti.ai&gt;` with your application URL.

Replace `&lt;1.141.1-01p&gt;` with the appliance version value. From the **Helm Install Instruction** value, copy the version number matching the format above and replace it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PKSLUNH4.png)

It downloads the files into your terminal’s local directory.
    3. Rename all the files and folders with the standard naming convention that the deployment procedure follows. In the directory where you downloaded the Helm chart, execute the following command.

```bash
for f in securiti-appliance-*.tgz; do mv "$f" "${f/securiti-appliance-/securiti-appliance-chart-}"; done && rename .tgz .tar.gz securiti-appliance-chart-*.tgz
```
2. Copy the contents of the values file under **Download values.yaml** into a file and name it as **values.yaml**. Make sure to modify the password field in the content before proceeding.

![values_yaml.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-382bb4e5-43f1-971f-e578-eb05652b0e83(4).png)This file contains several configurations. Some of these need modifications, so you must consider the following before proceeding.

- If you already have a Metrics service available in your cloud, you must set the following values to **false** in **values.yaml**.

```yaml
enableCustomMetricsApi: "false"
enableExternalMetricsApi: "false"
```
- If your external Elasticsearch requires a password to connect, in the **elasticsearch** block of **values.yaml** file, add your password in the following value by replacing it:

```yaml
global:
    elasticsearch:
        password: "thepassword"
```
- If your external Redis requires a password to connect, perform one of the following methods:
  - In the `values.yaml` file, add your external Redis password in the following value by replacing it.

```yaml
global:
    redis:
        password: "CHANGEMEOROVERRIDEME"
```

If there is no password required for Redis, make the `password` field empty.
  - To avoid storing secrets in plain text within `values.yaml`, provide your Redis password directly in the Helm Upgrade command in step 4:

```bash
 --set global.redis.password="password"
```

If Redis does not require a password, but a dummy value remains in your values.yaml, append the following flag to the Helm Upgrade command in Step 4:

```bash
--set global.redis.allowEmptyPassword=true
```

> [!NOTE]
> Note
> 
> If you are using CI/CD deployment like ArgoCD, you must maintain your password in your pipeline’s `values.yaml` file.
- If you want to configure a proxy for the pod, proceed with the following steps
  1. Add the following values in `values.yaml` file.

```yaml
 runtimeenvironment:
     env:
         HTTP_PROXY: http://192.168.2.31:3128
         HTTPS_PROXY: http://192.168.2.31:3128
         http_proxy: http://192.168.2.31:3128
         https_proxy: http://192.168.2.31:3128
         NO_PROXY: 0.0.0.0/0,.local,192.168.0.0/16
         no_proxy: 0.0.0.0/0,.local,192.168.0.0/16
         JAVA_NO_PROXY: 0.0.0.0,localhost
```

You must update your proxy IP or proxy endpoint in the above values.
  2. (Optional) If you want to intercept the proxy, your certificate must start with `----BEGIN CERTIFICATE----`. To convert your certificate into it, use one of the following commands depending on your operating system.

```bash
# Convert your certificate to PEM format (it must start with ----BEGIN CERTIFICATE-----)
openssl x509 -inform der -outform pem -in myCA2.der -out CERTIFICATE.crt
chmod 644 CERTIFICATE.crt

# For CentOS
cp CERTIFICATE.crt /etc/pki/ca-trust/source/anchors/
update-ca-trust

# For Ubuntu
sudo cp CERTIFICATE.crt /usr/local/share/ca-certificates/
sudo update-ca-certificates
```
  3. (Optional) Apply your proxy certificate to the Kubernetes cluster for intercepting proxy using the following command.

```bash
kubectl create configmap ca-pem-config -n <namespace> --from-file=custom-ca-cert.pem=/path/to/certfile
```
- Set `enable_sys_admin` to true, if you want to enable the following features and scans:
  - Labeling and quarantine policies for NFS/SMB data systems
  - XML-lineage feature
  - NFS/SMB discovery scans

```bash
enable_sys_admin: true
```
- If you are already using **Kubernetes Event-Driven Autoscaling** (KEDA) component in your Kubernetes cluster, you must proceed with the following steps:
  1. Ensure that you have the following list of components available in your Kubernetes Cluster.

| Resource | Component |
| --- | --- |
| Custom Resource Definitions | - `CustomResourceDefinition/scaledobjects.keda.sh` - `CustomResourceDefinition/triggerauthentications.keda.sh` |
| KEDA Operator | - `Deployment/keda-operator` - `ServiceAccount/keda-operator` - `Service/keda-operator` - `ClusterRole/keda-operator` - `ClusterRoleBinding/keda-operator` |
| External Metrics API | - `Deployment/keda-operator-metrics-apiserver` - `Service/keda-operator-metrics-apiserver` - `ServiceAccount/keda-metrics-server` - `ClusterRole/keda-operator-external-metrics-reader` - `ClusterRoleBinding/keda-operator-hpa-controller-external-metrics` - `APIService/v1beta1.external.metrics.k8s.io` |
| Admission Webhooks | - `Deployment/keda-admission-webhooks` - `Service/keda-admission-webhooks` - `ServiceAccount/keda-webhook` - `ClusterRole/keda-operator-webhook` - `ClusterRoleBinding/keda-operator-webhook` - `ClusterRoleBinding/keda-operator-system-auth-delegator` - `ValidatingWebhookConfiguration/keda-admission` |
  2. Add or replace the HPA autoscaling with the following KEDA values in `values.yaml`.

```yaml
global:
    autoscaler_type: keda
```

```yaml
tags:
    kube-metrics-adapter: false
```

> [!NOTE]
> Note
> 
> Every time you update the pods by applying new `values.yaml` file, you must update the above values in it before applying it to your Kubernetes cluster.
- To restrict the cluster-level Kubernetes resources from deploying in your EPod V2, set the following values to false in `values.yaml` file. This is helpful where the cluster-level permissions are restricted.

```yaml
global:
  deployPriorityClasses: false  
  deployClusterRoles: false  
  deployAdmissionWebhooks: false  
```

To use your custom Priority Classes, set the following values in `values.yaml`.

```yaml
global:
  useExistingPriorityClass: true
  existingPriorityClasses:
    pods_sql: "your sql Priority Class name"
    pods_ondemand: "your ondemand Priority Class name"
    pods_scanjob: "your scanjob Priority Class name"
```

For more information on Securiti supported Priority Classes, see [Prerequisites for EPod V2](/latest/docs/prerequisites-for-epod-v2).

1. (Optional) Upload your override file to the portal. This lets everyone with access to EPod V2 see, download, and reupload it by modifying the content.
  1. Create or modify your override file according to your infrastructure preferences.
  2. On the right to **values.yaml**, click **Upload Override File** to upload your override file to the portal.
  3. To download the override file, click **Download Override File**. It downloads the latest version of the file upload.

![EPodV2_Override_file_upload.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-181f6d82-33d4-105c-da58-3d48c8373256(2).png)
2. Proceed to the EPod V2 deployment:

**Deploy via Control Node**

If you are deploying the EPod V2 using Control Node, proceed with the following next steps:

1. Run the Helm install command under Helm Install Instructions. This step might take a few minutes to complete.
  - If you are using the Securiti registry, run the following command. Replace the tar file name with the one you obtained in the previous step from the Helm Install Instruction field.

```bash
helm upgrade -n default --install priv-appliance securiti-appliance-chart-1.122.0-12rc.tar.gz -f values.yaml
```
  - If you use the custom registry, run the following command. Replace the tar file name with the one you obtained in the previous step from the Helm Install Instruction field.

```bash
helm upgrade -n default --install priv-appliance securiti-appliance-chart-1.122.0-12rc.tar.gz -f values.yaml -f custom-override-values.yaml
```

Running the Helm command downloads the credential file, installs Helm, and registers the pod.
2. (Optional) Run the command under **Register Instruction** to register the pods if the Helm command did not register the pod.

> [!NOTE]
> **Note**
> 
> Use this step if you already have the pod in your Helm but have not registered it yet.

Click **Save and Continue**.

![install__register.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-775316d7-2c2a-fd14-de6e-19b3f20aef1d(2).png)

**Deploy via ArgoCD pipeline**

If you are deploying the EPod V2 using ArgoCD CI/CD pipeline, proceed with the following next steps:

1. Copy the following content and create a YAML file with it.

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
2. Upload the following files to your code repository:
  - `Values.yaml` file
  - Newly created *Ignore Difference* YAML file containing the content above
  - Helm Chart that you downloaded earlier
3. Execute your pipeline to deploy EPod V2 in your Kubernetes cluster.

1. Once the EPod V2 deployment finishes, the deployment on the Elastic Pods V2 page turns green.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-G6LBNSMP.png)
