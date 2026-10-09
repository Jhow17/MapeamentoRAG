---
title: "Pod custom installation guides (cluster version v1.28+)"
slug: "podcustom-installation-guides"
updated: 2026-08-19T13:25:30Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/podcustom-installation-guides"
stale: true
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Pod custom installation guides (cluster version v1.28+)

Choose automated installation if you want a standard pod installation for typical on-premises data systems. Choose manual if you need to customize the pod installation, for example, to configure HTTP or HTTPS proxy (based on your organization's internal IT policies).

- [Automated pod installation (cluster version v1.28+)](/v1/docs/podcustom-installation-guides#automated-pod-installation-cluster-version-v128)
- [Manual pod installation (cluster version v1.28+)](/v1/docs/podcustom-installation-guides#manual-pod-installation-cluster-version-v128)

Depending on your preferences, the Automated and Manual methods for pod installation differ as per the following table:

| Automatic | Manual |
| --- | --- |
| The installation method is autonomous, requiring only the input of a single user-generated CURL command into the server's terminal. The installation process is completed and gives a notification automatically. | The installation process is completed step-by-step (through entering separate manual commands). It is comparatively easy to identify any sources of potential errors that may occur within the process. |

## Automated pod installation (cluster version v1.28+)

1. In Securiti, click the jewel at the bottom of the dashboard.
2. From the list of tiles, click **Deployment**.
3. Under Deployment, click **Pods**.
4. If you are doing one of the following things, click the tile for the failed pod, then skip ahead to generating CURL Command:
  - Replacing a failed pod that you want to restore as described in [Backing up and restoring pods (cluster version v1.28+)](/v1/docs/backing-up-and-restoring-pod).
  - Migrating a pod of cluster version 1.0.12 to cluster version 1.28+ as described in [Migrating to pod (cluster version v1.28+)](/v1/docs/migrating-to-pod-cluster-version).
5. Near the top of the page, click **+ New Cluster** and choose **Custom Install**.

![Appliance_Main_Screen.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0379a6a2-fdf9-257a-42c7-e09b457eb1e6(2).png)
6. On the Basic Information tab, apply these settings:

| Cluster Name | Enter a convenient name. |
| --- | --- |
| Cluster Location | Use the tools to set the location. |
| Owners | Choose the owner, and if you want, one or more co-owners. By default, the owner is you. |

![Appliance_Basic_InformationBasicInfoAppliance.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d55a8ca4-62e1-4c66-d951-14c9404908f6(2).png)
7. Near the bottom of the page, click **Create Instance & Continue**.
8. On the Master Node tab, apply these settings:

| Installation Method | Choose **Automated Install**. |
| --- | --- |
| Download Airgapped Package | (Optional) If you are downloading a pod that you will register to a Securiti Sovereign Deployment, mark this checkbox to download a package that includes all dependencies needed to run the pod. > [!NOTE] > **Note** > > If you are not deploying the pod for Securiti Sovereign, do not download the airgapped package. |
| Cluster/Master Node IP | Enter your cluster/node private IP address. |
| Secret | Click **Generate Secret Key**. |
| (Optional) Proxy | If your organization has a proxy policy in place, enter a valid proxy address or hostname and enter the relevant port number. |
| Proxy Username and Password | Enter the username and password for connecting to the proxy server. Click **Setup authentication for the proxy (*****optional*****)** to see the fields for the username and password. ![System settings interface showing options for downloading and proxy authentication setup.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod-installation-proxy-creds.png) pod-installation-proxy-creds |

> [!NOTE]
> **Note**
> 
> By default, automated installation installs the pod in the /mnt directory. To install the pod elsewhere, contact [support@securiti.ai](mailto:support@securiti.ai) for assistance.

![automated-install.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-200d8259-adba-5a99-4520-6d2ba4e51f3d(2).png)
9. Click **Generate CURL Command**.

![automated-install-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c02e73e4-b924-42d3-2af3-0e8ccc3d621e(2).png)

Securiti generates a unique CURL command that you enter into your server's administrative suite.
10. Record the CURL command to use later.
11. (Optional) From the ​Pod Resource Profiles​​ dropdown menu, choose your preferred profile. For more information, see [Pod Resource Profiles](/v1/docs/pods-recommended-pod-provisioning#pod-resource-profiles).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod_resource_profile_automated.png)
12. Open a terminal window and log in to the compute instance where you are installing the pod.
13. Execute the `sudo su` command and enter the root credentials to become root.
14. Run the pre-flight diagnostic script to reset and validate system settings required by the pod:
  1. Find the poddiagnostics.sh file you downloaded earlier and copy it to the compute instance.
  2. Run the script with the `--check` flag, for example:

```bash
bash poddiagnostics.sh install --check
```

The script validates and resets system settings required by the pod, as shown below.

![Screenshot_2024-06-24_at_8_44_25_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-10607fd9-fa58-1db6-9c94-1cc2019cfc9e(2).png)
  3. Review the results of the pre-flight check and run this command to address any issues found:

```bash
bash poddiagnostics.sh install --fix
```
15. Paste the installation CURL command you recorded earlier into the terminal window and press **Enter**.
16. When the installation completes with status “Registration Successful”, refresh the Securiti browser window.
17. Use the following command to check the status of the pod:

```bash
kubectl get pods
```

![Appliance-Server_Confirmation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6ffb53ea-902e-af1c-15d6-6e0163aa80a0(4).png)
18. (Optional) Copy required jars (required only for SQL connectors): See [Uploading JDBC driver files in Securiti](/v1/docs/uploading-jdbc-driver-files-in-securiti) for more information.

## Manual pod installation (cluster version v1.28+)

The manual installation gives you more flexibility in customizing the pod configuration.

#### 1. Configure the pod in Securiti

1. In Securiti, from the top left corner of the Dashboard, click the **Jewel** icon.
2. From the Platform Services section, click **Settings > Deployment**.
3. Under Development, click **Pods**.
4. If you are replacing a failed pod that you want to restore as described in [Backing up and restoring pods (cluster version v1.28+)](/v1/docs/backing-up-and-restoring-pod), click the tile for the failed pod, then skip ahead to **Step 8** below.
5. Near the top of the page, click **+ New Cluster**, then **Custom Install**.
6. On the Basic Information tab, enter the following information:

| Cluster Name | Enter a convenient name. Do not use any spaces. |
| --- | --- |
| Cluster Location | Enter the location (country, state, and city). |
| Owners | Choose the owner, and if you want, one or more co-owners. By default, the owner is you. |

![appliance-manual-installation-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7496acde-75fb-d721-0554-a79bc4485391(2).png)
7. Near the bottom of the page, click **Create Instance & Continue**.
8. On the Master Node tab, for Installation Method choose **Manual Install**.

![custom-installationa-airgap.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-71b97c18-6616-0d63-d47b-280416ebd9eb(2).png)
9. **(Optional)** Mark the checkbox against **Download air gapped package** to download the airgapped bundle.
10. Do one of the following to download a .tar file containing the image:

> [!NOTE]
> **Note**
> 
> Downloading from CloudFront may be faster in locations such as Brazil and the Middle East.

![pod-download.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67743637-e7b5-a5b1-402b-751ace2599cd(2).png)
  - Click **Download Pod Image** to download the image from AWS S3.
  - Click **Download from CDN** to download the image from the CloudFront content delivery network.
11. Click **Download Pod Key**.

Securiti shows you the pod key.

![download-pod-key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2a59f9a7-77cb-ca0e-5ad0-b20649b329f4(2).png)
12. Near the right end of the box containing the key, click **Copy** to copy the key onto the clipboard.
13. (Optional) From the ​Pod Resource Profiles​​ dropdown menu, choose your preferred profile. For more information, see ​[Pod Resource Profiles​](/v1/docs/pods-recommended-pod-provisioning#pod-resource-profiles).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod_resource_profiles.png)
14. Record the key to use later.

#### 2. Copy the install bundle to the node

#### For online bundle

```bash
scp securiti-appliance-installer-online-<version>.tar <user@server:path>
```

For example:

```bash
scp securiti-appliance-installer-online-<version>.tar ubuntu@192.168.86.115:/tmp
```

#### For airgapped bundle

In case you downloaded the airgapped package, the install command will have a different installer name, such as:

```bash
scp securiti-appliance-installer-airgap-<version>.tar ubuntu@192.168.86.115:/tmp
```

#### 3. Extract files

#### For online bundle

```bash
ssh ubuntu@192.168.86.115
sudo su
cd <path where installer tar copied>
mv securiti-appliance-installer-online-<version>.tar /tmp/securiti-appliance-installer.tar.gz
INSTALLATION_DIR=/mnt/installation/securiti-appliance-installer
mkdir -p "$INSTALLATION_DIR"
sudo tar -xf /tmp/securiti-appliance-installer.tar.gz -C "$INSTALLATION_DIR" --strip-components=1
cd "$INSTALLATION_DIR"
```

#### For Airgapped bundle

Use the commands below to extract the files. Note that the first three commands from the script below are used to access the machine, and the actual extraction is taking place in the fourth command.

```bash
ssh ubuntu@192.168.86.115
sudo su
cd <path where installer tar copied>
mv securiti-appliance-installer-airgap-<version>.tar /tmp/securiti-appliance-installer.tar.gz
INSTALLATION_DIR=/mnt/installation/securiti-appliance-installer
mkdir -p "$INSTALLATION_DIR"
sudo tar -xf /tmp/securiti-appliance-installer.tar.gz -C "$INSTALLATION_DIR" --strip-components=1
cd "$INSTALLATION_DIR"
```

#### 4. Run the preflight diagnostic script

For more information, see [Using the pre-flight diagnostic script (cluster version v1.28+)](/v1/docs/pods-using-the-pre-flight-diagnostic-script).

1. Run the script with the `install --check` flag, for example:

```plaintext
bash poddiagnostics.sh install --check
```

The script validates and resets system settings required by the pod, as shown below.

![The script validates system settings required by the pod](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c54a4375-2ab2-4400-391d-69fa36e82ab6(7).png)
2. Review the results of the pre-flight check and run `bash poddiagnostics.sh install --fix` to address any issues found, as shown below.

![The script validates system settings required by the pod](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e9c73ef-c006-2717-acdd-da781b803d0a(7).png)

> [!NOTE]
> **Note**
> 
> We recommend that you reboot the node and run the `poddiagnostics.sh install --check` again after the reboot to ensure that the Securiti applied configuration does not conflict with any other config set by other system services.

#### 5. Install the primary node

#### For online bundle

```bash
export SECURITI_LICENSE="< key from earlier step>"
export SECURITI_NODE_JOIN_TOKEN="secretthatisusedforjoiningmorenodestothiscluster"
export SECURITI_REGISTRY_HOSTNAME="<securiti_host>" # Replace with securiti server domain where  is created
export SECURITI_REGISTRY_SECRET_B64="$(echo {\"auths\":{\"$SECURITI_REGISTRY_HOSTNAME\":{\"auth\":\"$SECURITI_LICENSE\"}}} | base64 -w 0)"
export SECURITI_SKIP_DOWNLOAD=true
bash install.sh
```

#### For airgapped bundle

Use the commands below to install the primary node.

```bash
export SECURITI_LICENSE="< key from earlier step>"
export SECURITI_NODE_JOIN_TOKEN="secretthatisusedforjoiningmorenodestothiscluster" #This must be an alphanumeric value and would be used for joining more nodes to this cluster
export SECURITI_SKIP_DOWNLOAD_CHECKSUM=true
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
export SECURITI_AIRGAP=true
export SECURITI_SKIP_DOWNLOAD=true
bash install.sh
```

For Securiti Sovereign:

```bash
export SECURITI_LICENSE="< key from earlier step>"
export SECURITI_NODE_JOIN_TOKEN="secretthatisusedforjoiningmorenodestothiscluster" #This must be an alphanumeric value and would be used for joining more nodes to this cluster
export SECURITI_REGISTRY_HOSTNAME="<securiti_host>"
export SECURITI_REGISTRY_SECRET_B64="$(echo {\"auths\":{\"$SECURITI_REGISTRY_HOSTNAME\":{\"auth\":\"$SECURITI_LICENSE\"}}} | base64 -w 0)"
export SECURITI_SKIP_DOWNLOAD_CHECKSUM=true
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
export SECURITI_AIRGAP=true
export SECURITI_SKIP_DOWNLOAD=true
bash install.sh
```

Where `&lt;securiti_host&gt;` is:

| Cloud | URL |
| --- | --- |
| US | `app.securiti.ai` |
| US1 | `app1.securiti.ai` |
| Canada | `app3.securiti.ai` |
| EU | `app.eu.securiti.ai` |
| Indonesia | `app2.securiti.ai` |
| Australia | `app4.securiti.ai` |
| UAE | `app5.securiti.ai` |
| India Cloud | `app6.securiti.ai` |
| KSA cloud | `app7.securiti.ai` |
| Qatar Cloud | `app8.securiti.ai` |
| Sovereign deployment | Consult the administrator of your Sovereign deployment |

![install_the_primary_node.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d8793117-749b-1fbc-29ad-5f4c0edb01ae(2).png)

#### 6. (Optional) Configure HTTP proxy

1. Add a `runtimeenvironment.env` block in the `local-override-values.yaml` file. Replace the IP address `10.151.20.176` with your own IP address.

> [!NOTE]
> **Note**
> 
> In certain scenarios, adding http to the IP addresses might not work. You can try removing http:// from your proxy IP address. However, K3s documentation recommends using the HTTP protocol with the proxy IP.

```bash
global:
  redis:
    password: "your_password"
  bin_dir: "/usr/bin"

runtimeenvironment:
  env:
    HTTP_PROXY: http://<username>:<password>@10.151.230.251:8080
    http_proxy: http://<username>:<password>@10.151.230.251:8080
    HTTPS_PROXY: http://<username>:<password>@10.151.230.251:8080
    https_proxy: http://<username>:<password>@10.151.230.251:8080
    NO_PROXY: 0.0.0.0/0,.local,priv-appliance-elasticsearch,10.42.0.0/16
    no_proxy: 0.0.0.0/0,.local,priv-appliance-elasticsearch,10.42.0.0/16
    JAVA_NO_PROXY: 127.0.0.1,localhost,local,priv-appliance-elasticsearch,10.0.*,10.0.0.*
    java_no_proxy: 127.0.0.1,localhost,local,priv-appliance-elasticsearch,10.0.*,10.0.0.*
```

If you don't have authentication credentials for your proxy server, use the proxy server URL without username and password. For example:

```bash
HTTP_PROXY: http://10.151.230.251:8080
```

> [!NOTE]
> **Note**
> 
> For Java-based services like the content-classification engine running on the pod, we recommend that you provide a separate environment variable to specify the proxy bypass list. This is because the Java proxy implementation understands patterns based on wildcarding. For example, you can wildcard an IP address like `52.11.*` or a DNS name like `*.cnn.com`.
2. Edit `/etc/systemd/system/k3s.service.env` file to add the following entries. You must replace the IP address `10.151.20.176` with your own IP address.

```bash
HTTP_PROXY=http://10.151.20.176:3128
HTTPS_PROXY=http://10.151.20.176:3128
NO_PROXY=0.0.0.0/0,.local,*.local
```
3. Apply settings to kubernetes (used for operations like image pulls):

```bash
systemctl restart k3s
```
4. Set KUBECONFIG for use by helm:

```bash
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
```
5. Apply settings to the pod:

```bash
$INSTALLATION_DIR/helm upgrade --atomic priv-appliance $INSTALLATION_DIR/securiti-appliance-0.1.0.tgz -f $INSTALLATION_DIR/values.yaml -f $INSTALLATION_DIR/local-override-values.yaml -f $INSTALLATION_DIR/customer-override-values.yaml --timeout 1500s --set download-worker.replicaCount=1 --set download-worker.minReplicas=1 --set download-worker.maxReplicas=1 --set dd-connector-async.replicaCount=1
```
6. If using an intercepting proxy, configure CA certificate:

```bash
openssl x509 -inform der -outform pem -in myCA2.der -out CERTIFICATE.crt (convert crt, so that it should start with ----BEGIN CERTIFICATE-----)
chmod 644 CERTIFICATE.crt

centos
cp CERTIFICATE.crt /etc/pki/ca-trust/source/anchors/
update-ca-trust

ubuntu
sudo cp CERTIFICATE.crt /usr/local/share/ca-certificates/
sudo update-ca-certificates
```
7. Use the following command to create a configmap:

```bash
kubectl create configmap ca-pem-config --from-file=custom-ca-cert.pem=/path/to/myCA.der(der, crt, pem)
```
8. Delete all pods to put the proxy configuration into effect:

```bash
kubectl get po |  grep "priv-app"  | awk '{print $1x}' | xargs kubectl delete po
```

#### Proxy Configuration and Troubleshooting

When configuring a proxy for your pod installation, you can use the Diagnostics script for both intercepting and transparent proxies. This script helps in troubleshooting and setting up the necessary network configurations.

> [!NOTE]
> **Important**
> 
> - The commands below are designed to work regardless of whether the pod is already installed.
> - If the pod needs to be freshly installed, the troubleshoot command will prepare the necessary files for the installation script to use during the setup process.

Navigate to the relevant directory by executing the following command:

```bash
cd /mnt/installation/securiti-appliance-installer
```

*/mnt* is the default install directory. The default installation directory can vary.

#### Transparent Proxy

To troubleshoot and set up a transparent proxy, use the following command:

```bash
sh poddiagnostics.sh troubleshoot network setup-proxy <hostname>:<port>
```

#### Intercepting Proxy

For an intercepting proxy, you need to specify the path to the certificate. Use the following command:

```bash
sh poddiagnostics.sh troubleshoot network setup-proxy <hostname>:<port> --cert /path/to/cert
```

#### Restarting application pods

When updating the proxy using the `poddiagnostics.sh` script on either the Master node or Worker node, you must restart the application to apply the changes. After modifying the proxy settings, the script prompts you to restart the application.

- If you accept the prompt, all pods restart automatically with the updated configurations.

![master-node-prompt.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6d7d3e08-509f-b725-5ba8-b4a9186229c0(2).png)
- If you decline the prompt, you can manually restart the pods at a later time to apply the changes.

When you deploy the pod, it performs the following actions:

- In the case of a single node:
  - It deploys the pod and connects it to Securiti application.
  - Once the pod is connected to Securiti application, it appears green on the interface.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WCJZ2DG8.png)
- In the case of a multi-node cluster:

You must configure the worker nodes after the master node is active on the UI. For more information, see [Adding secondary nodes](/latest/docs/pods-adding-secondary-nodes-cluster-version-v128).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod-quick-install-guides-cluster-version-v1.28-en-image-v2443j98.png)
  - It deploys the Securiti pod as the master node.
  - In addition, it creates the same number of empty worker node VMs defined in the **Number of Worker Instances** field for the AWS template.

If the pod you created does not meet the hardware resources baseline, it displays a warning banner at the following locations at **Pods** page:

1. A warning banner in red color above the pod name, if master node or any of the worker node is under-provisioned.
2. A yellow alert icon with the node is that specific node is under-provisioned. Hovering over the yellow alert icon displays the specific hardware that is under-provisioned.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-F2WIIQXA.png)

Each pod has a master node that manages the activities of the secondary nodes.

## Related

- [Pod quick install guides cluster version v1.28](/pod-quick-install-guides-cluster-version-v128-en.md)
- [Pod troubleshooting (cluster version v1.28+)](/podtroubleshooting.md)
- [Backing up and restoring pods](/backing-up-and-restoring-pod.md)
