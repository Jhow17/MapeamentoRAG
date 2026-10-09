---
title: "Permanently removing a node (cluster version v1.28+)"
slug: "pods-permanently-removing-a-node"
updated: 2025-12-09T13:07:27Z
published: 2025-12-09T13:07:27Z
canonical: "helpcenter.securiti.ai/pods-permanently-removing-a-node"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Permanently removing a node (cluster version v1.28+)

An existing node can cause problems during a reinstallation, so you should remove it before reinstalling the node. Before removing the node, you must migrate its data to the master node. Follow the steps below for the migration of the member/worker node’s data.

Before removing the node, you must copy all directories from the current installation directory (/mnt or /var/lib) to the new/master node's installation directory (/mnt or /var/lib).

1. Set the installation directory using the command below.

```bash
SECURITI_INSTALL_DIR=/mnt #/var/lib
```
2. Next, create a tarball named securiti-app-backup.tar that contains all files and directories within the securiti-app directory.

```bash
cd "$SECURITI_INSTALL_DIR/securiti-app/"
tar -cvf securiti-app-backup.tar *
```
3. Securely copy the tar file to the new/master node’s tmp directory.

```bash
scp "$SECURITI_INSTALL_DIR/securiti-app/securiti-app-backup.tar" user@remote_machine:/tmp/
```

Replace user with the appropriate username and remote machine with the IP address of the node.

As an alternative approach, use the PEM file to securely copy the file.

```bash
scp -i "$PEM_FILE" "$SECURITI_INSTALL_DIR/securiti-app/securiti-app-backup.tar" user@remote_machine:/tmp/ #change the user,remote_machine
```
4. Set the installation directory on the new/master node.

```bash
SECURITI_INSTALL_DIR=/mnt #/var/lib
```
5. Move the tar file from the /tmp directory to the installation_dir.

```bash
mv /tmp/securiti-app-backup.tar $SECURITI_INSTALL_DIR #/mnt or /var/lib
```
6. Untar the backup file into the installation directory using the commands below.

```bash
mkdir $SECURITI_INSTALL_DIR/securiti-app-backup
mv $SECURITI_INSTALL_DIR/securiti-app-backup.tar  $SECURITI_INSTALL_DIR/securiti-app-backup
cd $SECURITI_INSTALL_DIR/securiti-app-backup
tar -xvf securiti-app-backup.tar
```
7. Append all the internal content from the securiti-app-backup directory to the existing directory using the following bash script.

```bash
SOURCE_DIR=/mnt #/var/lib
SECURITI_INSTALL_DIR=${SOURCE_DIR}/securiti-app/
BACKUP_DIR=${SOURCE_DIR}/securiti-app-backup
for dir in data secrets tmpfs dagdata drivers source_queue_dump cc table-training-samples certs tmp; do
    if [ -d "$BACKUP_DIR/$dir" ]; then
        cp -r "$BACKUP_DIR/$dir/"* "$SECURITI_INSTALL_DIR/$dir/"
    fi
done
```

Alternatively, you can run all these commands one by one.

```bash
SOURCE_DIR=/mnt #/var/lib
SECURITI_INSTALL_DIR=${SOURCE_DIR}/securiti-app/
BACKUP_DIR=${SOURCE_DIR}/securiti-app-backup

cp -r  "$BACKUP_DIR"/data/* "$SECURITI_INSTALL_DIR"/data/
cp -r  "$BACKUP_DIR"/secrets/* "$SECURITI_INSTALL_DIR"/secrets/
cp -r  "$BACKUP_DIR"/tmpfs/* "$SECURITI_INSTALL_DIR"/tmpfs/
cp -r  "$BACKUP_DIR"/dagdata/* "$SECURITI_INSTALL_DIR"/dagdata/
cp -r  "$BACKUP_DIR"/drivers/* "$SECURITI_INSTALL_DIR"/drivers/
cp -r  "$BACKUP_DIR"/source_queue_dump/* "$SECURITI_INSTALL_DIR"/source_queue_dump/
cp -r  "$BACKUP_DIR"/cc/* "$SECURITI_INSTALL_DIR"/cc/
cp -r  "$BACKUP_DIR"/table-training-samples/* "$SECURITI_INSTALL_DIR"/table-training-samples/
cp -r  "$BACKUP_DIR"/certs/* "$SECURITI_INSTALL_DIR"/certs/
cp -r  "$BACKUP_DIR"/tmp/* "$SECURITI_INSTALL_DIR"/tmp/
```
8. Run the mapping command.

> [!NOTE]
> **Note**
> 
> Replace <old_host> with the hostname of the node you are removing, and <new_host> with the hostname of the master node.

```bash
kubectl exec -it deploy/priv-appliance-config-controller -- securitictl update-fc-node-mappings --mapping "[{\"old_host\": \"ip-172-31-23-22\", \"new_host\": \"ip-172-31-15-13\"}]"]
```
9. Uninstall the Securiti application from the Securiti worker node.

```bash
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
k3s-agent-uninstall.sh (secondary node)
rm -f <SECURITI_INSTALL_DIR>/installation/securiti-appliance-installer/*.yaml
# Delete all app data (cannot be recovered)
rm -rf <SECURITI_INSTALL_DIR>/rancher
rm -rf /etc/rancher
```
10. Run the following commands from the master node to completely delete the node:

```bash
kubectl get nodes
kubectl delete node <node-name>
```

## Related

- [Updating pod software (cluster version v1.28+)](/pod-updating-pod-software.md)
- [Pod custom installation guides (cluster version v1.28+)](/podcustom-installation-guides.md)
