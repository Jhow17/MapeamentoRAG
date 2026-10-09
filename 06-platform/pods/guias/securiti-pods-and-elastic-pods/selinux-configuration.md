---
title: "SELinux configuration"
slug: "selinux-configuration"
updated: 2025-12-05T13:49:12Z
published: 2025-12-05T13:49:12Z
canonical: "helpcenter.securiti.ai/selinux-configuration"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# SELinux configuration

Security Enhanced Linux (SELinux) is a built-in security feature in Linux that controls what users, processes, and applications can access on a system. It adds an extra layer of protection to the operating system.

This document describes the process to configure SELinux before the pod installation.

## Prerequisites

It requires the following prerequisites to configure SELinux:

- RHEL 9.6
- Root access to run the installation script

## Install SELinux policy and container support

Run the following commands to install and enable SELinux, which includes `container-selinux` as a dependency:

```bash
# Install base policy + container-selinux
dnf install selinux-policy

# Enforce selinux 
sed -i 's/^SELINUX=.*/SELINUX=enforcing/' /etc/selinux/config
setenforce 1

# Verify is changes are applied
sestatus
```

## Install K3s SELinux policy

Install the K3s-specific SELinux policy from the Rancher’s repository using the following command:

```bash
yum install -y https://rpm.rancher.io/k3s/latest/common/centos/9/noarch/k3s-selinux-1.6-1.el9.noarch.rpm
```

## Create and install Securiti custom SELinux policy

To create and install the Securiti custom policy, proceed with the following steps.

1. Create the policy file by running the following command:

```bash
cat > securiti-policy.te << 'EOF'
module securiti-policy 1.0;

require {
    type container_t;
    type container_runtime_t;
    type container_log_t;
    type container_file_t;
    type init_t;

    class file { read create setattr unlink write getattr open execute entrypoint };
    class lnk_file { read getattr open };
    class dir { add_name create getattr setattr search write remove_name read };
    class capability { chown fowner fsetid dac_override };
}

# Rule 1: Allow prom node-exporter to read proc mount points
allow container_t init_t:file { read getattr open };
allow container_t init_t:dir { read search getattr };

# Rule 2: Allow container/monitor-status processes to read log directories
allow container_t container_log_t:dir { read search getattr };
allow container_t container_log_t:file { read getattr open };
allow container_t container_log_t:lnk_file { read getattr open };

# Rule 3: Allow container use of certain capabilities
allow container_t self:capability { chown fowner fsetid dac_override };

# Rule 4: Allow container access to container_file_t
allow container_t container_file_t:file { read create setattr unlink write getattr open };
allow container_t container_file_t:dir { add_name create getattr setattr search write remove_name read };
EOF
```

1. Compile and install the policy using the following commands.

```plaintext
# Compile
checkmodule -M -m -o securiti-policy.mod securiti-policy.te

# Create package
semodule_package -o securiti-policy.pp -m securiti-policy.mod

# Install
sudo semodule -i securiti-policy.pp

# Verify Install
semodule -l | grep -E "(k3s|container|securiti)"
```

## Installation dependency

While installing or upgrading the pod, you must consider the following dependencies when SELinux is enabled:

- The following values must be set to true before the pod installation script file, or the airgap bundle scripts for both installation and upgrade.

```plaintext
SECURITI_ENABLE_SELINUX=true
```

- Use `SECURITI_INSTALL_DIR` variable must be `/var/lib` when SELinux is enabled because K3s supports the default data directory only.

> [!NOTE]
> Note
> 
> Contact support team at [support@securiti.ai](mailto:support@securiti.ai) to set the installation directory to `/var/lib` in your pod installation script.
- Ensure the following SELinux policies are installed before running the pod installer script:
  - Selinux-policy
  - k3s-selinux
  - Securiti-policy

## Troubleshooting

If the installation of SELinux fails, use the following commands for troubleshooting:

- For SELinux audit logs, execute the following command:

```plaintext
sudo ausearch -m AVC
```
- For K3s logs, execute the following command:

```plaintext
sudo journalctl -u k3s
```

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Pod installation (cluster version v1.28+)](/pod-installation-cluster-version-v128.md)
