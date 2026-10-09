---
title: "Pod FAQs"
slug: "pod-faqs"
updated: 2026-03-18T11:01:13Z
published: 2026-03-18T11:01:13Z
canonical: "helpcenter.securiti.ai/pod-faqs"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Pod FAQs

**Why are CIS hardened base OS not supported for Pod Install?**

Securiti Pod installations are not compatible with CIS hardened OS images. This is because CIS hardened images contain stringent security measures that clash with the dynamic operational needs of Securiti pod's embedded Kubernetes (K3s) system. The result is often installation failures and general instability due to issues like conflicting configurations, mismatched kernel parameters, and overly restrictive network policies. It's also important to note that if you attempt to modify these hardened images to work with Securiti pod, you will invalidate any support provided by the original image vendor.

**What commands require Sudo for pod installation?**

The following commands in pod installation require Sudo access.

- **journalctl** is a command-line utility for querying and displaying logs from the journal, which is a centralized logging system used by modern Linux distributions such as systemd-based systems. It provides access to the logs collected by systemd-journald, which is responsible for managing and storing log data.

```bash
journalctl -u <service>
```
- **systemctl** is a command-line utility used for controlling the systemd system and service manager, which is a central component of many modern Linux distributions. **systemd** is responsible for managing system services, daemons, and other system processes, as well as handling system startup and shutdown procedures.

```bash
systemctl <command>
```

Securiti only requires the following systemctl commands.

```bash
systemctl status <service>
systemctl disable <service>
systemctl enable <service>
systemctl restart <service>
systemctl is-active <service>
systemctl list-units --type=service
Example <service> : k3s, k3s-agent, teleports
```
- The following are application-level commands.
  - **kubectl** is a command-line tool to interact with Kubernetes clusters. It lets users perform various operations on Kubernetes clusters, such as deploying applications, inspecting and managing cluster resources, debugging applications, and accessing cluster information.

```bash
kubectl <and all sub commands>
```
  - **crictl** is a command-line utility used for interacting with Container Runtime Interface (CRI) compatible container runtimes. CRI is an interface between container runtimes (such as Docker, containerd, and others) and the Kubernetes kubelet that enables Kubernetes to use any container runtime that implements the CRI.
  - ```bash
crictl <command>
```
  - **install.sh** is a script used for installing the Pod.

```bash
install.sh
```
  - **poddiagnostics.sh** is a script used for running diagnostics and collecting troubleshooting information for the Pod.

```plaintext
poddiagnostics.sh
```

**Why do pod updates fail when security or compliance software is running on the pods, and how can this be prevented?**

Pod updates might fail when external security or compliance software interferes with Securiti pods during update operations. Such tools often block or scan files, containers, or network connections in real time, which could interrupt pod restarts or modify critical resources. To prevent these issues, you must allowlist Securiti pods, related directories, and namespaces in your security or compliance software. This ensures that the update process completes smoothly while maintaining compliance and security within your environment.

See the following list of directories that you must allowlist in your security software:

| Directory category | Directory list |
| --- | --- |
| Securiti application directories | - /mnt/installation - /mnt/securiti-app |
| Kubernetes directories | - /var/log/k3s/ - /var/lib/kubelet/ - /var/lib/containerd/ - /var/lib/rancher/k3s/ - /usr/local/bin/k3s - /run/k3s/ - /etc/rancher/k3s/ - /mnt/rancher |
