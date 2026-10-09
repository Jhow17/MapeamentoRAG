---
title: "Using the pre-flight diagnostic script (cluster version v1.28+)"
slug: "pods-using-the-pre-flight-diagnostic-script"
updated: 2026-01-05T07:51:11Z
published: 2026-01-05T07:51:11Z
canonical: "helpcenter.securiti.ai/pods-using-the-pre-flight-diagnostic-script"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Using the pre-flight diagnostic script (cluster version v1.28+)

Use the pod pre-flight diagnostic script to make sure the VM or server is correctly provisioned, and also to troubleshoot and address pod installation issues. We recommend you do this every time you install or upgrade a pod.

### Downloading the diagnostic script

1. On the Master Node tab for a pod cluster, for installation method choose **Manual install**, then click **Download Preflight Shell Script** as shown below:

![download-preflight.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d19ab78a-18fe-2bf6-5535-f765661d8eac(6).png)

You can also download the script when you are adding a new node:

![Pre-flight diagnostic script (when adding a new node)](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4def7d7-f8e4-71db-21be-b84a062bdf80(4).png)
2. After downloading the poddiagnostics.sh script, copy it to the compute instance.

### Running the diagnostic script

For new pod installations, we recommend that you use the `install --check` flag to check if there are any issues with the compute instance that would prevent the pod from installing and running properly:

```bash
sh poddiagnostics.sh install --check
```

> [!NOTE]
> **Note**
> 
> The script must have root access to run properly.

The script validates system settings required by the pod, as shown below.

![The script validates system settings required by the pod](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c54a4375-2ab2-4400-391d-69fa36e82ab6(6).png)

To address issues revealed by the diagnostic check, use the `install --fix` flag to try to fix them. The script can fix many, but not all software-related issues:

```bash
sh poddiagnostics.sh install --fix
```

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(225).png)

### Pods diagnostic report

You can review the pod's logs of the past 3 hours for troubleshooting if the process encounters issues. If any error occurs during installation, it lets you investigate the problem.

1. On the **Backup & Restore** tab, and next to the Pod Diagnostic Report, click **Generate Report**.

![Pod_generate_report.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0aa6d51-b5fc-3b02-9390-f6e13fa410ed(2).png)

It downloads a **.tar** file containing the relevant log files into your system storage. You can review the log files to investigate and resolve the errors.

> [!NOTE]
> **Note**
> 
> If the Generate Report button is disabled, you must activate your pod to generate and download the logs.

### Diagnostic script commands and options

Usage:

```bash
sh poddiagnostics.sh [command] [options]
```

To view the available options, invoke the script without commands or options:

```bash
Usage: sh poddiagnostics.sh COMMAND [OPTIONS]
Available Commands:
	install [OPTIONS]			 Parent command for running pre install diagnostics on your machine
	Available Options:
		-c, --check			 Check to see if the pod meets the required prerequisites
		-f, --fix			 Attempt to fix some issues that prevent the pod from being installed
	troubleshoot [OPTIONS] Parent command for troubleshooting pods
	Available Subcommands/Options:
		report			 Creates pod logs report
		pods			 Parent command for K8s pods operations. For details and subcommands, run: sh poddiagnostics.sh troubleshoot pods help
		node			 Parent command for K8s node operations. For details and subcommands, run: sh poddiagnostics.sh troubleshoot node help
		cleanup			 Clean up disk to recover storage. For details and subcommands, run: sh poddiagnostics.sh troubleshoot cleanup help
		registration		 Register or deregister the securiti pod. For details and subcommands, run: sh poddiagnostics.sh troubleshoot registration help
```

The table below describes all available diagnostic script commands and options:

