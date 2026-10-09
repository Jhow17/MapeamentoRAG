---
title: "Migrating to pod cluster version (cluster version v1.28+)"
slug: "migrating-to-pod-cluster-version"
updated: 2026-03-25T07:54:35Z
published: 2026-03-25T07:54:35Z
canonical: "helpcenter.securiti.ai/migrating-to-pod-cluster-version"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Migrating to pod cluster version (cluster version v1.28+)

The procedure in this section describes how to migrate an existing pod of cluster version 1.0.12 to a pod of cluster version 1.128+ on the same VM.

### Prerequisites

- The cluster is healthy, and you have applied all upgrades.
- You have SSH access to all nodes to perform the operations described in this topic.
- The VMs for the master node and any secondary nodes meet the prerequisites for pods of cluster version 1.128+ (specifically OS, vCPU, and RAM requirements) described in [Pod prerequisites (cluster version v1.28+)](/v1/docs/pod-prerequisites-cluster-version-v128).

If necessary, increase the VM CPUs as described in [Resizing pod VMs (cluster version v1.28+)](/v1/docs/pods-resizing-pod-vms).
- There is enough free disk space on the VM to do a database backup and install the new pod. 30GB free space on the installation mount (usually `/mnt`, sometimes `/var/lib`) should suffice.
- Ensure that all discovery scans are paused or finished in Sensitive Data Intelligence, as shown below.

![image__28_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-05052a0e-68cc-8489-111c-6a3a142b29c7(2).png)

