---
title: "Manual secondary node installation (cluster version v1.28+)"
slug: "pods-manual-secondary-node-installation"
updated: 2025-12-09T12:56:31Z
published: 2025-12-09T12:56:31Z
canonical: "helpcenter.securiti.ai/pods-manual-secondary-node-installation"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Manual secondary node installation (cluster version v1.28+)

Follow these steps to add an additional node to your active pod. You can add up to 9 secondary nodes:

1. In Securiti, from the top left corner of the Dashboard, click the **Jewel** icon.
2. From the Platform Services section, click **Settings** > **Deployment**.
3. Under Development, click **Pods**.
4. Click the card for the master node of the pod to which you want to add a secondary node.
5. On the **Master Node** tab, click **Download Preflight Shell Script** to download the diagnostics script.
6. Copy the `poddiagnostics.sh` file for the preflight script to the compute instance.
7. On the **Master Node** tab, click either **Download Pod Image** or **Download from CDN** to download the appliance image.

![manual_install_2ndary_node_download_image.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4380cfac-ff26-9647-84b4-96af066dc991(4).png)
8. Copy the install bundle to the VM or compute instance for the node:

```bash
scp securiti-appliance-installer-online-<version>.tar <user@server:path>
```

For example:

```bash
scp securiti-appliance-installer-online-<version>.tar ubuntu@192.168.86.115:/tmp
```
9. Extract the bundle:

```bash
ssh ubuntu@192.168.86.115
sudo su
cd <path where installer tar copied>
mv securiti-appliance-installer-online-<version>.tar /tmp/securiti-appliance-installer.tar.gz
INSTALLATION_DIR=/mnt/installation/securiti-appliance-installer
mkdir -p "$INSTALLATION_DIR"
tar -xf /tmp/securiti-appliance-installer.tar.gz -C "$INSTALLATION_DIR" --strip-components=1
cd "$INSTALLATION_DIR"
```
10. Run the preflight diagnostic script with the `install --check` flag, for example:

```bash
bash poddiagnostics.sh install --check
```

The script validates and resets system settings required by the node, as shown below.

![The script validates system settings required by the pod](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c54a4375-2ab2-4400-391d-69fa36e82ab6(8).png)
11. Review the results of the pre-flight check and run `bash poddiagnostics.sh install --fix` to address any issues found, as shown below.

![The script validates system settings required by the pod](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0e9c73ef-c006-2717-acdd-da781b803d0a(8).png)

> [!NOTE]
> **Note**
> 
> We recommend that you reboot the node and run the `poddiagnostics.sh install --check` again after the reboot. This helps ensure that the Securiti applied configuration does not conflict with any other config set by other system services.
12. Run the following command to add and activate the node on your existing pod.

```bash
export SECURITI_NODE_JOIN_TOKEN="<secret set when creating primary>"
export SECURITI_NODE_KIND="agent"
export SECURITI_LEADER_URL="https://<primary-node-ip>:6443"
export SECURITI_SKIP_DOWNLOAD=true
export SECURITI_SKIP_DOWNLOAD_CHECKSUM=true
bash install.sh
```

To perform the same step in your airgapped bundle, use the following commands.

```bash
export SECURITI_AIRGAP=true
export SECURITI_NODE_JOIN_TOKEN="<secret set when creating primary>"
export SECURITI_NODE_KIND="agent"
export SECURITI_LEADER_URL="https://<primary-node-ip>:6443"
export SECURITI_SKIP_DOWNLOAD=true
export SECURITI_SKIP_DOWNLOAD_CHECKSUM=true
bash install.sh
```
13. Run the following command to verify that the k3s agent is active on the secondary pod:

```bash
systemctl status k3s-agent
```
14. (Optional) Copy required jars (required only for SQL connectors): Download all jar drivers required for external SQL connectivity from the website for the data system, and then enter the following commands:

```bash
mkdir -p /mnt/securiti-app/drivers/<connector_type_if_not_present>
cp <jdbc*.jar> /mnt/securiti-app/drivers/<connector_type>
```

Where <connector_type> is one of the following, as appropriate:
  - amazon_athena
  - amazon_aurora_postgres
  - amazon_dynamodb
  - amazon_redshift
  - apache_hbase
  - apache_hive_onprem
  - apache_phoenix
  - azure_cosmos_db
  - azure_data_warehouse
  - btrieve_pervasive_sql
  - cassandra
  - couchbase
  - elasticsearch
  - google_bigquery
  - greenplum
  - ibm_db2
  - ibm_db2_zos
  - informix
  - intersystems_iris
  - mariadb
  - microsoft_access
  - mongodb
  - mysql
  - oracle
  - postgresql
  - sap_ecc sap_hana
  - snowflake_onprem
  - sql_server
  - sybase
  - teradata_onprem

## Related

- [Automated secondary node installation (cluster version v1.28+)](/pod-automated-secondary-node-installation.md)
- [Upgrading pods cluster version](/upgrading-pods-cluster-version.md)
- [Pod troubleshooting (cluster version v1.28+)](/podtroubleshooting.md)