| `install` | `-c` `--check` | Checks for potential issues like minimum hardware requirements, kernel parameters etc, to see if the environment meets the required prerequisites. |
| --- | --- | --- |
| `install` | `-f` `--fix` | Attempts to fix issues that prevent the pod from being installed. > [!NOTE] > **Note** > > If using the `-f `or `--fix` option makes any changes to the VM configuration, reboot the VM to put those changes into effect before re-trying the pod installation. |
| `troubleshoot` | `report` | Creates a logs bundle for troubleshooting. |
| `troubleshoot` | `pods` | `list` | List pods in the default namespace. Optional views are also available: |
| `troubleshoot` | `pods` | `list` | `-j` `--job` `--jobs` | Show only the jobs in the default namespace. |
| `troubleshoot` | `pods` | `list` | `-w` `--watch` | List and watch all pods in all namespace. |
| `troubleshoot` | `pods` | `list` | `-A` `--all-namespaces` | Show all pods across all the namespaces. |
| `troubleshoot` | `pods` | `scale` | `-d` | Scale a deployment to the specified size e.g: `troubleshoot pods scale -d &lt;deployment-name&gt; &lt;amount&gt;` |
| `troubleshoot` | `pods` | `delete` | Delete/restart specified pods: |
| `troubleshoot` | `pods` | `delete` | `--securiti` | Delete all Securiti Pods. |
| `troubleshoot` | `pods` | `delete` | `--failed` | Delete only failed pods. |
| `troubleshoot` | `pods` | `delete` | `--completed` | Delete only completed pods. |
| `troubleshoot` | `pods` | `delete` | `--all` | Delete all pods across all namespaces. |
| `troubleshoot` | `pods` | `logs` | Show logs for all K8s pods. You can use one or both of the following options to filter logs for only the specified pods: |
| `troubleshoot` | `pods` | `logs` | `-d &lt;deployment&gt;` | Specify the deployment to list logs for. |
| `troubleshoot` | `pods` | `logs` | `-c &lt;container&gt;` | Optional argument to only list logs for a specific container, e.g: `troubleshoot logs -d &lt;deployment-name&gt; &lt;container-name&gt;` |
| `troubleshoot` | `pods` | `help` | Describes available `troubleshoot pods` options. |
| `troubleshoot` | `network` | `setup-proxy &lt;username&gt;:&lt;password&gt;@&lt;hostname&gt;:&lt;port&gt;` | Sets up a proxy to use for connecting to the Securiti pod. The hostname and port must be a valid proxy endpoint. |
| `troubleshoot` | `network` | `setup-proxy &lt;username&gt;:&lt;password&gt;@&lt;hostname&gt;:&lt;port&gt;` | `--cert &lt;/path/to/cert-file&gt;` | In the case of an intercepting proxy, this optional argument imports the relevant certificate into K8s. |
| `troubleshoot` | `network` | `setup-proxy &lt;username&gt;:&lt;password&gt;@&lt;hostname&gt;:&lt;port&gt;` | `--no-proxy &lt;address1&gt;,&lt;adress2&gt;,...` | Adds custom addresses where the proxy is not applied. This optional argument can contain multiple, comma separated addresses. |
| `troubleshoot` | `network` | `install-proxy-K8s&nbsp;&lt;username&gt;:&lt;password&gt;@&lt;hostname&gt;:&lt;port&gt;` | If a proxy is set up before installing a Securiti Pod, use this command to ensure that K8s is properly set up to use it. The hostname and port must be a valid proxy endpoint. |
| `troubleshoot` | `network` | `install-proxy-K8s &lt;username&gt;:&lt;password&gt;@&lt;hostname&gt;:&lt;port&gt;` | `--cert &lt;/path/to/cert-file&gt;` | In the case of an intercepting proxy, this optional argument imports the relevant certificate into K8s. |
| `troubleshoot` | `network` | `install-proxy-K8s&nbsp;&lt;username&gt;:&lt;password&gt;@&lt;hostname&gt;:&lt;port&gt;` | `--no-proxy &lt;address1&gt;,&lt;adress2&gt;,...` | Adds custom addresses where the proxy is not applied. This optional argument can contain multiple, comma separated addresses. |
| `troubleshoot` | `network` | `override-cidr` | Use with the following arguments to override the default CIDR for K8s pods and services. You must include the subnet in the IP, for example "`10.46.0.0/16`". To override both CIDRs, use both of the following arguments in one command. Using separate commands with one argument each results in only the latest CIDR being set. |
| `troubleshoot` | `network` | `override-cidr` | `--pod-cidr &lt;IP&gt;` | Overrides the default CIDR of 10.42.0.0 for K8s pods. This command only works before you install the Securiti pod. |
| `troubleshoot` | `network` | `override-cidr` | `--service-cidr &lt;IP&gt;` | Override the default CIDR of 10.43.0.0 for K8s services. This command only works before you install the Securiti Pod. |
| `troubleshoot` | `network` | `help` | Describes available `troubleshoot network` options. |
| `troubleshoot` | `node` | `health` | Shows the health and details of the node where the Securiti pod is running. |
| `troubleshoot` | `node` | `help` | Describes available `troubleshoot node` options. |
| `troubleshoot` | `cleanup` | Frees up used disk storage space. Specify one of the following options, and press **Y** to confirm when prompted. You can skip the confirmation by adding a space and `-y` after the option: |
| `troubleshoot` | `cleanup` | `disk` | Delete all data in /mnt/data. |
| `troubleshoot` | `cleanup` | `images` | Delete old container images. If a specific version is provided (format like 1.103.0-03rc), only those images are deleted. |
| `troubleshoot` | `cleanup` | `all` | Delete all data in /mnt/data and all old container images. |
| `troubleshoot` | `cleanup` | `help` | Describes available `troubleshoot cleanup` options. |
| `troubleshoot` | `registration` | Registers or deregisters a Securiti Pod. Specify one of the following options: |
| `troubleshoot` | `registration` | `&lt;license-key&gt;` | Registers a pod using the specified license key. |
| `troubleshoot` | `registration` | `deregister` | Deregisters a pod. Press **Y** to confirm when prompted. You can skip the confirmation by adding `-y` after the option. |
| `troubleshoot` | `registration` | `help` | Describes available `troubleshoot registration` options. |

## Related

- [Pod quick install guides cluster version v1.28](/pod-quick-install-guides-cluster-version-v128-en.md)
- [Pod custom installation guides (cluster version v1.28+)](/podcustom-installation-guides.md)
- [Pod troubleshooting (cluster version v1.28+)](/podtroubleshooting.md)
- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