> [!NOTE]
> **Note**
> 
> Please refer to the [special case considerations sections](/v1/docs/migrating-to-pod-cluster-version#special-case-considerations) to understand how to handle the special cases such as node removal or data transfer from node A to node B.

### Node reduction considerations

When migrating multi-node clusters from version 1.0.12 to cluster version 1.28+, you might have the opportunity to reduce the number of nodes. If your earlier pod nodes are on 8 vCPU VMs, you can safely reduce by 50% the total number of nodes required when you migrate them to 16 vCPU VMs, or by 75% when you migrate them to 32 vCPU VMs. However, for each of your existing nodes for which you found table training data in **Step 8** below, you must update the mapping onto a new node as described later in **Step 13** below.

### Migration procedure

1. Run `gravity status` on the master node and preserve its output. You might need this information later if the pod has training data saved on it that you must remap later.

```bash
root@securiti-exa:~# gravity status
 name:		pensivegoldstine2992
 status:		active
Application:		privaci-appliance, version 1.84.0-03rc
Gravity version:	6.1.48 (client) / 6.1.48 (server)
Join token:		FM3dxRQdvw
Periodic updates:	Not Configured
Remote support:		Not Configured
Last completed operation:
    * Upgrade to version 1.84.0-07rc
      ID:	ebd0988c-4d60-4f35-930c-b449be7a62f0
      Started:	Thu Dec 22 18:00 UTC (8 minutes ago)
      Failed:	Thu Dec 22 18:01 UTC (8 minutes ago)
 endpoints:
    * Authentication gateway:
        - 10.0.0.18:32009
        - 10.0.0.97:32009
        - 10.0.0.235:32009
    *  management URL:
        - https://10.0.0.18:32009
        - https://10.0.0.97:32009
        - https://10.0.0.235:32009
 nodes:
    Masters:
        * securiti-qa-khi-03-5 / 10.0.0.18 / node
            Status:		healthy
            Remote access:	online
        * securiti-qa-khi-03-5-2 / 10.0.0.97 / worker
            Status:		healthy
            Remote access:	online
        * securiti-qa-khi-03-5-3 / 10.0.0.235 / worker
            Status:		healthy
            Remote access:	online
```
2. Download the `migration_util.sh` migration utility script from [this link](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/migration%20util.sh).
3. Copy the migration utility script to the master node and also to each member node.
4. On the master node, pause all scans by invoking `migration_util.sh` and choosing the `pause-scans` option:

```bash
root@securiti-example bash migration_util.sh
Select an option:
1. Pause-scans
2. Pre-migration
3.  Removal
4. Post-installation
5. Post-install-clean-up
6. Update-mapping
7. Quit
Enter your choice (1-7): 1
Setting migration flag to ensure no new scans are started
Warning: Using a password with '-a' or '-u' option on the command line interface may not be safe.
OK
Pausing scans to prevent data loss during migration. This might take a few minutes Defaulted container "config-controller" out of: config-controller, certificate-handler (init)
{"level": "INFO: ", "ts": "2024-04-01T22:45:25.832Z", "caller": "cryptoutil/key_loader.go:91", "msg": "Reading key names from pod's attache d cm"}
{"level": "INFO: ", "ts":"2024-04-01T22:45:25.856Z" {"level": "INFO: "
, "caller": "models/helpers.go:76", "msg": "Initializing cache with 3 retries"}
, "ts": "2024-04-01T22:45:26.325Z", "caller": "saml/saml.go:171", "msg": "IDP initiated trust length set to 10s. Check en
abled is set to true"}
{"level": "INFO: ", "ts": "2024-04-01T22:45:26.941Z", "caller": "cd/forceful_scan_job_action_cmd.go:40", "msg": "Handling forceful action"
"action": "pause-with-wait" }
{"level": "INFO: ", "ts": "2024-04-01T22:45:27.030Z", "caller": "cloud_communication/params.go:39", "msg": "Cloud communication params are loaded successfully."}
{"level": "INFO: ", "ts": "2024-04-01T22:45:27.089Z", "caller": "securiticlient/appliance.go:1499", "msg": "No eligible discovery scan foun d to pause. "} Scans paused
Select an option:
1. Pause-scans
2. Pre-migration
3. Post-installation
4. Update-mapping
5. Post-install-clean-up
6. Update-mapping
7. Quit
Enter your choice (1-7) : 7
Exiting the script. Goodbye!
```
5. On the **master node**, invoke `migration_util.sh` and choose the `Pre-migration` option:

```bash
root@ip-10-151-18-140:/home/ubuntu/migration_may6# bash migation.sh
Select an option:
1. Pause-scans
2. Pre-migration
3.  Removal
4. Post-installation
5. Post-install-clean-up
6. Update-mapping
7. Quit
Enter your choice (1-7): 2
Running migration readiness check\n
Running DB Health checks\n
Redis is healthy
Elasticsearch is healthy
Postgres is healthy
Please preserve the output of the following command to compare
once the migration is completeln
kubectl
command output:
{"level": " INFO:
","ts": "2024-02-20T20:58:18.143Z", "caller": "cryptoutil/key_loader.go:91" ,"msg": "Reading key names from pod's
{"level": "INFO: ","ts": "2024-02-20T20:58:18.147Z"
, "caller": "models/helpers.go:61", "msg":"Initializing cache
with
{"level": " INFO:
", "ts": "2024-02-20T20:58:18.254Z", "caller": "saml/saml.go:171", "msg":"IDP initiated trust length
retries"}
attached cm"}
10s.
Check
enabled is
Total Used Memory: 2.58M
# Keyspace
dbo:keys=36,expires=3,avg_ttl=59751
db1: keys=6, expires=0,avg_tt1=0
db5: keys=1, expires=1, avg_tt1=577249
set
to true"}
Checking if any connector pods are running\n
No active connector jobs, continue with migration
Checking source queue dump completeln
Dump Source queue in complete. Please wait for source queue dump to complete before proceeding\n
Copying redis backup fileln
Copied aof file to current directory\n unregister applianceln
{"level": "INFO: ", "ts": "2024-02-20T20:58:39.7377", "caller": "cryptoutil/key_loader.go:91", "msg": "Reading key names from pod's attached cm"} {"level":"INFO: ","ts": "2024-02-20T20:58:39.740Z", "caller": "models/helpers.go:61", "msg":"Initializing cache with 3 retries"} {"level": "INFO: ","ts": "2024-02-20T20:58:39.848Z", "caller".
: "saml/saml.go:171", "msg": "IDP initiated trust length set to 10s. Check enabled is set to true"}
{"level": " INFO:
, "ts": "2024-02-20T20:58:40.002Z"
"caller"
"cmd/redis_keys.go: 45",
"msg": "Appliance status unregistered successfully"}
{"level": " INFO:
, "ts": "2024-02-20T20:58:40.014Z" , "caller
"cmd/redis_keys.go:56",
"msg": "Redis Keys in kubernetes secret deleted successfully."}
{"level": "INFO: "
• "ts": "2024-02-20T20:58:40.4837", "caller": "cmd/redis_keys.go:70" , "msg": "Successfully rebooted pod priv-appliance-monitor-status-84dl"}
appliance un-registered\n
All pre-requisities are now complete. Please proceed with the next steps.
```
6. The next step is the **node removal step** using the migration_util.sh script. You must run this step for both single and multi-node clusters. However, for multi-node clusters, you must remove the member nodes first and then remove the master node. After performing the node removal step, you get a confirmation message to confirm the removal of the node from the pod. Type **yes** to confirm.
7. Revoke the pod:
  1. In Securiti, open **System Settings** and choose **Deployment > Pods**, then click the tile for the master node of the pod you are migrating. On the **Master Node** tab, choose **More Options > Revoke**.

![v2ming_revoke_pod.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8dec73bf-dd86-4563-af81-1c71824391a6(2).png)
  2. On the confirmation popup, click **Yes, continue** to revoke the pod.
8. (For multi-node clusters and reducing the number of nodes) Check for table training data:
  1. On each of the secondary nodes listed as "worker nodes" in the status output from **Step 1** above, run the following command to check for table training data:

```bash
ls /<SECURITI_INSTALL_DIR>/table-training-samples
```

Where <SECURITI_INSTALL_DIR> is the installation directory; usually `mnt` or `var/lib`.
  2. Check the result of the command:
    - If the output is empty, there is no table training data on the node, and you can safely eliminate it without further action.
    - If the output is not empty, you must migrate the table training data to either the master node or to a secondary node as described later in **Step 13** below.
9. On the master node, unset the kubeconfig in your shell:

```bash
unset KUBECONFIG
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
```
10. Run the [pre-flight diagnostic script](/v1/docs/pods-using-the-pre-flight-diagnostic-script). In the UI, you should reconfigure the cluster you revoked in **step 7**, select automated installation, and then add the IP Address and secret. Click on the Generate CURL command. Then, copy this CURL command, paste it on the VM, and then run it. It installs the new version.
11. On the master node, invoke `migration_util.sh` and choose the `Post-installation` option:

```bash
[root@ip-172-31-53-142 ec2-user]# bash migration_utils.sh
Select an option:
1. Pause-scans
2. Pre-migration
3.  Removal
4. Post-installation
5. Post-install-clean-up
6. Update-mapping
7. Quit
Enter your choice (1-7): 4
Running Post Revoke Steps\n
Awaiting default/deploy/priv-appliance-config-controller to be ready deployment "priv-appliance-config-controller" successfully rolled out statefulset.apps/priv-appliance-redis-master scaled statefulset.apps/priv-appliance-redis-master scaled
Awaiting default/statefulset/priv-appliance-redis-master to be ready
Waiting for 1 pods to be ready...
statefulset rolling update complete 1 pods at revision priv-appliance-redis-master-545f6db8df...
Defaulted container "config-controller" out of: config-controller, certificate-handler (init)
```
12. Run the `post-installation-clean-up` option on the master node to clean the post install directories. This is a mandatory step.

> [!WARNING]
> **Caution**
> 
> Proceed with this option only if and when the migration process has been successfully completed.

```bash
[root@ip-172-31-53-142 ec2-user]# bash migration_utils.sh
Select an option:
1. Pause-scans
2. Pre-migration
3.  Removal
4. Post-installation
5. Post-install-clean-up
6. Update-mapping
7. Quit
Enter your choice (1-7): 5
```
13. (For multi-node clusters and reducing the number of nodes) Update mapping for table training data:

For each node on which you found table training data in **Step 8** above, you must migrate it to a node on the new pod as described below.

The table training samples are mapped to a directory on each node. As part of the migration, you update the mapping to the new directory on the new pod.

It is required to move all the files/directories under /mnt/securiti-app/table-training-samples for the node that is being made the master node, before updating the mapping.
  1. On the master node, invoke `migration_util.sh` and choose the `Update-mapping` option.

```bash
root@securiti-example:~# bash migration_utils.sh
Select an option:
1. Pause-scans
2. Pre-migration
3.  Removal
4. Post-installation
5. Post-install-clean-up
6. Update-mapping
7. Quit
Enter your choice (1-7): 6
Enter old host:
securiti-dev-khi-taimur-05
Enter new host:
securiti-dev-khi-taimur-04
Defaulted container "config-controller" out of: config-controller, certificate-handler (init)
("level": "INFO: ", "ts": "2024-03-21T14:37:12. 481Z", "caller": "cryptoutil/key_loader. go:91", "msg": "Reading key names from pod
's attached cm"}
["level": "INFO: ", "ts":"2024-03-21T14:37:12.483Z", "caller": "models/helpers.go:76", "msg":"Initializing cache with 3 retries
宀
["level": "INFO: "
,"ts": "2024-03-2114:37:12.537Z", "caller": "saml/saml.go:171", "msg": "IDP initiated trust length set to 10s
• Check enabled is set to true"} ["level": "INFO: "
, "ts": "2024-03-21T14:37:12.712Z", "caller": "cmd/update_fc_node_mappings.go:44", "msg": "Going to update host
in FC sampled data path, mapping: [map[new_host:securiti-dev-khi-taimur-04:/mnt/securuti-app old_host:securiti-dev-khi-ta imur-05:/mnt]]"}
["level": "INFO: ","ts":"2024-03-21T14:37:12.716Z", "caller": "cloud_communication/params.go:39", "msg": "Cloud communication p arams are loaded successfully."}
["level": "INFO: ", "ts":"2024-03-21T14:37:12.913Z", "caller": "cmd/update_fo_node_mappings.go:32", "msg":"successfully updated host mappings for sampled data path"} Select an option:
1. Pause-scans
2. Pre-migration
3. Post-installation
4. Update-mapping
5. Post-install-clean-up
6. Update-mapping
7. Quit
Enter your choice (1-7): 7
```
  2. When prompted for the identity of the old host, enter the IP address of the former pod's node.
  3. When prompted for the identity of the new host, enter the hostname of the new pod's node. If you are eliminating the node, enter the hostname for the master node.
  4. Wait for the mapping to be updated. The process may take up to 20 minutes.
  5. Repeat the process for each secondary node for which there is table training data.
14. For a multi-node cluster:
  1. Re-add each secondary node to the new pod cluster as described in [Automated secondary node installation (cluster version v1.28+)](/v1/docs/pod-automated-secondary-node-installation).
  2. After re-adding each node, unset the kubeconfig in the node’s shell:

```bash
unset KUBECONFIG
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
```

### Special case considerations

#### Case 1: Member/Worker Node Removal

Follow the steps below for the removal of the member/worker node.

1. On the master node, execute the `migration_utils.sh` script and select **Pause scans** option to pause all the running scans.
2. On the same node, skip the `total_cpu` check by running the following command.

```bash
export SECURITI_SKIP_COMPUTE_CHECKS=true
```
3. Run the `pre-migration` step on the master node.
4. Run the `node-removal` step for the member node.
5. Run the `node-removal` step for the master node.
6. Before removing the node, you must copy all directories from the current installation directory (/mnt or /var/lib) to the new/master node's installation directory (/mnt or /var/lib).
7. Set the installation directory using the command below.

```bash
SECURITI_INSTALL_DIR=/mnt #/var/lib
```
8. Next, create a tarball named `securiti-app-backup.tar` containing all files and directories within **securiti-app**

```bash
cd "$SECURITI_INSTALL_DIR/securiti-app/"
tar -cvf securiti-app-backup.tar *
```
9. Run the command below to securely copy the tar file to the new/master node’s tmp directory.

```bash
scp "$SECURITI_INSTALL_DIR/securiti-app/securiti-app-backup.tar" user@remote_machine:/tmp/
```

Replace user with the appropriate **username** and remote machine with the IP address of the node.

**OR**

Use the PEM file to securely copy the file.

```bash
scp -i "$PEM_FILE" "$SECURITI_INSTALL_DIR/securiti-app/securiti-app-backup.tar" user@remote_machine:/tmp/ #change the user,remote_machine
```
10. Set the installation directory on the new/master node using the command below:

```bash
SECURITI_INSTALL_DIR=/mnt #/var/lib
```
11. Move the tar file from the /tmp directory to the installation_dir.

```bash
mv /tmp/securiti-app-backup.tar $SECURITI_INSTALL_DIR #/mnt or /var/lib
```
12. Untar the directory using the command below.

```bash
mkdir $SECURITI_INSTALL_DIR/securiti-app-backup
tar -xvf $SECURITI_INSTALL_DIR/securiti-app-backup.tar -C $SECURITI_INSTALL_DIR/securiti-app-backup/
```
13. Append all the internal content from the securiti-app-backup directory to the existing directory.

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

OR

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
14. [Revoke the v1 pod](/v1/docs/migrating-to-pod-cluster-version) and install the V2 pod on the same cluster.
15. Run the `Post-installation` step on master node.
16. Run the `Update-mapping` step on the master node.
17. [Re-add the secondary node](/v1/docs/migrating-to-pod-cluster-version) to the pod cluster.

#### Case 2: Moving the master node from Node A (old) to Node B (new)

When transferring the master node from Node A to Node B, follow these additional steps to ensure a smooth migration:

#### Steps on Node A (old)

1. Execute the migration_utils script and select the `pause-scans` option on the master node to pause all running scans.
2. Run the following command to skip the total CPU check.

```bash
export SECURITI_SKIP_COMPUTE_CHECKS=true
```
3. Execute the `pre-migration` step on the master node as instructed.
4. Execute the `node-removal` option on the member node. **This step is only required for a multi-node cluster.**
5. Execute the `node-removal` option on the master node.

#### Steps on Node B (New)

- On Node B, create a backup directory in /tmp.

```bash
mkdir /tmp/securiti-app-backup
```

#### Transferring Data from Node A to Node B

1. On Node A (old), transfer the **securiti-app** directory to Node B's backup directory.

```bash
SECURITI_INSTALL_DIR=/mnt # or /var/lib
```
2. Create a tarball named **securiti-app-backup.tar** containing all files and directories within **securiti-app**.

```bash
cd "$SECURITI_INSTALL_DIR/securiti-app/"
tar -cvf securiti-app-backup.tar *
```
3. Run the command below to securely copy the tar file to the new/master node’s tmp directory.

```bash
scp "$SECURITI_INSTALL_DIR/securiti-app/securiti-app-backup.tar" user@remote_machine:/tmp/ #change the user,remote_machine
```

Or, use the **PEM_FILE** instead:

```bash
scp -i "$PEM_FILE" "$SECURITI_INSTALL_DIR/securiti-app/securiti-app-backup.tar" user@remote_machine:/tmp/ #change the user,remote_machine
```
4. Set the installation directory on Node B using the command below:

```bash
SECURITI_INSTALL_DIR=/mnt #/var/lib
```
5. On Node B, move the backup directory to the installation directory (/mnt or /var/lib).

```bash
mv /tmp/securiti-app-backup.tar $SECURITI_INSTALL_DIR #/mnt or /var/lib
```
6. Untar the directory using the command below:

```bash
mkdir $SECURITI_INSTALL_DIR/securiti-app
tar -xvf $SECURITI_INSTALL_DIR/securiti-app-backup.tar -C $SECURITI_INSTALL_DIR/securiti-app/
```
7. Ensure the correct permissions for the securiti-app directory.

```bash
chmod -R 755 $SECURITI_INSTALL_DIR/securiti-app
```
8. Install the V2 pod version on the same cluster.
9. Run the `Post-installation` option for the Master node.
10. Run the `Update-mapping` option for the Master node.
11. (Optional) If you are migrating the pod between different cloud servers, proceed with the following steps:
  1. Unregister the pod.

```bash
cd /mnt/installation/securiti-appliance-installer # replace the path if you have a different directory path

sh poddiagnostics.sh troubleshoot registration deregister
```
  2. Register the pod.

```plaintext
sh poddiagnostics.sh registration <license-key>
```

To obtain the license key, revoke the pod again and see step 11 under [Configure the pod in Securiti](/v1/docs/podcustom-installation-guides#1-configure-the-pod-in).
12. [Re-add the secondary node](/v1/docs/migrating-to-pod-cluster-version) to the pod cluster.

Each pod has a master node that manages the activities of the secondary nodes.

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Pod installation (cluster version v1.28+)](/pod-installation-cluster-version-v128.md)
