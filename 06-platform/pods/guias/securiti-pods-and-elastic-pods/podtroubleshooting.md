---
title: "Pod troubleshooting (cluster version v1.28+)"
slug: "podtroubleshooting"
updated: 2026-02-26T08:54:44Z
published: 2026-02-26T08:54:44Z
canonical: "helpcenter.securiti.ai/podtroubleshooting"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Pod troubleshooting (cluster version v1.28+)

### Securiti cloud degraded state

If pod status changes to degraded on the cloud, it means no heartbeat is received from the pod. The cause could be a network connectivity issue, the compute instance is down, or some services are not running. After 20 minutes, the status changes to Offline.

### Connector

To view connector logs and see what files the pod has processed:

```bash
kubectl get pods | grep connector
```

To show containers:

```bash
kubectl logs -f connector-<type-id-XXXX>
```

```bash
kubectl logs -f <pod-name> <container-name>
```

To show the number of files sent to content classification:

```bash
kubectl logs -f <pod-name> <container-name> | grep "Sent message to CC" | wc -l
```

To show successful processing of files by content classification:

```bash
kubectl logs -f <pod-name> <container-name> | grep "Response from CC <{true" | wc -l
```

To check database connectivity:

```bash
telnet <db_ip> <port>
```

To check NFS connectivity:

- **Centos or Red Hat**

```bash
yum install nfs-utils
```
- **Ubuntu**

```bash
apt-get install -y nfs-common
mkdir /tmp/test
mount -t nfs -o proto=tcp,port=2049 -o nolock HostIP:HostPath /tmp/test
```

To check Samba connectivity:

- **Centos or Red Hat**

```bash
yum -y install samba samba-client cifs-utils
```
- **Ubuntu**

```bash
sudo apt install -y cifs-utils
mkdir /tmp/test
mount -t cifs //HostIP:HostPath /tmp/test -o username=USERID,password=USERPASSWORD
```

### Kubernetes health

To check the Kubernetes status:

- For a primary node:

```bash
systemctl status k3s
```
- For a secondary node:

```bash
systemctl status k3s-agent
```

To view logs for the Kubernetes service:

- For a primary node:

```bash
journalctl -u k3s
```
- For a secondary node:

```bash
journalctl -u k3s-agent
```

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Pod installation (cluster version v1.28+)](/pod-installation-cluster-version-v128.md)
- [Updating pod software (cluster version v1.28+)](/pod-updating-pod-software.md)
