---
title: "Automated secondary node installation (cluster version v1.28+)"
slug: "pod-automated-secondary-node-installation"
updated: 2025-12-09T12:55:36Z
published: 2025-12-09T12:55:36Z
canonical: "helpcenter.securiti.ai/pod-automated-secondary-node-installation"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Automated secondary node installation (cluster version v1.28+)

Follow these steps to add an additional node to an active pod. You can add up to 9 secondary nodes:

1. In Securiti, from the top left corner of the Dashboard, click the **Jewel** icon.
2. From the Platform Services section, click **Settings** > **Deployment**.
3. Under Deployment, click **Pods**.
4. On the card for the pod to which you want to add a secondary node, near the upper right corner, click **+**.

![_forSecondNode.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f6494bcd-14ae-da05-0fe0-da5c88e6eb2c(2).png)
5. For installation method, choose **Automated install**.

![automated-secondary-node-installation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a424ba8b-4bb6-ee3d-525a-560003168788(2).png)
6. In the Node IP box, enter the Private IP address for the server or VM where you want to install the additional node.
7. Click **Generate CURL command**.
8. Next to the CURL Command box, click **Copy to Clipboard**.

![CURL_CommandGenerator.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b7d0bcf9-a3ab-bdcb-6411-c6e7191e096c(2).png)
9. Open a server terminal window on the VM or compute instance where you are installing the node.
10. If you do not already have administrative rights, use the **sudo su** command to become an administrator.
11. [Copy and execute the pre-flight diagnostic script](/v1/docs/pods-using-the-pre-flight-diagnostic-script) in your server's terminal window.
12. Paste and execute the CURL command in your server's terminal window.

The command downloads and executes the installation script. The installation takes 10 to 15 minutes to complete.
13. When the installation completes, refresh the Securiti browser window to verify that the secondary node was successfully installed.

![secondary-node-installation.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-88c61f90-ad2f-1560-b3ab-d7f305aa35b9(2).png)
14. Run the following command to verify that the k3s agent is active on the secondary pod:

```bash
systemctl status k3s-agent
```
15. (Optional) Copy required jars (required only for SQL connectors): Download all jar drivers required for external SQL connectivity from the website for the data system, and then enter the following commands:

```bash
mkdir -p /mnt/drivers
cp <jdbc*.jar> /mnt/drivers/
```

## Add secondary nodes on pre-install appliance in AWS

If you are using AWS for your pods management, Securiti supports automation, which lets you create virtual machines (EC2 instances) for secondary nodes altogether. Otherwise, you must create all virtual machines manually.

> [!NOTE]
> Important
> 
> The procedure requires you meet the following requirements.
> 
> - You must have created your pod using the template (automated installation).
> - You must have your previous CloudFormation template you used for the automated installation of pods.

To add secondary nodes automatically using a template:

1. Open Pods installation page.
  1. In Securiti, from the top left corner of the Dashboard, click the **Jewel** icon.
  2. In the navigation bar, select Settings > Deployment > Pods.
2. On the top right corner of the screen, click **New Cluster** and select **Quick Install**.
3. In the **Add a Compute Pod for Discovery** popup, in the **Deployment method**, choose **Download Template**.
4. Click on **Prepare Template**.

It takes a while to prepare the new template.
5. When the **Prepare Template** button transitions into **Download Template**, click it.

It downloads the template into your system directory.
6. On your AWS Console, open the **CloudFormation** service and open your installed appliance template.
7. At the top right of your console, click **Create Stack** and select **With existing resources**.
8. In the templates, update your template by uploading the new template.

Uploading the new template provides you with the following new fields.

| Parameter | Description |
| --- | --- |
| Number of worker instances | It expects a number and creates the empty virtual machines for secondary nodes. You can later configure the virtual machines to configure secondary nodes. |
| Securiti Control VM CIDR to whitelist | It lets you add IP address range to the allow-list for accessing the machine. |

It updates your existing appliance with the new template, as well as installs empty virtual machines for secondary nodes.

## Related

- [Manual secondary node installation (cluster version v1.28+)](/pods-manual-secondary-node-installation.md)
- [Upgrading pods cluster version](/upgrading-pods-cluster-version.md)
- [Pod troubleshooting (cluster version v1.28+)](/podtroubleshooting.md)
